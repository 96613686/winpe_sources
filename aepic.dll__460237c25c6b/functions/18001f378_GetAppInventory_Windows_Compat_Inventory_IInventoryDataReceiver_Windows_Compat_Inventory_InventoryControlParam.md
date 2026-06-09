# GetAppInventory(Windows::Compat::Inventory::IInventoryDataReceiver *,Windows::Compat::Inventory::InventoryControlParams *,char const *)

- ea: `0x18001f378`
- end: `0x180021034`
- name: `?GetAppInventory@@YAJPEAVIInventoryDataReceiver@Inventory@Compat@Windows@@PEAUInventoryControlParams@234@PEBD@Z`
- size: `7356`
- prototype: `__int64 __fastcall(struct Windows::Compat::Inventory::IInventoryDataReceiver *, struct Windows::Compat::Inventory::InventoryControlParams *, const char *)`
- caller_count: `1`
- callee_count: `71`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180021040`

## callees

- `0x180005890`
- `0x180006040`
- `0x180006938`
- `0x18000f0bc`
- `0x18000faac`
- `0x18000faf0`
- `0x18001084c`
- `0x180015cf0`
- `0x18001c5f0`
- `0x18001d448`
- `0x18001d4ec`
- `0x18001d988`
- `0x18001daec`
- `0x18001de0c`
- `0x18001deb4`
- `0x18001df20`
- `0x18001df50`
- `0x18001df8c`
- `0x18001e464`
- `0x18001e510`
- `0x18001e93c`
- `0x18001eab4`
- `0x18001f038`
- `0x18001f318`
- `0x18001f378`
- `0x1800211ec`
- `0x1800213c0`
- `0x180021530`
- `0x18002156c`
- `0x18002174c`
- `0x18002248c`
- `0x1800224dc`
- `0x180022544`
- `0x180022580`
- `0x180022610`
- `0x180022668`
- `0x1800295dc`
- `0x18002c680`
- `0x1800c2404`
- `0x1800c2d74`
- `0x1800c3280`
- `0x1800c3478`
- `0x1800c34a8`
- `0x1800c43c0`
- `0x1800c7f00`
- `0x1800c8f6c`
- `0x1800c9400`
- `0x1800ca9c4`
- `0x1800cc8cc`
- `0x1800cce68`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f45d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180020ea3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f45d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180020ea3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001f3b4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180020e72`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001f3b4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180020e72`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001f4bc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001f4bc`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x18001f46e`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x180020eb4`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x18001f46e`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x180020eb4`

## string_xrefs

