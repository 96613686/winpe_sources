# Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan(Windows::Compat::Appraiser::GatingStateInfo &,Windows::Compat::Appraiser::DataFile &,Windows::Compat::Appraiser::RunOptions &)

- ea: `0x180031920`
- end: `0x1800342b3`
- name: `?CheckExistingIndicatorStateForGatedScan@SetupAppraiser@Appraiser@Compat@Windows@@AEAAJAEAUGatingStateInfo@234@AEAVDataFile@234@AEAURunOptions@234@@Z`
- size: `10643`
- prototype: `__int64 __fastcall(Windows::Compat::Appraiser::SetupAppraiser *__hidden this, struct Windows::Compat::Appraiser::GatingStateInfo *, struct Windows::Compat::Appraiser::DataFile *, struct Windows::Compat::Appraiser::RunOptions *)`
- caller_count: `1`
- callee_count: `43`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180041b90`

## callees

- `0x18000147c`
- `0x180008570`
- `0x18000945c`
- `0x180011d94`
- `0x180013c7c`
- `0x180013f90`
- `0x1800144c4`
- `0x1800151f4`
- `0x180026fd0`
- `0x18002780c`
- `0x1800278b8`
- `0x1800287d4`
- `0x180028928`
- `0x180029258`
- `0x18002a114`
- `0x18002a8b4`
- `0x18002ebb8`
- `0x1800301d0`
- `0x180031920`
- `0x1800670a4`
- `0x180067124`
- `0x1800686dc`
- `0x180068908`
- `0x180068ab8`
- `0x180068bc8`
- `0x180068ce0`
- `0x180068e74`
- `0x180069ed8`
- `0x180082830`
- `0x180082e74`
- `0x180083094`
- `0x18008b018`
- `0x18008bfbc`
- `0x18008c378`
- `0x18008cccc`
- `0x18008f7bc`
- `0x180096f80`
- `0x1800a17cc`
- `0x1800a17fc`
- `0x1800a5aec`
- `0x1801dc788`
- `0x1801dc8f0`
- `0x1802174cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x180032449`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x180032449`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180032e29`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180032e5e`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180032e29`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180032e5e`
- `KERNEL32!InitOnceExecuteOnce` at `0x180031da5`
- `KERNEL32!InitOnceExecuteOnce` at `0x180033333`
- `KERNEL32!InitOnceExecuteOnce` at `0x180031da5`
- `KERNEL32!InitOnceExecuteOnce` at `0x180033333`
- `KERNEL32!GetProductInfo` at `0x180032330`
- `KERNEL32!GetProductInfo` at `0x180032330`
- `KERNEL32!GetSystemTime` at `0x18003368f`
- `KERNEL32!GetSystemTime` at `0x180034161`
- `KERNEL32!GetSystemTime` at `0x18003368f`
- `KERNEL32!GetSystemTime` at `0x180034161`
- `KERNEL32!GetProcessHeap` at `0x180031a0d`
- `KERNEL32!GetProcessHeap` at `0x180031a6c`
- `KERNEL32!GetProcessHeap` at `0x180031abb`
- `KERNEL32!GetProcessHeap` at `0x180031ad2`
- `KERNEL32!GetProcessHeap` at `0x18003420c`
- `KERNEL32!GetProcessHeap` at `0x180031a0d`
- `KERNEL32!GetProcessHeap` at `0x180031a6c`
- `KERNEL32!GetProcessHeap` at `0x180031abb`
- `KERNEL32!GetProcessHeap` at `0x180031ad2`
- `KERNEL32!GetProcessHeap` at `0x18003420c`
- `KERNEL32!GetLastError` at `0x18003233a`
- `KERNEL32!GetLastError` at `0x180032359`
- `KERNEL32!GetLastError` at `0x18003233a`
- `KERNEL32!GetLastError` at `0x180032359`
- `KERNEL32!HeapFree` at `0x18003421a`
- `KERNEL32!HeapFree` at `0x180034242`
- `KERNEL32!HeapFree` at `0x180034277`
- `KERNEL32!HeapFree` at `0x18003421a`
- `KERNEL32!HeapFree` at `0x180034242`
- `KERNEL32!HeapFree` at `0x180034277`

## string_xrefs

