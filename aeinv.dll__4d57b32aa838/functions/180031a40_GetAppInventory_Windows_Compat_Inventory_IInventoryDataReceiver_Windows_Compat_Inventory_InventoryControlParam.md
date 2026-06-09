# GetAppInventory(Windows::Compat::Inventory::IInventoryDataReceiver *,Windows::Compat::Inventory::InventoryControlParams *,char const *)

- ea: `0x180031a40`
- end: `0x1800340bc`
- name: `?GetAppInventory@@YAJPEAVIInventoryDataReceiver@Inventory@Compat@Windows@@PEAUInventoryControlParams@234@PEBD@Z`
- size: `9852`
- prototype: `__int64 __fastcall(struct Windows::Compat::Inventory::IInventoryDataReceiver *, struct Windows::Compat::Inventory::InventoryControlParams *, const char *)`
- caller_count: `1`
- callee_count: `91`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180066e80`

## callees

- `0x180008e58`
- `0x18000a194`
- `0x18000b364`
- `0x18000b7cc`
- `0x18000d834`
- `0x18000eb5c`
- `0x18000ecac`
- `0x18000ef50`
- `0x18000f3b4`
- `0x18000f700`
- `0x1800118d0`
- `0x180013450`
- `0x1800142a4`
- `0x1800172bc`
- `0x1800188f4`
- `0x180018a60`
- `0x1800197d4`
- `0x18001dbb4`
- `0x18001e0d0`
- `0x1800217f8`
- `0x1800218c0`
- `0x1800274b0`
- `0x1800289d0`
- `0x18002bdfc`
- `0x18002d3b8`
- `0x18002d580`
- `0x18002d5d0`
- `0x18002d624`
- `0x18002da48`
- `0x18002debc`
- `0x18002ee80`
- `0x180030430`
- `0x180030fc0`
- `0x1800315c0`
- `0x180031a40`
- `0x180034908`
- `0x180034ff0`
- `0x180035dc0`
- `0x18003a050`
- `0x18003fb20`
- `0x180040254`
- `0x1800403ac`
- `0x1800404c4`
- `0x1800417a8`
- `0x180043598`
- `0x180046510`
- `0x1800482d0`
- `0x1800498d4`
- `0x18004dc14`
- `0x18004f3c4`

## import_xrefs

- `ntdll!EtwEventWriteNoRegistration` at `0x180033dff`
- `ntdll!EtwEventWriteNoRegistration` at `0x180033dff`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180033e3b`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180033e3b`
- `KERNEL32!Sleep` at `0x180031bdf`
- `KERNEL32!Sleep` at `0x180031bdf`
- `KERNEL32!GetCurrentThread` at `0x180031b31`
- `KERNEL32!GetCurrentThread` at `0x180033ecd`
- `KERNEL32!GetCurrentThread` at `0x180031b31`
- `KERNEL32!GetCurrentThread` at `0x180033ecd`
- `KERNEL32!QueryThreadCycleTime` at `0x180031b42`
- `KERNEL32!QueryThreadCycleTime` at `0x180033ede`
- `KERNEL32!QueryThreadCycleTime` at `0x180031b42`
- `KERNEL32!QueryThreadCycleTime` at `0x180033ede`
- `KERNEL32!GetTickCount` at `0x180031a88`
- `KERNEL32!GetTickCount` at `0x180033ea0`
- `KERNEL32!GetTickCount` at `0x180031a88`
- `KERNEL32!GetTickCount` at `0x180033ea0`

## string_xrefs

- `0x180031bb4`: `Inventory already running. Waiting for it to complete.`
- `0x180031c17`: `Inventory still hasn't completed. Continuing [0x%08x]`
- `0x18003237a`: `Skipping scan, returning cached inventory`
- `0x18003404b`: `onecore\internal\base\inc\appcompat\inventory\GetAppInventory.cpp`
- `0x18003406a`: `onecore\internal\base\inc\appcompat\inventory\GetAppInventory.cpp`
- `0x180034089`: `onecore\internal\base\inc\appcompat\inventory\GetAppInventory.cpp`
- `0x1800340a9`: `onecore\internal\base\inc\appcompat\inventory\GetAppInventory.cpp`
- `0x180032991`: `Loaded user hive SID: %ws`
- `0x1800329e6`: `Loaded user hive SID: %ws`
- `0x180032b3c`: `Per-user app: User hive loaded: appUserSid: %ws loadedUserHiveSid: %ws AppName: %ws`
- `0x180032c2c`: `Per-user app: User hive loaded: appUserSid: %ws loadedUserHiveSid: %ws AppName: %ws`
- `0x180032d25`: `Per-user app: User hive not loaded (cleared batch marker so its not removed): Name: %ws ProgramId: %ws ArpRegistryKeyPath: %ws AppUserSid: %ws`
- `0x1800336ef`: `Per-user app file (user hive not loaded). ProgramId: %ws FileId: %ws FilePath: %ws`
- `0x180033626`: `File's ProgramId no longer exist. Calculating new orphan ProgramId. GetFilePathHash: %ls GetProgramId: %ls GetFileId: %ls GetFilePath: %ls`
- `0x180033dc5`: `ReturnCachedInventoryItems failed: [0x%08x]`
- `0x180033e66`: `TelCacheProvider::SetMetadata failed [%#x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=73
__int64 __fastcall GetAppInventory(
        struct Windows::Compat::Inventory::IInventoryDataReceiver *a1,
        struct Windows::Compat::Inventory::InventoryControlParams *a2,
        const char *a3)
{
  int v6; // r15d
  HANDLE CurrentThread; // rax
  unsigned int v8; // edx
  struct THUNKS *v9; // rcx
  Windows::Compat::Shared::Telemetry::TelemetryProvider *v11; // rcx
  bool IsAeInvAlreadyRunning; // al
  int v13; // edi
  Windows::Compat::Shared::Telemetry::TelemetryProvider *v14; // rcx
  int v15; // esi
  char v16; // r13
  int v17; // edi
  Application *v18; // rax
  __int64 *v19; // rdx
  int v20; // ebx
  File *v21; // rax
  char *v22; // r8
  __int64 *v23; // rdx
  int v24; // ebx
  AmiFrameworkItem *v25; // rax
  __int64 *v26; // rdx
  int v27; // ebx
  AmiShortcutItem *v28; // rax
  AmiShortcutItem *v29; // rax
  __int64 *v30; // rdx
  int v31; // ebx
  int v32; // ebx
  int v33; // ebx
  int v34; // ebx
  unsigned int v35; // esi
  struct Windows::Compat::Inventory::IInventoryDataReceiver *v36; // rbx
  unsigned __int16 v37; // r8
  unsigned int v38; // edx
  int v39; // ebx
  int v40; // ebx
  char v41; // bl
  int v42; // eax
  __int64 v43; // rcx
  __int64 LoadedUserHiveSids; // rax
  char IsEnabled; // al
  File *v46; // rbx
  File *v47; // rdi
  File *v48; // rax
  _QWORD *v49; // rax
  int FirstItem; // ebx
  wchar_t *v51; // rcx
  char v52; // al
  File *v53; // rbx
  File *v54; // rdi
  File *v55; // r8
  _QWORD *v56; // rcx
  _QWORD *v57; // rcx
  _QWORD *v58; // rax
  _QWORD *v59; // r8
  _QWORD *v60; // rcx
  _QWORD *v61; // rdx
  File *v62; // rcx
  _QWORD *v63; // rax
  _QWORD *v64; // r8
  _QWORD *v65; // rdx
  File *v66; // rcx
  _QWORD *v67; // rax
  int v68; // eax
  char v69; // al
  struct Application *v70; // rbx
  struct Application *v71; // rdi
  __int64 v72; // rax
  unsigned int v73; // r12d
  unsigned int v74; // edi
  unsigned int v75; // esi
  __int64 FilesFromCache; // rax
  File *v77; // rax
  File *v78; // rbx
  File *v79; // r13
  int v80; // eax
  int v81; // eax
  __int64 v82; // rax
  __int64 v83; // rax
  File *v84; // rsi
  File *i; // rdi
  __int64 v86; // rax
  _QWORD *v87; // rax
  __int64 v88; // rax
  _QWORD *v89; // rax
  char v90; // si
  unsigned __int64 v91; // r15
  bool v92; // zf
  struct Application *v93; // rax
  struct Application *v94; // r14
  __int64 v95; // rax
  __int64 v96; // rdi
  char *v97; // r14
  __int64 v98; // rax
  _QWORD *v99; // rax
  _QWORD *v100; // r15
  _QWORD *v101; // rax
  _QWORD *v102; // rsi
  File *v103; // rax
  File *v104; // rdi
  _QWORD *v105; // rax
  __int64 v106; // rax
  __int64 v107; // rax
  const struct Application *j; // r13
  __int64 v109; // rax
  __int64 DirectoryFromPath; // rax
  char found; // di
  _QWORD *v112; // r12
  _QWORD *v113; // rax
  _QWORD *v114; // rsi
  File *v115; // rax
  File *v116; // rdi
  _QWORD *v117; // rax
  _QWORD *v118; // rax
  _QWORD *v119; // r14
  _QWORD *v120; // rax
  _QWORD *v121; // rsi
  File *v122; // rax
  File *v123; // rdi
  _QWORD *v124; // rax
  _QWORD *v125; // rax
  _QWORD *v126; // rsi
  File *v127; // rax
  File *v128; // rdi
  _QWORD *v129; // rax
  unsigned int v130; // r12d
  struct Application *v131; // rbx
  struct Application *v132; // r15
  char *v133; // r14
  __int64 v134; // rax
  _QWORD *v135; // rax
  _QWORD *v136; // rax
  const struct File *k; // rdi
  _QWORD *v138; // rsi
  _QWORD *v139; // rax
  __int64 v140; // r9
  __int64 v141; // rdx
  __int64 v142; // rax
  const struct Application *v143; // rdi
  struct Application *v144; // rsi
  _QWORD *v145; // rax
  _QWORD *v146; // rax
  const struct File *m; // rbx
  _QWORD *v148; // r8
  _QWORD *v149; // rcx
  __int64 v150; // rax
  int n; // eax
  const wchar_t *v152; // rcx
  _QWORD *v153; // rax
  __int64 v154; // rsi
  int v155; // edi
  int v156; // ebx
  int v157; // eax
  int v158; // eax
  int v159; // eax
  HANDLE v160; // rax
  int v161[2]; // [rsp+20h] [rbp-1E48h]
  DWORD v162; // [rsp+20h] [rbp-1E48h]
  File *v163; // [rsp+28h] [rbp-1E40h]
  _QWORD *v164; // [rsp+30h] [rbp-1E38h]
  _QWORD *v165; // [rsp+38h] [rbp-1E30h]
  unsigned int v166; // [rsp+A0h] [rbp-1DC8h]
  int v167; // [rsp+A4h] [rbp-1DC4h]
  void *v168; // [rsp+A8h] [rbp-1DC0h] BYREF
  int v169; // [rsp+B0h] [rbp-1DB8h]
  File *v170; // [rsp+B8h] [rbp-1DB0h]
  int v171; // [rsp+C0h] [rbp-1DA8h]
  int v172; // [rsp+C4h] [rbp-1DA4h]
  int v173; // [rsp+C8h] [rbp-1DA0h] BYREF
  int v174; // [rsp+CCh] [rbp-1D9Ch] BYREF
  struct Application *v175[2]; // [rsp+D0h] [rbp-1D98h] BYREF
  __int64 v176; // [rsp+E0h] [rbp-1D88h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+E8h] [rbp-1D80h] BYREF
  struct Windows::Compat::Inventory::IInventoryDataReceiver *v178; // [rsp+F0h] [rbp-1D78h]
  _QWORD v179[2]; // [rsp+F8h] [rbp-1D70h] BYREF
  File *v180; // [rsp+108h] [rbp-1D60h]
  _QWORD v181[2]; // [rsp+110h] [rbp-1D58h] BYREF
  DWORD TickCount; // [rsp+120h] [rbp-1D48h]
  unsigned __int64 v183; // [rsp+128h] [rbp-1D40h] BYREF
  unsigned __int64 CycleTime; // [rsp+130h] [rbp-1D38h] BYREF
  _BYTE v185[16]; // [rsp+138h] [rbp-1D30h] BYREF
  _QWORD v186[2]; // [rsp+148h] [rbp-1D20h] BYREF
  _QWORD v187[31]; // [rsp+158h] [rbp-1D10h] BYREF
  _QWORD v188[2]; // [rsp+250h] [rbp-1C18h] BYREF
  __int64 v189; // [rsp+260h] [rbp-1C08h]
  unsigned __int64 v190; // [rsp+268h] [rbp-1C00h]
  File *v191[2]; // [rsp+270h] [rbp-1BF8h] BYREF
  __int64 v192; // [rsp+280h] [rbp-1BE8h]
  _QWORD v193[3]; // [rsp+290h] [rbp-1BD8h] BYREF
  unsigned __int64 v194; // [rsp+2A8h] [rbp-1BC0h]
  _BYTE v195[32]; // [rsp+2B0h] [rbp-1BB8h] BYREF
  __int64 v196; // [rsp+2D0h] [rbp-1B98h] BYREF
  char v197[80]; // [rsp+2D8h] [rbp-1B90h] BYREF
  __int64 v198; // [rsp+328h] [rbp-1B40h]
  __int16 v199; // [rsp+330h] [rbp-1B38h]
  __int64 v200; // [rsp+338h] [rbp-1B30h]
  __int128 v201; // [rsp+340h] [rbp-1B28h]
  __int64 v202; // [rsp+350h] [rbp-1B18h]
  int v203; // [rsp+358h] [rbp-1B10h]
  char v204; // [rsp+35Ch] [rbp-1B0Ch]
  _BYTE v205[32]; // [rsp+360h] [rbp-1B08h] BYREF
  __int64 v206; // [rsp+380h] [rbp-1AE8h] BYREF
  char v207[80]; // [rsp+388h] [rbp-1AE0h] BYREF
  __int64 v208; // [rsp+3D8h] [rbp-1A90h]
  __int16 v209; // [rsp+3E0h] [rbp-1A88h]
  __int64 v210; // [rsp+3E8h] [rbp-1A80h]
  __int128 v211; // [rsp+3F0h] [rbp-1A78h]
  __int64 v212; // [rsp+400h] [rbp-1A68h]
  int v213; // [rsp+408h] [rbp-1A60h]
  char v214; // [rsp+40Ch] [rbp-1A5Ch]
  __int64 v215; // [rsp+410h] [rbp-1A58h] BYREF
  char v216[80]; // [rsp+418h] [rbp-1A50h] BYREF
  __int64 v217; // [rsp+468h] [rbp-1A00h]
  __int16 v218; // [rsp+470h] [rbp-19F8h]
  __int64 v219; // [rsp+478h] [rbp-19F0h]
  __int128 v220; // [rsp+480h] [rbp-19E8h]
  __int64 v221; // [rsp+490h] [rbp-19D8h]
  int v222; // [rsp+498h] [rbp-19D0h]
  char v223; // [rsp+49Ch] [rbp-19CCh]
  __int64 v224; // [rsp+4A0h] [rbp-19C8h] BYREF
  char v225[80]; // [rsp+4A8h] [rbp-19C0h] BYREF
  __int64 v226; // [rsp+4F8h] [rbp-1970h]
  __int16 v227; // [rsp+500h] [rbp-1968h]
  __int64 v228; // [rsp+508h] [rbp-1960h]
  __int128 v229; // [rsp+510h] [rbp-1958h]
  __int64 v230; // [rsp+520h] [rbp-1948h]
  int v231; // [rsp+528h] [rbp-1940h]
  char v232; // [rsp+52Ch] [rbp-193Ch]
  _BYTE v233[32]; // [rsp+530h] [rbp-1938h] BYREF
  _BYTE v234[16]; // [rsp+550h] [rbp-1918h] BYREF
  TelCacheProvider *v235; // [rsp+560h] [rbp-1908h]
  __int64 *v236; // [rsp+570h] [rbp-18F8h]
  __int64 *v237; // [rsp+578h] [rbp-18F0h]
  _BYTE v238[56]; // [rsp+640h] [rbp-1828h] BYREF
  _QWORD v239[4]; // [rsp+678h] [rbp-17F0h] BYREF
  _QWORD *v240; // [rsp+698h] [rbp-17D0h] BYREF
  _QWORD v241[3]; // [rsp+6A0h] [rbp-17C8h] BYREF
  unsigned __int64 v242; // [rsp+6B8h] [rbp-17B0h]
  __int64 v243; // [rsp+700h] [rbp-1768h] BYREF
  unsigned __int64 v244; // [rsp+710h] [rbp-1758h]
  wchar_t *v245[12]; // [rsp+790h] [rbp-16D8h] BYREF
  _QWORD v246[72]; // [rsp+7F0h] [rbp-1678h] BYREF
  char v247[8]; // [rsp+A30h] [rbp-1438h] BYREF
  _BYTE v248[16]; // [rsp+A38h] [rbp-1430h] BYREF
  char v249[32]; // [rsp+A48h] [rbp-1420h] BYREF
  _QWORD v250[2]; // [rsp+A68h] [rbp-1400h] BYREF
  _QWORD v251[3]; // [rsp+A78h] [rbp-13F0h] BYREF
  _QWORD *v252; // [rsp+A90h] [rbp-13D8h] BYREF
  char v253[16]; // [rsp+A98h] [rbp-13D0h] BYREF
  unsigned __int64 v254; // [rsp+AA8h] [rbp-13C0h]
  wchar_t *String1[33]; // [rsp+AB8h] [rbp-13B0h] BYREF
  char v256[16]; // [rsp+BC0h] [rbp-12A8h] BYREF
  __int64 v257; // [rsp+BD0h] [rbp-1298h]
  _BYTE v258[56]; // [rsp+E20h] [rbp-1048h] BYREF
  char v259[4040]; // [rsp+E58h] [rbp-1010h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E68h] [rbp+0h]

  v187[1] = -2;
  v178 = a1;
  TickCount = GetTickCount();
  CycleTime = 0;
  v183 = 0;
  v6 = *((_DWORD *)a2 + 4);
  v166 = v6;
  v168 = 0;
  if ( v6 )
  {
    if ( (v6 & 0x10) != 0 )
      AslLogCallPrintf(
        1,
        (unsigned int)"GetAppInventory",
        89,
        (unsigned int)"Request of deprecated flag: GAI_FLAG_APPLICATION_INFO [%#x]");
    else
      v166 = v6;
    if ( (v6 & 0x20) != 0 )
      AslLogCallPrintf(
        1,
        (unsigned int)"GetAppInventory",
        93,
        (unsigned int)"Request of deprecated flag: GAI_FLAG_FILE_INFO [%#x]");
  }
  else
  {
    v6 = 983051;
    v166 = 983051;
  }
  CurrentThread = GetCurrentThread();
  QueryThreadCycleTime(CurrentThread, &CycleTime);
  DownlevelThunksInitEx(v9, v8);
  if ( !(unsigned int)GetInvInboxRedirectImpl("GetAppInventory", a1, a2, a3) )
  {
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v168);
    return 0;
  }
  (**(void (__fastcall ***)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *))a1)(
    a1,
    L"DISCARD_AND_RESET_ASSETS");
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &v168,
    0);
  if ( Utility::IsAeInvAlreadyRunning(&v168) )
  {
    AslLogCallPrintf(
      3,
      (unsigned int)"GetAppInventory",
      117,
      (unsigned int)"Inventory already running. Waiting for it to complete.");
    IsAeInvAlreadyRunning = 1;
    v13 = 0;
    while ( IsAeInvAlreadyRunning )
    {
      Sleep(0x64u);
      wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &v168,
        0);
      IsAeInvAlreadyRunning = Utility::IsAeInvAlreadyRunning(&v168);
      if ( (unsigned int)++v13 >= 0xBB8 )
      {
        if ( IsAeInvAlreadyRunning )
          AslLogCallPrintf(
            1,
            (unsigned int)"GetAppInventory",
            128,
            (unsigned int)"Inventory still hasn't completed. Continuing [0x%08x]");
        break;
      }
    }
  }
  Windows::Compat::Shared::Telemetry::TelemetryProvider::InitializeCoreProvider(v11, *((_DWORD *)a2 + 5) == 1);
  Windows::Compat::Shared::Telemetry::TelemetryProvider::ExtendCv(v14, a3);
  v15 = *((_DWORD *)a2 + 2);
  v16 = v15 != 0;
  v17 = *((_DWORD *)a2 + 3);
  LOBYTE(v169) = v17 != 0;
  if ( (v6 & 8) != 0 )
    GetInvModuleVersion(a1);
  memset_0(v197, 0, 0x4Eu);
  v199 = 0;
  v200 = 0;
  v201 = 0;
  v202 = 0;
  v203 = 0;
  v204 = 0;
  v198 = 0;
  v196 = 0;
  memset_0(v225, 0, 0x4Eu);
  v227 = 0;
  v228 = 0;
  v229 = 0;
  v230 = 0;
  v231 = 0;
  v232 = 0;
  v226 = 0;
  v224 = 0;
  memset_0(v216, 0, 0x4Eu);
  v218 = 0;
  v219 = 0;
  v220 = 0;
  v221 = 0;
  v222 = 0;
  v223 = 0;
  v217 = 0;
  v215 = 0;
  memset_0(v207, 0, 0x4Eu);
  v209 = 0;
  v210 = 0;
  v211 = 0;
  v212 = 0;
  v213 = 0;
  v214 = 0;
  v208 = 0;
  v206 = 0;
  if ( (v6 & 0x10000000) != 0 )
    goto LABEL_55;
  v170 = (File *)operator new(0x3F0u);
  v18 = Application::Application(v170);
  v19 = &Application::ApplicationCacheProviderName;
  if ( (unsigned __int64)qword_180182A38 > 7 )
    v19 = (__int64 *)Application::ApplicationCacheProviderName;
  v20 = TelCacheProvider::Initialize(&v196, v19, v18, 0, 2, 5, 500);
  if ( v20 < 0 )
  {
    AslLogCallPrintf(1, (unsigned int)"GetAppInventory", 154, (unsigned int)"[%#x]");
    TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v206);
    TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v215);
    TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v224);
    TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v196);
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v168);
    return (unsigned int)v20;
  }
  v170 = (File *)operator new(0x330u);
  v21 = File::File(v170);
  if ( v21 )
    v22 = (char *)v21 + 8;
  else
    v22 = 0;
  v23 = &File::FileCacheProviderName;
  if ( (unsigned __int64)qword_180183038 > 7 )
    v23 = (__int64 *)File::FileCacheProviderName;
  v24 = TelCacheProvider::Initialize(&v224, v23, v22, 0, 2, 5, 500);
  if ( v24 < 0 )
  {
    AslLogCallPrintf(1, (unsigned int)"GetAppInventory", 155, (unsigned int)"[%#x]");
    TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v206);
    TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v215);
    TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v224);
    TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v196);
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v168);
    return (unsigned int)v24;
  }
  v170 = (File *)operator new(0x90u);
  v25 = AmiFrameworkItem::AmiFrameworkItem(v170);
  v26 = &AmiFrameworkItem::ApplicationFrameworkCacheProviderName;
  if ( (unsigned __int64)qword_180183278 > 7 )
    v26 = (__int64 *)AmiFrameworkItem::ApplicationFrameworkCacheProviderName;
  v27 = TelCacheProvider::Initialize(&v215, v26, v25, 0, 2, 5, 500);
  if ( v27 < 0 )
  {
    AslLogCallPrintf(1, (unsigned int)"GetAppInventory", 157, (unsigned int)"[%#x]");
    TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v206);
    TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v215);
    TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v224);
    TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v196);
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v168);
    return (unsigned int)v27;
  }
  v28 = (AmiShortcutItem *)operator new(0xA8u);
  v29 = AmiShortcutItem::AmiShortcutItem(v28);
  v30 = &AmiShortcutItem::ShortcutCacheProviderName;
  if ( (unsigned __int64)qword_180183338 > 7 )
    v30 = (__int64 *)AmiShortcutItem::ShortcutCacheProviderName;
  v31 = TelCacheProvider::Initialize(&v206, v30, v29, 0, 2, 5, 500);
  if ( v31 < 0 )
  {
    AslLogCallPrintf(1, (unsigned int)"GetAppInventory", 158, (unsigned int)"[%#x]");
    TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v206);
    TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v215);
    TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v224);
    TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v196);
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v168);
    return (unsigned int)v31;
  }
  if ( v15 )
  {
    v32 = TelCacheProvider::ClearData((TelCacheProvider *)&v196);
    if ( v32 < 0 )
    {
      AslLogCallPrintf(1, (unsigned int)"GetAppInventory", 163, (unsigned int)"[%#x]");
      TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v206);
      TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v215);
      TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v224);
      TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v196);
      wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v168);
      return (unsigned int)v32;
    }
    if ( v17 )
    {
      v33 = TelCacheProvider::ClearData((TelCacheProvider *)&v215);
      if ( v33 < 0 )
      {
        AslLogCallPrintf(1, (unsigned int)"GetAppInventory", 168, (unsigned int)"[%#x]");
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v206);
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v215);
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v224);
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v196);
        wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v168);
        return (unsigned int)v33;
      }
      v34 = TelCacheProvider::ClearData((TelCacheProvider *)&v206);
      if ( v34 < 0 )
      {
        AslLogCallPrintf(1, (unsigned int)"GetAppInventory", 169, (unsigned int)"[%#x]");
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v206);
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v215);
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v224);
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v196);
        wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v168);
        return (unsigned int)v34;
      }
      goto LABEL_55;
    }
  }
  else if ( v17 )
  {
LABEL_55:
    v35 = v166;
    goto LABEL_56;
  }
  if ( (unsigned int)IsInventoryCacheFresh((struct TelCacheProvider *)&v196) )
    goto LABEL_55;
  Application::Application((Application *)v258);
  File::File((File *)v238);
  AmiFrameworkItem::AmiFrameworkItem((AmiFrameworkItem *)v247);
  v35 = v166;
  v36 = v178;
  if ( !(unsigned int)ReturnCachedInventoryItems<Application>(v178, &v196, v258, v166)
    && !(unsigned int)ReturnCachedInventoryItems<File>(v36, &v224, v238, v166)
    && !(unsigned int)ReturnCachedInventoryItems<Application>(v36, &v215, v247, v166) )
  {
    AslLogCallPrintf(3, (unsigned int)"GetAppInventory", 188, (unsigned int)"Skipping scan, returning cached inventory");
    AmiFrameworkItem::~AmiFrameworkItem((AmiFrameworkItem *)v247);
    File::~File((File *)v238);
    Application::~Application((Application *)v258);
    TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v206);
    TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v215);
    TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v224);
    TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v196);
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v168);
    return 0;
  }
  (**(void (__fastcall ***)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *))v36)(
    v36,
    L"DISCARD_AND_RESET_ASSETS");
  if ( (v6 & 8) != 0 )
    GetInvModuleVersion(v36);
  AmiFrameworkItem::~AmiFrameworkItem((AmiFrameworkItem *)v247);
  File::~File((File *)v238);
  Application::~Application((Application *)v258);
LABEL_56:
  AslLogCallPrintf(3, (unsigned int)"GetAppInventory", 202, (unsigned int)"Performing application scan");
  v174 = -2147221008;
  v173 = -2147221008;
  if ( IsWindowsVersionOrGreater(6u, 2u, v37) )
  {
    v40 = Common::AutoWinRTInitialize::Initialize(&v174);
    if ( v40 < 0 )
    {
      AslLogCallPrintf(1, (unsigned int)"GetAppInventory", 215, (unsigned int)"[%#x]");
      Common::AutoCoInitialize::~AutoCoInitialize((Common::AutoCoInitialize *)&v173);
      Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v174);
      TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v206);
      TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v215);
      TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v224);
      TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v196);
      wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v168);
      return (unsigned int)v40;
    }
  }
  else
  {
    v39 = Common::AutoCoInitialize::Initialize((Common::AutoCoInitialize *)&v173, v38);
    if ( v39 < 0 )
    {
      AslLogCallPrintf(1, (unsigned int)"GetAppInventory", 210, (unsigned int)"[%#x]");
      Common::AutoCoInitialize::~AutoCoInitialize((Common::AutoCoInitialize *)&v173);
      Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v174);
      TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v206);
      TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v215);
      TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v224);
      TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v196);
      wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v168);
      return (unsigned int)v39;
    }
  }
  std::wstring::wstring(v233, &byte_1801389F0);
  std::wstring::wstring(v205, &byte_1801389F0);
  std::wstring::wstring(v193, &byte_1801389F0);
  std::wstring::wstring(v188, &byte_1801389F0);
  std::wstring::wstring(v191, &byte_1801389F0);
  ConfigSettings::ConfigSettings(
    (unsigned int)v234,
    (v35 & 0x20000000) != 0 ? 5 : 0,
    (unsigned int)&v196,
    (unsigned int)&v224,
    v169,
    v16,
    3,
    (__int64)v191,
    (__int64)v188,
    (__int64)v193,
    (__int64)v205,
    (__int64)v233,
    0);
  std::wstring::~wstring(v191);
  std::wstring::~wstring(v188);
  std::wstring::~wstring(v193);
  std::wstring::~wstring(v205);
  std::wstring::~wstring(v233);
  *(_OWORD *)v175 = 0;
  v176 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_Performance>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppInv_Performance>::GetImpl'::`2'::impl) )
    std::vector<Application>::reserve(v175, 200);
  v236 = &v206;
  v237 = &v215;
  if ( (v35 & 0xF0000) != 0xF0000 || (v6 & 0x10000000) != 0 )
  {
    v41 = 0;
  }
  else
  {
    v41 = 1;
    v42 = TelCacheProvider::BatchBegin((TelCacheProvider *)&v196);
    if ( v42 < 0 )
    {
      v161[0] = v42;
      AslLogCallPrintf(1, (unsigned int)"GetAppInventory", 266, (unsigned int)"BatchBegin failed: [0x%08x]");
    }
  }
  Utility::InitializeWatchdogTimer();
  if ( (v35 & 0x20000) != 0 )
  {
    v170 = (File *)&StoreAppFinder::`vftable';
    StoreAppFinder::EnumeratePackages(v234, v175);
  }
  if ( (v35 & 0x10000) != 0 )
  {
    Utility::KickWatchdogTimer();
    if ( Utility::IsCrmWindowClosed )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x120,
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\GetAppInventory.cpp",
        (const char *)0x80004004LL,
        v161[0]);
    v170 = (File *)&StoreAppFinder::`vftable';
    AppvAppFinder::EnumeratePackages(v234, v175);
  }
  if ( (v35 & 0x40000) != 0 )
  {
    v170 = (File *)&StoreAppFinder::`vftable';
    ArpAppFinder::GetEvidenceFromAllArpEntries(v234, v175);
  }
  if ( (v35 & 0x80000) != 0 )
  {
    Utility::KickWatchdogTimer();
    if ( Utility::IsCrmWindowClosed )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x136,
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\GetAppInventory.cpp",
        (const char *)0x80004004LL,
        v161[0]);
    v170 = (File *)&StoreAppFinder::`vftable';
    AppPlatformFinder::GetEvidence(v234, v175);
  }
  if ( (v35 & 2) != 0 )
  {
    Utility::KickWatchdogTimer();
    if ( Utility::IsCrmWindowClosed )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x145,
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\GetAppInventory.cpp",
        (const char *)0x80004004LL,
        v161[0]);
    OrphanFileFinder::GetEvidence((struct ConfigSettings *)v234);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_Performance>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppInv_Performance>::GetImpl'::`2'::impl) )
      Bucketizer::BucketizeOrphanFiles2((const struct ConfigSettings *)v234);
    else
      Bucketizer::BucketizeOrphanFiles((const struct ConfigSettings *)v234);
  }
  std::set<std::wstring>::set<std::wstring>(v186);
  if ( v41 )
  {
    Application::Application((Application *)v238);
    LoadedUserHiveSids = Utility::GetLoadedUserHiveSids(v43);
    std::vector<std::wstring>::vector<std::wstring>(v191, LoadedUserHiveSids);
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_Performance>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppInv_Performance>::GetImpl'::`2'::impl);
    v46 = v191[0];
    v47 = v191[1];
    if ( IsEnabled )
    {
      while ( v46 != v47 )
      {
        if ( *((_QWORD *)v46 + 3) <= 7u )
          v48 = v46;
        else
          v48 = *(File **)v46;
        *(_QWORD *)v161 = v48;
        AslLogCallPrintf(3, (unsigned int)"GetAppInventory", 357, (unsigned int)"Loaded user hive SID: %ws");
        v46 = (File *)((char *)v46 + 32);
      }
    }
    else
    {
      while ( v46 != v47 )
      {
        std::wstring::wstring(v188, v46);
        v49 = v188;
        if ( v190 > 7 )
          v49 = (_QWORD *)v188[0];
        *(_QWORD *)v161 = v49;
        AslLogCallPrintf(3, (unsigned int)"GetAppInventory", 364, (unsigned int)"Loaded user hive SID: %ws");
        std::wstring::~wstring(v188);
        v46 = (File *)((char *)v46 + 32);
      }
    }
    FirstItem = TelCacheProvider::GetFirstItem(v235, (struct IAmiInventoryItem *)v238);
    while ( FirstItem >= 0 )
    {
      Utility::GetUserSidFromArpKeyPath(v188, v246);
      if ( v189 )
      {
        v51 = (wchar_t *)v245;
        if ( v245[3] > (wchar_t *)7 )
          v51 = v245[0];
        if ( Application::IsWin32App(v51) )
        {
          v52 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_Performance>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppInv_Performance>::GetImpl'::`2'::impl);
          v53 = v191[0];
          v54 = v191[1];
          if ( v52 )
          {
            while ( v53 != v54 )
            {
              if ( *((_QWORD *)v53 + 3) <= 7u )
                v55 = v53;
              else
                v55 = *(File **)v53;
              v56 = v188;
              if ( v190 > 7 )
                v56 = (_QWORD *)v188[0];
              if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                                      v56,
                                      v189,
                                      v55,
                                      *((_QWORD *)v53 + 2),
                                      *(_QWORD *)v161,
                                      v163,
                                      v164,
                                      v165) )
              {
                v57 = v241;
                if ( v242 > 7 )
                  v57 = (_QWORD *)v241[0];
                if ( *((_QWORD *)v53 + 3) > 7u )
                  v53 = *(File **)v53;
                v58 = v188;
                if ( v190 > 7 )
                  v58 = (_QWORD *)v188[0];
                v164 = v57;
                v163 = v53;
                *(_QWORD *)v161 = v58;
                AslLogCallPrintf(
                  3,
                  (unsigned int)"GetAppInventory",
                  387,
                  (unsigned int)"Per-user app: User hive loaded: appUserSid: %ws loadedUserHiveSid: %ws AppName: %ws");
                goto LABEL_139;
              }
              v53 = (File *)((char *)v53 + 32);
            }
          }
          else
          {
            while ( v53 != v54 )
            {
              std::wstring::wstring(v193, v53);
              v59 = v193;
              if ( v194 > 7 )
                v59 = (_QWORD *)v193[0];
              v60 = v188;
              if ( v190 > 7 )
                v60 = (_QWORD *)v188[0];
              if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                                      v60,
                                      v189,
                                      v59,
                                      v193[2],
                                      *(_QWORD *)v161,
                                      v163,
                                      v164,
                                      v165) )
              {
                v61 = v241;
                if ( v242 > 7 )
                  v61 = (_QWORD *)v241[0];
                v62 = (File *)v193;
                if ( v194 > 7 )
                  v62 = (File *)v193[0];
                v63 = v188;
                if ( v190 > 7 )
                  v63 = (_QWORD *)v188[0];
                v164 = v61;
                v163 = v62;
                *(_QWORD *)v161 = v63;
                AslLogCallPrintf(
                  3,
                  (unsigned int)"GetAppInventory",
                  403,
                  (unsigned int)"Per-user app: User hive loaded: appUserSid: %ws loadedUserHiveSid: %ws AppName: %ws");
                std::wstring::~wstring(v193);
                goto LABEL_139;
              }
              std::wstring::~wstring(v193);
              v53 = (File *)((char *)v53 + 32);
            }
          }
          Application::GetApplicationFromCache((struct IAmiInventoryItem *)v238);
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
            v186,
            v185,
            v239);
          v64 = v188;
          if ( v190 > 7 )
            v64 = (_QWORD *)v188[0];
          v65 = v246;
          if ( v246[3] > 7u )
            v65 = (_QWORD *)v246[0];
          v66 = (File *)v239;
          if ( v239[3] > 7u )
            v66 = (File *)v239[0];
          v67 = v241;
          if ( v242 > 7 )
            v67 = (_QWORD *)v241[0];
          v165 = v64;
          v164 = v65;
          v163 = v66;
          *(_QWORD *)v161 = v67;
          AslLogCallPrintf(
            3,
            (unsigned int)"GetAppInventory",
            423,
            (unsigned int)"Per-user app: User hive not loaded (cleared batch marker so its not removed): Name: %ws Progra"
                          "mId: %ws ArpRegistryKeyPath: %ws AppUserSid: %ws");
        }
      }