- `0x18001f491`: `Inventory already running. Waiting for it to complete.`
- `0x18001f4ff`: `Inventory still hasn't completed. Continuing [0x%08x]`
- `0x18001f898`: `Skipping scan, returning cached inventory`
- `0x18001fc3b`: `Loaded user hive SID: %ws`
- `0x18001fc90`: `Loaded user hive SID: %ws`
- `0x18001fde3`: `Per-user app: User hive loaded: appUserSid: %ws loadedUserHiveSid: %ws AppName: %ws`
- `0x18001fed3`: `Per-user app: User hive loaded: appUserSid: %ws loadedUserHiveSid: %ws AppName: %ws`
- `0x18001ffcc`: `Per-user app: User hive not loaded (cleared batch marker so its not removed): Name: %ws ProgramId: %ws ArpRegistryKeyPath: %ws AppUserSid: %ws`
- `0x1800209db`: `Per-user app file (user hive not loaded). ProgramId: %ws FileId: %ws FilePath: %ws`
- `0x18002091b`: `File's ProgramId no longer exist. Calculating new orphan ProgramId. GetFilePathHash: %ls GetProgramId: %ls GetFileId: %ls GetFilePath: %ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=40 #try_helpers=1
__int64 __fastcall GetAppInventory(
        struct Windows::Compat::Inventory::IInventoryDataReceiver *a1,
        struct Windows::Compat::Inventory::InventoryControlParams *a2,
        const char *a3)
{
  struct Windows::Compat::Inventory::IInventoryDataReceiver *v5; // rbx
  int v6; // r15d
  HANDLE CurrentThread; // rax
  Windows::Compat::Shared::Telemetry::TelemetryProvider *v8; // rcx
  bool IsAeInvAlreadyRunning; // al
  int v10; // ebx
  Windows::Compat::Shared::Telemetry::TelemetryProvider *v11; // rcx
  int v12; // esi
  int v13; // edi
  char v14; // r13
  int v15; // r14d
  int v16; // r15d
  Application *v17; // rax
  __int64 *v18; // rdx
  int v19; // eax
  unsigned int v20; // ebx
  File *v22; // rax
  char *v23; // r8
  __int64 *v24; // rdx
  int v25; // eax
  unsigned int v26; // ebx
  int v27; // eax
  unsigned int v28; // ebx
  struct Windows::Compat::Inventory::IInventoryDataReceiver *v29; // rdi
  int v30; // eax
  unsigned int v31; // ebx
  unsigned int v32; // r14d
  char v33; // di
  int v34; // eax
  unsigned __int16 v35; // r8
  __int64 LoadedUserHiveSids; // rax
  char IsEnabled; // al
  _QWORD *v38; // rbx
  _QWORD *v39; // rdi
  _QWORD *v40; // rax
  _QWORD *v41; // rax
  int FirstItem; // ebx
  wchar_t *v43; // rcx
  char v44; // al
  _QWORD *v45; // rbx
  _QWORD *v46; // rdi
  _QWORD *v47; // r8
  _QWORD *v48; // rcx
  _QWORD *v49; // rcx
  _QWORD *v50; // rax
  _QWORD *v51; // r8
  _QWORD *v52; // rcx
  _QWORD *v53; // rdx
  _QWORD *v54; // rcx
  _QWORD *v55; // rax
  _QWORD *v56; // r8
  _QWORD *v57; // rdx
  _QWORD *v58; // rcx
  _QWORD *v59; // rax
  int v60; // eax
  char v61; // al
  struct Application *v62; // rbx
  struct Application *v63; // rdi
  __int64 v64; // rax
  __int64 FilesFromCache; // rbx
  struct File *v66; // rsi
  char *v67; // r13
  unsigned int v68; // r12d
  unsigned int v69; // edi
  unsigned int v70; // r14d
  File *v71; // rbx
  int v72; // eax
  int v73; // eax
  __int64 v74; // rax
  __int64 v75; // rax
  File *v76; // rsi
  char *i; // rdi
  __int64 v78; // rax
  _QWORD *v79; // rax
  __int64 v80; // rax
  _QWORD *v81; // rax
  char v82; // r14
  unsigned __int64 v83; // r15
  bool v84; // zf
  struct Application *v85; // rax
  struct Application *v86; // rsi
  __int64 v87; // rax
  __int64 v88; // rdi
  char *v89; // rsi
  __int64 v90; // rax
  _QWORD *v91; // rax
  _QWORD *v92; // r13
  _QWORD *v93; // rax
  _QWORD *v94; // r12
  _QWORD *v95; // rax
  _QWORD *v96; // r15
  _QWORD *v97; // rax
  _QWORD *v98; // r14
  _QWORD *v99; // rax
  _QWORD *v100; // rdi
  _QWORD *v101; // rax
  __int64 v102; // rax
  __int64 v103; // rax
  const struct Application *j; // r13
  __int64 v105; // rax
  __int64 DirectoryFromPath; // rax
  char found; // di
  _QWORD *v108; // r14
  _QWORD *v109; // r15
  _QWORD *v110; // r12
  _QWORD *v111; // rax
  _QWORD *v112; // rsi
  _QWORD *v113; // rax
  _QWORD *v114; // rdi
  _QWORD *v115; // rax
  __int64 v116; // rax
  const wchar_t *v117; // r14
  __int64 v118; // rax
  const wchar_t *v119; // rsi
  __int64 v120; // rax
  const wchar_t *v121; // rdi
  __int64 v122; // rax
  _QWORD *v123; // rax
  _QWORD *v124; // rsi
  _QWORD *v125; // rax
  _QWORD *v126; // rdi
  _QWORD *v127; // rax
  unsigned int v128; // r15d
  struct Application *v129; // rbx
  struct Application *v130; // r12
  char *v131; // r14
  __int64 v132; // rax
  _QWORD *v133; // rax
  __int64 v134; // rax
  const struct File *k; // rdi
  _QWORD *v136; // rsi
  _QWORD *v137; // rax
  __int64 v138; // r9
  __int64 v139; // rdx
  __int64 v140; // rax
  const struct Application *v141; // rdi
  struct Application *v142; // rsi
  struct File *v143; // r14
  _QWORD *v144; // rax
  const wchar_t *v145; // rax
  const struct File *m; // rbx
  _QWORD *v147; // r8
  _QWORD *v148; // rcx
  __int64 v149; // rax
  DWORD v150; // ebx
  HANDLE v151; // rax
  int v152; // [rsp+30h] [rbp-1938h]
  int v153; // [rsp+A0h] [rbp-18C8h]
  unsigned int v154; // [rsp+A4h] [rbp-18C4h]
  int v155; // [rsp+A8h] [rbp-18C0h]
  HANDLE hObject; // [rsp+B0h] [rbp-18B8h] BYREF
  int v157; // [rsp+B8h] [rbp-18B0h]
  int v158; // [rsp+BCh] [rbp-18ACh] BYREF
  struct Application *v159[2]; // [rsp+C0h] [rbp-18A8h] BYREF
  __int64 v160; // [rsp+D0h] [rbp-1898h]
  struct Windows::Compat::Inventory::IInventoryDataReceiver *v161; // [rsp+D8h] [rbp-1890h]
  struct File *v162; // [rsp+E0h] [rbp-1888h]
  File *v163; // [rsp+E8h] [rbp-1880h]
  _QWORD v164[2]; // [rsp+F0h] [rbp-1878h] BYREF
  char *v165; // [rsp+100h] [rbp-1868h]
  __int128 v166; // [rsp+108h] [rbp-1860h] BYREF
  __int64 v167; // [rsp+118h] [rbp-1850h]
  DWORD TickCount; // [rsp+120h] [rbp-1848h]
  unsigned __int64 v169; // [rsp+128h] [rbp-1840h] BYREF
  unsigned __int64 CycleTime; // [rsp+130h] [rbp-1838h] BYREF
  _QWORD v171[2]; // [rsp+138h] [rbp-1830h] BYREF
  struct Application *v172; // [rsp+148h] [rbp-1820h]
  _QWORD v173[2]; // [rsp+150h] [rbp-1818h] BYREF
  char v174[240]; // [rsp+160h] [rbp-1808h] BYREF
  _QWORD v175[2]; // [rsp+250h] [rbp-1718h] BYREF
  __int64 v176; // [rsp+260h] [rbp-1708h]
  unsigned __int64 v177; // [rsp+268h] [rbp-1700h]
  _QWORD *v178; // [rsp+270h] [rbp-16F8h] BYREF
  _QWORD *v179; // [rsp+278h] [rbp-16F0h]
  _QWORD v180[3]; // [rsp+290h] [rbp-16D8h] BYREF
  unsigned __int64 v181; // [rsp+2A8h] [rbp-16C0h]
  _BYTE v182[32]; // [rsp+2B0h] [rbp-16B8h] BYREF
  _BYTE v183[32]; // [rsp+2D0h] [rbp-1698h] BYREF
  __int64 v184; // [rsp+2F0h] [rbp-1678h] BYREF
  char v185[80]; // [rsp+2F8h] [rbp-1670h] BYREF
  __int64 v186; // [rsp+348h] [rbp-1620h]
  __int16 v187; // [rsp+350h] [rbp-1618h]
  __int64 v188; // [rsp+358h] [rbp-1610h]
  __int128 v189; // [rsp+360h] [rbp-1608h]
  __int64 v190; // [rsp+370h] [rbp-15F8h]
  int v191; // [rsp+378h] [rbp-15F0h]
  char v192; // [rsp+37Ch] [rbp-15ECh]
  __int64 v193; // [rsp+390h] [rbp-15D8h] BYREF
  char v194[80]; // [rsp+398h] [rbp-15D0h] BYREF
  __int64 v195; // [rsp+3E8h] [rbp-1580h]
  __int16 v196; // [rsp+3F0h] [rbp-1578h]
  __int64 v197; // [rsp+3F8h] [rbp-1570h]
  __int128 v198; // [rsp+400h] [rbp-1568h]
  __int64 v199; // [rsp+410h] [rbp-1558h]
  int v200; // [rsp+418h] [rbp-1550h]
  char v201; // [rsp+41Ch] [rbp-154Ch]
  _BYTE v202[32]; // [rsp+420h] [rbp-1548h] BYREF
  _BYTE v203[16]; // [rsp+440h] [rbp-1528h] BYREF
  TelCacheProvider *v204; // [rsp+450h] [rbp-1518h]
  _BYTE v205[56]; // [rsp+530h] [rbp-1438h] BYREF
  _QWORD v206[4]; // [rsp+568h] [rbp-1400h] BYREF
  _QWORD *v207; // [rsp+588h] [rbp-13E0h] BYREF
  _QWORD v208[3]; // [rsp+590h] [rbp-13D8h] BYREF
  unsigned __int64 v209; // [rsp+5A8h] [rbp-13C0h]
  wchar_t *String1[12]; // [rsp+680h] [rbp-12E8h] BYREF
  _QWORD v211[72]; // [rsp+6E0h] [rbp-1288h] BYREF
  char v212[8]; // [rsp+920h] [rbp-1048h] BYREF
  char v213[16]; // [rsp+928h] [rbp-1040h] BYREF
  char v214[32]; // [rsp+938h] [rbp-1030h] BYREF
  _QWORD v215[3]; // [rsp+958h] [rbp-1010h] BYREF
  unsigned __int64 v216; // [rsp+970h] [rbp-FF8h]
  _QWORD v217[3]; // [rsp+980h] [rbp-FE8h] BYREF
  unsigned __int64 v218; // [rsp+998h] [rbp-FD0h]
  _QWORD v219[2]; // [rsp+9E0h] [rbp-F88h] BYREF
  unsigned __int64 v220; // [rsp+9F0h] [rbp-F78h]
  unsigned __int64 v221; // [rsp+9F8h] [rbp-F70h]
  char v222[16]; // [rsp+AB0h] [rbp-EB8h] BYREF
  __int64 v223; // [rsp+AC0h] [rbp-EA8h]

  v5 = a1;
  v161 = a1;
  TickCount = GetTickCount();
  CycleTime = 0;
  v169 = 0;
  v6 = *((_DWORD *)a2 + 4);
  v154 = v6;
  hObject = 0;
  if ( v6 )
  {
    if ( (v6 & 0x10) != 0 )
      AslLogCallPrintf(
        1,
        "GetAppInventory",
        89,
        "Request of deprecated flag: GAI_FLAG_APPLICATION_INFO [%#x]",
        -2147024809);
    else
      v154 = v6;
    if ( (v6 & 0x20) != 0 )
      AslLogCallPrintf(1, "GetAppInventory", 93, "Request of deprecated flag: GAI_FLAG_FILE_INFO [%#x]", -2147024809);
  }
  else
  {
    v6 = 131083;
    v154 = 131083;
  }
  CurrentThread = GetCurrentThread();
  QueryThreadCycleTime(CurrentThread, &CycleTime);
  hObject = 0;
  if ( Utility::IsAeInvAlreadyRunning(&hObject) )
  {
    AslLogCallPrintf(3, "GetAppInventory", 117, "Inventory already running. Waiting for it to complete.");
    IsAeInvAlreadyRunning = 1;
    v10 = 0;
    while ( IsAeInvAlreadyRunning )
    {
      Sleep(0x64u);
      if ( hObject )
        wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(hObject);
      hObject = 0;
      IsAeInvAlreadyRunning = Utility::IsAeInvAlreadyRunning(&hObject);
      if ( (unsigned int)++v10 >= 0xBB8 )
      {
        if ( IsAeInvAlreadyRunning )
          AslLogCallPrintf(
            1,
            "GetAppInventory",
            128,
            "Inventory still hasn't completed. Continuing [0x%08x]",
            -2147024726);
        break;
      }
    }
    v5 = v161;
  }
  Windows::Compat::Shared::Telemetry::TelemetryProvider::InitializeCoreProvider(v8, *((_DWORD *)a2 + 5) == 1);
  Windows::Compat::Shared::Telemetry::TelemetryProvider::ExtendCv(v11, a3);
  v12 = *((_DWORD *)a2 + 2);
  v13 = *((_DWORD *)a2 + 3);
  v14 = v13 != 0;
  v15 = v6 & 8;
  if ( (v6 & 8) != 0 )
    GetInvModuleVersion(v5);
  memset_0(v194, 0, 0x4Eu);
  v196 = 0;
  v197 = 0;
  v198 = 0;
  v199 = 0;
  v200 = 0;
  v201 = 0;
  v195 = 0;
  v193 = 0;
  memset_0(v185, 0, 0x4Eu);
  v187 = 0;
  v188 = 0;
  v189 = 0;
  v190 = 0;
  v191 = 0;
  v192 = 0;
  v186 = 0;
  v184 = 0;
  v16 = v6 & 0x10000000;
  if ( !v16 )
  {
    v163 = (File *)operator new(0x3F0u);
    v17 = Application::Application(v163);
    v18 = &Application::ApplicationCacheProviderName;
    if ( (unsigned __int64)qword_1801222A8 > 7 )
      v18 = (__int64 *)Application::ApplicationCacheProviderName;
    v19 = TelCacheProvider::Initialize(&v193, v18, v17, 0, 2, 5, 500);
    v20 = v19;
    if ( v19 < 0 )
    {
      AslLogCallPrintf(1, "GetAppInventory", 154, "[%#x]", v19);
      TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v184);
      TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v193);
      wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hObject);
      return v20;
    }
    v163 = (File *)operator new(0x330u);
    v22 = File::File(v163);
    if ( v22 )
      v23 = (char *)v22 + 8;
    else
      v23 = 0;
    v24 = &File::FileCacheProviderName;
    if ( (unsigned __int64)qword_180121AA8 > 7 )
      v24 = (__int64 *)File::FileCacheProviderName;
    v25 = TelCacheProvider::Initialize(&v184, v24, v23, 0, 2, 5, 500);
    v26 = v25;
    if ( v25 < 0 )
    {
      AslLogCallPrintf(1, "GetAppInventory", 155, "[%#x]", v25);
      TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v184);
      TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v193);
      wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hObject);
      return v26;
    }
    if ( v12 )
    {
      v27 = TelCacheProvider::ClearData((TelCacheProvider *)&v193);
      v28 = v27;
      if ( v27 < 0 )
      {
        AslLogCallPrintf(1, "GetAppInventory", 163, "[%#x]", v27);
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v184);
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v193);
        wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hObject);
        return v28;
      }
    }
    if ( !v13 && !(unsigned int)IsInventoryCacheFresh((struct TelCacheProvider *)&v193) )
    {
      Application::Application((Application *)v212);
      File::File((File *)v205);
      v29 = v161;
      if ( !(unsigned int)ReturnCachedInventoryItems<Application>(v161, &v193, v212, v154)
        && !(unsigned int)ReturnCachedInventoryItems<File>(v29, &v184, v205, v154) )
      {
        AslLogCallPrintf(3, "GetAppInventory", 188, "Skipping scan, returning cached inventory");
        File::~File((File *)v205);
        Application::~Application((Application *)v212);
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v184);
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v193);
        wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hObject);
        return 0;
      }
      (**(void (__fastcall ***)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *))v29)(
        v29,
        L"DISCARD_AND_RESET_ASSETS");
      if ( v15 )
        GetInvModuleVersion(v29);
      File::~File((File *)v205);
      Application::~Application((Application *)v212);
    }
  }
  AslLogCallPrintf(3, "GetAppInventory", 202, "Performing application scan");
  v158 = -2147221008;
  v30 = Common::AutoWinRTInitialize::Initialize(&v158);
  v31 = v30;
  if ( v30 < 0 )
  {
    AslLogCallPrintf(1, "GetAppInventory", 215, "[%#x]", v30);
    Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v158);
    TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v184);
    TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v193);
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hObject);
    return v31;
  }
  v32 = v154;
  std::wstring::wstring(v182, &pszFormat);
  std::wstring::wstring(v202, &pszFormat);
  std::wstring::wstring(v180, &pszFormat);
  std::wstring::wstring(v175, &pszFormat);
  std::wstring::wstring(&v178, &pszFormat);
  ConfigSettings::ConfigSettings(
    (unsigned int)v203,
    (v154 & 0x20000000) != 0 ? 5 : 0,
    (unsigned int)&v193,
    (unsigned int)&v184,
    v14,
    v12 != 0,
    v152,
    (__int64)&v178,
    (__int64)v175,
    (__int64)v180,
    (__int64)v202,
    (__int64)v182);
  std::wstring::_Tidy_deallocate(&v178);
  std::wstring::_Tidy_deallocate(v175);
  std::wstring::_Tidy_deallocate(v180);
  std::wstring::_Tidy_deallocate(v202);
  std::wstring::_Tidy_deallocate(v182);
  *(_OWORD *)v159 = 0;
  v160 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_Performance>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppInv_Performance>::GetImpl'::`2'::impl) )
    std::vector<Application>::reserve(v159);
  if ( (v154 & 0x20000) == 0 || v16 )
  {
    v33 = 0;
  }
  else
  {
    v33 = 1;
    v34 = TelCacheProvider::BatchBegin((TelCacheProvider *)&v193);
    if ( v34 < 0 )
      AslLogCallPrintf(1, "GetAppInventory", 266, "BatchBegin failed: [0x%08x]", v34);
  }
  Utility::InitializeWatchdogTimer();
  if ( (v154 & 0x20000) != 0 )
  {
    v163 = (File *)&StoreAppFinder::`vftable';
    StoreAppFinder::EnumeratePackages((__int64)v203, v159, v35);
  }
  std::set<std::wstring>::set<std::wstring>(v173);
  if ( v33 )
  {
    Application::Application((Application *)v205);
    LoadedUserHiveSids = Utility::GetLoadedUserHiveSids();
    std::vector<std::wstring>::vector<std::wstring>(&v178, LoadedUserHiveSids);
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_Performance>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppInv_Performance>::GetImpl'::`2'::impl);
    v38 = v178;
    v39 = v179;
    if ( IsEnabled )
    {
      while ( v38 != v39 )
      {
        if ( v38[3] <= 7u )
          v40 = v38;
        else
          v40 = (_QWORD *)*v38;
        AslLogCallPrintf(3, "GetAppInventory", 357, "Loaded user hive SID: %ws", v40);
        v38 += 4;
      }
    }
    else
    {
      while ( v38 != v39 )
      {
        std::wstring::wstring(v175, v38);
        v41 = v175;
        if ( v177 > 7 )
          v41 = (_QWORD *)v175[0];
        AslLogCallPrintf(3, "GetAppInventory", 364, "Loaded user hive SID: %ws", v41);
        std::wstring::_Tidy_deallocate(v175);
        v38 += 4;
      }
    }
    FirstItem = TelCacheProvider::GetFirstItem(v204, (struct IAmiInventoryItem *)v205);
    while ( FirstItem >= 0 )
    {
      Utility::GetUserSidFromArpKeyPath(v175, v211);
      if ( v176 )
      {
        v43 = (wchar_t *)String1;
        if ( String1[3] > (wchar_t *)7 )
          v43 = String1[0];
        if ( Application::IsWin32App(v43) )
        {
          v44 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_Performance>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppInv_Performance>::GetImpl'::`2'::impl);
          v45 = v178;
          v46 = v179;
          if ( v44 )
          {
            while ( v45 != v46 )
            {
              if ( v45[3] <= 7u )
                v47 = v45;
              else
                v47 = (_QWORD *)*v45;
              v48 = v175;
              if ( v177 > 7 )
                v48 = (_QWORD *)v175[0];
              if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v48, v176, v47, v45[2]) )
              {
                v49 = v208;
                if ( v209 > 7 )
                  v49 = (_QWORD *)v208[0];
                if ( v45[3] > 7u )
                  v45 = (_QWORD *)*v45;
                v50 = v175;
                if ( v177 > 7 )
                  v50 = (_QWORD *)v175[0];
                AslLogCallPrintf(
                  3,
                  "GetAppInventory",
                  387,
                  "Per-user app: User hive loaded: appUserSid: %ws loadedUserHiveSid: %ws AppName: %ws",
                  v50,
                  v45,
                  v49);
                goto LABEL_109;
              }
              v45 += 4;
            }
          }
          else
          {
            while ( v45 != v46 )
            {
              std::wstring::wstring(v180, v45);
              v51 = v180;
              if ( v181 > 7 )
                v51 = (_QWORD *)v180[0];
              v52 = v175;
              if ( v177 > 7 )
                v52 = (_QWORD *)v175[0];
              if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v52, v176, v51, v180[2]) )
              {
                v53 = v208;
                if ( v209 > 7 )
                  v53 = (_QWORD *)v208[0];
                v54 = v180;
                if ( v181 > 7 )
                  v54 = (_QWORD *)v180[0];
                v55 = v175;
                if ( v177 > 7 )
                  v55 = (_QWORD *)v175[0];
                AslLogCallPrintf(
                  3,
                  "GetAppInventory",
                  403,
                  "Per-user app: User hive loaded: appUserSid: %ws loadedUserHiveSid: %ws AppName: %ws",
                  v55,
                  v54,
                  v53);
                std::wstring::_Tidy_deallocate(v180);
                goto LABEL_109;
              }
              std::wstring::_Tidy_deallocate(v180);
              v45 += 4;
            }
          }
          Application::GetApplicationFromCache((struct IAmiInventoryItem *)v205);
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
            v173,
            v182,
            v206);
          v56 = v175;
          if ( v177 > 7 )
            v56 = (_QWORD *)v175[0];
          v57 = v211;
          if ( v211[3] > 7u )
            v57 = (_QWORD *)v211[0];
          v58 = v206;
          if ( v206[3] > 7u )
            v58 = (_QWORD *)v206[0];
          v59 = v208;
          if ( v209 > 7 )
            v59 = (_QWORD *)v208[0];
          AslLogCallPrintf(
            3,
            "GetAppInventory",
            423,
            "Per-user app: User hive not loaded (cleared batch marker so its not removed): Name: %ws ProgramId: %ws ArpRe"
            "gistryKeyPath: %ws AppUserSid: %ws",
            v59,
            v58,
            v57,
            v56);
        }
      }