- `0x18003276c`: `Failed ReadAvailableTargetVersions: [0x%x]`
- `0x180032792`: `Failed ReadAvailableTargetVersions: [0x%x]`
- `0x180031b5f`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x180031b8e`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x180031b58`: `Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan`
- `0x180031b87`: `Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan`
- `0x180031cfc`: `AdlLinkListed`
- `0x180031ff9`: `Error reading WU configuration: [0x%x].`
- `0x18003201f`: `Error reading WU configuration: [0x%x].`
- `0x180032210`: `DisableWUAccess`
- `0x18003227a`: `WUConfigChecksAllSucceeded`
- `0x180032557`: `Error reading registry value: [0x%x].`
- `0x1800325b7`: `Error reading registry value: [0x%x].`
- `0x180033bf9`: `Error reading registry value: [0x%x].`
- `0x180033c1a`: `Error reading registry value: [0x%x].`
- `0x1800327fb`: `Error reading indicators: [0x%x].`
- `0x180032821`: `Error reading indicators: [0x%x].`
- `0x180032a1b`: `Failed to copy string: [0x%x].`
- `0x180032df7`: `Failed to copy string: [0x%x].`
- `0x180032ecc`: `DataVerRecommended`
- `0x180032fb3`: `InboxIndicatorDataVerRecommended`
- `0x1800332d3`: `InboxIndicatorVersionRecommended`
- `0x180033282`: `InboxIndicatorDataVerRecommendedPresent`
- `0x1800335af`: `Error getting WIP configuration, swallowing: [0x%x].`
- `0x180033713`: `Error getting WIP configuration, swallowing: [0x%x].`
- `0x180033a13`: `WufbBranchReadinessLevelDisabled`
- `0x180033bb3`: `DataRequireGatedScanForFeatureUpdates`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan(
        Windows::Compat::Appraiser::SetupAppraiser *this,
        struct Windows::Compat::Appraiser::GatingStateInfo *a2,
        struct Windows::Compat::Appraiser::DataFile *a3,
        struct Windows::Compat::Appraiser::RunOptions *a4)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // ebx
  int appended; // eax
  char v10; // dl
  _WORD *v11; // rcx
  unsigned __int64 v12; // r12
  bool v13; // r8
  const unsigned __int16 *v14; // rax
  unsigned int v15; // ebx
  int v16; // eax
  unsigned __int64 v17; // r13
  __int64 *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rax
  const unsigned __int16 *v21; // r8
  const unsigned __int16 **v22; // rdx
  __int64 v23; // rcx
  struct Windows::Compat::Appraiser::RunOptions *v24; // r13
  int WuConfigRegKeys; // eax
  const unsigned __int16 *v26; // r12
  const unsigned __int16 *v27; // r8
  unsigned __int16 *v28; // r8
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int OsVersionInfo; // eax
  signed int LastError; // eax
  int v34; // eax
  unsigned __int64 v35; // r13
  unsigned __int64 v36; // r12
  unsigned __int64 v37; // r12
  HKEY v38; // r9
  int Value; // eax
  int v40; // eax
  HKEY v41; // r9
  int v42; // eax
  const char *v43; // rcx
  bool v44; // r12
  unsigned __int64 v45; // rax
  int v46; // eax
  int AvailableTargetVersions; // eax
  struct Windows::Compat::Appraiser::RunOptions *v48; // rbx
  int v49; // eax
  unsigned __int64 v50; // rcx
  unsigned __int64 v51; // rax
  unsigned __int16 *v52; // r13
  const unsigned __int16 *v53; // r12
  __int64 v54; // rax
  const char *v55; // r9
  char v56; // dl
  unsigned __int64 v57; // r13
  unsigned __int64 v58; // rax
  unsigned __int64 v59; // r12
  wchar_t *v60; // rax
  bool *v61; // rbx
  int v62; // eax
  char v63; // bl
  char v64; // r13
  char v65; // r12
  int v66; // eax
  int v67; // eax
  int v68; // eax
  int v69; // eax
  char *v70; // rcx
  unsigned __int64 v71; // rax
  int v72; // eax
  int v73; // eax
  int v74; // eax
  int v75; // eax
  int v76; // eax
  int v77; // eax
  int v78; // eax
  unsigned __int64 v79; // r15
  unsigned __int64 v80; // rcx
  __int64 *v81; // rax
  __int64 v82; // rdx
  __int64 v83; // rax
  __int64 v84; // r10
  const unsigned __int16 **v85; // rdx
  unsigned __int64 v86; // rax
  bool v87; // al
  int v88; // eax
  const char *v89; // r15
  int v90; // eax
  __int64 v91; // rax
  unsigned __int64 v92; // rax
  int v93; // eax
  unsigned __int64 v94; // r9
  int WipConfigSettings; // eax
  unsigned int v96; // r15d
  volatile signed __int64 *v97; // rcx
  void **v98; // rdx
  int v99; // ebx
  int v100; // r8d
  int v101; // r9d
  int v102; // eax
  int v103; // eax
  int v104; // eax
  int v105; // eax
  int v106; // eax
  int v107; // eax
  int v108; // eax
  int v109; // eax
  int v110; // eax
  int v111; // eax
  int v112; // eax
  int v113; // eax
  HKEY v114; // r9
  int v115; // eax
  bool v116; // r15
  int v117; // eax
  void *v118; // rdx
  bool *v119; // r12
  struct Windows::Compat::Appraiser::DataFile *v120; // r13
  int TableDecision; // eax
  int v122; // eax
  int v123; // eax
  int v124; // eax
  int v125; // eax
  int v126; // eax
  int v127; // eax
  int v128; // eax
  int v129; // eax
  int v130; // eax
  int v131; // r15d
  volatile signed __int64 *v132; // rcx
  void **v133; // rdx
  int v134; // ebx
  int v135; // r8d
  int v136; // r9d
  wchar_t *v137; // rdi
  HANDLE ProcessHeap; // rax
  const char *pdwReturnedProductType; // [rsp+28h] [rbp-E0h]
  const char *pdwReturnedProductTypea; // [rsp+28h] [rbp-E0h]
  const char *v142; // [rsp+30h] [rbp-D8h]
  const char *v143; // [rsp+30h] [rbp-D8h]
  bool *v144; // [rsp+38h] [rbp-D0h]
  bool *v145; // [rsp+48h] [rbp-C0h]
  bool *v146; // [rsp+50h] [rbp-B8h]
  bool v147; // [rsp+78h] [rbp-90h] BYREF
  bool v148; // [rsp+79h] [rbp-8Fh]
  bool v149; // [rsp+7Ah] [rbp-8Eh] BYREF
  bool v150; // [rsp+7Bh] [rbp-8Dh] BYREF
  bool v151; // [rsp+7Ch] [rbp-8Ch] BYREF
  bool v152; // [rsp+7Dh] [rbp-8Bh] BYREF
  bool v153; // [rsp+7Eh] [rbp-8Ah] BYREF
  bool v154; // [rsp+7Fh] [rbp-89h] BYREF
  bool v155; // [rsp+80h] [rbp-88h] BYREF
  bool v156; // [rsp+81h] [rbp-87h] BYREF
  char v157; // [rsp+82h] [rbp-86h]
  char v158; // [rsp+83h] [rbp-85h]
  bool v159; // [rsp+84h] [rbp-84h] BYREF
  bool v160; // [rsp+85h] [rbp-83h] BYREF
  bool v161; // [rsp+86h] [rbp-82h] BYREF
  bool v162; // [rsp+87h] [rbp-81h] BYREF
  bool v163; // [rsp+88h] [rbp-80h] BYREF
  bool v164; // [rsp+89h] [rbp-7Fh] BYREF
  bool v165; // [rsp+8Ah] [rbp-7Eh] BYREF
  bool v166; // [rsp+8Bh] [rbp-7Dh] BYREF
  bool v167; // [rsp+8Ch] [rbp-7Ch] BYREF
  bool v168; // [rsp+8Dh] [rbp-7Bh] BYREF
  struct _OSVERSIONINFOEXW *v169; // [rsp+90h] [rbp-78h] BYREF
  unsigned int v170[2]; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int16 *v171; // [rsp+A0h] [rbp-68h] BYREF
  unsigned int pvData[4]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v173[80]; // [rsp+B8h] [rbp-50h] BYREF
  const char *v174; // [rsp+108h] [rbp+0h] BYREF
  unsigned __int16 *v175; // [rsp+110h] [rbp+8h] BYREF
  unsigned __int16 *v176; // [rsp+118h] [rbp+10h] BYREF
  unsigned __int16 *v177; // [rsp+120h] [rbp+18h] BYREF
  char v178[4]; // [rsp+128h] [rbp+20h] BYREF
  unsigned int v179; // [rsp+12Ch] [rbp+24h] BYREF
  unsigned int v180; // [rsp+130h] [rbp+28h] BYREF
  DWORD v181; // [rsp+134h] [rbp+2Ch] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+138h] [rbp+30h] BYREF
  struct Windows::Compat::Appraiser::RunOptions *v183; // [rsp+148h] [rbp+40h]
  bool *v184; // [rsp+150h] [rbp+48h] BYREF
  wchar_t *Context; // [rsp+158h] [rbp+50h] BYREF
  char *v186; // [rsp+160h] [rbp+58h] BYREF
  wchar_t *String; // [rsp+168h] [rbp+60h] BYREF
  struct _SYSTEMTIME v188; // [rsp+178h] [rbp+70h] BYREF
  struct Windows::Compat::Appraiser::DataFile *v189; // [rsp+188h] [rbp+80h] BYREF
  HANDLE hHeap[2]; // [rsp+190h] [rbp+88h] BYREF
  __int128 v191; // [rsp+1A0h] [rbp+98h]
  LPVOID lpMem[2]; // [rsp+1B0h] [rbp+A8h]
  HANDLE v193[2]; // [rsp+1C0h] [rbp+B8h] BYREF
  __int128 v194; // [rsp+1D0h] [rbp+C8h]
  LPVOID v195[2]; // [rsp+1E0h] [rbp+D8h]
  int v196; // [rsp+1F0h] [rbp+E8h]
  __int128 v197; // [rsp+1F8h] [rbp+F0h] BYREF
  __int128 v198; // [rsp+208h] [rbp+100h]
  __int128 v199; // [rsp+218h] [rbp+110h]
  _BYTE v200[112]; // [rsp+228h] [rbp+120h] BYREF
  __int64 v201; // [rsp+298h] [rbp+190h]
  unsigned __int16 *v202[2]; // [rsp+2A8h] [rbp+1A0h] BYREF
  struct _SYSTEMTIME v203; // [rsp+2B8h] [rbp+1B0h] BYREF
  unsigned __int64 v204[2]; // [rsp+2C8h] [rbp+1C0h] BYREF
  _BYTE v205[144]; // [rsp+2D8h] [rbp+1D0h] BYREF
  unsigned __int16 v206[24]; // [rsp+368h] [rbp+260h] BYREF
  char v207[144]; // [rsp+398h] [rbp+290h] BYREF
  unsigned __int16 v208[264]; // [rsp+428h] [rbp+320h] BYREF
  unsigned __int16 v209[264]; // [rsp+638h] [rbp+530h] BYREF
  unsigned __int16 v210[264]; // [rsp+848h] [rbp+740h] BYREF
  unsigned __int16 v211[264]; // [rsp+A58h] [rbp+950h] BYREF

  v201 = -2;
  v183 = a4;
  v189 = a3;
  v184 = (bool *)a2;
  v168 = 0;
  Windows::Compat::Appraiser::PropertyBag::PropertyBag((Windows::Compat::Appraiser::PropertyBag *)v173);
  v147 = 0;
  v151 = 0;
  v152 = 0;
  v153 = 0;
  v154 = 0;
  v155 = 0;
  v156 = 0;
  v159 = 0;
  v160 = 0;
  v161 = 0;
  v149 = 0;
  v162 = 0;
  v163 = 0;
  v164 = 0;
  v165 = 0;
  v150 = 0;
  v166 = 0;
  v167 = 0;
  v170[0] = 0;
  *(_DWORD *)v178 = 0;
  v179 = 0;
  v180 = 0;
  v181 = 0;
  *(_QWORD *)&v188.wYear = 0;
  v177 = 0;
  v175 = 0;
  v171 = 0;
  v176 = 0;
  pvData[0] = 0;
  *(_OWORD *)v193 = 0;
  *(_OWORD *)v195 = 0;
  v193[0] = GetProcessHeap();
  v195[0] = (LPVOID)16;
  v194 = 0;
  v195[1] = 0;
  v193[1] = (HANDLE)16;
  v196 = 0;
  RtlArray<RtlStringArray::RTL_STRING_ITEM>::Initialize(v193, v6, v7, 16);
  v186 = 0;
  v174 = 0;
  v197 = 0;
  v199 = 0;
  *(_QWORD *)&v197 = GetProcessHeap();
  v199 = 0x10u;
  v198 = 0;
  *((_QWORD *)&v197 + 1) = 16;
  Windows::Compat::Shared::Generics::StringLibrary::StringLibrary((Windows::Compat::Shared::Generics::StringLibrary *)v200);
  v203 = 0;
  v204[0] = 0;
  v169 = 0;
  GetProcessHeap();
  *(_OWORD *)hHeap = 0;
  *(_OWORD *)lpMem = 0;
  hHeap[0] = GetProcessHeap();
  lpMem[0] = (LPVOID)16;
  v191 = 0;
  lpMem[1] = 0;
  hHeap[1] = (HANDLE)8;
  v202[0] = 0;
  Context = 0;
  String = 0;
  if ( !*((_BYTE *)a4 + 3) )
  {
    v8 = 1;
    goto LABEL_465;
  }
  Windows::Compat::Appraiser::DataFile::GetInboxDataFileVersion(v170);
  appended = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
               (Windows::Compat::Appraiser::PropertyBag *)v173,
               L"InboxDataVersion",
               v170[0]);
  v8 = appended;
  if ( appended < 0 )
  {
    LODWORD(v144) = appended;
    v142 = "Error adding init property to bag: [0x%x].";
    LODWORD(pdwReturnedProductType) = appended;
    v10 = 35;
LABEL_5:
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v10,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      pdwReturnedProductType,
      (int)v142,
      (const char *)v144);
    goto LABEL_465;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x423u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error adding init property to bag: [0x%x].",
      appended);
  v8 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
         (Windows::Compat::Appraiser::PropertyBag *)v173,
         L"CurrentDataVersion",
         *((_DWORD *)a3 + 160));
  if ( v8 < 0 )
  {
    v10 = 38;
LABEL_10:
    LODWORD(v144) = v8;
    v142 = "Error adding init property to bag: [0x%x].";
LABEL_11:
    LODWORD(pdwReturnedProductType) = v8;
    goto LABEL_5;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x426u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error adding init property to bag: [0x%x].",
      v8);
  v8 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
         (Windows::Compat::Appraiser::PropertyBag *)v173,
         L"AdlDataVersion",
         *(_DWORD *)((char *)a4 + 17));
  if ( v8 < 0 )
  {
    v10 = 41;
    goto LABEL_10;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x429u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error adding init property to bag: [0x%x].",
      v8);
  v8 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
         (Windows::Compat::Appraiser::PropertyBag *)v173,
         L"SdbVer",
         *((_DWORD *)a3 + 162));
  if ( v8 < 0 )
  {
    v10 = 44;
    goto LABEL_10;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x42Cu,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error adding init property to bag: [0x%x].",
      v8);
  v8 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
         (Windows::Compat::Appraiser::PropertyBag *)v173,
         L"PreviousSdbVerBeforeReuse",
         *(_DWORD *)((char *)a4 + 25));
  if ( v8 < 0 )
  {
    v10 = 47;
    goto LABEL_10;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x42Fu,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error adding init property to bag: [0x%x].",
      v8);
  v11 = (_WORD *)*((_QWORD *)a4 + 10);
  v12 = 0;
  if ( !v11 || (v13 = 1, !*v11) )
    v13 = 0;
  v8 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
         (Windows::Compat::Appraiser::PropertyBag *)v173,
         L"AdlLinkListed",
         v13);
  if ( v8 < 0 )
  {
    v10 = 50;
    goto LABEL_10;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x432u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error adding init property to bag: [0x%x].",
      v8);
  v14 = Windows::Compat::Appraiser::WicaFactory::AppraiserVersion();
  v8 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
         (Windows::Compat::Appraiser::PropertyBag *)v173,
         L"AppraiserVersion",
         v14);
  if ( v8 < 0 )
  {
    v10 = 53;
    goto LABEL_10;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x435u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error adding init property to bag: [0x%x].",
      v8);
  v15 = *((_DWORD *)a3 + 162);
  InitOnceExecuteOnce(
    &Windows::Compat::Appraiser::AppraiserSettings::InitOnce,
    Windows::Compat::Appraiser::AppraiserSettings::InitOnceCallback,
    0,
    0);
  v16 = Windows::Compat::Appraiser::Utilities::CalculateSdbVerExpDateExtensionProperties(
          (struct RtlNameValueArray *)hHeap,
          (const struct RtlNameValueArray *)&Windows::Compat::Appraiser::AppraiserSettings::SettingSetupAdditionalInitProperties,
          L"SETUPINIT_",
          v15);
  v8 = v16;
  if ( v16 < 0 )
  {
    LODWORD(v144) = v16;
    v142 = "Error calculating sdb ver expiration properties: [0x%x].";
    v10 = 59;
    goto LABEL_11;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x43Bu,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error calculating sdb ver expiration properties: [0x%x].",
      v16);
  v17 = v191;
  if ( (_QWORD)v191 )
  {
    while ( 1 )
    {
      v18 = 0;
      if ( v12 < v17 )
      {
        *(_QWORD *)&SystemTime.wYear = 0;
        if ( !is_mul_ok((unsigned __int64)hHeap[1], v12)
          || (v18 = (__int64 *)((char *)lpMem[1] + (unsigned __int64)hHeap[1] * v12), v18 < lpMem[1]) )
        {
          v18 = 0;
        }
      }
      v19 = *v18;
      v20 = -1;
      do
        ++v20;
      while ( *(_WORD *)(v19 + 2 * v20) );
      v21 = (const unsigned __int16 *)(v19 + 2 * (v20 + 1));
      v22 = 0;
      if ( v12 < v17 )
      {
        *(_QWORD *)&SystemTime.wYear = 0;
        v23 = (unsigned __int64)hHeap[1] * v12;
        if ( !is_mul_ok((unsigned __int64)hHeap[1], v12)
          || (v22 = (const unsigned __int16 **)((char *)lpMem[1] + v23), (char *)lpMem[1] + v23 < lpMem[1]) )
        {
          v22 = 0;
        }
      }
      v8 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
             (Windows::Compat::Appraiser::PropertyBag *)v173,
             *v22,
             v21);
      if ( v8 < 0 )
        break;
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x440u,
          "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
          "Error adding init property to bag: [0x%x].",
          v8);
      if ( ++v12 >= v17 )
        goto LABEL_56;
    }
    v10 = 64;
    goto LABEL_10;
  }