LABEL_139:
      FirstItem = TelCacheProvider::GetNextItem(v235, (struct IAmiInventoryItem *)v238);
      if ( ((FirstItem + 0x80000000) & 0x80000000) == 0 && FirstItem != -2147024637 )
      {
        v161[0] = FirstItem;
        AslLogCallPrintf(1, (unsigned int)"GetAppInventory", 430, (unsigned int)"GetNextItem failed: [0x%08x]");
      }
      std::wstring::~wstring(v188);
    }
    v68 = TelCacheProvider::BatchEnd((TelCacheProvider *)&v196);
    if ( v68 < 0 )
    {
      v161[0] = v68;
      AslLogCallPrintf(1, (unsigned int)"GetAppInventory", 438, (unsigned int)"BatchEnd failed: [0x%08x]");
    }
    std::vector<std::wstring>::_Tidy(v191);
    Application::~Application((Application *)v238);
  }
  std::set<std::wstring>::set<std::wstring>(v181);
  v69 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_Performance>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppInv_Performance>::GetImpl'::`2'::impl);
  v70 = v175[0];
  v71 = v175[1];
  if ( v69 )
  {
    while ( v70 != v71 )
    {
      v72 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v70 + 2) + 16LL))((__int64)v70 + 16);
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
        v181,
        v185,
        v72);
      v70 = (struct Application *)((char *)v70 + 1008);
    }
  }
  else
  {
    while ( v70 != v71 )
    {
      Application::Application((Application *)v258, v70);
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
        v181,
        v185,
        v259);
      Application::~Application((Application *)v258);
      v70 = (struct Application *)((char *)v70 + 1008);
    }
  }
  std::set<std::wstring>::set<std::wstring>(v179);
  *(_OWORD *)v191 = 0;
  v192 = 0;
  if ( (v35 & 0x80000022) != 0 )
  {
    v73 = 0;
    v167 = 0;
    v74 = 0;
    v171 = 0;
    v75 = 0;
    v172 = 0;
    FilesFromCache = File::GetFilesFromCache(v188, v234);
    std::vector<File>::operator=(v191, FilesFromCache);
    std::vector<File>::_Tidy(v188);
    v77 = v191[0];
    v78 = v191[0];
    v79 = v191[1];
    v180 = v191[1];
    while ( 1 )
    {
      if ( v78 == v79 )
      {
        AslTelemetryTrackMetric(qword_1801822A0, "AppInv_Num_Total_Files", 0xFAFAFAFAFAFAFAFBuLL * ((v79 - v77) >> 4));
        AslTelemetryTrackMetric(qword_1801822A0, "AppInv_Num_Orphan_Files", v73);
        AslTelemetryTrackMetric(qword_1801822A0, "AppInv_FileIdsCalculated", v74);
        AslTelemetryTrackMetric(qword_1801822A0, "AppInv_FilesMissingId", v75);
        v35 = v166;
        goto LABEL_230;
      }
      Utility::KickWatchdogTimer();
      v80 = File::Verify(v78, v234) - 1;
      if ( !v80 )
        goto LABEL_159;
      v81 = v80 - 1;
      if ( v81 )
        break;
      if ( !(*(unsigned __int8 (__fastcall **)(File *))(*(_QWORD *)v78 + 144LL))(v78)
        && !(*(unsigned __int8 (__fastcall **)(File *))(*(_QWORD *)v78 + 136LL))(v78) )
      {
        v83 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)v78 + 112LL))(v78);
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
          v179,
          v233,
          v83);
      }
      v84 = v78;
      for ( i = (File *)((char *)v78 + 816); i != v79; i = (File *)((char *)i + 816) )
      {
        File::operator=(v84, i);
        v84 = (File *)((char *)v84 + 816);
      }
      v79 = (File *)((char *)v79 - 816);
      v180 = v79;
      (**(void (__fastcall ***)(File *, _QWORD))v79)(v79, 0);
      v191[1] = v79;
      v74 = v171;
      v75 = v172;
