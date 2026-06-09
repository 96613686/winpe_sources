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
  int v68; // r12d
  int v69; // edi
  int v70; // r14d
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
  const struct Application *j; // r13
  __int64 v104; // rax
  __int64 DirectoryFromPath; // rax
  char found; // di
  _QWORD *v107; // r14
  _QWORD *v108; // r15
  _QWORD *v109; // r12
  _QWORD *v110; // rax
  _QWORD *v111; // rsi
  _QWORD *v112; // rax
  _QWORD *v113; // rdi
  _QWORD *v114; // rax
  __int64 v115; // rax
  const wchar_t *v116; // r14
  __int64 v117; // rax
  const wchar_t *v118; // rsi
  __int64 v119; // rax
  const wchar_t *v120; // rdi
  __int64 v121; // rax
  _QWORD *v122; // rax
  _QWORD *v123; // rsi
  _QWORD *v124; // rax
  _QWORD *v125; // rdi
  _QWORD *v126; // rax
  int v127; // r15d
  struct Application *v128; // rbx
  struct Application *v129; // r12
  char *v130; // r14
  __int64 v131; // rax
  _QWORD *v132; // rax
  __int64 v133; // rax
  const struct File *k; // rdi
  _QWORD *v135; // rsi
  _QWORD *v136; // rax
  __int64 v137; // rdx
  const struct Application *v138; // rdi
  struct Application *v139; // rsi
  struct File *v140; // r14
  _QWORD *v141; // rax
  const wchar_t *v142; // rax
  const struct File *m; // rbx
  _QWORD *v144; // r8
  _QWORD *v145; // rcx
  int v146; // ebx
  HANDLE v147; // rax
  int v148; // [rsp+30h] [rbp-1938h]
  int v149; // [rsp+A0h] [rbp-18C8h]
  unsigned int v150; // [rsp+A4h] [rbp-18C4h]
  int v151; // [rsp+A8h] [rbp-18C0h]
  HANDLE hObject; // [rsp+B0h] [rbp-18B8h] BYREF
  int v153; // [rsp+B8h] [rbp-18B0h]
  int v154; // [rsp+BCh] [rbp-18ACh] BYREF
  struct Application *v155[2]; // [rsp+C0h] [rbp-18A8h] BYREF
  __int64 v156; // [rsp+D0h] [rbp-1898h]
  struct Windows::Compat::Inventory::IInventoryDataReceiver *v157; // [rsp+D8h] [rbp-1890h]
  struct File *v158; // [rsp+E0h] [rbp-1888h]
  File *v159; // [rsp+E8h] [rbp-1880h]
  _QWORD v160[2]; // [rsp+F0h] [rbp-1878h] BYREF
  char *v161; // [rsp+100h] [rbp-1868h]
  __int128 v162; // [rsp+108h] [rbp-1860h] BYREF
  __int64 v163; // [rsp+118h] [rbp-1850h]
  DWORD TickCount; // [rsp+120h] [rbp-1848h]
  unsigned __int64 v165; // [rsp+128h] [rbp-1840h] BYREF
  unsigned __int64 CycleTime; // [rsp+130h] [rbp-1838h] BYREF
  _QWORD v167[2]; // [rsp+138h] [rbp-1830h] BYREF
  struct Application *v168; // [rsp+148h] [rbp-1820h]
  _QWORD v169[2]; // [rsp+150h] [rbp-1818h] BYREF
  char v170[240]; // [rsp+160h] [rbp-1808h] BYREF
  _QWORD v171[2]; // [rsp+250h] [rbp-1718h] BYREF
  __int64 v172; // [rsp+260h] [rbp-1708h]
  unsigned __int64 v173; // [rsp+268h] [rbp-1700h]
  _QWORD *v174; // [rsp+270h] [rbp-16F8h] BYREF
  _QWORD *v175; // [rsp+278h] [rbp-16F0h]
  _QWORD v176[2]; // [rsp+290h] [rbp-16D8h] BYREF
  unsigned __int64 v177; // [rsp+2A8h] [rbp-16C0h]
  _BYTE v178[32]; // [rsp+2B0h] [rbp-16B8h] BYREF
  _BYTE v179[32]; // [rsp+2D0h] [rbp-1698h] BYREF
  __int64 v180; // [rsp+2F0h] [rbp-1678h] BYREF
  char v181[80]; // [rsp+2F8h] [rbp-1670h] BYREF
  __int64 v182; // [rsp+348h] [rbp-1620h]
  __int16 v183; // [rsp+350h] [rbp-1618h]
  __int64 v184; // [rsp+358h] [rbp-1610h]
  __int128 v185; // [rsp+360h] [rbp-1608h]
  __int64 v186; // [rsp+370h] [rbp-15F8h]
  int v187; // [rsp+378h] [rbp-15F0h]
  char v188; // [rsp+37Ch] [rbp-15ECh]
  __int64 v189; // [rsp+390h] [rbp-15D8h] BYREF
  char v190[80]; // [rsp+398h] [rbp-15D0h] BYREF
  __int64 v191; // [rsp+3E8h] [rbp-1580h]
  __int16 v192; // [rsp+3F0h] [rbp-1578h]
  __int64 v193; // [rsp+3F8h] [rbp-1570h]
  __int128 v194; // [rsp+400h] [rbp-1568h]
  __int64 v195; // [rsp+410h] [rbp-1558h]
  int v196; // [rsp+418h] [rbp-1550h]
  char v197; // [rsp+41Ch] [rbp-154Ch]
  _BYTE v198[32]; // [rsp+420h] [rbp-1548h] BYREF
  _BYTE v199[16]; // [rsp+440h] [rbp-1528h] BYREF
  TelCacheProvider *v200; // [rsp+450h] [rbp-1518h]
  _BYTE v201[56]; // [rsp+530h] [rbp-1438h] BYREF
  _QWORD v202[4]; // [rsp+568h] [rbp-1400h] BYREF
  _QWORD *v203; // [rsp+588h] [rbp-13E0h] BYREF
  _QWORD v204[3]; // [rsp+590h] [rbp-13D8h] BYREF
  unsigned __int64 v205; // [rsp+5A8h] [rbp-13C0h]
  wchar_t *String1[12]; // [rsp+680h] [rbp-12E8h] BYREF
  _QWORD v207[72]; // [rsp+6E0h] [rbp-1288h] BYREF
  char v208[8]; // [rsp+920h] [rbp-1048h] BYREF
  char v209[16]; // [rsp+928h] [rbp-1040h] BYREF
  char v210[32]; // [rsp+938h] [rbp-1030h] BYREF
  _QWORD v211[2]; // [rsp+958h] [rbp-1010h] BYREF
  unsigned __int64 v212; // [rsp+970h] [rbp-FF8h]
  _QWORD v213[3]; // [rsp+980h] [rbp-FE8h] BYREF
  unsigned __int64 v214; // [rsp+998h] [rbp-FD0h]
  _QWORD v215[2]; // [rsp+9E0h] [rbp-F88h] BYREF
  unsigned __int64 v216; // [rsp+9F0h] [rbp-F78h]
  unsigned __int64 v217; // [rsp+9F8h] [rbp-F70h]
  char v218[16]; // [rsp+AB0h] [rbp-EB8h] BYREF
  __int64 v219; // [rsp+AC0h] [rbp-EA8h]

  v5 = a1;
  v157 = a1;
  TickCount = GetTickCount();
  CycleTime = 0;
  v165 = 0;
  v6 = *((_DWORD *)a2 + 4);
  v150 = v6;
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
      v150 = v6;
    if ( (v6 & 0x20) != 0 )
      AslLogCallPrintf(1, "GetAppInventory", 93, "Request of deprecated flag: GAI_FLAG_FILE_INFO [%#x]", -2147024809);
  }
  else
  {
    v6 = 131083;
    v150 = 131083;
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
    v5 = v157;
  }
  Windows::Compat::Shared::Telemetry::TelemetryProvider::InitializeCoreProvider(v8, *((_DWORD *)a2 + 5) == 1);
  Windows::Compat::Shared::Telemetry::TelemetryProvider::ExtendCv(v11, a3);
  v12 = *((_DWORD *)a2 + 2);
  v13 = *((_DWORD *)a2 + 3);
  v14 = v13 != 0;
  v15 = v6 & 8;
  if ( (v6 & 8) != 0 )
    GetInvModuleVersion(v5);
  memset_0(v190, 0, 0x4Eu);
  v192 = 0;
  v193 = 0;
  v194 = 0;
  v195 = 0;
  v196 = 0;
  v197 = 0;
  v191 = 0;
  v189 = 0;
  memset_0(v181, 0, 0x4Eu);
  v183 = 0;
  v184 = 0;
  v185 = 0;
  v186 = 0;
  v187 = 0;
  v188 = 0;
  v182 = 0;
  v180 = 0;
  v16 = v6 & 0x10000000;
  if ( !v16 )
  {
    v159 = (File *)operator new(0x3F0u);
    v17 = Application::Application(v159);
    v18 = &Application::ApplicationCacheProviderName;
    if ( (unsigned __int64)qword_1801222A8 > 7 )
      v18 = (__int64 *)Application::ApplicationCacheProviderName;
    v19 = TelCacheProvider::Initialize(&v189, v18, v17, 0, 2, 5, 500);
    v20 = v19;
    if ( v19 < 0 )
    {
      AslLogCallPrintf(1, "GetAppInventory", 154, "[%#x]", v19);
      TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v180);
      TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v189);
      wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hObject);
      return v20;
    }
    v159 = (File *)operator new(0x330u);
    v22 = File::File(v159);
    if ( v22 )
      v23 = (char *)v22 + 8;
    else
      v23 = 0;
    v24 = &File::FileCacheProviderName;
    if ( (unsigned __int64)qword_180121AA8 > 7 )
      v24 = (__int64 *)File::FileCacheProviderName;
    v25 = TelCacheProvider::Initialize(&v180, v24, v23, 0, 2, 5, 500);
    v26 = v25;
    if ( v25 < 0 )
    {
      AslLogCallPrintf(1, "GetAppInventory", 155, "[%#x]", v25);
      TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v180);
      TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v189);
      wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hObject);
      return v26;
    }
    if ( v12 )
    {
      v27 = TelCacheProvider::ClearData((TelCacheProvider *)&v189);
      v28 = v27;
      if ( v27 < 0 )
      {
        AslLogCallPrintf(1, "GetAppInventory", 163, "[%#x]", v27);
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v180);
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v189);
        wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hObject);
        return v28;
      }
    }
    if ( !v13 && !(unsigned int)IsInventoryCacheFresh((struct TelCacheProvider *)&v189) )
    {
      Application::Application((Application *)v208);
      File::File((File *)v201);
      v29 = v157;
      if ( !(unsigned int)ReturnCachedInventoryItems<Application>(v157, &v189, v208, v150)
        && !(unsigned int)ReturnCachedInventoryItems<File>(v29, &v180, v201, v150) )
      {
        AslLogCallPrintf(3, "GetAppInventory", 188, "Skipping scan, returning cached inventory");
        File::~File((File *)v201);
        Application::~Application((Application *)v208);
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v180);
        TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v189);
        wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hObject);
        return 0;
      }
      (**(void (__fastcall ***)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, const wchar_t *))v29)(
        v29,
        L"DISCARD_AND_RESET_ASSETS");
      if ( v15 )
        GetInvModuleVersion(v29);
      File::~File((File *)v201);
      Application::~Application((Application *)v208);
    }
  }
  AslLogCallPrintf(3, "GetAppInventory", 202, "Performing application scan");
  v154 = -2147221008;
  v30 = Common::AutoWinRTInitialize::Initialize(&v154);
  v31 = v30;
  if ( v30 < 0 )
  {
    AslLogCallPrintf(1, "GetAppInventory", 215, "[%#x]", v30);
    Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v154);
    TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v180);
    TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v189);
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hObject);
    return v31;
  }
  v32 = v150;
  std::wstring::wstring(v178, &pszFormat);
  std::wstring::wstring(v198, &pszFormat);
  std::wstring::wstring(v176, &pszFormat);
  std::wstring::wstring(v171, &pszFormat);
  std::wstring::wstring(&v174, &pszFormat);
  ConfigSettings::ConfigSettings(
    (unsigned int)v199,
    (v150 & 0x20000000) != 0 ? 5 : 0,
    (unsigned int)&v189,
    (unsigned int)&v180,
    v14,
    v12 != 0,
    v148,
    (__int64)&v174,
    (__int64)v171,
    (__int64)v176,
    (__int64)v198,
    (__int64)v178);
  std::wstring::_Tidy_deallocate(&v174);
  std::wstring::_Tidy_deallocate(v171);
  std::wstring::_Tidy_deallocate(v176);
  std::wstring::_Tidy_deallocate(v198);
  std::wstring::_Tidy_deallocate(v178);
  *(_OWORD *)v155 = 0;
  v156 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_Performance>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppInv_Performance>::GetImpl'::`2'::impl) )
    std::vector<Application>::reserve(v155);
  if ( (v150 & 0x20000) == 0 || v16 )
  {
    v33 = 0;
  }
  else
  {
    v33 = 1;
    v34 = TelCacheProvider::BatchBegin((TelCacheProvider *)&v189);
    if ( v34 < 0 )
      AslLogCallPrintf(1, "GetAppInventory", 266, "BatchBegin failed: [0x%08x]", v34);
  }
  Utility::InitializeWatchdogTimer();
  if ( (v150 & 0x20000) != 0 )
  {
    v159 = (File *)&StoreAppFinder::`vftable';
    StoreAppFinder::EnumeratePackages((__int64)v199, v155, v35);
  }
  std::set<std::wstring>::set<std::wstring>(v169);
  if ( v33 )
  {
    Application::Application((Application *)v201);
    LoadedUserHiveSids = Utility::GetLoadedUserHiveSids();
    std::vector<std::wstring>::vector<std::wstring>(&v174, LoadedUserHiveSids);
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_Performance>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppInv_Performance>::GetImpl'::`2'::impl);
    v38 = v174;
    v39 = v175;
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
        std::wstring::wstring(v171, v38);
        v41 = v171;
        if ( v173 > 7 )
          v41 = (_QWORD *)v171[0];
        AslLogCallPrintf(3, "GetAppInventory", 364, "Loaded user hive SID: %ws", v41);
        std::wstring::_Tidy_deallocate(v171);
        v38 += 4;
      }
    }
    FirstItem = TelCacheProvider::GetFirstItem(v200, (struct IAmiInventoryItem *)v201);
    while ( FirstItem >= 0 )
    {
      Utility::GetUserSidFromArpKeyPath(v171, v207);
      if ( v172 )
      {
        v43 = (wchar_t *)String1;
        if ( String1[3] > (wchar_t *)7 )
          v43 = String1[0];
        if ( Application::IsWin32App(v43) )
        {
          v44 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_Performance>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppInv_Performance>::GetImpl'::`2'::impl);
          v45 = v174;
          v46 = v175;
          if ( v44 )
          {
            while ( v45 != v46 )
            {
              if ( v45[3] <= 7u )
                v47 = v45;
              else
                v47 = (_QWORD *)*v45;
              v48 = v171;
              if ( v173 > 7 )
                v48 = (_QWORD *)v171[0];
              if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v48, v172, v47) )
              {
                v49 = v204;
                if ( v205 > 7 )
                  v49 = (_QWORD *)v204[0];
                if ( v45[3] > 7u )
                  v45 = (_QWORD *)*v45;
                v50 = v171;
                if ( v173 > 7 )
                  v50 = (_QWORD *)v171[0];
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
              std::wstring::wstring(v176, v45);
              v51 = v176;
              if ( v177 > 7 )
                v51 = (_QWORD *)v176[0];
              v52 = v171;
              if ( v173 > 7 )
                v52 = (_QWORD *)v171[0];
              if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v52, v172, v51) )
              {
                v53 = v204;
                if ( v205 > 7 )
                  v53 = (_QWORD *)v204[0];
                v54 = v176;
                if ( v177 > 7 )
                  v54 = (_QWORD *)v176[0];
                v55 = v171;
                if ( v173 > 7 )
                  v55 = (_QWORD *)v171[0];
                AslLogCallPrintf(
                  3,
                  "GetAppInventory",
                  403,
                  "Per-user app: User hive loaded: appUserSid: %ws loadedUserHiveSid: %ws AppName: %ws",
                  v55,
                  v54,
                  v53);
                std::wstring::_Tidy_deallocate(v176);
                goto LABEL_109;
              }
              std::wstring::_Tidy_deallocate(v176);
              v45 += 4;
            }
          }
          Application::GetApplicationFromCache((struct IAmiInventoryItem *)v201);
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
            v169,
            v178,
            v202);
          v56 = v171;
          if ( v173 > 7 )
            v56 = (_QWORD *)v171[0];
          v57 = v207;
          if ( v207[3] > 7u )
            v57 = (_QWORD *)v207[0];
          v58 = v202;
          if ( v202[3] > 7u )
            v58 = (_QWORD *)v202[0];
          v59 = v204;
          if ( v205 > 7 )
            v59 = (_QWORD *)v204[0];
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
      FirstItem = TelCacheProvider::GetNextItem(v200, (struct IAmiInventoryItem *)v201);
      if ( ((FirstItem + 0x80000000) & 0x80000000) == 0 && FirstItem != -2147024637 )
        AslLogCallPrintf(1, "GetAppInventory", 430, "GetNextItem failed: [0x%08x]", FirstItem);
      std::wstring::_Tidy_deallocate(v171);
    }
    v60 = TelCacheProvider::BatchEnd((TelCacheProvider *)&v189);
    if ( v60 < 0 )
      AslLogCallPrintf(1, "GetAppInventory", 438, "BatchEnd failed: [0x%08x]", v60);
    std::vector<std::wstring>::_Tidy(&v174);
    Application::~Application((Application *)v201);
  }
  std::set<std::wstring>::set<std::wstring>(v167);
  v61 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_Performance>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppInv_Performance>::GetImpl'::`2'::impl);
  v62 = v155[0];
  v63 = v155[1];
  if ( v61 )
  {
    while ( v62 != v63 )
    {
      v64 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v62 + 2) + 16LL))((__int64)v62 + 16);
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
        v167,
        v178,
        v64);
      v62 = (struct Application *)((char *)v62 + 1008);
    }
  }
  else
  {
    while ( v62 != v63 )
    {
      Application::Application((Application *)v208, v62);
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
        v167,
        v178,
        v211);
      Application::~Application((Application *)v208);
      v62 = (struct Application *)((char *)v62 + 1008);
    }
  }
  std::set<std::wstring>::set<std::wstring>(v160);
  v162 = 0;
  v163 = 0;
  if ( (v150 & 0x80000022) != 0 )
  {
    FilesFromCache = File::GetFilesFromCache(&v174, v199);
    if ( &v162 == (__int128 *)FilesFromCache )
    {
      v67 = (char *)*((_QWORD *)&v162 + 1);
      v66 = (struct File *)v162;
    }
    else
    {
      std::vector<File>::_Tidy(&v162);
      v66 = *(struct File **)FilesFromCache;
      *(_QWORD *)&v162 = *(_QWORD *)FilesFromCache;
      v67 = *(char **)(FilesFromCache + 8);
      *((_QWORD *)&v162 + 1) = v67;
      v163 = *(_QWORD *)(FilesFromCache + 16);
      *(_QWORD *)FilesFromCache = 0;
      *(_QWORD *)(FilesFromCache + 8) = 0;
      *(_QWORD *)(FilesFromCache + 16) = 0;
    }
    v158 = v66;
    v161 = v67;
    v68 = 0;
    v149 = 0;
    v69 = 0;
    v151 = 0;
    v70 = 0;
    v153 = 0;
    std::vector<File>::_Tidy(&v174);
    v71 = v66;
    while ( 1 )
    {
      if ( v71 == (File *)v67 )
      {
        AslTelemetryTrackMetric(qword_1801216A8, "AppInv_Num_Total_Files", -84215045 * ((v67 - (char *)v66) >> 4));
        AslTelemetryTrackMetric(qword_1801216A8, "AppInv_Num_Orphan_Files", v68);
        AslTelemetryTrackMetric(qword_1801216A8, "AppInv_FileIdsCalculated", v69);
        AslTelemetryTrackMetric(qword_1801216A8, "AppInv_FilesMissingId", v70);
        v32 = v150;
        goto LABEL_211;
      }
      Utility::KickWatchdogTimer();
      v72 = File::Verify(v71, v199) - 1;
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
          v160,
          v198,
          v75);
      }
      v76 = v71;
      for ( i = (char *)v71 + 816; i != v67; i += 816 )
      {
        File::operator=(v76, i);
        v76 = (File *)((char *)v76 + 816);
      }
      v67 -= 816;
      v161 = v67;
      (**(void (__fastcall ***)(char *, _QWORD))v67)(v67, 0);
      *((_QWORD *)&v162 + 1) = v67;
      v69 = v151;