LABEL_56:
  v24 = v183;
  v8 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
         (Windows::Compat::Appraiser::PropertyBag *)v173,
         L"TargetVersion",
         *((const unsigned __int16 **)v183 + 4));
  if ( v8 < 0 )
  {
    v10 = 68;
    goto LABEL_10;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x444u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error adding init property to bag: [0x%x].",
      v8);
  v8 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
         (Windows::Compat::Appraiser::PropertyBag *)v173,
         L"ReusingInboxAdlSdb",
         *((_BYTE *)v24 + 8));
  if ( v8 < 0 )
  {
    v10 = 71;
    goto LABEL_10;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x447u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error adding init property to bag: [0x%x].",
      v8);
  WuConfigRegKeys = Windows::Compat::Appraiser::Utilities::GetWuConfigRegKeys(
                      v209,
                      &v147,
                      0x104u,
                      v210,
                      &v151,
                      0x104u,
                      (unsigned int *)v178,
                      &v152,
                      &v179,
                      &v153,
                      &v180,
                      &v154,
                      &v155);
  v8 = WuConfigRegKeys;
  if ( WuConfigRegKeys < 0 )
  {
    LODWORD(v144) = WuConfigRegKeys;
    v142 = "Error reading WU configuration: [0x%x].";
    v10 = 90;
    goto LABEL_11;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x45Au,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error reading WU configuration: [0x%x].",
      WuConfigRegKeys);
  v26 = L"TRUE";
  v27 = L"TRUE";
  if ( !v147 )
    v27 = L"FALSE";
  v8 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
         (Windows::Compat::Appraiser::PropertyBag *)v173,
         L"WUStatusServerIsSet",
         v27);
  if ( v8 < 0 )
  {
    v10 = 93;
    goto LABEL_10;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x45Du,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error adding init property to bag: [0x%x].",
      v8);
  v28 = v209;
  if ( !v147 )
    v28 = L"[VariableValueNotSet]";
  v8 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
         (Windows::Compat::Appraiser::PropertyBag *)v173,
         L"WUStatusServer",
         v28);
  if ( v8 < 0 )
  {
    v10 = 96;
    goto LABEL_10;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x460u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error adding init property to bag: [0x%x].",
      v8);
  if ( v151 )
  {
    v8 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
           (Windows::Compat::Appraiser::PropertyBag *)v173,
           L"WUServer",
           v210);
    if ( v8 < 0 )
    {
      v10 = 101;
      goto LABEL_10;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x465u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
        "Error adding init property to bag: [0x%x].",
        v8);
  }
  if ( v152 )
  {
    v29 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
            (Windows::Compat::Appraiser::PropertyBag *)v173,
            L"UseWUServer",
            *(unsigned int *)v178);
    v8 = v29;
    if ( v29 < 0 )
    {
      LODWORD(v144) = v29;
      v142 = "Error appending property: [0x%x].";
      v10 = 107;
      goto LABEL_11;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x46Bu,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
        "Error appending property: [0x%x].",
        v29);
  }
  if ( v153 )
  {
    v30 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
            (Windows::Compat::Appraiser::PropertyBag *)v173,
            L"DoNotConnectToWU",
            v179);
    v8 = v30;
    if ( v30 < 0 )
    {
      LODWORD(v144) = v30;
      v142 = "Error appending property: [0x%x].";
      v10 = 113;
      goto LABEL_11;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x471u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
        "Error appending property: [0x%x].",
        v30);
  }
  if ( v154 )
  {
    v31 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
            (Windows::Compat::Appraiser::PropertyBag *)v173,
            L"DisableWUAccess",
            v180);
    v8 = v31;
    if ( v31 < 0 )
    {
      LODWORD(v144) = v31;
      v142 = "Error appending property: [0x%x].";
      v10 = 119;
      goto LABEL_11;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x477u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
        "Error appending property: [0x%x].",
        v31);
  }
  if ( !v155 )
    v26 = L"FALSE";
  v8 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
         (Windows::Compat::Appraiser::PropertyBag *)v173,
         L"WUConfigChecksAllSucceeded",
         v26);
  if ( v8 < 0 )
  {
    v10 = 123;
    goto LABEL_10;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x47Bu,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error adding init property to bag: [0x%x].",
      v8);
  OsVersionInfo = Windows::Compat::Appraiser::Utilities::GetOsVersionInfo((const struct _OSVERSIONINFOEXW **)&v169);
  v8 = OsVersionInfo;
  if ( OsVersionInfo < 0 )
  {
    LODWORD(v144) = OsVersionInfo;
    v142 = "Error getting os version: [0x%x].";
    v10 = -125;
    goto LABEL_11;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x483u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error getting os version: [0x%x].",
      OsVersionInfo);
  if ( !GetProductInfo(
          v169->dwMajorVersion,
          v169->dwMinorVersion,
          v169->wServicePackMajor,
          v169->wServicePackMinor,
          &v181) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 >= 0 )
      v8 = -2147467259;
    LODWORD(v144) = GetLastError();
    v142 = "Error getting os SKU: [%d].";
    v10 = -116;
    goto LABEL_11;
  }
  v34 = StringCchPrintfW(v206, 0x15u, L"0x%08X", v181);
  v8 = v34;
  if ( v34 < 0 )
  {
    LODWORD(v144) = v34;
    v142 = "Error printing value: [0x%x].";
    v10 = -112;
    goto LABEL_11;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x490u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error printing value: [0x%x].",
      v34);
  v8 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
         (Windows::Compat::Appraiser::PropertyBag *)v173,
         L"HostOsSku",
         v206);
  if ( v8 < 0 )
  {
    v10 = -109;
    goto LABEL_10;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x493u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error adding init property to bag: [0x%x].",
      v8);
  v35 = Windows::Compat::Appraiser::Utilities::Now();
  *(_QWORD *)v170 = v35;
  if ( Windows::Compat::Appraiser::AppraiserTestHooks::OverrideNowTime((const unsigned __int16 **)&v176) )
    v36 = _o__wcstoui64(v176, 0, 10);
  else
    v36 = v35;
  v169 = (struct _OSVERSIONINFOEXW *)v36;
  v8 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
         (Windows::Compat::Appraiser::PropertyBag *)v173,
         L"NowTime",
         v36);
  if ( v8 < 0 )
  {
    v10 = -89;
    goto LABEL_10;
  }
  v37 = v36 / 0x989680 - 0x2B6109100LL;
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x4A7u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error adding init property to bag: [0x%x].",
      v8);
  v8 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
         (Windows::Compat::Appraiser::PropertyBag *)v173,
         L"NowTimeEpoch",
         v37);
  if ( v8 < 0 )
  {
    v10 = -86;
    goto LABEL_10;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x4AAu,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error adding init property to bag: [0x%x].",
      v8);
  pvData[0] = 0;
  *(_QWORD *)&SystemTime.wYear = 4;
  Value = Windows::Compat::Shared::Registry::ReadValue(
            pvData,
            (unsigned __int64 *)&SystemTime.wYear,
            0x10u,
            v38,
            Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
            L"IndicatorDataVersion");
  v8 = Value;
  if ( Value == -2147024894 )
  {
    pvData[0] = 0;
    v8 = 0;
  }
  else if ( Value < 0 )
  {
    LODWORD(v144) = Value;
    v142 = "Error reading registry value: [0x%x].";
    LODWORD(pdwReturnedProductType) = Value;
    v10 = -79;
    goto LABEL_5;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x4B1u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error reading registry value: [0x%x].",
      v8);
  v40 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
          (Windows::Compat::Appraiser::PropertyBag *)v173,
          L"IndicatorDataVersion",
          pvData[0]);
  v8 = v40;
  if ( v40 < 0 )
  {
    LODWORD(v144) = v40;
    v142 = "Error appending property: [0x%x].";
    v10 = -76;
    goto LABEL_11;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x4B4u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error appending property: [0x%x].",
      v40);
  v174 = 0;
  *(_QWORD *)&SystemTime.wYear = 8;
  v42 = Windows::Compat::Shared::Registry::ReadValue(
          &v174,
          (unsigned __int64 *)&SystemTime.wYear,
          0x40u,
          v41,
          Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
          L"IndicatorOnesettingsEvidenceTimestamp");
  v8 = v42;
  if ( v42 == -2147024894 )
  {
    v43 = 0;
    v174 = 0;
    v8 = 0;
  }
  else
  {
    if ( v42 < 0 )
    {
      LODWORD(v144) = v42;
      v142 = "Error reading registry value: [0x%x].";
      LODWORD(pdwReturnedProductType) = v42;
      v10 = -73;
      goto LABEL_5;
    }
    v43 = v174;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
  {
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x4B7u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error reading registry value: [0x%x].",
      v8);
    v43 = v174;
  }
  if ( (unsigned __int64)v43 <= v35 )
  {
    v44 = 0;
  }
  else
  {
    LODWORD(v145) = -2147418113;
    LODWORD(pdwReturnedProductType) = -2147418113;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      192,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      pdwReturnedProductType,
      (int)"Indicator onesettings evidence timestamp: [%llu] is greater than now: [%llu] : [0x%x].",
      v43,
      v35,
      v145);
    v44 = 0;
    v43 = 0;
    v174 = 0;
  }
  if ( v169 >= (struct _OSVERSIONINFOEXW *)v43 )
    v45 = ((char *)v169 - v43) / 0xC92A69C000uLL;
  else
    v45 = 0;
  v46 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
          (Windows::Compat::Appraiser::PropertyBag *)v173,
          L"IndicatorOnesettingsAge",
          v45);
  v8 = v46;
  if ( v46 < 0 )
  {
    LODWORD(v144) = v46;
    v142 = "Error appending property: [0x%x].";
    v10 = -56;
    goto LABEL_11;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x4C8u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error appending property: [0x%x].",
      v46);
  AvailableTargetVersions = Windows::Compat::Shared::IndicatorWriter::ReadAvailableTargetVersions(
                              (struct RtlStringArray *)v193,
                              L"TargetVersionUpgradeExperienceIndicators");
  v8 = AvailableTargetVersions;
  if ( AvailableTargetVersions < 0 )
  {
    LODWORD(v144) = AvailableTargetVersions;
    v142 = "Failed ReadAvailableTargetVersions: [0x%x]";
    v10 = -49;
    goto LABEL_11;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x4CFu,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Failed ReadAvailableTargetVersions: [0x%x]",
      AvailableTargetVersions);
  v48 = v183;
  if ( RtlStringArray::Find((RtlStringArray *)v193, *((const unsigned __int16 **)v183 + 4)) <= -1 )
  {
    v148 = 0;
    v158 = 0;
    v64 = 0;
    v157 = 0;
  }
  else
  {
    v49 = Windows::Compat::Shared::IndicatorWriter::Read(
            &v156,
            &v186,
            &v197,
            L"TargetVersionUpgradeExperienceIndicators",
            *((_QWORD *)v48 + 4),
            0);
    v8 = v49;
    if ( v49 < 0 )
    {
      LODWORD(v144) = v49;
      v142 = "Error reading indicators: [0x%x].";
      v10 = -42;
      goto LABEL_11;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x4D6u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
        "Error reading indicators: [0x%x].",
        v49);
    v50 = 0;
    *(_QWORD *)&SystemTime.wYear = 0;
    if ( (_QWORD)v198 )
    {
      while ( 1 )
      {
        v51 = 0;
        if ( v50 < (unsigned __int64)v198 )
        {
          v176 = 0;
          if ( !is_mul_ok(*((unsigned __int64 *)&v197 + 1), v50)
            || (v51 = *((_QWORD *)&v199 + 1) + *((_QWORD *)&v197 + 1) * v50, v51 < *((_QWORD *)&v199 + 1)) )
          {
            v51 = 0;
          }
        }
        v52 = *(unsigned __int16 **)v51;
        v176 = v52;
        v53 = *(const unsigned __int16 **)(v51 + 8);
        v8 = StringCchPrintfW(v208, 0x104u, L"InboxIndicator_%ls", v52);
        if ( v8 < 0 )
          break;
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x4E1u,
            "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
            "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
            "Error printing name: [0x%x].",
            v8);
        v8 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
               (Windows::Compat::Appraiser::PropertyBag *)v173,
               v208,
               v53);
        if ( v8 < 0 )
        {
          v10 = -28;
          goto LABEL_10;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x4E4u,
            "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
            "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
            "Error adding init property to bag: [0x%x].",
            v8);
        if ( !wcscmp_0(L"DataRelDate", v52) || !wcscmp_0(L"DataExpDate", v52) )
        {
          v203 = 0;
          if ( swscanf_s(v53, L"%02hd/%02hd/%04hd", &v203.wMonth, &v203.wDay, &v203) == 3 )
          {
            v8 = Windows::Compat::Appraiser::Utilities::ConvertSystemTimeToULongLongTime(v204, &v203);
            if ( v8 < 0 )
            {
              LODWORD(v144) = v8;
              v142 = "Error converting date to large integer: [%#x].";
              v10 = -5;
              goto LABEL_11;
            }
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0x4FBu,
                "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
                "Error converting date to large integer: [%#x].",
                v8);
            v8 = StringCchPrintfW(v208, 0x104u, L"InboxIndicatorTime_%ls", v52);
            if ( v8 < 0 )
            {
              LODWORD(v144) = v8;
              v142 = "Error printing name: [0x%x].";
              v10 = 2;
              goto LABEL_11;
            }
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0x502u,
                "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
                "Error printing name: [0x%x].",
                v8);
            v57 = v204[0];
            v8 = StringCchPrintfW(v206, 0x15u, L"0x%016llX", v204[0]);
            if ( v8 < 0 )
            {
              LODWORD(v144) = v8;
              v142 = "Error printing value: [0x%x].";
              v10 = 5;
              goto LABEL_11;
            }
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0x505u,
                "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
                "Error printing value: [0x%x].",
                v8);
            v8 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
                   (Windows::Compat::Appraiser::PropertyBag *)v173,
                   v208,
                   v206);
            if ( v8 < 0 )
            {
              v10 = 8;
              goto LABEL_10;
            }
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0x508u,
                "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
                "Error adding init property to bag: [0x%x].",
                v8);
            if ( v57 >= (unsigned __int64)v169 )
              v58 = v57 - (_QWORD)v169;
            else
              v58 = (unsigned __int64)v169 - v57;
            v59 = v58 / 0xC92A69C000LL;
            v8 = StringCchPrintfW(v208, 0x104u, L"InboxIndicatorTimeDelta_%ls", v176);
            if ( v8 < 0 )
            {
              LODWORD(v144) = v8;
              v142 = "Error printing name: [0x%x].";
              v10 = 19;
              goto LABEL_11;
            }
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0x513u,
                "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
                "Error printing name: [0x%x].",
                v8);
            v8 = StringCchPrintfW(v206, 0x15u, L"0x%016llX", v59);
            if ( v8 < 0 )
            {
              LODWORD(v144) = v8;
              v142 = "Error printing value: [0x%x].";
              v10 = 22;
              goto LABEL_11;
            }
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0x516u,
                "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
                "Error printing value: [0x%x].",
                v8);
            v8 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
                   (Windows::Compat::Appraiser::PropertyBag *)v173,
                   v208,
                   v206);
            if ( v8 < 0 )
            {
              v10 = 25;
              goto LABEL_10;
            }
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0x519u,
                "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
                "Error adding init property to bag: [0x%x].",
                v8);
            v8 = StringCchPrintfW(v208, 0x104u, L"InboxIndicatorTimeBeforeNow_%ls", v176);
            if ( v8 < 0 )
            {
              LODWORD(v144) = v8;
              v142 = "Error printing name: [0x%x].";
              v10 = 32;
              goto LABEL_11;
            }
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0x520u,
                "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
                "Error printing name: [0x%x].",
                v8);
            v8 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
                   (Windows::Compat::Appraiser::PropertyBag *)v173,
                   v208,
                   v57 < (unsigned __int64)v169);
            if ( v8 < 0 )
            {
              v10 = 35;
              goto LABEL_10;
            }
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0x523u,
                "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
                "Error adding init property to bag: [0x%x].",
                v8);
          }
          else
          {
            LODWORD(pdwReturnedProductType) = -2147019873;
            Windows::Compat::Appraiser::WriteLog(
              (Windows::Compat::Appraiser *)1,
              246,
              (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
              "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
              pdwReturnedProductType,
              (int)"Date indicator was not formatted correctly.",
              (const char *)v144);
          }
        }
        v50 = *(_QWORD *)&SystemTime.wYear + 1LL;
        *(_QWORD *)&SystemTime.wYear = v50;
        if ( v50 >= (unsigned __int64)v198 )
          goto LABEL_188;
      }
      LODWORD(v144) = v8;
      v142 = "Error printing name: [0x%x].";
      v10 = -31;
      goto LABEL_11;
    }