LABEL_228:
      v77 = v191[0];
    }
    if ( v81 == 1 )
    {
      v171 = ++v74;
LABEL_159:
      if ( !(*(unsigned __int8 (__fastcall **)(File *))(*(_QWORD *)v78 + 136LL))(v78)
        && !(*(unsigned __int8 (__fastcall **)(File *))(*(_QWORD *)v78 + 144LL))(v78) )
      {
        v82 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)v78 + 112LL))(v78);
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
          v179,
          v205,
          v82);
      }
    }
    if ( !(*(unsigned __int8 (__fastcall **)(File *))(*(_QWORD *)v78 + 136LL))(v78) )
    {
      if ( (*(unsigned __int8 (__fastcall **)(File *))(*(_QWORD *)v78 + 144LL))(v78) )
      {
        v167 = ++v73;
      }
      else
      {
        v86 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)v78 + 112LL))(v78);
        v87 = (_QWORD *)std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(
                          v181,
                          v187,
                          v86);
        if ( *v87 == v181[0] )
        {
          v88 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)v78 + 112LL))(v78);
          v89 = (_QWORD *)std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(
                            v186,
                            v185,
                            v88);
          if ( *v89 == v186[0] )
          {
            v90 = 0;
            v91 = 0;
            v92 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_Performance>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppInv_Performance>::GetImpl'::`2'::impl) == 0;
            v93 = v175[1];
            v170 = v175[1];
            if ( v92 )
            {
              for ( j = v175[0]; j != v93; j = (const struct Application *)((char *)j + 1008) )
              {
                Application::Application((Application *)v238, j);
                v109 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)v78 + 24LL))(v78);
                DirectoryFromPath = Utility::GetDirectoryFromPath(v195, v109);
                found = Utility::FoundSubstring(&v243, DirectoryFromPath);
                std::wstring::~wstring(v195);
                if ( found && v244 && v244 >= v91 )
                {
                  v112 = v241;
                  if ( v242 > 7 )
                    v112 = (_QWORD *)v241[0];
                  v113 = (_QWORD *)(*(__int64 (__fastcall **)(File *))(*(_QWORD *)v78 + 112LL))(v78);
                  v114 = v113;
                  if ( v113[3] > 7u )
                    v114 = (_QWORD *)*v113;
                  v115 = (File *)(*(__int64 (__fastcall **)(File *))(*(_QWORD *)v78 + 24LL))(v78);
                  v116 = v115;
                  if ( *((_QWORD *)v115 + 3) > 7u )
                    v116 = *(File **)v115;
                  v117 = (_QWORD *)(*(__int64 (__fastcall **)(File *))(*(_QWORD *)v78 + 32LL))(v78);
                  if ( v117[3] > 7u )
                    v117 = (_QWORD *)*v117;
                  v165 = v112;
                  v164 = v114;
                  v163 = v116;
                  v161[0] = (int)v117;
                  AslLogCallPrintf(
                    3,
                    (unsigned int)"GetAppInventory",
                    570,
                    (unsigned int)"File's ProgramId no longer exist: %ws | %ws | %ws re-mapped to %ws | %ws | %ws");
                  v91 = v244;
                  std::wstring::operator=((char *)v78 + 88, v239);
                  File::SaveFileToCache(v78, (const struct ConfigSettings *)v234);
                  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
                    v179,
                    v188,
                    v239);
                  v90 = 1;
                }
                Application::~Application((Application *)v238);
                v93 = v170;
              }
            }
            else
            {
              v94 = v175[0];
              while ( 1 )
              {
                SystemTimeAsFileTime = (struct _FILETIME)v94;
                if ( v94 == v93 )
                  break;
                v95 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)v78 + 24LL))(v78);
                v96 = Utility::GetDirectoryFromPath(v195, v95);
                v97 = (char *)v94 + 16;
                v98 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v97 + 40LL))(v97);
                LOBYTE(v96) = Utility::FoundSubstring(v98, v96);
                std::wstring::~wstring(v195);
                if ( (_BYTE)v96
                  && *(_QWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v97 + 40LL))(v97) + 16)
                  && *(_QWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v97 + 40LL))(v97) + 16) >= v91 )
                {
                  (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v97 + 16LL))(v97);
                  (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v97 + 40LL))(v97);
                  v99 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v97 + 8LL))(v97);
                  v100 = v99;
                  if ( v99[3] > 7u )
                    v100 = (_QWORD *)*v99;
                  v101 = (_QWORD *)(*(__int64 (__fastcall **)(File *))(*(_QWORD *)v78 + 112LL))(v78);
                  v102 = v101;
                  if ( v101[3] > 7u )
                    v102 = (_QWORD *)*v101;
                  v103 = (File *)(*(__int64 (__fastcall **)(File *))(*(_QWORD *)v78 + 24LL))(v78);
                  v104 = v103;
                  if ( *((_QWORD *)v103 + 3) > 7u )
                    v104 = *(File **)v103;
                  v105 = (_QWORD *)(*(__int64 (__fastcall **)(File *))(*(_QWORD *)v78 + 32LL))(v78);
                  if ( v105[3] > 7u )
                    v105 = (_QWORD *)*v105;
                  v165 = v100;
                  v164 = v102;
                  v163 = v104;
                  v161[0] = (int)v105;
                  AslLogCallPrintf(
                    3,
                    (unsigned int)"GetAppInventory",
                    540,
                    (unsigned int)"File's ProgramId no longer exist: %ws | %ws | %ws re-mapped to %ws | %ws | %ws");
                  v91 = *(_QWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v97 + 40LL))(v97) + 16);
                  v106 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v97 + 16LL))(v97);
                  std::wstring::operator=((char *)v78 + 88, v106);
                  File::SaveFileToCache(v78, (const struct ConfigSettings *)v234);
                  v107 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v97 + 16LL))(v97);
                  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
                    v179,
                    v193,
                    v107);
                  v90 = 1;
                }
                v94 = (struct Application *)(*(_QWORD *)&SystemTimeAsFileTime + 1008LL);
                v93 = v170;
              }
            }
            if ( v90 )
            {
              v73 = v167;
            }
            else
            {
              v118 = (_QWORD *)(*(__int64 (__fastcall **)(File *))(*(_QWORD *)v78 + 24LL))(v78);
              v119 = v118;
              if ( v118[3] > 7u )
                v119 = (_QWORD *)*v118;
              v120 = (_QWORD *)(*(__int64 (__fastcall **)(File *))(*(_QWORD *)v78 + 16LL))(v78);
              v121 = v120;
              if ( v120[3] > 7u )
                v121 = (_QWORD *)*v120;
              v122 = (File *)(*(__int64 (__fastcall **)(File *))(*(_QWORD *)v78 + 112LL))(v78);
              v123 = v122;
              if ( *((_QWORD *)v122 + 3) > 7u )
                v123 = *(File **)v122;
              v124 = (_QWORD *)(*(__int64 (__fastcall **)(File *))(*(_QWORD *)v78 + 8LL))(v78);
              if ( v124[3] > 7u )
                v124 = (_QWORD *)*v124;
              v165 = v119;
              v164 = v121;
              v163 = v123;
              v161[0] = (int)v124;
              AslLogCallPrintf(
                3,
                (unsigned int)"GetAppInventory",
                592,
                (unsigned int)"File's ProgramId no longer exist. Calculating new orphan ProgramId. GetFilePathHash: %ls G"
                              "etProgramId: %ls GetFileId: %ls GetFilePath: %ls");
              (*(void (__fastcall **)(File *))(*(_QWORD *)v78 + 24LL))(v78);
              File::SetBoeProgramId(v78);
              File::SaveFileToCache(v78, (const struct ConfigSettings *)v234);
              v73 = ++v167;
            }
            v79 = v180;
          }
          else
          {
            v125 = (_QWORD *)(*(__int64 (__fastcall **)(File *))(*(_QWORD *)v78 + 24LL))(v78);
            v126 = v125;
            if ( v125[3] > 7u )
              v126 = (_QWORD *)*v125;
            v127 = (File *)(*(__int64 (__fastcall **)(File *))(*(_QWORD *)v78 + 16LL))(v78);
            v128 = v127;
            if ( *((_QWORD *)v127 + 3) > 7u )
              v128 = *(File **)v127;
            v129 = (_QWORD *)(*(__int64 (__fastcall **)(File *))(*(_QWORD *)v78 + 112LL))(v78);
            if ( v129[3] > 7u )
              v129 = (_QWORD *)*v129;
            v164 = v126;
            v163 = v128;
            v161[0] = (int)v129;
            AslLogCallPrintf(
              3,
              (unsigned int)"GetAppInventory",
              514,
              (unsigned int)"Per-user app file (user hive not loaded). ProgramId: %ws FileId: %ws FilePath: %ws");
          }
          v74 = v171;
          v75 = v172;
        }
      }
    }
    (*(void (__fastcall **)(__int64, struct Windows::Compat::Inventory::IInventoryDataReceiver *, _QWORD))(*((_QWORD *)v78 + 2) + 8LL))(
      (__int64)v78 + 16,
      v178,
      v166);
    if ( !*(_QWORD *)((*(__int64 (__fastcall **)(File *))(*(_QWORD *)v78 + 16LL))(v78) + 16) )
      v172 = ++v75;
    v78 = (File *)((char *)v78 + 816);
    goto LABEL_228;
  }
  v79 = v191[1];