LABEL_109:
      FirstItem = TelCacheProvider::GetNextItem(v204, (struct IAmiInventoryItem *)v205);
      if ( ((FirstItem + 0x80000000) & 0x80000000) == 0 && FirstItem != -2147024637 )
        AslLogCallPrintf(1, "GetAppInventory", 430, "GetNextItem failed: [0x%08x]", FirstItem);
      std::wstring::_Tidy_deallocate(v175);
    }
    v60 = TelCacheProvider::BatchEnd((TelCacheProvider *)&v193);
    if ( v60 < 0 )
      AslLogCallPrintf(1, "GetAppInventory", 438, "BatchEnd failed: [0x%08x]", v60);
    std::vector<std::wstring>::_Tidy(&v178);
    Application::~Application((Application *)v205);
  }
  std::set<std::wstring>::set<std::wstring>(v171);
  v61 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_Performance>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppInv_Performance>::GetImpl'::`2'::impl);
  v62 = v159[0];
  v63 = v159[1];
  if ( v61 )
  {
    while ( v62 != v63 )
    {
      v64 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v62 + 2) + 16LL))((__int64)v62 + 16);
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
        v171,
        v182,
        v64);
      v62 = (struct Application *)((char *)v62 + 1008);
    }
  }
  else
  {
    while ( v62 != v63 )
    {
      Application::Application((Application *)v212, v62);
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
        v171,
        v182,
        v215);
      Application::~Application((Application *)v212);
      v62 = (struct Application *)((char *)v62 + 1008);
    }
  }
  std::set<std::wstring>::set<std::wstring>(v164);
  v166 = 0;
  v167 = 0;
  if ( (v154 & 0x80000022) != 0 )
  {
    FilesFromCache = File::GetFilesFromCache(&v178, v203);
    if ( &v166 == (__int128 *)FilesFromCache )
    {
      v67 = (char *)*((_QWORD *)&v166 + 1);
      v66 = (struct File *)v166;
    }
    else
    {
      std::vector<File>::_Tidy(&v166);
      v66 = *(struct File **)FilesFromCache;
      *(_QWORD *)&v166 = *(_QWORD *)FilesFromCache;
      v67 = *(char **)(FilesFromCache + 8);
      *((_QWORD *)&v166 + 1) = v67;
      v167 = *(_QWORD *)(FilesFromCache + 16);
      *(_QWORD *)FilesFromCache = 0;
      *(_QWORD *)(FilesFromCache + 8) = 0;
      *(_QWORD *)(FilesFromCache + 16) = 0;
    }
    v162 = v66;
    v165 = v67;
    v68 = 0;
    v153 = 0;
    v69 = 0;
    v155 = 0;
    v70 = 0;
    v157 = 0;
    std::vector<File>::_Tidy(&v178);
    v71 = v66;
    while ( 1 )
    {
      if ( v71 == (File *)v67 )
      {
        AslTelemetryTrackMetric(
          qword_1801216A8,
          "AppInv_Num_Total_Files",
          0xFAFAFAFAFAFAFAFBuLL * ((v67 - (char *)v66) >> 4));
        AslTelemetryTrackMetric(qword_1801216A8, "AppInv_Num_Orphan_Files", v68);
        AslTelemetryTrackMetric(qword_1801216A8, "AppInv_FileIdsCalculated", v69);
        AslTelemetryTrackMetric(qword_1801216A8, "AppInv_FilesMissingId", v70);
        v32 = v154;
        goto LABEL_211;
      }
      Utility::KickWatchdogTimer();
      v72 = File::Verify(v71, v203) - 1;
      if ( !v72 )
        goto LABEL_132;
      v73 = v72 - 1;
      if ( v73 )
        break;
      if ( !(*(unsigned __int8 (__fastcall **)(File *))(*(_QWORD *)v71 + 144LL))(v71)
        && !(*(unsigned __int8 (__fastcall **)(File *))(*(_QWORD *)v71 + 136LL))(v71) )
      {
        v75 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 112LL))(v71);
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
          v164,
          v202,
          v75);
      }
      v76 = v71;
      for ( i = (char *)v71 + 816; i != v67; i += 816 )
      {
        File::operator=(v76, i);
        v76 = (File *)((char *)v76 + 816);
      }
      v67 -= 816;
      v165 = v67;
      (**(void (__fastcall ***)(char *, _QWORD))v67)(v67, 0);
      *((_QWORD *)&v166 + 1) = v67;
      v69 = v155;