LABEL_188:
    if ( (unsigned __int8)Windows::Compat::Shared::Generics::Map<unsigned short const *,unsigned short const *,&public: static int Windows::Compat::Shared::Generics::Compare::String(unsigned short const * const &,unsigned short const * const &)>::TryGetValue(
                            &v197,
                            L"GatedBlockId",
                            v202) )
    {
      v54 = -1;
      do
        ++v54;
      while ( v202[0][v54] );
      if ( v54 && v202[0][v54 - 1] == 59 )
      {
        v8 = Windows::Compat::Appraiser::Utilities::CopyStringNonConstAlloc(&String, v202[0]);
        if ( v8 < 0 )
        {
          v55 = "Failed to copy string: [0x%x].";
          v56 = 44;
LABEL_195:
          LODWORD(v144) = v8;
          LODWORD(v143) = (_DWORD)v55;
          goto LABEL_196;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x52Cu,
            "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
            "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
            "Failed to copy string: [0x%x].",
            v8);
        if ( String )
        {
          Context = 0;
          v60 = wcstok_s(String, L";", &Context);
          if ( v60 )
          {
            v61 = v184;
            while ( *v60 )
            {
              v62 = RtlStringArray::Append((RtlStringArray *)(v61 + 8), v60, 0);
              if ( v62 < 0 )
              {
                LODWORD(v144) = v62;
                LODWORD(pdwReturnedProductType) = v62;
                Windows::Compat::Appraiser::WriteLog(
                  (Windows::Compat::Appraiser *)1,
                  56,
                  (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                  "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
                  pdwReturnedProductType,
                  (int)"Failed to append gated block id: [0x%x].",
                  (const char *)v144);
                break;
              }
              v60 = wcstok_s(0, L";", &Context);
              if ( !v60 )
                break;
            }
          }
        }
      }
    }
    v63 = Windows::Compat::Shared::Generics::Map<unsigned short const *,unsigned short const *,&public: static int Windows::Compat::Shared::Generics::Compare::String(unsigned short const * const &,unsigned short const * const &)>::TryGetValue(
            &v197,
            L"GStatus",
            &v188);
    v157 = v63;
    v64 = Windows::Compat::Shared::Generics::Map<unsigned short const *,unsigned short const *,&public: static int Windows::Compat::Shared::Generics::Compare::String(unsigned short const * const &,unsigned short const * const &)>::TryGetValue(
            &v197,
            L"DataVer",
            &v177);
    v65 = Windows::Compat::Shared::Generics::Map<unsigned short const *,unsigned short const *,&public: static int Windows::Compat::Shared::Generics::Compare::String(unsigned short const * const &,unsigned short const * const &)>::TryGetValue(
            &v197,
            L"DataVerRecommended",
            &v175);
    v158 = v65;
    v148 = Windows::Compat::Shared::Generics::Map<unsigned short const *,unsigned short const *,&public: static int Windows::Compat::Shared::Generics::Compare::String(unsigned short const * const &,unsigned short const * const &)>::TryGetValue(
             &v197,
             L"Version",
             &v171);
    if ( v63 )
    {
      v66 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
              (Windows::Compat::Appraiser::PropertyBag *)v173,
              L"InboxGStatus",
              *(const unsigned __int16 **)&v188.wYear);
      v8 = v66;
      if ( v66 < 0 )
      {
        LODWORD(v144) = v66;
        v143 = "Error adding init property to bag: [0x%x].";
        v56 = 73;
        goto LABEL_196;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x549u,
          "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
          "Error adding init property to bag: [0x%x].",
          v66);
    }
    if ( v64 )
    {
      v67 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
              (Windows::Compat::Appraiser::PropertyBag *)v173,
              L"InboxIndicatorDataVer",
              v177);
      v8 = v67;
      if ( v67 < 0 )
      {
        LODWORD(v144) = v67;
        v143 = "Error adding init property to bag: [0x%x].";
        v56 = 79;
        goto LABEL_196;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x54Fu,
          "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
          "Error adding init property to bag: [0x%x].",
          v67);
    }
    if ( v65 )
    {
      v68 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
              (Windows::Compat::Appraiser::PropertyBag *)v173,
              L"InboxIndicatorDataVerRecommended",
              v175);
      v8 = v68;
      if ( v68 < 0 )
      {
        LODWORD(v144) = v68;
        v143 = "Error adding init property to bag: [0x%x].";
        v56 = 85;
        goto LABEL_196;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x555u,
          "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
          "Error adding init property to bag: [0x%x].",
          v68);
    }
    if ( v148 )
    {
      v69 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
              (Windows::Compat::Appraiser::PropertyBag *)v173,
              L"InboxIndicatorVersion",
              v171);
      v8 = v69;
      if ( v69 < 0 )
      {
        LODWORD(v144) = v69;
        v143 = "Error adding init property to bag: [0x%x].";
        v56 = 91;
        goto LABEL_196;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x55Bu,
          "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
          "Error adding init property to bag: [0x%x].",
          v69);
    }
    v70 = v186;
    if ( (unsigned __int64)v186 > *(_QWORD *)v170 )
    {
      LODWORD(v146) = -2147418113;
      LODWORD(pdwReturnedProductType) = -2147418113;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        106,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
        pdwReturnedProductType,
        (int)"Indicator timestamp: [%llu] for target %ls is greater than now: [%llu] : [0x%x].",
        v186,
        *((_QWORD *)v183 + 4),
        *(_QWORD *)v170,
        v146);
      v70 = 0;
      v186 = 0;
    }
    if ( v169 >= (struct _OSVERSIONINFOEXW *)v70 )
      v71 = ((char *)v169 - v70) / 0xC92A69C000uLL;
    else
      v71 = 0;
    v72 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
            (Windows::Compat::Appraiser::PropertyBag *)v173,
            L"DaysSinceUpdatingIndicatorsForTarget",
            v71);
    v8 = v72;
    if ( v72 < 0 )
    {
      LODWORD(v144) = v72;
      v143 = "Error adding init property to bag: [0x%x].";
      v56 = 114;
      goto LABEL_196;
    }
    v44 = 1;
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x572u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
        "Error adding init property to bag: [0x%x].",
        v72);
  }
  v73 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
          (Windows::Compat::Appraiser::PropertyBag *)v173,
          L"InboxIndicatorsPresent",
          v44);
  v8 = v73;
  if ( v73 < 0 )
  {
    LODWORD(v144) = v73;
    v143 = "Error adding init property to bag: [0x%x].";
    v56 = 122;
    goto LABEL_196;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x57Au,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error adding init property to bag: [0x%x].",
      v73);
  v74 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
          (Windows::Compat::Appraiser::PropertyBag *)v173,
          L"InboxIndicatorsIntact",
          v156);
  v8 = v74;
  if ( v74 < 0 )
  {
    LODWORD(v144) = v74;
    v143 = "Error adding init property to bag: [0x%x].";
    v56 = 125;
    goto LABEL_196;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x57Du,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error adding init property to bag: [0x%x].",
      v74);
  v75 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
          (Windows::Compat::Appraiser::PropertyBag *)v173,
          L"InboxGStatusPresent",
          v157);
  v8 = v75;
  if ( v75 < 0 )
  {
    LODWORD(v144) = v75;
    v143 = "Error adding init property to bag: [0x%x].";
    v56 = 0x80;
    goto LABEL_196;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x580u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error adding init property to bag: [0x%x].",
      v75);
  v76 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
          (Windows::Compat::Appraiser::PropertyBag *)v173,
          L"InboxIndicatorDataVerPresent",
          v64);
  v8 = v76;
  if ( v76 < 0 )
  {
    LODWORD(v144) = v76;
    v143 = "Error adding init property to bag: [0x%x].";
    v56 = -125;
    goto LABEL_196;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x583u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error adding init property to bag: [0x%x].",
      v76);
  v77 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
          (Windows::Compat::Appraiser::PropertyBag *)v173,
          L"InboxIndicatorDataVerRecommendedPresent",
          v158);
  v8 = v77;
  if ( v77 < 0 )
  {
    LODWORD(v144) = v77;
    v143 = "Error adding init property to bag: [0x%x].";
    v56 = -122;
    goto LABEL_196;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x586u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error adding init property to bag: [0x%x].",
      v77);
  v78 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
          (Windows::Compat::Appraiser::PropertyBag *)v173,
          L"InboxIndicatorVersionRecommended",
          v148);
  v8 = v78;
  if ( v78 < 0 )
  {
    LODWORD(v144) = v78;
    v143 = "Error adding init property to bag: [0x%x].";
    v56 = -119;
    goto LABEL_196;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x589u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error adding init property to bag: [0x%x].",
      v78);
  InitOnceExecuteOnce(
    &Windows::Compat::Appraiser::AppraiserSettings::InitOnce,
    Windows::Compat::Appraiser::AppraiserSettings::InitOnceCallback,
    0,
    0);
  v79 = 0;
  v80 = xmmword_1802CB3E8;
  if ( (_QWORD)xmmword_1802CB3E8 )
  {
    while ( 1 )
    {
      v81 = 0;
      if ( v79 < v80 )
      {
        v171 = 0;
        if ( !is_mul_ok(
                (unsigned __int64)*(&Windows::Compat::Appraiser::AppraiserSettings::SettingSetupAdditionalInitProperties
                                  + 1),
                v79)
          || (v81 = (__int64 *)(*((_QWORD *)&xmmword_1802CB3F8 + 1)
                              + (_QWORD)*(&Windows::Compat::Appraiser::AppraiserSettings::SettingSetupAdditionalInitProperties
                                        + 1)
                              * v79),
              (unsigned __int64)v81 < *((_QWORD *)&xmmword_1802CB3F8 + 1)) )
        {
          v81 = 0;
        }
      }
      v82 = *v81;
      v83 = -1;
      do
        ++v83;
      while ( *(_WORD *)(v82 + 2 * v83) );
      v84 = v82 + 2 * v83;
      v85 = 0;
      if ( v79 < v80 )
      {
        v171 = 0;
        v86 = (_QWORD)*(&Windows::Compat::Appraiser::AppraiserSettings::SettingSetupAdditionalInitProperties + 1) * v79;
        if ( !is_mul_ok(
                (unsigned __int64)*(&Windows::Compat::Appraiser::AppraiserSettings::SettingSetupAdditionalInitProperties
                                  + 1),
                v79)
          || (v85 = (const unsigned __int16 **)(*((_QWORD *)&xmmword_1802CB3F8 + 1) + v86),
              *((_QWORD *)&xmmword_1802CB3F8 + 1) + v86 < *((_QWORD *)&xmmword_1802CB3F8 + 1)) )
        {
          v85 = 0;
        }
      }
      v8 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
             (Windows::Compat::Appraiser::PropertyBag *)v173,
             *v85,
             (const unsigned __int16 *)(v84 + 2));
      if ( v8 < 0 )
        break;
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x595u,
          "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
          "Error appending property: [0x%x].",
          v8);
      ++v79;
      v80 = xmmword_1802CB3E8;
      if ( v79 >= (unsigned __int64)xmmword_1802CB3E8 )
        goto LABEL_317;
    }
    LODWORD(v144) = v8;
    v143 = "Error appending property: [0x%x].";
    v56 = -107;
    goto LABEL_196;
  }