LABEL_230:
  if ( (v35 & 0x41000011) != 0 )
  {
    v130 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_Performance>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppInv_Performance>::GetImpl'::`2'::impl) )
    {
      v131 = v175[0];
      v132 = v175[1];
      while ( v131 != v132 )
      {
        Utility::KickWatchdogTimer();
        v133 = (char *)v131 + 16;
        v134 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v131 + 2) + 16LL))((__int64)v131 + 16);
        v135 = (_QWORD *)std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(
                           v179,
                           v185,
                           v134);
        if ( *v135 != v179[0] )
        {
          std::_Tree<std::_Tset_traits<File,std::less<File>,std::allocator<File>,0>>::clear((char *)v131 + 24);
          v136 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v133 + 8LL))((__int64)v131 + 16);
          if ( v136[3] > 7u )
            v136 = (_QWORD *)*v136;
          *(_QWORD *)v161 = v136;
          AslLogCallPrintf(
            3,
            (unsigned int)"GetAppInventory",
            630,
            (unsigned int)"Updating ProgramInstanceId because of file change/removal. App:%ls");
          for ( k = v191[0]; k != v79; k = (const struct File *)((char *)k + 816) )
          {
            v138 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v133 + 16LL))((__int64)v131 + 16);
            v139 = (_QWORD *)(*(__int64 (__fastcall **)(const struct File *))(*(_QWORD *)k + 112LL))(k);
            v140 = v138[2];
            if ( v138[3] > 7u )
              v138 = (_QWORD *)*v138;
            v141 = v139[2];
            if ( v139[3] > 7u )
              v139 = (_QWORD *)*v139;
            if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                                    v139,
                                    v141,
                                    v138,
                                    v140,
                                    *(_QWORD *)v161,
                                    v163,
                                    v164,
                                    v165) )
              Application::SetFile(v131, k);
          }
          v142 = Application::ComputeProgramInstanceId(v131, v195);
          std::wstring::operator=((char *)v131 + 400, v142);
          std::wstring::~wstring(v195);
          Application::SaveApplicationToCache(v131, (const struct ConfigSettings *)v234);
          v35 = v166;
        }
        (*(void (__fastcall **)(__int64, struct Windows::Compat::Inventory::IInventoryDataReceiver *, _QWORD))(*((_QWORD *)v131 + 1) + 8LL))(
          (__int64)v131 + 8,
          v178,
          v35);
        if ( *(_QWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v133 + 80LL))((__int64)v131 + 16) + 16) )
          ++v130;
        v131 = (struct Application *)((char *)v131 + 1008);
      }
    }
    else
    {
      v143 = v175[0];
      v144 = v175[1];
      while ( v143 != v144 )
      {
        Application::Application((Application *)v247, v143);
        Utility::KickWatchdogTimer();
        v145 = (_QWORD *)std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(
                           v179,
                           v185,
                           v250);
        if ( *v145 != v179[0] )
        {
          std::_Tree<std::_Tset_traits<File,std::less<File>,std::allocator<File>,0>>::clear(v249);
          v146 = &v252;
          if ( v254 > 7 )
            v146 = v252;
          *(_QWORD *)v161 = v146;
          AslLogCallPrintf(
            3,
            (unsigned int)"GetAppInventory",
            659,
            (unsigned int)"Updating ProgramInstanceId because of file change/removal. App:%ls");
          for ( m = v191[0]; m != v79; m = (const struct File *)((char *)m + 816) )
          {
            File::File((File *)v238, m);
            v148 = v250;
            if ( v251[1] > 7u )
              v148 = (_QWORD *)v250[0];
            v149 = &v240;
            if ( v241[2] > 7u )
              v149 = v240;
            if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                                    v149,
                                    v241[1],
                                    v148,
                                    v251[0],
                                    *(_QWORD *)v161,
                                    v163,
                                    v164,
                                    v165) )
              Application::SetFile((Application *)v247, (const struct File *)v238);
            File::~File((File *)v238);
          }
          v150 = Application::ComputeProgramInstanceId(v247, v195);
          std::wstring::operator=(v256, v150);
          std::wstring::~wstring(v195);
          Application::SaveApplicationToCache((Application *)v247, (const struct ConfigSettings *)v234);
        }
        Application::ProvideInventory((Application *)v248, v178, v166);
        if ( v257 )
          ++v130;
        Application::~Application((Application *)v247);
        v143 = (const struct Application *)((char *)v143 + 1008);
      }
      v35 = v166;
    }
    AslTelemetryTrackMetric(qword_1801822A0, "AppInv_ProgramCount", 0xEFBEFBEFBEFBEFBFuLL * ((v175[1] - v175[0]) >> 4));
    AslTelemetryTrackMetric(qword_1801822A0, "AppInv_ProgramIIDCount", v130);
  }
  if ( (v35 & 0x80u) != 0 )
  {
    AmiShortcutItem::AmiShortcutItem((AmiShortcutItem *)v247);
    for ( n = TelCacheProvider::GetFirstItem((TelCacheProvider *)&v206, (struct IAmiInventoryItem *)v247);
          n >= 0;
          n = TelCacheProvider::GetNextItem((TelCacheProvider *)&v206, (struct IAmiInventoryItem *)v247) )
    {
      if ( String1[2] )
      {
        v152 = (const wchar_t *)String1;
        if ( String1[3] > (wchar_t *)7 )
          v152 = String1[0];
        if ( wcscmp_0(v152, L"0000f519feec486de87ed73cb92d3cac802400000000") )
        {
          v153 = (_QWORD *)std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(
                             v181,
                             v185,
                             String1);
          if ( *v153 == v181[0] )
          {
            AmiShortcutItem::GetItemKey((AmiShortcutItem *)v247);
            AslLogCallPrintf(
              3,
              (unsigned int)"GetAppInventory",
              697,
              (unsigned int)"Removing invalid ProgramID from AmiShortcutItem : %ws");
            v187[0] = v195;
            v154 = std::wstring::wstring(v195, &byte_1801389F0);
            v170 = (File *)v188;
            v155 = std::wstring::wstring(v188, v253);
            SystemTimeAsFileTime = (struct _FILETIME)v193;
            v156 = std::wstring::wstring(v193, v251);
            v157 = std::wstring::wstring(v205, v248);
            AmiShortcutItem::AmiShortcutItem((unsigned int)v238, v157, v156, v155, v154);
            v158 = TelCacheProvider::AddItem((TelCacheProvider *)&v206, (struct IAmiInventoryItem *)v238);
            if ( v158 < 0 )
            {
              v161[0] = v158;
              AslLogCallPrintf(1, (unsigned int)"GetAppInventory", 706, (unsigned int)"AddItem failed [%#x]");
            }
            AmiShortcutItem::~AmiShortcutItem((AmiShortcutItem *)v238);
          }
        }
      }
    }
    if ( n != -2147024637 )
    {
      v161[0] = n;
      AslLogCallPrintf(1, (unsigned int)"GetAppInventory", 713, (unsigned int)"GetNextItem failed [%#x]");
    }
    AmiShortcutItem::~AmiShortcutItem((AmiShortcutItem *)v247);
    v35 = v166;
  }
  if ( (v35 & 0x44) != 0 )
  {
    Utility::KickWatchdogTimer();
    if ( Utility::IsCrmWindowClosed )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x2D4,
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\GetAppInventory.cpp",
        (const char *)0x80004004LL,
        v161[0]);
    AmiFrameworkItem::AmiFrameworkItem((AmiFrameworkItem *)v247);
    if ( (int)ReturnCachedInventoryItems<Application>(v178, &v215, v247, v35) < 0 )
      AslLogCallPrintf(
        1,
        (unsigned int)"GetAppInventory",
        732,
        (unsigned int)"ReturnCachedInventoryItems failed: [0x%08x]");
    AmiFrameworkItem::~AmiFrameworkItem((AmiFrameworkItem *)v247);
  }
  if ( (unsigned int)EtwEventWriteNoRegistration(AE_LOG, AE_PCA_AMI_REFRESH_COMPLETE, 0, 0) )
    AslLogCallPrintf(3, (unsigned int)"GetAppInventory", 740, (unsigned int)"Failed to send ETW event [%d]");
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v159 = TelCacheProvider::SetMetadata((TelCacheProvider *)&v196, L"LastScanTime", *(_QWORD *)&SystemTimeAsFileTime);
  if ( v159 < 0 )
  {
    if ( v159 == -2147467262 )
      AslLogCallPrintf(
        3,
        (unsigned int)"SetLastInventoryScanTime",
        565,
        (unsigned int)"TelCacheProvider::SetMetadata failed [%#x]");
    else
      AslLogCallPrintf(
        1,
        (unsigned int)"SetLastInventoryScanTime",
        561,
        (unsigned int)"TelCacheProvider::SetMetadata failed [%#x]");
  }
  v162 = GetTickCount() - TickCount;
  AslLogCallPrintf(3, (unsigned int)"GetAppInventory", 749, (unsigned int)"GetAppInventory elapsed time: %d (ticks)");
  v160 = GetCurrentThread();
  QueryThreadCycleTime(v160, &v183);
  AslTelemetryTrackMetric(
    qword_1801822A0,
    "AppInv_Nightly_Cpu_0.1gCycles",
    (unsigned int)((v183 - CycleTime) / 0x5F5E100));
  AslTelemetryTrackMetric(qword_1801822A0, "AppInv_Nightly_Ms", v162);
  std::vector<File>::_Tidy(v191);
  std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(
    v179,
    v179);
  std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(
    v181,
    v181);
  std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(
    v186,
    v186);
  std::vector<Application>::_Tidy(v175);
  ConfigSettings::~ConfigSettings((ConfigSettings *)v234);
  Common::AutoCoInitialize::~AutoCoInitialize((Common::AutoCoInitialize *)&v173);
  Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v174);
  TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v206);
  TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v215);
  TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v224);
  TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v196);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v168);
  Utility::UninitializeWatchdogTimer();
  return 0;
}