LABEL_209:
      v66 = v158;
    }
    if ( v73 == 1 )
    {
      v151 = ++v69;
LABEL_132:
      if ( !(*(unsigned __int8 (__fastcall **)(File *))(*(_QWORD *)v71 + 136LL))(v71)
        && !(*(unsigned __int8 (__fastcall **)(File *))(*(_QWORD *)v71 + 144LL))(v71) )
      {
        v74 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 112LL))(v71);
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
          v160,
          v176,
          v74);
      }
    }
    if ( !(*(unsigned __int8 (__fastcall **)(File *))(*(_QWORD *)v71 + 136LL))(v71) )
    {
      if ( (*(unsigned __int8 (__fastcall **)(File *))(*(_QWORD *)v71 + 144LL))(v71) )
      {
        v149 = ++v68;
      }
      else
      {
        v78 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 112LL))(v71);
        v79 = (_QWORD *)std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(
                          v167,
                          v170,
                          v78);
        if ( *v79 == v167[0] )
        {
          v80 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 112LL))(v71);
          v81 = (_QWORD *)std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(
                            v169,
                            v178,
                            v80);
          if ( *v81 == v169[0] )
          {
            v82 = 0;
            v83 = 0;
            v84 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_Performance>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppInv_Performance>::GetImpl'::`2'::impl) == 0;
            v85 = v155[1];
            v159 = v155[1];
            if ( v84 )
            {
              for ( j = v155[0]; j != v85; j = (const struct Application *)((char *)j + 1008) )
              {
                Application::Application((Application *)v208, j);
                v104 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 24LL))(v71);
                DirectoryFromPath = Utility::GetDirectoryFromPath(v179, v104);
                found = Utility::FoundSubstring(v215, DirectoryFromPath);
                std::wstring::_Tidy_deallocate(v179);
                if ( found && v216 && v216 >= v83 )
                {
                  v107 = v211;
                  if ( v212 > 7 )
                    v107 = (_QWORD *)v211[0];
                  v108 = v215;
                  if ( v217 > 7 )
                    v108 = (_QWORD *)v215[0];
                  v109 = v213;
                  if ( v214 > 7 )
                    v109 = (_QWORD *)v213[0];
                  v110 = (_QWORD *)(*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 112LL))(v71);
                  v111 = v110;
                  if ( v110[3] > 7u )
                    v111 = (_QWORD *)*v110;
                  v112 = (_QWORD *)(*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 24LL))(v71);
                  v113 = v112;
                  if ( v112[3] > 7u )
                    v113 = (_QWORD *)*v112;
                  v114 = (_QWORD *)(*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 32LL))(v71);
                  if ( v114[3] > 7u )
                    v114 = (_QWORD *)*v114;
                  AslLogCallPrintf(
                    3,
                    "GetAppInventory",
                    570,
                    "File's ProgramId no longer exist: %ws | %ws | %ws re-mapped to %ws | %ws | %ws",
                    v114,
                    v113,
                    v111,
                    v109,
                    v108,
                    v107);
                  v83 = v216;
                  std::wstring::operator=((char *)v71 + 88);
                  File::SaveFileToCache(v71, (const struct ConfigSettings *)v199);
                  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
                    v160,
                    &v174,
                    v211);
                  v82 = 1;
                }
                Application::~Application((Application *)v208);
                v85 = v159;
              }
            }
            else
            {
              v86 = v155[0];
              while ( 1 )
              {
                v168 = v86;
                if ( v86 == v85 )
                  break;
                v87 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 24LL))(v71);
                v88 = Utility::GetDirectoryFromPath(v179, v87);
                v89 = (char *)v86 + 16;
                v90 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v89 + 40LL))(v89);
                LOBYTE(v88) = Utility::FoundSubstring(v90, v88);
                std::wstring::_Tidy_deallocate(v179);
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
                  (*(void (__fastcall **)(char *))(*(_QWORD *)v89 + 16LL))(v89);
                  std::wstring::operator=((char *)v71 + 88);
                  File::SaveFileToCache(v71, (const struct ConfigSettings *)v199);
                  v102 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v89 + 16LL))(v89);
                  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
                    v160,
                    v171,
                    v102);
                  v82 = 1;
                }
                v86 = (struct Application *)((char *)v168 + 1008);
                v85 = v159;
              }
            }
            if ( v82 )
            {
              v68 = v149;
            }
            else
            {
              v115 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 24LL))(v71);
              v116 = (const wchar_t *)v115;
              if ( *(_QWORD *)(v115 + 24) > 7u )
                v116 = *(const wchar_t **)v115;
              v117 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 16LL))(v71);
              v118 = (const wchar_t *)v117;
              if ( *(_QWORD *)(v117 + 24) > 7u )
                v118 = *(const wchar_t **)v117;
              v119 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 112LL))(v71);
              v120 = (const wchar_t *)v119;
              if ( *(_QWORD *)(v119 + 24) > 7u )
                v120 = *(const wchar_t **)v119;
              v121 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 8LL))(v71);
              if ( *(_QWORD *)(v121 + 24) > 7u )
                v121 = *(_QWORD *)v121;
              AslLogCallPrintf(
                3,
                "GetAppInventory",
                592,
                "File's ProgramId no longer exist. Calculating new orphan ProgramId. GetFilePathHash: %ls GetProgramId: %"
                "ls GetFileId: %ls GetFilePath: %ls",
                (const wchar_t *)v121,
                v120,
                v118,
                v116);
              (*(void (__fastcall **)(File *))(*(_QWORD *)v71 + 24LL))(v71);
              File::SetBoeProgramId(v71);
              File::SaveFileToCache(v71, (const struct ConfigSettings *)v199);
              v68 = ++v149;
            }
            v67 = v161;
            v70 = v153;
          }
          else
          {
            v122 = (_QWORD *)(*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 24LL))(v71);
            v123 = v122;
            if ( v122[3] > 7u )
              v123 = (_QWORD *)*v122;
            v124 = (_QWORD *)(*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 16LL))(v71);
            v125 = v124;
            if ( v124[3] > 7u )
              v125 = (_QWORD *)*v124;
            v126 = (_QWORD *)(*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 112LL))(v71);
            if ( v126[3] > 7u )
              v126 = (_QWORD *)*v126;
            AslLogCallPrintf(
              3,
              "GetAppInventory",
              514,
              "Per-user app file (user hive not loaded). ProgramId: %ws FileId: %ws FilePath: %ws",
              v126,
              v125,
              v123);
          }
          v69 = v151;
        }
      }
    }
    (*(void (__fastcall **)(_QWORD *, struct Windows::Compat::Inventory::IInventoryDataReceiver *, _QWORD))(*((_QWORD *)v71 + 2) + 8LL))(
      (_QWORD *)v71 + 2,
      v157,
      v150);
    if ( !*(_QWORD *)((*(__int64 (__fastcall **)(File *))(*(_QWORD *)v71 + 16LL))(v71) + 16) )
      v153 = ++v70;
    v71 = (File *)((char *)v71 + 816);
    goto LABEL_209;
  }
  v67 = (char *)*((_QWORD *)&v162 + 1);
  v66 = (struct File *)v162;
  v158 = (struct File *)v162;