LABEL_317:
  v87 = Windows::Compat::Appraiser::AppraiserSettings::OneSettingsFresh();
  v88 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
          (Windows::Compat::Appraiser::PropertyBag *)v173,
          L"OneSettingsFresh",
          v87);
  v8 = v88;
  if ( v88 < 0 )
  {
    LODWORD(v144) = v88;
    v143 = "Error appending property: [0x%x].";
    v56 = -96;
    goto LABEL_196;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x5A0u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error appending property: [0x%x].",
      v88);
  v89 = (const char *)Windows::Compat::Appraiser::AppraiserSettings::OneSettingsFreshnessTimestamp();
  v90 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
          (Windows::Compat::Appraiser::PropertyBag *)v173,
          L"OneSettingsFreshnessTimestamp",
          (unsigned __int64)v89);
  v8 = v90;
  if ( v90 < 0 )
  {
    LODWORD(v144) = v90;
    v143 = "Error appending property: [0x%x].";
    v56 = -91;
    goto LABEL_196;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x5A5u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error appending property: [0x%x].",
      v90);
  v91 = *(_QWORD *)v170;
  if ( (unsigned __int64)v89 > *(_QWORD *)v170 )
  {
    LODWORD(v145) = -2147418113;
    LODWORD(pdwReturnedProductType) = -2147418113;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      178,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      pdwReturnedProductType,
      (int)"Onesettings timestamp: [%llu] is greater than now: [%llu] : [0x%x].",
      v89,
      *(_QWORD *)v170,
      v145);
    v89 = 0;
    v91 = *(_QWORD *)v170;
  }
  if ( v169 >= (struct _OSVERSIONINFOEXW *)v89 )
    v92 = (v91 - (__int64)v89) / 0xC92A69C000uLL;
  else
    v92 = 0;
  v93 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
          (Windows::Compat::Appraiser::PropertyBag *)v173,
          L"OneSettingsFreshnessAge",
          v92);
  v8 = v93;
  if ( v93 < 0 )
  {
    LODWORD(v144) = v93;
    v143 = "Error appending property: [0x%x].";
    v56 = -70;
    goto LABEL_196;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x5BAu,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error appending property: [0x%x].",
      v93);
  WipConfigSettings = Windows::Compat::Appraiser::Utilities::GetWipConfigSettings(&v159, &v160, v211, v94);
  v96 = WipConfigSettings;
  if ( WipConfigSettings >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x5C1u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
        "Error getting WIP configuration, swallowing: [0x%x].",
        WipConfigSettings);
  }
  else
  {
    LODWORD(v144) = WipConfigSettings;
    LODWORD(pdwReturnedProductType) = WipConfigSettings;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      193,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      pdwReturnedProductType,
      (int)"Error getting WIP configuration, swallowing: [0x%x].",
      (const char *)v144);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v205);
    v97 = (volatile signed __int64 *)v205;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v97 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v97,
      _InterlockedExchangeAdd64(v97 + 17, 0),
      v207);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v98);
    v99 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      v171 = (unsigned __int16 *)v207;
      v170[0] = v96;
      v175 = (unsigned __int16 *)"Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan";
      v177 = (unsigned __int16 *)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp";
      LODWORD(v169) = 1473;
      *(_QWORD *)&v188.wYear = &szValueBuf;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      *(struct _SYSTEMTIME *)v204 = SystemTime;
      v202[0] = (unsigned __int16 *)v204;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v99,
        (unsigned int)&unk_18029F2B6,
        v100,
        v101,
        (__int64)v202,
        (__int64)&v188,
        (__int64)&v169,
        (__int64)&v177,
        (__int64)&v175,
        (__int64)v170,
        (__int64)&v171);
    }
  }
  v102 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
           (Windows::Compat::Appraiser::PropertyBag *)v173,
           L"FlightingDataFound",
           v96 == 0);
  v8 = v102;
  if ( v102 < 0 )
  {
    LODWORD(v144) = v102;
    v143 = "Error appending property: [0x%x].";
    v56 = -58;
    goto LABEL_196;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x5C6u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error appending property: [0x%x].",
      v102);
  if ( !v96 )
  {
    v103 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
             (Windows::Compat::Appraiser::PropertyBag *)v173,
             L"IsFlightingEnabled",
             v159);
    v8 = v103;
    if ( v103 < 0 )
    {
      LODWORD(v144) = v103;
      v143 = "Error appending property: [0x%x].";
      v56 = -53;
      goto LABEL_196;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x5CBu,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
        "Error appending property: [0x%x].",
        v103);
    v104 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
             (Windows::Compat::Appraiser::PropertyBag *)v173,
             L"IsRetailOs",
             v160);
    v8 = v104;
    if ( v104 < 0 )
    {
      LODWORD(v144) = v104;
      v143 = "Error appending property: [0x%x].";
      v56 = -50;
      goto LABEL_196;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x5CEu,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
        "Error appending property: [0x%x].",
        v104);
    v105 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
             (Windows::Compat::Appraiser::PropertyBag *)v173,
             L"FlightRing",
             v211);
    v8 = v105;
    if ( v105 < 0 )
    {
      LODWORD(v144) = v105;
      v143 = "Error appending property: [0x%x].";
      v56 = -47;
      goto LABEL_196;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x5D1u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
        "Error appending property: [0x%x].",
        v105);
  }
  Windows::Compat::Appraiser::Utilities::GetWufbProperties(
    &v161,
    &v149,
    &v162,
    &v163,
    &v164,
    &v165,
    &v150,
    &v166,
    &v167);
  v106 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
           (Windows::Compat::Appraiser::PropertyBag *)v173,
           L"WufbPoliciesAvailable",
           v161);
  v8 = v106;
  if ( v106 < 0 )
  {
    LODWORD(v144) = v106;
    v143 = "Error appending property: [0x%x].";
    v56 = -29;
    goto LABEL_196;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x5E3u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error appending property: [0x%x].",
      v106);
  v107 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
           (Windows::Compat::Appraiser::PropertyBag *)v173,
           L"WufbPoliciesFound",
           v149);
  v8 = v107;
  if ( v107 < 0 )
  {
    LODWORD(v144) = v107;
    v143 = "Error appending property: [0x%x].";
    v56 = -26;
    goto LABEL_196;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x5E6u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error appending property: [0x%x].",
      v107);
  if ( v149 )
  {
    v108 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
             (Windows::Compat::Appraiser::PropertyBag *)v173,
             L"WufbEnabled",
             v162);
    v8 = v108;
    if ( v108 < 0 )
    {
      LODWORD(v144) = v108;
      v143 = "Error appending property: [0x%x].";
      v56 = -21;
      goto LABEL_196;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x5EBu,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
        "Error appending property: [0x%x].",
        v108);
    v109 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
             (Windows::Compat::Appraiser::PropertyBag *)v173,
             L"WufbDeferralStatusDisabled",
             v163);
    v8 = v109;
    if ( v109 < 0 )
    {
      LODWORD(v144) = v109;
      v143 = "Error appending property: [0x%x].";
      v56 = -18;
      goto LABEL_196;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x5EEu,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
        "Error appending property: [0x%x].",
        v109);
    v110 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
             (Windows::Compat::Appraiser::PropertyBag *)v173,
             L"WufbBranchReadinessLevelDisabled",
             v164);
    v8 = v110;
    if ( v110 < 0 )
    {
      LODWORD(v144) = v110;
      v143 = "Error appending property: [0x%x].";
      v56 = -15;
      goto LABEL_196;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x5F1u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
        "Error appending property: [0x%x].",
        v110);
  }
  v111 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
           (Windows::Compat::Appraiser::PropertyBag *)v173,
           L"WufbEnableWufbSafeguardsPolicyAvailable",
           v165);
  v8 = v111;
  if ( v111 < 0 )
  {
    LODWORD(v144) = v111;
    v143 = "Error appending property: [0x%x].";
    v56 = -11;
    goto LABEL_196;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x5F5u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error appending property: [0x%x].",
      v111);
  v112 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
           (Windows::Compat::Appraiser::PropertyBag *)v173,
           L"WufbEnableWufbSafeguardsPolicyFound",
           v150);
  v8 = v112;
  if ( v112 < 0 )
  {
    LODWORD(v144) = v112;
    v143 = "Error appending property: [0x%x].";
    v56 = -8;
    goto LABEL_196;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x5F8u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error appending property: [0x%x].",
      v112);
  v113 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
           (Windows::Compat::Appraiser::PropertyBag *)v173,
           L"WufbEnableWufbSafeguardsPolicySet",
           v166);
  v8 = v113;
  if ( v113 < 0 )
  {
    LODWORD(v144) = v113;
    v143 = "Error appending property: [0x%x].";
    v56 = -5;
    goto LABEL_196;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x5FBu,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
      "Error appending property: [0x%x].",
      v113);
  if ( v150 )
  {
    v115 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
             (Windows::Compat::Appraiser::PropertyBag *)v173,
             L"WufbEnableWufbSafeguards",
             v167);
    v8 = v115;
    if ( v115 < 0 )
    {
      LODWORD(v144) = v115;
      v143 = "Error appending property: [0x%x].";
      v56 = 0;
      goto LABEL_196;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x600u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
        "Error appending property: [0x%x].",
        v115);
  }
  v170[0] = 0;
  v171 = (unsigned __int16 *)4;
  v8 = Windows::Compat::Shared::Registry::ReadValue(
         v170,
         (unsigned __int64 *)&v171,
         0x10u,
         v114,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\502505fe-762c-4e80-911e-0c3fa4c63fb0",
         L"DataRequireGatedScanForFeatureUpdates");
  v116 = v170[0] != 0;
  if ( (unsigned int)(v8 + 2147024894) > 1 )
  {
    if ( v8 < 0 )
    {
      v55 = "Error reading registry value: [0x%x].";
      v56 = 10;
      goto LABEL_195;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x60Au,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
        "Error reading registry value: [0x%x].",
        v8);
    v117 = Windows::Compat::Appraiser::PropertyBag::AppendProperty(
             (Windows::Compat::Appraiser::PropertyBag *)v173,
             L"SetupGatedScanEnterpriseOptIn",
             v116);
    v8 = v117;
    if ( v117 < 0 )
    {
      LODWORD(v144) = v117;
      v143 = "Error appending property: [0x%x].";
      v56 = 13;
      goto LABEL_196;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x60Du,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
        "Error appending property: [0x%x].",
        v117);
  }
  v118 = (void *)*((_QWORD *)v183 + 12);
  if ( v118 )
  {
    v8 = Windows::Compat::Appraiser::PropertyBag::AppendCapabilityProperties(
           (Windows::Compat::Appraiser::PropertyBag *)v173,
           v118);
    if ( v8 < 0 )
    {
      v55 = "Error appending capability properties: [0x%x].";
      v56 = 23;
      goto LABEL_195;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x617u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
        "Error appending capability properties: [0x%x].",
        v8);
  }
  v119 = v184;
  v120 = v189;
  TableDecision = Windows::Compat::Appraiser::PropertyBag::GetTableDecision(
                    (Windows::Compat::Appraiser::PropertyBag *)v173,
                    v184 + 1,
                    L"RT_ALL_SetupOnly_GatedStateSet",
                    v189,
                    L"Setup");
  v8 = TableDecision;
  if ( TableDecision >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x620u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
        "Failed to get table decision: [0x%x].",
        TableDecision);
    v122 = Windows::Compat::Appraiser::PropertyBag::GetTableDecision(
             (Windows::Compat::Appraiser::PropertyBag *)v173,
             v119,
             L"RT_ANY_SetupOnly_GatedStateTrusted",
             v120,
             L"Setup");
    v8 = v122;
    if ( v122 >= 0 )
    {
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x623u,
          "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
          "Failed to get table decision: [0x%x].",
          v122);
      v123 = Windows::Compat::Appraiser::PropertyBag::GetTableDecision(
               (Windows::Compat::Appraiser::PropertyBag *)v173,
               v119 + 2,
               L"RT_ALL_SetupOnly_MachineIsGated",
               v120,
               L"Setup");
      v8 = v123;
      if ( v123 >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x626u,
            "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
            "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
            "Failed to get table decision: [0x%x].",
            v123);
        v124 = Windows::Compat::Appraiser::PropertyBag::GetTableDecision(
                 (Windows::Compat::Appraiser::PropertyBag *)v173,
                 v119 + 3,
                 L"RT_ALL_SetupOnly_NewScanWouldBeImprovement",
                 v120,
                 L"Setup");
        v8 = v124;
        if ( v124 >= 0 )
        {
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x629u,
              "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
              "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
              "Failed to get table decision: [0x%x].",
              v124);
          v125 = Windows::Compat::Appraiser::PropertyBag::GetTableDecision(
                   (Windows::Compat::Appraiser::PropertyBag *)v173,
                   v119 + 4,
                   L"RT_ANY_SetupOnly_NewScanWouldBeTrusted",
                   v120,
                   L"Setup");
          v8 = v125;
          if ( v125 >= 0 )
          {
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0x62Cu,
                "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
                "Failed to get table decision: [0x%x].",
                v125);
            v126 = Windows::Compat::Appraiser::PropertyBag::GetTableDecision(
                     (Windows::Compat::Appraiser::PropertyBag *)v173,
                     v119 + 5,
                     L"RT_ANY_SetupOnly_DontTryToImproveOnTrustedUngatedState",
                     v120,
                     L"Setup");
            v8 = v126;
            if ( v126 >= 0 )
            {
              if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
                Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                  0x62Fu,
                  "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                  "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
                  "Failed to get table decision: [0x%x].",
                  v126);
              v127 = Windows::Compat::Appraiser::PropertyBag::GetTableDecision(
                       (Windows::Compat::Appraiser::PropertyBag *)v173,
                       v119 + 6,
                       L"RT_ANY_SetupOnly_GatedScanExposeUnexpectedFailureCode",
                       v120,
                       L"Setup");
              v8 = v127;
              if ( v127 >= 0 )
              {
                if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
                  Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                    0x632u,
                    "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                    "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
                    "Failed to get table decision: [0x%x].",
                    v127);
                v128 = Windows::Compat::Appraiser::PropertyBag::GetTableDecision(
                         (Windows::Compat::Appraiser::PropertyBag *)v173,
                         v119 + 7,
                         L"RT_ANY_SetupOnly_GatedScanEnterpriseOptOut",
                         v120,
                         L"Setup");
                v8 = v128;
                if ( v128 >= 0 )
                {
                  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
                    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                      0x635u,
                      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                      "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
                      "Failed to get table decision: [0x%x].",
                      v128);
                  v129 = Windows::Compat::Appraiser::PropertyBag::GetTableDecision(
                           (Windows::Compat::Appraiser::PropertyBag *)v173,
                           &v168,
                           L"RT_ALL_SetupOnly_GatingScanApplicable",
                           v120,
                           L"Setup");
                  v8 = v129;
                  if ( v129 >= 0 )
                  {
                    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
                      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                        0x63Cu,
                        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                        "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
                        "Failed to get table decision: [0x%x].",
                        v129);
                    v130 = Windows::Compat::Appraiser::PropertyBag::DumpPropertiesAndRunTables(
                             (Windows::Compat::Appraiser::PropertyBag *)v173,
                             0xFAu,
                             v120,
                             (wchar_t *)L"SetupOnly_",
                             0,
                             (char *)L"Setup");
                    v131 = v130;
                    if ( v130 >= 0 )
                    {
                      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
                        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                          0x63Fu,
                          "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                          "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
                          "Failed to dump table decisions: [0x%x].",
                          v130);
                    }
                    else
                    {
                      LODWORD(v144) = v130;
                      LODWORD(pdwReturnedProductTypea) = v130;
                      Windows::Compat::Appraiser::WriteLog(
                        (Windows::Compat::Appraiser *)1,
                        63,
                        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                        "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
                        pdwReturnedProductTypea,
                        (int)"Failed to dump table decisions: [0x%x].",
                        (const char *)v144);
                      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v205);
                      v132 = (volatile signed __int64 *)v205;
                      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
                        v132 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
                      TraceLoggingCorrelationVector::ToStringImpl(
                        (TraceLoggingCorrelationVector *)v132,
                        _InterlockedExchangeAdd64(v132 + 17, 0),
                        v207);
                      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
                        UtcThrottle::Throttle(
                          (UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler,
                          v133);
                      v134 = qword_1802C9628;
                      if ( *(_DWORD *)qword_1802C9628 > 5u
                        && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
                        && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
                      {
                        v189 = (struct Windows::Compat::Appraiser::DataFile *)v207;
                        LODWORD(v169) = v131;
                        v184 = (bool *)"Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan";
                        v171 = (unsigned __int16 *)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp";
                        v170[0] = 1599;
                        v175 = (unsigned __int16 *)&szValueBuf;
                        v188 = 0;
                        GetSystemTime(&v188);
                        *(struct _SYSTEMTIME *)v202 = v188;
                        v177 = (unsigned __int16 *)v202;
                        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                          v134,
                          (unsigned int)&unk_18029F253,
                          v135,
                          v136,
                          (__int64)&v177,
                          (__int64)&v175,
                          (__int64)v170,
                          (__int64)&v171,
                          (__int64)&v184,
                          (__int64)&v169,
                          (__int64)&v189);
                      }
                    }
                    v8 = !v168;
                    goto LABEL_463;
                  }
                  LODWORD(v144) = v129;
                  v143 = "Failed to get table decision: [0x%x].";
                  v56 = 60;
                }
                else
                {
                  LODWORD(v144) = v128;
                  v143 = "Failed to get table decision: [0x%x].";
                  v56 = 53;
                }
              }
              else
              {
                LODWORD(v144) = v127;
                v143 = "Failed to get table decision: [0x%x].";
                v56 = 50;
              }
            }
            else
            {
              LODWORD(v144) = v126;
              v143 = "Failed to get table decision: [0x%x].";
              v56 = 47;
            }
          }
          else
          {
            LODWORD(v144) = v125;
            v143 = "Failed to get table decision: [0x%x].";
            v56 = 44;
          }
        }
        else
        {
          LODWORD(v144) = v124;
          v143 = "Failed to get table decision: [0x%x].";
          v56 = 41;
        }
      }
      else
      {
        LODWORD(v144) = v123;
        v143 = "Failed to get table decision: [0x%x].";
        v56 = 38;
      }
    }
    else
    {
      LODWORD(v144) = v122;
      v143 = "Failed to get table decision: [0x%x].";
      v56 = 35;
    }
  }
  else
  {
    LODWORD(v144) = TableDecision;
    v143 = "Failed to get table decision: [0x%x].";
    v56 = 32;
  }