```

## disassembly

```asm
0x180031a40  push    rbx
0x180031a42  push    rsi
0x180031a43  push    rdi
0x180031a44  push    r12
0x180031a46  push    r13
0x180031a48  push    r14
0x180031a4a  push    r15
0x180031a4c  mov     eax, 1E30h
0x180031a51  call    _alloca_probe
0x180031a56  sub     rsp, rax
0x180031a59  mov     [rsp+1E68h+var_1D08], 0FFFFFFFFFFFFFFFEh
0x180031a65  mov     rax, cs:__security_cookie
0x180031a6c  xor     rax, rsp
0x180031a6f  mov     [rsp+1E68h+var_48], rax
0x180031a77  mov     rsi, r8
0x180031a7a  mov     rbx, rdx
0x180031a7d  mov     r12, rcx
0x180031a80  mov     [rsp+1E68h+var_1D78], rcx
0x180031a88  call    cs:__imp_GetTickCount
0x180031a8e  mov     [rsp+1E68h+var_1D48], eax
0x180031a95  xor     r14d, r14d
0x180031a98  mov     [rsp+1E68h+CycleTime], r14
0x180031aa0  mov     [rsp+1E68h+var_1D40], r14
0x180031aa8  mov     r15d, [rbx+10h]
0x180031aac  mov     [rsp+1E68h+var_1DC8], r15d
0x180031ab4  mov     [rsp+1E68h+var_1DC0], r14
0x180031abc  test    r15d, r15d
0x180031abf  jnz     short loc_180031AD1
0x180031ac1  mov     r15d, 0F000Bh
0x180031ac7  mov     [rsp+1E68h+var_1DC8], r15d
0x180031acf  jmp     short loc_180031B31
0x180031ad1  test    r15b, 10h
0x180031ad5  jz      short loc_180031AFE
0x180031ad7  mov     [rsp+1E68h+var_1E48], 80070057h
0x180031adf  lea     r9, aRequestOfDepre; "Request of deprecated flag: GAI_FLAG_AP"...
0x180031ae6  mov     r8d, 59h ; 'Y'
0x180031aec  lea     rdx, aGetappinventor_1; "GetAppInventory"
0x180031af3  lea     ecx, [r8-58h]
0x180031af7  call    AslLogCallPrintf
0x180031afc  jmp     short loc_180031B06
0x180031afe  mov     [rsp+1E68h+var_1DC8], r15d
0x180031b06  test    r15b, 20h
0x180031b0a  jz      short loc_180031B31
0x180031b0c  mov     [rsp+1E68h+var_1E48], 80070057h
0x180031b14  lea     r9, aRequestOfDepre_0; "Request of deprecated flag: GAI_FLAG_FI"...
0x180031b1b  mov     r8d, 5Dh ; ']'
0x180031b21  lea     rdx, aGetappinventor_1; "GetAppInventory"
0x180031b28  lea     ecx, [r8-5Ch]
0x180031b2c  call    AslLogCallPrintf
0x180031b31  call    cs:__imp_GetCurrentThread
0x180031b37  mov     rcx, rax; ThreadHandle
0x180031b3a  lea     rdx, [rsp+1E68h+CycleTime]; CycleTime
0x180031b42  call    cs:__imp_QueryThreadCycleTime
0x180031b48  call    ?DownlevelThunksInitEx@@YAHPEAUTHUNKS@@K@Z; DownlevelThunksInitEx(THUNKS *,ulong)
0x180031b4d  mov     r9, rsi; char *
0x180031b50  mov     r8, rbx; struct Windows::Compat::Inventory::InventoryControlParams *
0x180031b53  mov     rdx, r12; struct Windows::Compat::Inventory::IInventoryDataReceiver *
0x180031b56  lea     rcx, aGetappinventor_1; "GetAppInventory"
0x180031b5d  call    ?GetInvInboxRedirectImpl@@YAJPEBDPEAVIInventoryDataReceiver@Inventory@Compat@Windows@@PEAUInventoryControlParams@234@0@Z; GetInvInboxRedirectImpl(char const *,Windows::Compat::Inventory::IInventoryDataReceiver *,Windows::Compat::Inventory::InventoryControlParams *,char const *)
0x180031b62  test    eax, eax
0x180031b64  jnz     short loc_180031B7A
0x180031b66  lea     rcx, [rsp+1E68h+var_1DC0]
0x180031b6e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180031b73  xor     eax, eax
0x180031b75  jmp     loc_180034016
0x180031b7a  mov     rax, [r12]
0x180031b7e  lea     rdx, aDiscardAndRese; "DISCARD_AND_RESET_ASSETS"
0x180031b85  mov     rcx, r12
0x180031b88  mov     rax, [rax]
0x180031b8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031b90  xor     edx, edx
0x180031b92  lea     rcx, [rsp+1E68h+var_1DC0]
0x180031b9a  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180031b9f  lea     rcx, [rsp+1E68h+var_1DC0]; void **
0x180031ba7  call    ?IsAeInvAlreadyRunning@Utility@@SA_NPEAPEAX@Z; Utility::IsAeInvAlreadyRunning(void * *)
0x180031bac  test    al, al
0x180031bae  jz      loc_180031C34
0x180031bb4  lea     r9, aInventoryAlrea; "Inventory already running. Waiting for "...
0x180031bbb  mov     r8d, 75h ; 'u'
0x180031bc1  lea     rdx, aGetappinventor_1; "GetAppInventory"
0x180031bc8  lea     ecx, [r8-72h]
0x180031bcc  call    AslLogCallPrintf
0x180031bd1  mov     al, 1
0x180031bd3  mov     edi, r14d
0x180031bd6  test    al, al
0x180031bd8  jz      short loc_180031C34
0x180031bda  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180031bdf  call    cs:__imp_Sleep
0x180031be5  xor     edx, edx
0x180031be7  lea     rcx, [rsp+1E68h+var_1DC0]
0x180031bef  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180031bf4  lea     rcx, [rsp+1E68h+var_1DC0]; void **
0x180031bfc  call    ?IsAeInvAlreadyRunning@Utility@@SA_NPEAPEAX@Z; Utility::IsAeInvAlreadyRunning(void * *)
0x180031c01  inc     edi
0x180031c03  cmp     edi, 0BB8h
0x180031c09  jb      short loc_180031BD6
0x180031c0b  test    al, al
0x180031c0d  jz      short loc_180031C34
0x180031c0f  mov     [rsp+1E68h+var_1E48], 800700AAh
0x180031c17  lea     r9, aInventoryStill; "Inventory still hasn't completed. Conti"...
0x180031c1e  mov     r8d, 80h
0x180031c24  lea     rdx, aGetappinventor_1; "GetAppInventory"
0x180031c2b  lea     ecx, [r8-7Fh]
0x180031c2f  call    AslLogCallPrintf
0x180031c34  cmp     dword ptr [rbx+14h], 1
0x180031c38  setz    dl; bool
0x180031c3b  call    ?InitializeCoreProvider@TelemetryProvider@Telemetry@Shared@Compat@Windows@@IEAAX_N@Z; Windows::Compat::Shared::Telemetry::TelemetryProvider::InitializeCoreProvider(bool)
0x180031c40  mov     rdx, rsi; char *
0x180031c43  call    ?ExtendCv@TelemetryProvider@Telemetry@Shared@Compat@Windows@@QEAAXPEBD@Z; Windows::Compat::Shared::Telemetry::TelemetryProvider::ExtendCv(char const *)
0x180031c48  mov     esi, [rbx+8]
0x180031c4b  test    esi, esi
0x180031c4d  setnz   r13b
0x180031c51  mov     edi, [rbx+0Ch]
0x180031c54  test    edi, edi
0x180031c56  setnz   byte ptr [rsp+1E68h+var_1DB8]
0x180031c5e  mov     r14d, r15d
0x180031c61  and     r14d, 8
0x180031c65  jz      short loc_180031C6F
0x180031c67  mov     rcx, r12; struct Windows::Compat::Inventory::IInventoryDataReceiver *
0x180031c6a  call    ?GetInvModuleVersion@@YAJPEAVIInventoryDataReceiver@Inventory@Compat@Windows@@@Z; GetInvModuleVersion(Windows::Compat::Inventory::IInventoryDataReceiver *)
0x180031c6f  mov     ebx, 4Eh ; 'N'
0x180031c74  mov     r8d, ebx; Size
0x180031c77  xor     edx, edx; Val
0x180031c79  lea     rcx, [rsp+1E68h+var_1B90]; void *
0x180031c81  call    memset_0
0x180031c86  xor     r12d, r12d
0x180031c89  mov     [rsp+1E68h+var_1B38], r12w
0x180031c92  mov     [rsp+1E68h+var_1B30], r12
0x180031c9a  xorps   xmm0, xmm0
0x180031c9d  movdqa  [rsp+1E68h+var_1B28], xmm0
0x180031ca6  mov     [rsp+1E68h+var_1B18], r12
0x180031cae  mov     [rsp+1E68h+var_1B10], r12d
0x180031cb6  mov     [rsp+1E68h+var_1B0C], r12b
0x180031cbe  mov     [rsp+1E68h+var_1B40], r12
0x180031cc6  mov     [rsp+1E68h+var_1B98], r12
0x180031cce  mov     r8d, ebx; Size
0x180031cd1  xor     edx, edx; Val
0x180031cd3  lea     rcx, [rsp+1E68h+var_19C0]; void *
0x180031cdb  call    memset_0
0x180031ce0  mov     [rsp+1E68h+var_1968], r12w
0x180031ce9  mov     [rsp+1E68h+var_1960], r12
0x180031cf1  xorps   xmm0, xmm0
0x180031cf4  movdqa  [rsp+1E68h+var_1958], xmm0
0x180031cfd  mov     [rsp+1E68h+var_1948], r12
0x180031d05  mov     [rsp+1E68h+var_1940], r12d
0x180031d0d  mov     [rsp+1E68h+var_193C], r12b
0x180031d15  mov     [rsp+1E68h+var_1970], r12
0x180031d1d  mov     [rsp+1E68h+var_19C8], r12
0x180031d25  mov     r8d, ebx; Size
0x180031d28  xor     edx, edx; Val
0x180031d2a  lea     rcx, [rsp+1E68h+var_1A50]; void *
0x180031d32  call    memset_0
0x180031d37  mov     [rsp+1E68h+var_19F8], r12w
0x180031d40  mov     [rsp+1E68h+var_19F0], r12
0x180031d48  xorps   xmm0, xmm0
0x180031d4b  movdqa  [rsp+1E68h+var_19E8], xmm0
0x180031d54  mov     [rsp+1E68h+var_19D8], r12
0x180031d5c  mov     [rsp+1E68h+var_19D0], r12d
0x180031d64  mov     [rsp+1E68h+var_19CC], r12b
0x180031d6c  mov     [rsp+1E68h+var_1A00], r12
0x180031d74  mov     [rsp+1E68h+var_1A58], r12
0x180031d7c  mov     r8d, ebx; Size
0x180031d7f  xor     edx, edx; Val
0x180031d81  lea     rcx, [rsp+1E68h+var_1AE0]; void *
0x180031d89  call    memset_0
0x180031d8e  mov     [rsp+1E68h+var_1A88], r12w
0x180031d97  mov     [rsp+1E68h+var_1A80], r12
0x180031d9f  xorps   xmm0, xmm0
0x180031da2  movdqa  [rsp+1E68h+var_1A78], xmm0
0x180031dab  mov     [rsp+1E68h+var_1A68], r12
0x180031db3  mov     [rsp+1E68h+var_1A60], r12d
0x180031dbb  mov     [rsp+1E68h+var_1A5C], r12b
0x180031dc3  mov     [rsp+1E68h+var_1A90], r12
0x180031dcb  mov     [rsp+1E68h+var_1AE8], r12
0x180031dd3  mov     eax, r15d
0x180031dd6  and     eax, 10000000h
0x180031ddb  mov     [rsp+1E68h+var_1DC4], eax
0x180031de2  jnz     loc_18003245B
0x180031de8  mov     ecx, 3F0h; Size
0x180031ded  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031df2  mov     [rsp+1E68h+var_1DB0], rax
0x180031dfa  mov     rcx, rax; this
0x180031dfd  call    ??0Application@@QEAA@XZ; Application::Application(void)
0x180031e02  nop
0x180031e03  lea     rdx, ?ApplicationCacheProviderName@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ApplicationCacheProviderName
0x180031e0a  cmp     cs:qword_180182A38, 7
0x180031e12  cmova   rdx, cs:?ApplicationCacheProviderName@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ApplicationCacheProviderName
0x180031e1a  mov     dword ptr [rsp+1E68h+var_1E38], 1F4h
0x180031e22  lea     r15d, [rbx-49h]
0x180031e26  mov     dword ptr [rsp+1E68h+var_1E40], r15d
0x180031e2b  lea     r12d, [rbx-4Ch]
0x180031e2f  mov     [rsp+1E68h+var_1E48], r12d
0x180031e34  xor     r9d, r9d
0x180031e37  mov     r8, rax
0x180031e3a  lea     rcx, [rsp+1E68h+var_1B98]
0x180031e42  call    ?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z; TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)
0x180031e47  mov     ebx, eax
0x180031e49  test    eax, eax
0x180031e4b  jns     short loc_180031EBB
0x180031e4d  mov     [rsp+1E68h+var_1E48], eax
0x180031e51  lea     r9, asc_18013E640; "[%#x]"
0x180031e58  mov     r8d, 9Ah
0x180031e5e  lea     rdx, aGetappinventor_1; "GetAppInventory"
0x180031e65  lea     ecx, [r15-4]
0x180031e69  call    AslLogCallPrintf
0x180031e6e  nop
0x180031e6f  lea     rcx, [rsp+1E68h+var_1AE8]; this
0x180031e77  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180031e7c  nop
0x180031e7d  lea     rcx, [rsp+1E68h+var_1A58]; this
0x180031e85  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180031e8a  nop
0x180031e8b  lea     rcx, [rsp+1E68h+var_19C8]; this
0x180031e93  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180031e98  nop
0x180031e99  lea     rcx, [rsp+1E68h+var_1B98]; this
0x180031ea1  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180031ea6  nop
0x180031ea7  lea     rcx, [rsp+1E68h+var_1DC0]
0x180031eaf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180031eb4  mov     eax, ebx
0x180031eb6  jmp     loc_180034016
0x180031ebb  mov     ecx, 330h; Size
0x180031ec0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031ec5  mov     [rsp+1E68h+var_1DB0], rax
0x180031ecd  mov     rcx, rax; this
0x180031ed0  call    ??0File@@QEAA@XZ; File::File(void)
0x180031ed5  nop
0x180031ed6  test    rax, rax
0x180031ed9  jz      short loc_180031EE1
0x180031edb  lea     r8, [rax+8]
0x180031edf  jmp     short loc_180031EE4
0x180031ee1  xor     r8d, r8d
0x180031ee4  lea     rdx, ?FileCacheProviderName@File@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::FileCacheProviderName
0x180031eeb  cmp     cs:qword_180183038, 7
0x180031ef3  cmova   rdx, cs:?FileCacheProviderName@File@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::FileCacheProviderName
0x180031efb  mov     dword ptr [rsp+1E68h+var_1E38], 1F4h
0x180031f03  mov     dword ptr [rsp+1E68h+var_1E40], r15d
0x180031f08  mov     [rsp+1E68h+var_1E48], r12d
0x180031f0d  xor     r9d, r9d
0x180031f10  lea     rcx, [rsp+1E68h+var_19C8]
0x180031f18  call    ?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z; TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)
0x180031f1d  mov     ebx, eax
0x180031f1f  test    eax, eax
0x180031f21  jns     short loc_180031F92
0x180031f23  mov     [rsp+1E68h+var_1E48], eax
0x180031f27  lea     r9, asc_18013E640; "[%#x]"
0x180031f2e  mov     r8d, 9Bh
0x180031f34  lea     rdx, aGetappinventor_1; "GetAppInventory"
0x180031f3b  mov     ecx, 1
0x180031f40  call    AslLogCallPrintf
0x180031f45  nop
0x180031f46  lea     rcx, [rsp+1E68h+var_1AE8]; this
0x180031f4e  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180031f53  nop
0x180031f54  lea     rcx, [rsp+1E68h+var_1A58]; this
0x180031f5c  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180031f61  nop
0x180031f62  lea     rcx, [rsp+1E68h+var_19C8]; this
0x180031f6a  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180031f6f  nop
0x180031f70  lea     rcx, [rsp+1E68h+var_1B98]; this
0x180031f78  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x180031f7d  nop
0x180031f7e  lea     rcx, [rsp+1E68h+var_1DC0]
0x180031f86  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180031f8b  mov     eax, ebx
0x180031f8d  jmp     loc_180034016
0x180031f92  mov     ecx, 90h; Size
0x180031f97  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031f9c  mov     [rsp+1E68h+var_1DB0], rax
0x180031fa4  mov     rcx, rax; this
0x180031fa7  call    ??0AmiFrameworkItem@@QEAA@XZ; AmiFrameworkItem::AmiFrameworkItem(void)
0x180031fac  nop
0x180031fad  lea     rdx, ?ApplicationFrameworkCacheProviderName@AmiFrameworkItem@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring AmiFrameworkItem::ApplicationFrameworkCacheProviderName
0x180031fb4  cmp     cs:qword_180183278, 7
0x180031fbc  cmova   rdx, cs:?ApplicationFrameworkCacheProviderName@AmiFrameworkItem@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring AmiFrameworkItem::ApplicationFrameworkCacheProviderName
0x180031fc4  mov     dword ptr [rsp+1E68h+var_1E38], 1F4h
0x180031fcc  mov     dword ptr [rsp+1E68h+var_1E40], r15d
0x180031fd1  mov     [rsp+1E68h+var_1E48], r12d
0x180031fd6  xor     r9d, r9d
0x180031fd9  mov     r8, rax
0x180031fdc  lea     rcx, [rsp+1E68h+var_1A58]
0x180031fe4  call    ?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z; TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)
0x180031fe9  mov     ebx, eax
0x180031feb  test    eax, eax
0x180031fed  jns     short loc_18003205E
0x180031fef  mov     [rsp+1E68h+var_1E48], eax
0x180031ff3  lea     r9, asc_18013E640; "[%#x]"
0x180031ffa  mov     r8d, 9Dh
0x180032000  lea     rdx, aGetappinventor_1; "GetAppInventory"
0x180032007  mov     ecx, 1
0x18003200c  call    AslLogCallPrintf
0x180032011  nop
0x180032012  lea     rcx, [rsp+1E68h+var_1AE8]; this
0x18003201a  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x18003201f  nop
0x180032020  lea     rcx, [rsp+1E68h+var_1A58]; this
0x180032028  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x18003202d  nop
  ... truncated ...
```