LABEL_211:
  if ( (v32 & 0x41000011) != 0 )
  {
    v127 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_Performance>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppInv_Performance>::GetImpl'::`2'::impl) )
    {
      v128 = v155[0];
      v129 = v155[1];
      while ( v128 != v129 )
      {
        Utility::KickWatchdogTimer();
        v130 = (char *)v128 + 16;
        v131 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v128 + 2) + 16LL))((__int64)v128 + 16);
        v132 = (_QWORD *)std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(
                           v160,
                           v178,
                           v131);
        if ( *v132 != v160[0] )
        {
          std::_Tree<std::_Tset_traits<File,std::less<File>,std::allocator<File>,0>>::clear((char *)v128 + 24);
          v133 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v130 + 8LL))((__int64)v128 + 16);
          if ( *(_QWORD *)(v133 + 24) > 7u )
            v133 = *(_QWORD *)v133;
          AslLogCallPrintf(
            3,
            "GetAppInventory",
            630,
            "Updating ProgramInstanceId because of file change/removal. App:%ls",
            (const wchar_t *)v133);
          for ( k = v66; k != (const struct File *)v67; k = (const struct File *)((char *)k + 816) )
          {
            v135 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v130 + 16LL))((__int64)v128 + 16);
            v136 = (_QWORD *)(*(__int64 (__fastcall **)(const struct File *))(*(_QWORD *)k + 112LL))(k);
            if ( v135[3] > 7u )
              v135 = (_QWORD *)*v135;
            v137 = v136[2];
            if ( v136[3] > 7u )
              v136 = (_QWORD *)*v136;
            if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v136, v137, v135) )
              Application::SetFile(v128, k);
          }
          Application::ComputeProgramInstanceId(v128, v179);
          std::wstring::operator=((char *)v128 + 400);
          std::wstring::_Tidy_deallocate(v179);
          Application::SaveApplicationToCache(v128, (const struct ConfigSettings *)v199);
          v66 = v158;
        }
        (*(void (__fastcall **)(__int64, struct Windows::Compat::Inventory::IInventoryDataReceiver *, _QWORD))(*((_QWORD *)v128 + 1) + 8LL))(
          (__int64)v128 + 8,
          v157,
          v150);
        if ( *(_QWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v130 + 80LL))((__int64)v128 + 16) + 16) )
          ++v127;
        v128 = (struct Application *)((char *)v128 + 1008);
      }
    }
    else
    {
      v138 = v155[0];
      v139 = v155[1];
      v140 = v158;
      while ( v138 != v139 )
      {
        Application::Application((Application *)v208, v138);
        Utility::KickWatchdogTimer();
        v141 = (_QWORD *)std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(
                           v160,
                           v178,
                           v211);
        if ( *v141 != v160[0] )
        {
          std::_Tree<std::_Tset_traits<File,std::less<File>,std::allocator<File>,0>>::clear(v210);
          v142 = (const wchar_t *)v213;
          if ( v214 > 7 )
            v142 = (const wchar_t *)v213[0];
          AslLogCallPrintf(
            3,
            "GetAppInventory",
            659,
            "Updating ProgramInstanceId because of file change/removal. App:%ls",
            v142);
          for ( m = v140; m != (const struct File *)v67; m = (const struct File *)((char *)m + 816) )
          {
            File::File((File *)v201, m);
            v144 = v211;
            if ( v212 > 7 )
              v144 = (_QWORD *)v211[0];
            v145 = &v203;
            if ( v204[2] > 7u )
              v145 = v203;
            if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v145, v204[1], v144) )
              Application::SetFile((Application *)v208, (const struct File *)v201);
            File::~File((File *)v201);
          }
          Application::ComputeProgramInstanceId(v208, v179);
          std::wstring::operator=(v218);
          std::wstring::_Tidy_deallocate(v179);
          Application::SaveApplicationToCache((Application *)v208, (const struct ConfigSettings *)v199);
        }
        Application::ProvideInventory((Application *)v209, v157, v150);
        if ( v219 )
          ++v127;
        Application::~Application((Application *)v208);
        v138 = (const struct Application *)((char *)v138 + 1008);
      }
    }
    AslTelemetryTrackMetric(qword_1801216A8, "AppInv_ProgramCount", -1090785345 * ((v155[1] - v155[0]) >> 4));
    AslTelemetryTrackMetric(qword_1801216A8, "AppInv_ProgramIIDCount", v127);
  }
  SetLastInventoryScanTime((struct TelCacheProvider *)&v189);
  v146 = GetTickCount() - TickCount;
  AslLogCallPrintf(3, "GetAppInventory", 749, "GetAppInventory elapsed time: %d (ticks)", v146);
  v147 = GetCurrentThread();
  QueryThreadCycleTime(v147, &v165);
  AslTelemetryTrackMetric(qword_1801216A8, "AppInv_Nightly_Cpu_0.1gCycles", (v165 - CycleTime) / 0x5F5E100);
  AslTelemetryTrackMetric(qword_1801216A8, "AppInv_Nightly_Ms", v146);
  std::vector<File>::_Tidy(&v162);
  std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(
    v160,
    v160);
  std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(
    v167,
    v167);
  std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(
    v169,
    v169);
  if ( v155[0] )
  {
    std::_Destroy_range<std::allocator<Application>>(v155[0], v155[1]);
    std::_Deallocate<16>(v155[0], 16 * ((signed __int64)(v156 - (unsigned __int64)v155[0]) >> 4));
    *(_OWORD *)v155 = 0;
    v156 = 0;
  }
  ConfigSettings::~ConfigSettings((ConfigSettings *)v199);
  Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v154);
  TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v180);
  TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v189);
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