LABEL_209:
      v66 = v162;
    }
    if ( v73 == 1 )
    {
      v155 = ++v69;
LABEL_132:
      if ( !(*(unsigned __int8 (__fastcall **)(File *))(*(_QWORD *)v71 + 136LL))(v71)
        && !(*(unsigned __int8 (__fastcall **)(File *))(*(_QWORD *)v71 + 144LL))(v71) )
      {
        v74 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 112LL))(v71);
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
          v164,
          v180,
          v74);
      }
    }
    if ( !(*(unsigned __int8 (__fastcall **)(File *))(*(_QWORD *)v71 + 136LL))(v71) )
    {
      if ( (*(unsigned __int8 (__fastcall **)(File *))(*(_QWORD *)v71 + 144LL))(v71) )
      {
        v153 = ++v68;
      }
      else
      {
        v78 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 112LL))(v71);
        v79 = (_QWORD *)std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(
                          v171,
                          v174,
                          v78);
        if ( *v79 == v171[0] )
        {
          v80 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 112LL))(v71);
          v81 = (_QWORD *)std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(
                            v173,
                            v182,
                            v80);
          if ( *v81 == v173[0] )
          {
            v82 = 0;
            v83 = 0;
            v84 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_Performance>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppInv_Performance>::GetImpl'::`2'::impl) == 0;
            v85 = v159[1];
            v163 = v159[1];
            if ( v84 )
            {
              for ( j = v159[0]; j != v85; j = (const struct Application *)((char *)j + 1008) )
              {
                Application::Application((Application *)v212, j);
                v105 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 24LL))(v71);
                DirectoryFromPath = Utility::GetDirectoryFromPath(v183, v105);
                found = Utility::FoundSubstring(v219, DirectoryFromPath);
                std::wstring::_Tidy_deallocate(v183);
                if ( found && v220 && v220 >= v83 )
                {
                  v108 = v215;
                  if ( v216 > 7 )
                    v108 = (_QWORD *)v215[0];
                  v109 = v219;
                  if ( v221 > 7 )
                    v109 = (_QWORD *)v219[0];
                  v110 = v217;
                  if ( v218 > 7 )
                    v110 = (_QWORD *)v217[0];
                  v111 = (_QWORD *)(*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 112LL))(v71);
                  v112 = v111;
                  if ( v111[3] > 7u )
                    v112 = (_QWORD *)*v111;
                  v113 = (_QWORD *)(*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 24LL))(v71);
                  v114 = v113;
                  if ( v113[3] > 7u )
                    v114 = (_QWORD *)*v113;
                  v115 = (_QWORD *)(*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 32LL))(v71);
                  if ( v115[3] > 7u )
                    v115 = (_QWORD *)*v115;
                  AslLogCallPrintf(
                    3,
                    "GetAppInventory",
                    570,
                    "File's ProgramId no longer exist: %ws | %ws | %ws re-mapped to %ws | %ws | %ws",
                    v115,
                    v114,
                    v112,
                    v110,
                    v109,
                    v108);
                  v83 = v220;
                  std::wstring::operator=((char *)v71 + 88, v215);
                  File::SaveFileToCache(v71, (const struct ConfigSettings *)v203);
                  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
                    v164,
                    &v178,
                    v215);
                  v82 = 1;
                }
                Application::~Application((Application *)v212);
                v85 = v163;
              }
            }
            else
            {
              v86 = v159[0];
              while ( 1 )
              {
                v172 = v86;
                if ( v86 == v85 )
                  break;
                v87 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 24LL))(v71);
                v88 = Utility::GetDirectoryFromPath(v183, v87);
                v89 = (char *)v86 + 16;
                v90 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v89 + 40LL))(v89);
                LOBYTE(v88) = Utility::FoundSubstring(v90, v88);
                std::wstring::_Tidy_deallocate(v183);
                if ( (_BYTE)v88
                  && *(_QWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v89 + 40LL))(v89) + 16)
                  && *(_QWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v89 + 40LL))(v89) + 16) >= v83 )
                {
                  v91 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v89 + 16LL))(v89);
                  v92 = v91;
                  if ( v91[3] > 7u )
                    v92 = (_QWORD *)*v91;
                  v93 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v89 + 40LL))(v89);
                  v94 = v93;
                  if ( v93[3] > 7u )
                    v94 = (_QWORD *)*v93;
                  v95 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v89 + 8LL))(v89);
                  v96 = v95;
                  if ( v95[3] > 7u )
                    v96 = (_QWORD *)*v95;
                  v97 = (_QWORD *)(*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 112LL))(v71);
                  v98 = v97;
                  if ( v97[3] > 7u )
                    v98 = (_QWORD *)*v97;
                  v99 = (_QWORD *)(*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 24LL))(v71);
                  v100 = v99;
                  if ( v99[3] > 7u )
                    v100 = (_QWORD *)*v99;
                  v101 = (_QWORD *)(*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 32LL))(v71);
                  if ( v101[3] > 7u )
                    v101 = (_QWORD *)*v101;
                  AslLogCallPrintf(
                    3,
                    "GetAppInventory",
                    540,
                    "File's ProgramId no longer exist: %ws | %ws | %ws re-mapped to %ws | %ws | %ws",
                    v101,
                    v100,
                    v98,
                    v96,
                    v94,
                    v92);
                  v83 = *(_QWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v89 + 40LL))(v89) + 16);
                  v102 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v89 + 16LL))(v89);
                  std::wstring::operator=((char *)v71 + 88, v102);
                  File::SaveFileToCache(v71, (const struct ConfigSettings *)v203);
                  v103 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v89 + 16LL))(v89);
                  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
                    v164,
                    v175,
                    v103);
                  v82 = 1;
                }
                v86 = (struct Application *)((char *)v172 + 1008);
                v85 = v163;
              }
            }
            if ( v82 )
            {
              v68 = v153;
            }
            else
            {
              v116 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 24LL))(v71);
              v117 = (const wchar_t *)v116;
              if ( *(_QWORD *)(v116 + 24) > 7u )
                v117 = *(const wchar_t **)v116;
              v118 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 16LL))(v71);
              v119 = (const wchar_t *)v118;
              if ( *(_QWORD *)(v118 + 24) > 7u )
                v119 = *(const wchar_t **)v118;
              v120 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 112LL))(v71);
              v121 = (const wchar_t *)v120;
              if ( *(_QWORD *)(v120 + 24) > 7u )
                v121 = *(const wchar_t **)v120;
              v122 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 8LL))(v71);
              if ( *(_QWORD *)(v122 + 24) > 7u )
                v122 = *(_QWORD *)v122;
              AslLogCallPrintf(
                3,
                "GetAppInventory",
                592,
                "File's ProgramId no longer exist. Calculating new orphan ProgramId. GetFilePathHash: %ls GetProgramId: %"
                "ls GetFileId: %ls GetFilePath: %ls",
                (const wchar_t *)v122,
                v121,
                v119,
                v117);
              (*(void (__fastcall **)(File *))(*(_QWORD *)v71 + 24LL))(v71);
              File::SetBoeProgramId(v71);
              File::SaveFileToCache(v71, (const struct ConfigSettings *)v203);
              v68 = ++v153;
            }
            v67 = v165;
            v70 = v157;
          }
          else
          {
            v123 = (_QWORD *)(*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 24LL))(v71);
            v124 = v123;
            if ( v123[3] > 7u )
              v124 = (_QWORD *)*v123;
            v125 = (_QWORD *)(*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 16LL))(v71);
            v126 = v125;
            if ( v125[3] > 7u )
              v126 = (_QWORD *)*v125;
            v127 = (_QWORD *)(*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 112LL))(v71);
            if ( v127[3] > 7u )
              v127 = (_QWORD *)*v127;
            AslLogCallPrintf(
              3,
              "GetAppInventory",
              514,
              "Per-user app file (user hive not loaded). ProgramId: %ws FileId: %ws FilePath: %ws",
              v127,
              v126,
              v124);
          }
          v69 = v155;
        }
      }
    }
    (*(void (__fastcall **)(_QWORD *, struct Windows::Compat::Inventory::IInventoryDataReceiver *, _QWORD))(*((_QWORD *)v71 + 2) + 8LL))(
      (_QWORD *)v71 + 2,
      v161,
      v154);
    if ( !*(_QWORD *)((*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 16LL))(v71) + 16) )
      v157 = ++v70;
    v71 = (File *)((char *)v71 + 816);
    goto LABEL_209;
  }
  v67 = (char *)*((_QWORD *)&v166 + 1);
  v66 = (struct File *)v166;
  v162 = (struct File *)v166;