LABEL_196:
  LODWORD(pdwReturnedProductType) = v8;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    v56,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
    "Windows::Compat::Appraiser::SetupAppraiser::CheckExistingIndicatorStateForGatedScan",
    pdwReturnedProductType,
    (int)v143,
    (const char *)v144);
LABEL_463:
  v137 = String;
  if ( String )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v137);
  }
LABEL_465:
  RtlStringArray::Clear((RtlStringArray *)hHeap);
  if ( lpMem[1] )
    HeapFree(hHeap[0], 0, lpMem[1]);
  Windows::Compat::Shared::Generics::StringMap::~StringMap((Windows::Compat::Shared::Generics::StringMap *)&v197);
  RtlStringArray::Clear((RtlStringArray *)v193);
  if ( v195[1] )
    HeapFree(v193[0], 0, v195[1]);
  Windows::Compat::Appraiser::PropertyBag::~PropertyBag((Windows::Compat::Appraiser::PropertyBag *)v173);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180031920  mov     rax, rsp
0x180031923  push    rbp
0x180031924  push    rsi
0x180031925  push    rdi
0x180031926  push    r12
0x180031928  push    r13
0x18003192a  push    r14
0x18003192c  push    r15
0x18003192e  lea     rbp, [rax-0BA8h]
0x180031935  sub     rsp, 0C70h
0x18003193c  mov     [rbp+0BA0h+var_A10], 0FFFFFFFFFFFFFFFEh
0x180031947  mov     [rax+8], rbx
0x18003194b  mov     rax, cs:__security_cookie
0x180031952  xor     rax, rsp
0x180031955  mov     [rbp+0BA0h+var_40], rax
0x18003195c  mov     r12, r9
0x18003195f  mov     [rbp+0BA0h+var_B60], r9
0x180031963  mov     r13, r8
0x180031966  mov     [rbp+0BA0h+var_B20], r8
0x18003196d  mov     [rbp+0BA0h+var_B58], rdx
0x180031971  xor     edi, edi
0x180031973  mov     [rbp+0BA0h+var_C1B], dil
0x180031977  lea     rcx, [rbp+0BA0h+var_BF0]; this
0x18003197b  call    ??0PropertyBag@Appraiser@Compat@Windows@@QEAA@XZ; Windows::Compat::Appraiser::PropertyBag::PropertyBag(void)
0x180031980  nop
0x180031981  mov     [rsp+0CA0h+var_C30], dil
0x180031986  mov     [rsp+0CA0h+var_C2C], dil
0x18003198b  mov     [rsp+0CA0h+var_C2B], dil
0x180031990  mov     [rsp+0CA0h+var_C2A], dil
0x180031995  mov     [rsp+0CA0h+var_C29], dil
0x18003199a  mov     [rsp+0CA0h+var_C28], dil
0x18003199f  mov     [rsp+0CA0h+var_C27], dil
0x1800319a4  mov     [rsp+0CA0h+var_C24], dil
0x1800319a9  mov     [rsp+0CA0h+var_C23], dil
0x1800319ae  mov     [rsp+0CA0h+var_C22], dil
0x1800319b3  mov     [rsp+0CA0h+var_C2E], dil
0x1800319b8  mov     [rsp+0CA0h+var_C21], dil
0x1800319bd  mov     [rbp+0BA0h+var_C20], dil
0x1800319c1  mov     [rbp+0BA0h+var_C1F], dil
0x1800319c5  mov     [rbp+0BA0h+var_C1E], dil
0x1800319c9  mov     [rsp+0CA0h+var_C2D], dil
0x1800319ce  mov     [rbp+0BA0h+var_C1D], dil
0x1800319d2  mov     [rbp+0BA0h+var_C1C], dil
0x1800319d6  mov     [rbp+0BA0h+var_C10], edi
0x1800319d9  mov     dword ptr [rbp+0BA0h+var_B80], edi
0x1800319dc  mov     [rbp+0BA0h+var_B7C], edi
0x1800319df  mov     [rbp+0BA0h+var_B78], edi
0x1800319e2  mov     [rbp+0BA0h+var_B74], edi
0x1800319e5  mov     qword ptr [rbp+0BA0h+var_B30.wYear], rdi
0x1800319e9  mov     [rbp+0BA0h+var_B88], rdi
0x1800319ed  mov     [rbp+0BA0h+var_B98], rdi
0x1800319f1  mov     [rbp+0BA0h+var_C08], rdi
0x1800319f5  mov     [rbp+0BA0h+var_B90], rdi
0x1800319f9  mov     [rbp+0BA0h+pvData], edi
0x1800319fc  xorps   xmm0, xmm0
0x1800319ff  movups  xmmword ptr [rbp+0BA0h+var_AE8], xmm0
0x180031a06  movups  xmmword ptr [rbp+0BA0h+var_AC8], xmm0
0x180031a0d  call    cs:__imp_GetProcessHeap
0x180031a13  mov     [rbp+0BA0h+var_AE8], rax
0x180031a1a  lea     ebx, [rdi+10h]
0x180031a1d  mov     [rbp+0BA0h+var_AC8], rbx
0x180031a24  xorps   xmm0, xmm0
0x180031a27  movdqu  [rbp+0BA0h+var_AD8], xmm0
0x180031a2f  mov     [rbp+0BA0h+var_AC8+8], rdi
0x180031a36  mov     [rbp+0BA0h+var_AE8+8], rbx
0x180031a3d  mov     [rbp+0BA0h+var_AB8], edi
0x180031a43  mov     r9d, ebx
0x180031a46  lea     rcx, [rbp+0BA0h+var_AE8]
0x180031a4d  call    ?Initialize@?$RtlArray@URTL_STRING_ITEM@RtlStringArray@@@@QEAAJPEAX_K1H@Z; RtlArray<RtlStringArray::RTL_STRING_ITEM>::Initialize(void *,unsigned __int64,unsigned __int64,int)
0x180031a52  nop
0x180031a53  mov     [rbp+0BA0h+var_B48], rdi
0x180031a57  mov     [rbp+0BA0h+var_BA0], rdi
0x180031a5b  xorps   xmm0, xmm0
0x180031a5e  movups  [rbp+0BA0h+var_AB0], xmm0
0x180031a65  movups  [rbp+0BA0h+var_A90], xmm0
0x180031a6c  call    cs:__imp_GetProcessHeap
0x180031a72  mov     qword ptr [rbp+0BA0h+var_AB0], rax
0x180031a79  mov     qword ptr [rbp+0BA0h+var_A90], rbx
0x180031a80  xorps   xmm0, xmm0
0x180031a83  movdqa  [rbp+0BA0h+var_AA0], xmm0
0x180031a8b  mov     qword ptr [rbp+0BA0h+var_A90+8], rdi
0x180031a92  mov     qword ptr [rbp+0BA0h+var_AB0+8], rbx
0x180031a99  lea     rcx, [rbp+0BA0h+var_A80]; this
0x180031aa0  call    ??0StringLibrary@Generics@Shared@Compat@Windows@@QEAA@XZ; Windows::Compat::Shared::Generics::StringLibrary::StringLibrary(void)
0x180031aa5  nop
0x180031aa6  xorps   xmm0, xmm0
0x180031aa9  movups  xmmword ptr [rbp+0BA0h+var_9F0.wYear], xmm0
0x180031ab0  mov     [rbp+0BA0h+var_9E0], rdi
0x180031ab7  mov     [rbp+0BA0h+var_C18], rdi
0x180031abb  call    cs:__imp_GetProcessHeap
0x180031ac1  xorps   xmm0, xmm0
0x180031ac4  movups  xmmword ptr [rbp+0BA0h+hHeap], xmm0
0x180031acb  movups  xmmword ptr [rbp+0BA0h+lpMem], xmm0
0x180031ad2  call    cs:__imp_GetProcessHeap
0x180031ad8  mov     [rbp+0BA0h+hHeap], rax
0x180031adf  mov     [rbp+0BA0h+lpMem], rbx
0x180031ae6  xorps   xmm0, xmm0
0x180031ae9  movdqu  [rbp+0BA0h+var_B08], xmm0
0x180031af1  mov     [rbp+0BA0h+lpMem+8], rdi
0x180031af8  mov     [rbp+0BA0h+hHeap+8], 8
0x180031b03  mov     [rbp+0BA0h+var_A00], rdi
0x180031b0a  mov     [rbp+0BA0h+Context], rdi
0x180031b0e  mov     [rbp+0BA0h+String], rdi
0x180031b12  cmp     [r12+3], dil
0x180031b17  jnz     short loc_180031B21
0x180031b19  lea     ebx, [rdi+1]
0x180031b1c  jmp     loc_180034221
0x180031b21  lea     rcx, [rbp+0BA0h+var_C10]; unsigned int *
0x180031b25  call    ?GetInboxDataFileVersion@DataFile@Appraiser@Compat@Windows@@SAJAEAK@Z; Windows::Compat::Appraiser::DataFile::GetInboxDataFileVersion(ulong &)
0x180031b2a  mov     r8d, [rbp+0BA0h+var_C10]; unsigned int
0x180031b2e  lea     rdx, aInboxdataversi; "InboxDataVersion"
0x180031b35  lea     rcx, [rbp+0BA0h+var_BF0]; this
0x180031b39  call    ?AppendProperty@PropertyBag@Appraiser@Compat@Windows@@QEAAJPEBGK@Z; Windows::Compat::Appraiser::PropertyBag::AppendProperty(ushort const *,ulong)
0x180031b3e  mov     ebx, eax
0x180031b40  lea     r15, aErrorAddingIni; "Error adding init property to bag: [0x%"...
0x180031b47  test    eax, eax
0x180031b49  jns     short loc_180031B7A
0x180031b4b  mov     dword ptr [rsp+0CA0h+var_C70], eax; char *
0x180031b4f  mov     [rsp+0CA0h+var_C78], r15; int
0x180031b54  mov     dword ptr [rsp+0CA0h+pdwReturnedProductType], eax; char *
0x180031b58  lea     r9, aWindowsCompatA_95; "Windows::Compat::Appraiser::SetupApprai"...
0x180031b5f  lea     r8, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x180031b66  mov     edx, 423h; bool
0x180031b6b  mov     ecx, 1; this
0x180031b70  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180031b75  jmp     loc_180034221
0x180031b7a  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180031b80  mov     edi, 1
0x180031b85  and     eax, edi
0x180031b87  lea     rsi, aWindowsCompatA_95; "Windows::Compat::Appraiser::SetupApprai"...
0x180031b8e  lea     r14, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x180031b95  test    al, al
0x180031b97  jz      short loc_180031BB0
0x180031b99  mov     dword ptr [rsp+0CA0h+pdwReturnedProductType], ebx
0x180031b9d  mov     r9, r15; char *
0x180031ba0  mov     r8, rsi; char *
0x180031ba3  mov     rdx, r14; char *
0x180031ba6  mov     ecx, 423h; unsigned int
0x180031bab  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180031bb0  mov     r8d, [r13+280h]; unsigned int
0x180031bb7  lea     rdx, aCurrentdataver; "CurrentDataVersion"
0x180031bbe  lea     rcx, [rbp+0BA0h+var_BF0]; this
0x180031bc2  call    ?AppendProperty@PropertyBag@Appraiser@Compat@Windows@@QEAAJPEBGK@Z; Windows::Compat::Appraiser::PropertyBag::AppendProperty(ushort const *,ulong)
0x180031bc7  mov     ebx, eax
0x180031bc9  test    eax, eax
0x180031bcb  jns     short loc_180031BE9
0x180031bcd  mov     edx, 426h
0x180031bd2  mov     dword ptr [rsp+0CA0h+var_C70], ebx
0x180031bd6  mov     [rsp+0CA0h+var_C78], r15
0x180031bdb  mov     dword ptr [rsp+0CA0h+pdwReturnedProductType], ebx
0x180031bdf  mov     r9, rsi
0x180031be2  mov     r8, r14
0x180031be5  mov     ecx, edi
0x180031be7  jmp     short loc_180031B70
0x180031be9  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180031bef  and     eax, edi
0x180031bf1  test    al, al
0x180031bf3  jz      short loc_180031C0C
0x180031bf5  mov     dword ptr [rsp+0CA0h+pdwReturnedProductType], ebx
0x180031bf9  mov     r9, r15; char *
0x180031bfc  mov     r8, rsi; char *
0x180031bff  mov     rdx, r14; char *
0x180031c02  mov     ecx, 426h; unsigned int
0x180031c07  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180031c0c  mov     r8d, [r12+11h]; unsigned int
0x180031c11  lea     rdx, aAdldataversion; "AdlDataVersion"
0x180031c18  lea     rcx, [rbp+0BA0h+var_BF0]; this
0x180031c1c  call    ?AppendProperty@PropertyBag@Appraiser@Compat@Windows@@QEAAJPEBGK@Z; Windows::Compat::Appraiser::PropertyBag::AppendProperty(ushort const *,ulong)
0x180031c21  mov     ebx, eax
0x180031c23  test    eax, eax
0x180031c25  jns     short loc_180031C2E
0x180031c27  mov     edx, 429h
0x180031c2c  jmp     short loc_180031BD2
0x180031c2e  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180031c34  and     eax, edi
0x180031c36  test    al, al
0x180031c38  jz      short loc_180031C51
0x180031c3a  mov     dword ptr [rsp+0CA0h+pdwReturnedProductType], ebx
0x180031c3e  mov     r9, r15; char *
0x180031c41  mov     r8, rsi; char *
0x180031c44  mov     rdx, r14; char *
0x180031c47  mov     ecx, 429h; unsigned int
0x180031c4c  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180031c51  mov     r8d, [r13+288h]; unsigned int
0x180031c58  lea     rdx, aSdbver; "SdbVer"
0x180031c5f  lea     rcx, [rbp+0BA0h+var_BF0]; this
0x180031c63  call    ?AppendProperty@PropertyBag@Appraiser@Compat@Windows@@QEAAJPEBGK@Z; Windows::Compat::Appraiser::PropertyBag::AppendProperty(ushort const *,ulong)
0x180031c68  mov     ebx, eax
0x180031c6a  test    eax, eax
0x180031c6c  jns     short loc_180031C78
0x180031c6e  mov     edx, 42Ch
0x180031c73  jmp     loc_180031BD2
0x180031c78  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180031c7e  and     eax, edi
0x180031c80  test    al, al
0x180031c82  jz      short loc_180031C9B
0x180031c84  mov     dword ptr [rsp+0CA0h+pdwReturnedProductType], ebx
0x180031c88  mov     r9, r15; char *
0x180031c8b  mov     r8, rsi; char *
0x180031c8e  mov     rdx, r14; char *
0x180031c91  mov     ecx, 42Ch; unsigned int
0x180031c96  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180031c9b  mov     r8d, [r12+19h]; unsigned int
0x180031ca0  lea     rdx, aPrevioussdbver; "PreviousSdbVerBeforeReuse"
0x180031ca7  lea     rcx, [rbp+0BA0h+var_BF0]; this
0x180031cab  call    ?AppendProperty@PropertyBag@Appraiser@Compat@Windows@@QEAAJPEBGK@Z; Windows::Compat::Appraiser::PropertyBag::AppendProperty(ushort const *,ulong)
0x180031cb0  mov     ebx, eax
0x180031cb2  test    eax, eax
0x180031cb4  jns     short loc_180031CC0
0x180031cb6  mov     edx, 42Fh
0x180031cbb  jmp     loc_180031BD2
0x180031cc0  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180031cc6  and     eax, edi
0x180031cc8  test    al, al
0x180031cca  jz      short loc_180031CE3
0x180031ccc  mov     dword ptr [rsp+0CA0h+pdwReturnedProductType], ebx
0x180031cd0  mov     r9, r15; char *
0x180031cd3  mov     r8, rsi; char *
0x180031cd6  mov     rdx, r14; char *
0x180031cd9  mov     ecx, 42Fh; unsigned int
0x180031cde  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180031ce3  mov     rcx, [r12+50h]
0x180031ce8  xor     r12d, r12d
0x180031ceb  test    rcx, rcx
0x180031cee  jz      short loc_180031CF9
0x180031cf0  cmp     r12w, [rcx]
0x180031cf4  mov     r8b, dil
0x180031cf7  jnz     short loc_180031CFC
0x180031cf9  mov     r8b, r12b; bool
0x180031cfc  lea     rdx, aAdllinklisted; "AdlLinkListed"
0x180031d03  lea     rcx, [rbp+0BA0h+var_BF0]; this
0x180031d07  call    ?AppendProperty@PropertyBag@Appraiser@Compat@Windows@@QEAAJPEBG_N@Z; Windows::Compat::Appraiser::PropertyBag::AppendProperty(ushort const *,bool)
0x180031d0c  mov     ebx, eax
0x180031d0e  test    eax, eax
0x180031d10  jns     short loc_180031D1C
0x180031d12  mov     edx, 432h
0x180031d17  jmp     loc_180031BD2
0x180031d1c  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180031d22  and     eax, edi
0x180031d24  test    al, al
0x180031d26  jz      short loc_180031D3F
0x180031d28  mov     dword ptr [rsp+0CA0h+pdwReturnedProductType], ebx
0x180031d2c  mov     r9, r15; char *
0x180031d2f  mov     r8, rsi; char *
0x180031d32  mov     rdx, r14; char *
0x180031d35  mov     ecx, 432h; unsigned int
0x180031d3a  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180031d3f  call    ?AppraiserVersion@WicaFactory@Appraiser@Compat@Windows@@SAPEBGXZ; Windows::Compat::Appraiser::WicaFactory::AppraiserVersion(void)
0x180031d44  mov     r8, rax; unsigned __int16 *
0x180031d47  lea     rdx, aAppraiserversi; "AppraiserVersion"
0x180031d4e  lea     rcx, [rbp+0BA0h+var_BF0]; this
0x180031d52  call    ?AppendProperty@PropertyBag@Appraiser@Compat@Windows@@QEAAJPEBG0@Z; Windows::Compat::Appraiser::PropertyBag::AppendProperty(ushort const *,ushort const *)
0x180031d57  mov     ebx, eax
0x180031d59  test    eax, eax
0x180031d5b  jns     short loc_180031D67
0x180031d5d  mov     edx, 435h
0x180031d62  jmp     loc_180031BD2
0x180031d67  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180031d6d  and     eax, edi
0x180031d6f  test    al, al
0x180031d71  jz      short loc_180031D8A
0x180031d73  mov     dword ptr [rsp+0CA0h+pdwReturnedProductType], ebx
0x180031d77  mov     r9, r15; char *
0x180031d7a  mov     r8, rsi; char *
0x180031d7d  mov     rdx, r14; char *
0x180031d80  mov     ecx, 435h; unsigned int
0x180031d85  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180031d8a  mov     ebx, [r13+288h]
0x180031d91  xor     r9d, r9d; Context
0x180031d94  xor     r8d, r8d; Parameter
0x180031d97  lea     rdx, ?InitOnceCallback@AppraiserSettings@Appraiser@Compat@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180031d9e  lea     rcx, ?InitOnce@AppraiserSettings@Appraiser@Compat@Windows@@0T_RTL_RUN_ONCE@@A; InitOnce
0x180031da5  call    cs:__imp_InitOnceExecuteOnce
0x180031dab  mov     r9d, ebx; unsigned int
0x180031dae  lea     r8, aSetupinit; "SETUPINIT_"
0x180031db5  lea     rdx, ?SettingSetupAdditionalInitProperties@AppraiserSettings@Appraiser@Compat@Windows@@0VRtlNameValueArray@@A; struct RtlNameValueArray *
0x180031dbc  lea     rcx, [rbp+0BA0h+hHeap]; this
0x180031dc3  call    ?CalculateSdbVerExpDateExtensionProperties@Utilities@Appraiser@Compat@Windows@@SAJAEAVRtlNameValueArray@@PEBV5@PEBGK@Z; Windows::Compat::Appraiser::Utilities::CalculateSdbVerExpDateExtensionProperties(RtlNameValueArray &,RtlNameValueArray const *,ushort const *,ulong)
0x180031dc8  mov     ebx, eax
0x180031dca  test    eax, eax
0x180031dcc  jns     short loc_180031DE8
0x180031dce  mov     dword ptr [rsp+0CA0h+var_C70], eax
0x180031dd2  lea     r9, aErrorCalculati; "Error calculating sdb ver expiration pr"...
0x180031dd9  mov     [rsp+0CA0h+var_C78], r9
0x180031dde  mov     edx, 43Bh
0x180031de3  jmp     loc_180031BDB
0x180031de8  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180031dee  and     eax, edi
0x180031df0  test    al, al
0x180031df2  jz      short loc_180031E0F
0x180031df4  mov     dword ptr [rsp+0CA0h+pdwReturnedProductType], ebx
0x180031df8  lea     r9, aErrorCalculati; "Error calculating sdb ver expiration pr"...
0x180031dff  mov     r8, rsi; char *
0x180031e02  mov     rdx, r14; char *
0x180031e05  mov     ecx, 43Bh; unsigned int
0x180031e0a  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180031e0f  mov     r13, qword ptr [rbp+0BA0h+var_B08]
0x180031e16  xor     r9d, r9d
0x180031e19  test    r13, r13
0x180031e1c  jz      loc_180031EE1
  ... truncated ...
```