LABEL_211:
  if ( (v32 & 0x41000011) != 0 )
  {
    v128 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_Performance>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppInv_Performance>::GetImpl'::`2'::impl) )
    {
      v129 = v159[0];
      v130 = v159[1];
      while ( v129 != v130 )
      {
        Utility::KickWatchdogTimer();
        v131 = (char *)v129 + 16;
        v132 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v129 + 2) + 16LL))((__int64)v129 + 16);
        v133 = (_QWORD *)std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(
                           v164,
                           v182,
                           v132);
        if ( *v133 != v164[0] )
        {
          std::_Tree<std::_Tset_traits<File,std::less<File>,std::allocator<File>,0>>::clear((char *)v129 + 24);
          v134 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v131 + 8LL))((__int64)v129 + 16);
          if ( *(_QWORD *)(v134 + 24) > 7u )
            v134 = *(_QWORD *)v134;
          AslLogCallPrintf(
            3,
            "GetAppInventory",
            630,
            "Updating ProgramInstanceId because of file change/removal. App:%ls",
            (const wchar_t *)v134);
          for ( k = v66; k != (const struct File *)v67; k = (const struct File *)((char *)k + 816) )
          {
            v136 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v131 + 16LL))((__int64)v129 + 16);
            v137 = (_QWORD *)(*(__int64 (__fastcall **)(const struct File *))(*(_QWORD *)k + 112LL))(k);
            v138 = v136[2];
            if ( v136[3] > 7u )
              v136 = (_QWORD *)*v136;
            v139 = v137[2];
            if ( v137[3] > 7u )
              v137 = (_QWORD *)*v137;
            if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v137, v139, v136, v138) )
              Application::SetFile(v129, k);
          }
          v140 = Application::ComputeProgramInstanceId(v129, v183);
          std::wstring::operator=((char *)v129 + 400, v140);
          std::wstring::_Tidy_deallocate(v183);
          Application::SaveApplicationToCache(v129, (const struct ConfigSettings *)v203);
          v66 = v162;
        }
        (*(void (__fastcall **)(__int64, struct Windows::Compat::Inventory::IInventoryDataReceiver *, _QWORD))(*((_QWORD *)v129 + 1) + 8LL))(
          (__int64)v129 + 8,
          v161,
          v154);
        if ( *(_QWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v131 + 80LL))((__int64)v129 + 16) + 16) )
          ++v128;
        v129 = (struct Application *)((char *)v129 + 1008);
      }
    }
    else
    {
      v141 = v159[0];
      v142 = v159[1];
      v143 = v162;
      while ( v141 != v142 )
      {
        Application::Application((Application *)v212, v141);
        Utility::KickWatchdogTimer();
        v144 = (_QWORD *)std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(
                           v164,
                           v182,
                           v215);
        if ( *v144 != v164[0] )
        {
          std::_Tree<std::_Tset_traits<File,std::less<File>,std::allocator<File>,0>>::clear(v214);
          v145 = (const wchar_t *)v217;
          if ( v218 > 7 )
            v145 = (const wchar_t *)v217[0];
          AslLogCallPrintf(
            3,
            "GetAppInventory",
            659,
            "Updating ProgramInstanceId because of file change/removal. App:%ls",
            v145);
          for ( m = v143; m != (const struct File *)v67; m = (const struct File *)((char *)m + 816) )
          {
            File::File((File *)v205, m);
            v147 = v215;
            if ( v216 > 7 )
              v147 = (_QWORD *)v215[0];
            v148 = &v207;
            if ( v208[2] > 7u )
              v148 = v207;
            if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v148, v208[1], v147, v215[2]) )
              Application::SetFile((Application *)v212, (const struct File *)v205);
            File::~File((File *)v205);
          }
          v149 = Application::ComputeProgramInstanceId(v212, v183);
          std::wstring::operator=(v222, v149);
          std::wstring::_Tidy_deallocate(v183);
          Application::SaveApplicationToCache((Application *)v212, (const struct ConfigSettings *)v203);
        }
        Application::ProvideInventory((Application *)v213, v161, v154);
        if ( v223 )
          ++v128;
        Application::~Application((Application *)v212);
        v141 = (const struct Application *)((char *)v141 + 1008);
      }
    }
    AslTelemetryTrackMetric(qword_1801216A8, "AppInv_ProgramCount", 0xEFBEFBEFBEFBEFBFuLL * ((v159[1] - v159[0]) >> 4));
    AslTelemetryTrackMetric(qword_1801216A8, "AppInv_ProgramIIDCount", v128);
  }
  SetLastInventoryScanTime((struct TelCacheProvider *)&v193);
  v150 = GetTickCount() - TickCount;
  AslLogCallPrintf(3, "GetAppInventory", 749, "GetAppInventory elapsed time: %d (ticks)", v150);
  v151 = GetCurrentThread();
  QueryThreadCycleTime(v151, &v169);
  AslTelemetryTrackMetric(
    qword_1801216A8,
    "AppInv_Nightly_Cpu_0.1gCycles",
    (unsigned int)((v169 - CycleTime) / 0x5F5E100));
  AslTelemetryTrackMetric(qword_1801216A8, "AppInv_Nightly_Ms", v150);
  std::vector<File>::_Tidy(&v166);
  std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(
    v164,
    v164);
  std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(
    v171,
    v171);
  std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(
    v173,
    v173);
  if ( v159[0] )
  {
    std::_Destroy_range<std::allocator<Application>>(v159[0], v159[1]);
    std::_Deallocate<16>(v159[0], 16 * ((signed __int64)(v160 - (unsigned __int64)v159[0]) >> 4));
    *(_OWORD *)v159 = 0;
    v160 = 0;
  }
  ConfigSettings::~ConfigSettings((ConfigSettings *)v203);
  Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v158);
  TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v184);
  TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v193);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hObject);
  Utility::UninitializeWatchdogTimer();
  return 0;
}

```

## disassembly

```asm
0x18001f378  push    rbx
0x18001f37a  push    rsi
0x18001f37b  push    rdi
0x18001f37c  push    r12
0x18001f37e  push    r13
0x18001f380  push    r14
0x18001f382  push    r15
0x18001f384  mov     eax, 1930h
0x18001f389  call    _alloca_probe
0x18001f38e  sub     rsp, rax
0x18001f391  mov     rax, cs:__security_cookie
0x18001f398  xor     rax, rsp
0x18001f39b  mov     [rsp+1968h+var_48], rax
0x18001f3a3  mov     rsi, r8
0x18001f3a6  mov     rdi, rdx
0x18001f3a9  mov     rbx, rcx
0x18001f3ac  mov     [rsp+1968h+var_1890], rcx
0x18001f3b4  call    cs:__imp_GetTickCount
0x18001f3ba  mov     [rsp+1968h+var_1848], eax
0x18001f3c1  xor     r14d, r14d
0x18001f3c4  mov     [rsp+1968h+CycleTime], r14
0x18001f3cc  mov     [rsp+1968h+var_1840], r14
0x18001f3d4  mov     r15d, [rdi+10h]
0x18001f3d8  mov     [rsp+1968h+var_18C4], r15d
0x18001f3e0  mov     [rsp+1968h+hObject], r14
0x18001f3e8  test    r15d, r15d
0x18001f3eb  jnz     short loc_18001F3FD
0x18001f3ed  mov     r15d, 2000Bh
0x18001f3f3  mov     [rsp+1968h+var_18C4], r15d
0x18001f3fb  jmp     short loc_18001F45D
0x18001f3fd  test    r15b, 10h
0x18001f401  jz      short loc_18001F42A
0x18001f403  mov     dword ptr [rsp+1968h+var_1948], 80070057h
0x18001f40b  lea     r9, aRequestOfDepre; "Request of deprecated flag: GAI_FLAG_AP"...
0x18001f412  mov     r8d, 59h ; 'Y'
0x18001f418  lea     rdx, aGetappinventor_4; "GetAppInventory"
0x18001f41f  lea     ecx, [r8-58h]
0x18001f423  call    AslLogCallPrintf
0x18001f428  jmp     short loc_18001F432
0x18001f42a  mov     [rsp+1968h+var_18C4], r15d
0x18001f432  test    r15b, 20h
0x18001f436  jz      short loc_18001F45D
0x18001f438  mov     dword ptr [rsp+1968h+var_1948], 80070057h
0x18001f440  lea     r9, aRequestOfDepre_0; "Request of deprecated flag: GAI_FLAG_FI"...
0x18001f447  mov     r8d, 5Dh ; ']'
0x18001f44d  lea     rdx, aGetappinventor_4; "GetAppInventory"
0x18001f454  lea     ecx, [r8-5Ch]
0x18001f458  call    AslLogCallPrintf
0x18001f45d  call    cs:__imp_GetCurrentThread
0x18001f463  mov     rcx, rax; ThreadHandle
0x18001f466  lea     rdx, [rsp+1968h+CycleTime]; CycleTime
0x18001f46e  call    cs:__imp_QueryThreadCycleTime
0x18001f474  mov     [rsp+1968h+hObject], r14
0x18001f47c  lea     rcx, [rsp+1968h+hObject]; void **
0x18001f484  call    ?IsAeInvAlreadyRunning@Utility@@SA_NPEAPEAX@Z; Utility::IsAeInvAlreadyRunning(void * *)
0x18001f489  test    al, al
0x18001f48b  jz      loc_18001F524
0x18001f491  lea     r9, aInventoryAlrea; "Inventory already running. Waiting for "...
0x18001f498  mov     r8d, 75h ; 'u'
0x18001f49e  lea     rdx, aGetappinventor_4; "GetAppInventory"
0x18001f4a5  lea     ecx, [r8-72h]
0x18001f4a9  call    AslLogCallPrintf
0x18001f4ae  mov     al, 1
0x18001f4b0  mov     ebx, r14d
0x18001f4b3  test    al, al
0x18001f4b5  jz      short loc_18001F51C
0x18001f4b7  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18001f4bc  call    cs:__imp_Sleep
0x18001f4c2  mov     rcx, [rsp+1968h+hObject]; hObject
0x18001f4ca  test    rcx, rcx
0x18001f4cd  jz      short loc_18001F4D4
0x18001f4cf  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18001f4d4  mov     [rsp+1968h+hObject], r14
0x18001f4dc  lea     rcx, [rsp+1968h+hObject]; void **
0x18001f4e4  call    ?IsAeInvAlreadyRunning@Utility@@SA_NPEAPEAX@Z; Utility::IsAeInvAlreadyRunning(void * *)
0x18001f4e9  inc     ebx
0x18001f4eb  cmp     ebx, 0BB8h
0x18001f4f1  jb      short loc_18001F4B3
0x18001f4f3  test    al, al
0x18001f4f5  jz      short loc_18001F51C
0x18001f4f7  mov     dword ptr [rsp+1968h+var_1948], 800700AAh
0x18001f4ff  lea     r9, aInventoryStill; "Inventory still hasn't completed. Conti"...
0x18001f506  mov     r8d, 80h
0x18001f50c  lea     rdx, aGetappinventor_4; "GetAppInventory"
0x18001f513  lea     ecx, [r8-7Fh]
0x18001f517  call    AslLogCallPrintf
0x18001f51c  mov     rbx, [rsp+1968h+var_1890]
0x18001f524  cmp     dword ptr [rdi+14h], 1
0x18001f528  setz    dl; bool
0x18001f52b  call    ?InitializeCoreProvider@TelemetryProvider@Telemetry@Shared@Compat@Windows@@IEAAX_N@Z; Windows::Compat::Shared::Telemetry::TelemetryProvider::InitializeCoreProvider(bool)
0x18001f530  mov     rdx, rsi; char *
0x18001f533  call    ?ExtendCv@TelemetryProvider@Telemetry@Shared@Compat@Windows@@QEAAXPEBD@Z; Windows::Compat::Shared::Telemetry::TelemetryProvider::ExtendCv(char const *)
0x18001f538  mov     esi, [rdi+8]
0x18001f53b  test    esi, esi
0x18001f53d  setnz   r12b
0x18001f541  mov     edi, [rdi+0Ch]
0x18001f544  test    edi, edi
0x18001f546  setnz   r13b
0x18001f54a  mov     r14d, r15d
0x18001f54d  and     r14d, 8
0x18001f551  jz      short loc_18001F55B
0x18001f553  mov     rcx, rbx; struct Windows::Compat::Inventory::IInventoryDataReceiver *
0x18001f556  call    ?GetInvModuleVersion@@YAJPEAVIInventoryDataReceiver@Inventory@Compat@Windows@@@Z; GetInvModuleVersion(Windows::Compat::Inventory::IInventoryDataReceiver *)
0x18001f55b  mov     ebx, 4Eh ; 'N'
0x18001f560  mov     r8d, ebx; Size
0x18001f563  xor     edx, edx; Val
0x18001f565  lea     rcx, [rsp+1968h+var_15D0]; void *
0x18001f56d  call    memset_0
0x18001f572  xor     eax, eax
0x18001f574  mov     [rsp+1968h+var_1578], ax
0x18001f57c  mov     [rsp+1968h+var_1570], rax
0x18001f584  xorps   xmm0, xmm0
0x18001f587  movdqa  [rsp+1968h+var_1568], xmm0
0x18001f590  mov     [rsp+1968h+var_1558], rax
0x18001f598  mov     [rsp+1968h+var_1550], eax
0x18001f59f  mov     [rsp+1968h+var_154C], al
0x18001f5a6  mov     [rsp+1968h+var_1580], rax
0x18001f5ae  mov     [rsp+1968h+var_15D8], rax
0x18001f5b6  mov     r8d, ebx; Size
0x18001f5b9  xor     edx, edx; Val
0x18001f5bb  lea     rcx, [rsp+1968h+var_1670]; void *
0x18001f5c3  call    memset_0
0x18001f5c8  mov     [rsp+1968h+var_1618], 0
0x18001f5d2  mov     [rsp+1968h+var_1610], 0
0x18001f5de  xorps   xmm0, xmm0
0x18001f5e1  movdqa  [rsp+1968h+var_1608], xmm0
0x18001f5ea  mov     [rsp+1968h+var_15F8], 0
0x18001f5f6  mov     [rsp+1968h+var_15F0], 0
0x18001f601  mov     [rsp+1968h+var_15EC], 0
0x18001f609  mov     [rsp+1968h+var_1620], 0
0x18001f615  mov     [rsp+1968h+var_1678], 0
0x18001f621  and     r15d, 10000000h
0x18001f628  jnz     loc_18001F93F
0x18001f62e  mov     ecx, 3F0h; Size
0x18001f633  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f638  mov     [rsp+1968h+var_1880], rax
0x18001f640  mov     rcx, rax; this
0x18001f643  call    ??0Application@@QEAA@XZ; Application::Application(void)
0x18001f648  nop
0x18001f649  lea     rdx, ?ApplicationCacheProviderName@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ApplicationCacheProviderName
0x18001f650  cmp     cs:qword_1801222A8, 7
0x18001f658  cmova   rdx, cs:?ApplicationCacheProviderName@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ApplicationCacheProviderName
0x18001f660  mov     dword ptr [rsp+1968h+var_1938], 1F4h
0x18001f668  mov     dword ptr [rsp+1968h+var_1940], 5
0x18001f670  mov     dword ptr [rsp+1968h+var_1948], 2
0x18001f678  xor     r9d, r9d
0x18001f67b  mov     r8, rax
0x18001f67e  lea     rcx, [rsp+1968h+var_15D8]
0x18001f686  call    ?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z; TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)
0x18001f68b  mov     ebx, eax
0x18001f68d  test    eax, eax
0x18001f68f  jns     short loc_18001F6E3
0x18001f691  mov     dword ptr [rsp+1968h+var_1948], eax
0x18001f695  lea     r9, asc_1800F3FD8; "[%#x]"
0x18001f69c  mov     r8d, 9Ah
0x18001f6a2  lea     rdx, aGetappinventor_4; "GetAppInventory"
0x18001f6a9  lea     ecx, [r15+1]
0x18001f6ad  call    AslLogCallPrintf
0x18001f6b2  nop
0x18001f6b3  lea     rcx, [rsp+1968h+var_1678]; this
0x18001f6bb  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x18001f6c0  nop
0x18001f6c1  lea     rcx, [rsp+1968h+var_15D8]; this
0x18001f6c9  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x18001f6ce  nop
0x18001f6cf  lea     rcx, [rsp+1968h+hObject]
0x18001f6d7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001f6dc  mov     eax, ebx
0x18001f6de  jmp     loc_18002100D
0x18001f6e3  mov     ecx, 330h; Size
0x18001f6e8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f6ed  mov     [rsp+1968h+var_1880], rax
0x18001f6f5  mov     rcx, rax; this
0x18001f6f8  call    ??0File@@QEAA@XZ; File::File(void)
0x18001f6fd  nop
0x18001f6fe  test    rax, rax
0x18001f701  jz      short loc_18001F709
0x18001f703  lea     r8, [rax+8]
0x18001f707  jmp     short loc_18001F70C
0x18001f709  xor     r8d, r8d
0x18001f70c  lea     rdx, ?FileCacheProviderName@File@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::FileCacheProviderName
0x18001f713  cmp     cs:qword_180121AA8, 7
0x18001f71b  cmova   rdx, cs:?FileCacheProviderName@File@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring File::FileCacheProviderName
0x18001f723  mov     dword ptr [rsp+1968h+var_1938], 1F4h
0x18001f72b  mov     dword ptr [rsp+1968h+var_1940], 5
0x18001f733  mov     dword ptr [rsp+1968h+var_1948], 2
0x18001f73b  xor     r9d, r9d
0x18001f73e  lea     rcx, [rsp+1968h+var_1678]
0x18001f746  call    ?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z; TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)
0x18001f74b  mov     ebx, eax
0x18001f74d  test    eax, eax
0x18001f74f  jns     short loc_18001F7A4
0x18001f751  mov     dword ptr [rsp+1968h+var_1948], eax
0x18001f755  lea     r9, asc_1800F3FD8; "[%#x]"
0x18001f75c  mov     r8d, 9Bh
0x18001f762  lea     rdx, aGetappinventor_4; "GetAppInventory"
0x18001f769  mov     ecx, 1
0x18001f76e  call    AslLogCallPrintf
0x18001f773  nop
0x18001f774  lea     rcx, [rsp+1968h+var_1678]; this
0x18001f77c  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x18001f781  nop
0x18001f782  lea     rcx, [rsp+1968h+var_15D8]; this
0x18001f78a  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x18001f78f  nop
0x18001f790  lea     rcx, [rsp+1968h+hObject]
0x18001f798  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001f79d  mov     eax, ebx
0x18001f79f  jmp     loc_18002100D
0x18001f7a4  test    esi, esi
0x18001f7a6  jz      short loc_18001F80E
0x18001f7a8  lea     rcx, [rsp+1968h+var_15D8]; this
0x18001f7b0  call    ?ClearData@TelCacheProvider@@QEAAJXZ; TelCacheProvider::ClearData(void)
0x18001f7b5  mov     ebx, eax
0x18001f7b7  test    eax, eax
0x18001f7b9  jns     short loc_18001F80E
0x18001f7bb  mov     dword ptr [rsp+1968h+var_1948], eax
0x18001f7bf  lea     r9, asc_1800F3FD8; "[%#x]"
0x18001f7c6  mov     r8d, 0A3h
0x18001f7cc  lea     rdx, aGetappinventor_4; "GetAppInventory"
0x18001f7d3  mov     ecx, 1
0x18001f7d8  call    AslLogCallPrintf
0x18001f7dd  nop
0x18001f7de  lea     rcx, [rsp+1968h+var_1678]; this
0x18001f7e6  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x18001f7eb  nop
0x18001f7ec  lea     rcx, [rsp+1968h+var_15D8]; this
0x18001f7f4  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x18001f7f9  nop
0x18001f7fa  lea     rcx, [rsp+1968h+hObject]
0x18001f802  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001f807  mov     eax, ebx
0x18001f809  jmp     loc_18002100D
0x18001f80e  test    edi, edi
0x18001f810  jnz     loc_18001F93F
0x18001f816  lea     rcx, [rsp+1968h+var_15D8]; struct TelCacheProvider *
0x18001f81e  call    ?IsInventoryCacheFresh@@YAJAEAVTelCacheProvider@@@Z; IsInventoryCacheFresh(TelCacheProvider &)
0x18001f823  test    eax, eax
0x18001f825  jnz     loc_18001F93F
0x18001f82b  lea     rcx, [rsp+1968h+var_1048]; this
0x18001f833  call    ??0Application@@QEAA@XZ; Application::Application(void)
0x18001f838  nop
0x18001f839  lea     rcx, [rsp+1968h+var_1438]; this
0x18001f841  call    ??0File@@QEAA@XZ; File::File(void)
0x18001f846  nop
0x18001f847  mov     ebx, [rsp+1968h+var_18C4]
0x18001f84e  mov     r9d, ebx
0x18001f851  lea     r8, [rsp+1968h+var_1048]
0x18001f859  lea     rdx, [rsp+1968h+var_15D8]
0x18001f861  mov     rdi, [rsp+1968h+var_1890]
0x18001f869  mov     rcx, rdi
0x18001f86c  call    ??$ReturnCachedInventoryItems@VApplication@@@@YAJPEAVIInventoryDataReceiver@Inventory@Compat@Windows@@AEAVTelCacheProvider@@AEAVApplication@@K@Z; ReturnCachedInventoryItems<Application>(Windows::Compat::Inventory::IInventoryDataReceiver *,TelCacheProvider &,Application &,ulong)
0x18001f871  test    eax, eax
0x18001f873  jnz     loc_18001F901
0x18001f879  mov     r9d, ebx
0x18001f87c  lea     r8, [rsp+1968h+var_1438]
0x18001f884  lea     rdx, [rsp+1968h+var_1678]
0x18001f88c  mov     rcx, rdi
0x18001f88f  call    ??$ReturnCachedInventoryItems@VFile@@@@YAJPEAVIInventoryDataReceiver@Inventory@Compat@Windows@@AEAVTelCacheProvider@@AEAVFile@@K@Z; ReturnCachedInventoryItems<File>(Windows::Compat::Inventory::IInventoryDataReceiver *,TelCacheProvider &,File &,ulong)
0x18001f894  test    eax, eax
0x18001f896  jnz     short loc_18001F901
0x18001f898  lea     r9, aSkippingScanRe; "Skipping scan, returning cached invento"...
0x18001f89f  mov     r8d, 0BCh
0x18001f8a5  lea     rdx, aGetappinventor_4; "GetAppInventory"
0x18001f8ac  lea     ecx, [rax+3]
0x18001f8af  call    AslLogCallPrintf
0x18001f8b4  nop
0x18001f8b5  lea     rcx, [rsp+1968h+var_1438]; this
0x18001f8bd  call    ??1File@@UEAA@XZ; File::~File(void)
0x18001f8c2  nop
0x18001f8c3  lea     rcx, [rsp+1968h+var_1048]; this
0x18001f8cb  call    ??1Application@@UEAA@XZ; Application::~Application(void)
0x18001f8d0  nop
0x18001f8d1  lea     rcx, [rsp+1968h+var_1678]; this
0x18001f8d9  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x18001f8de  nop
0x18001f8df  lea     rcx, [rsp+1968h+var_15D8]; this
0x18001f8e7  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x18001f8ec  nop
0x18001f8ed  lea     rcx, [rsp+1968h+hObject]
0x18001f8f5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001f8fa  xor     eax, eax
0x18001f8fc  jmp     loc_18002100D
0x18001f901  mov     rax, [rdi]
0x18001f904  lea     rdx, aDiscardAndRese; "DISCARD_AND_RESET_ASSETS"
0x18001f90b  mov     rcx, rdi
0x18001f90e  mov     rax, [rax]
0x18001f911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f916  test    r14d, r14d
0x18001f919  jz      short loc_18001F924
0x18001f91b  mov     rcx, rdi; struct Windows::Compat::Inventory::IInventoryDataReceiver *
0x18001f91e  call    ?GetInvModuleVersion@@YAJPEAVIInventoryDataReceiver@Inventory@Compat@Windows@@@Z; GetInvModuleVersion(Windows::Compat::Inventory::IInventoryDataReceiver *)
0x18001f923  nop
0x18001f924  lea     rcx, [rsp+1968h+var_1438]; this
0x18001f92c  call    ??1File@@UEAA@XZ; File::~File(void)
0x18001f931  nop
0x18001f932  lea     rcx, [rsp+1968h+var_1048]; this
0x18001f93a  call    ??1Application@@UEAA@XZ; Application::~Application(void)
0x18001f93f  lea     r9, aPerformingAppl; "Performing application scan"
0x18001f946  mov     r8d, 0CAh
  ... truncated ...
```
