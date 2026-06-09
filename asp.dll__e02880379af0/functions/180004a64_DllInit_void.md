# DllInit(void)

- ea: `0x180004a64`
- end: `0x18000505d`
- name: `?DllInit@@YAHXZ`
- size: `1529`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `43`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800014c0`

## callees

- `0x180001548`
- `0x18000198c`
- `0x180002220`
- `0x1800038b0`
- `0x180003b6c`
- `0x180003c54`
- `0x180003dd0`
- `0x1800049cc`
- `0x180004a64`
- `0x1800050b8`
- `0x1800051c4`
- `0x180005210`
- `0x18000526c`
- `0x1800052dc`
- `0x18000534c`
- `0x1800053cc`
- `0x180005454`
- `0x180005e30`
- `0x1800070b0`
- `0x18001a950`
- `0x18001be78`
- `0x18001c880`
- `0x18001ca08`
- `0x18001d780`
- `0x180023dd0`
- `0x180032c9c`
- `0x1800352dc`
- `0x180035340`
- `0x18003cf2c`
- `0x18003fd5c`
- `0x18003fe28`
- `0x18003ff24`
- `0x180040ba8`
- `0x1800456ec`
- `0x180048a08`
- `0x180049630`
- `0x180049b2c`
- `0x180049e04`
- `0x180057034`
- `0x180060008`
- `0x180060a84`
- `0x180063c40`
- `0x180064010`

## import_xrefs

- `msvcrt!srand` at `0x180004e36`
- `msvcrt!srand` at `0x180004e36`
- `msvcrt!time` at `0x180004e2d`
- `msvcrt!time` at `0x180004e2d`
- `ole32!CoCreateInstance` at `0x180004fe1`
- `ole32!CoCreateInstance` at `0x180004fe1`
- `KERNEL32!HeapAlloc` at `0x180004d0f`
- `KERNEL32!HeapAlloc` at `0x180004d0f`
- `KERNEL32!HeapDestroy` at `0x180026316`
- `KERNEL32!HeapDestroy` at `0x180026316`
- `KERNEL32!HeapSetInformation` at `0x180004cdc`
- `KERNEL32!HeapSetInformation` at `0x180004cdc`
- `KERNEL32!HeapCreate` at `0x180004cb4`
- `KERNEL32!HeapCreate` at `0x180004cb4`
- `KERNEL32!OutputDebugStringA` at `0x180025c15`
- `KERNEL32!OutputDebugStringA` at `0x180025c15`
- `KERNEL32!LocalAlloc` at `0x180004ea7`
- `KERNEL32!LocalAlloc` at `0x180004ea7`
- `KERNEL32!DeleteCriticalSection` at `0x1800262e5`
- `KERNEL32!DeleteCriticalSection` at `0x18002632e`
- `KERNEL32!DeleteCriticalSection` at `0x18002633b`
- `KERNEL32!DeleteCriticalSection` at `0x180026348`
- `KERNEL32!DeleteCriticalSection` at `0x180026355`
- `KERNEL32!DeleteCriticalSection` at `0x1800262e5`
- `KERNEL32!DeleteCriticalSection` at `0x18002632e`
- `KERNEL32!DeleteCriticalSection` at `0x18002633b`
- `KERNEL32!DeleteCriticalSection` at `0x180026348`
- `KERNEL32!DeleteCriticalSection` at `0x180026355`
- `KERNEL32!GetLastError` at `0x180004b73`
- `KERNEL32!GetLastError` at `0x180004bc5`
- `KERNEL32!GetLastError` at `0x180004c17`
- `KERNEL32!GetLastError` at `0x180004c69`
- `KERNEL32!GetLastError` at `0x180004b73`
- `KERNEL32!GetLastError` at `0x180004bc5`
- `KERNEL32!GetLastError` at `0x180004c17`
- `KERNEL32!GetLastError` at `0x180004c69`
- `iisutil!PuDeleteDebugPrintsObject` at `0x1800263d3`
- `iisutil!PuDeleteDebugPrintsObject` at `0x1800263d3`
- `iisutil!DestroyRefTraceLog` at `0x18002636e`
- `iisutil!DestroyRefTraceLog` at `0x180026387`
- `iisutil!DestroyRefTraceLog` at `0x1800263a0`
- `iisutil!DestroyRefTraceLog` at `0x1800263b9`
- `iisutil!DestroyRefTraceLog` at `0x1800263c6`
- `iisutil!DestroyRefTraceLog` at `0x18002636e`
- `iisutil!DestroyRefTraceLog` at `0x180026387`
- `iisutil!DestroyRefTraceLog` at `0x1800263a0`
- `iisutil!DestroyRefTraceLog` at `0x1800263b9`
- `iisutil!DestroyRefTraceLog` at `0x1800263c6`
- `iisutil!CreateRefTraceLog` at `0x180025c28`
- `iisutil!CreateRefTraceLog` at `0x180025c47`
- `iisutil!CreateRefTraceLog` at `0x180025c66`
- `iisutil!CreateRefTraceLog` at `0x180025c85`
- `iisutil!CreateRefTraceLog` at `0x180025ca4`
- `iisutil!CreateRefTraceLog` at `0x180025c28`
- `iisutil!CreateRefTraceLog` at `0x180025c47`
- `iisutil!CreateRefTraceLog` at `0x180025c66`
- `iisutil!CreateRefTraceLog` at `0x180025c85`
- `iisutil!CreateRefTraceLog` at `0x180025ca4`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x180004af6`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x180004af6`
- `iisutil!PuCreateDebugPrintsObject` at `0x180004abc`
- `iisutil!PuCreateDebugPrintsObject` at `0x180004abc`
- `iisutil!PuDbgPrint` at `0x180025cd5`
- `iisutil!PuDbgPrint` at `0x180025d00`
- `iisutil!PuDbgPrint` at `0x180025d2b`
- `iisutil!PuDbgPrint` at `0x180025dab`
- `iisutil!PuDbgPrint` at `0x180025dd6`
- `iisutil!PuDbgPrint` at `0x180025e01`
- `iisutil!PuDbgPrint` at `0x180025e2c`
- `iisutil!PuDbgPrint` at `0x180025e57`
- `iisutil!PuDbgPrint` at `0x180025e82`
- `iisutil!PuDbgPrint` at `0x180025ead`
- `iisutil!PuDbgPrint` at `0x180025ed8`
- `iisutil!PuDbgPrint` at `0x180025f0a`
- `iisutil!PuDbgPrint` at `0x180025f35`
- `iisutil!PuDbgPrint` at `0x180025f60`
- `iisutil!PuDbgPrint` at `0x180025f8b`
- `iisutil!PuDbgPrint` at `0x180025fb6`
- `iisutil!PuDbgPrint` at `0x180025fe1`
- `iisutil!PuDbgPrint` at `0x18002600c`
- `iisutil!PuDbgPrint` at `0x180026047`
- `iisutil!PuDbgPrint` at `0x180026072`
- `iisutil!PuDbgPrint` at `0x1800260a5`
- `iisutil!PuDbgPrint` at `0x1800260d0`
- `iisutil!PuDbgPrint` at `0x180026116`
- `iisutil!PuDbgPrint` at `0x180025cd5`
- `iisutil!PuDbgPrint` at `0x180025d00`
- `iisutil!PuDbgPrint` at `0x180025d2b`
- `iisutil!PuDbgPrint` at `0x180025dab`
- `iisutil!PuDbgPrint` at `0x180025dd6`
- `iisutil!PuDbgPrint` at `0x180025e01`
- `iisutil!PuDbgPrint` at `0x180025e2c`
- `iisutil!PuDbgPrint` at `0x180025e57`
- `iisutil!PuDbgPrint` at `0x180025e82`
- `iisutil!PuDbgPrint` at `0x180025ead`
- `iisutil!PuDbgPrint` at `0x180025ed8`
- `iisutil!PuDbgPrint` at `0x180025f0a`
- `iisutil!PuDbgPrint` at `0x180025f35`
- `iisutil!PuDbgPrint` at `0x180025f60`
- `iisutil!PuDbgPrint` at `0x180025f8b`
- `iisutil!PuDbgPrint` at `0x180025fb6`
- `iisutil!PuDbgPrint` at `0x180025fe1`
- `iisutil!PuDbgPrint` at `0x18002600c`
- `iisutil!PuDbgPrint` at `0x180026047`
- `iisutil!PuDbgPrint` at `0x180026072`
- `iisutil!PuDbgPrint` at `0x1800260a5`
- `iisutil!PuDbgPrint` at `0x1800260d0`
- `iisutil!PuDbgPrint` at `0x180026116`
- `iisutil!IISInitializeCriticalSection` at `0x180004b69`
- `iisutil!IISInitializeCriticalSection` at `0x180004bbb`
- `iisutil!IISInitializeCriticalSection` at `0x180004c0d`
- `iisutil!IISInitializeCriticalSection` at `0x180004c5f`
- `iisutil!IISInitializeCriticalSection` at `0x180004b69`
- `iisutil!IISInitializeCriticalSection` at `0x180004bbb`
- `iisutil!IISInitializeCriticalSection` at `0x180004c0d`
- `iisutil!IISInitializeCriticalSection` at `0x180004c5f`

## string_xrefs

- `0x180004a7d`: `System\CurrentControlSet\Services\W3Svc\ASP`
- `0x180025c0e`: `Unable to Create Debug Print Object \n`
- `0x180004b46`: `DllInit`
- `0x180004b97`: `DllInit`
- `0x180004be9`: `DllInit`
- `0x180004c3b`: `DllInit`
- `0x180004c8d`: `DllInit`
- `0x1800260e3`: `DllInit`
- `0x180025d8c`: `ASP Init -- Per-Class Cache Init\n`
- `0x180025db7`: `ASP Init -- Cached BSTRs Init\n`
- `0x180025de2`: `ASP Init -- Cache Std TypeInfos\n`
- `0x180025e0d`: `ASP Init -- Typelib Cache Init\n`
- `0x180025f41`: `ASP Init -- Template Cache Init\n`
- `0x180025fed`: `ASP Init -- CTemplate Init Class\n`
- `0x1800260b1`: `ASP Init -- Denali DLL Initialized\n`
- `0x1800260f7`: `ASP Init -- Error in DllInit.  initStatus = %d\n`

## pseudocode

```c
__int64 DllInit(void)
{
  unsigned int v0; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v1; // rdx
  ATL::CComModule *v2; // rcx
  int DebugFlagsFromRegStr; // eax
  CPerfProcBlock *v4; // rcx
  signed int v5; // edi
  signed int LastError; // eax
  signed int v7; // edi
  signed int v8; // eax
  signed int v9; // edi
  signed int v10; // eax
  signed int v11; // edi
  signed int v12; // eax
  HANDLE v13; // rax
  CDirMonitor *v14; // rax
  HINSTANCE v15; // r8
  const struct _GUID *v16; // r9
  unsigned int v17; // eax
  CIdGenerator *v18; // rcx
  HRESULT Instance; // eax
  unsigned int v21; // ebx
  unsigned int v22; // ebx
  unsigned int v23; // ebx
  unsigned int v24; // ebx
  unsigned int v25; // ebx
  unsigned int v26; // ebx
  unsigned int v27; // ebx
  unsigned int v28; // ebx
  unsigned int v29; // ebx
  unsigned int v30; // ebx
  unsigned int v31; // ebx
  unsigned int v32; // ebx
  unsigned int v33; // ebx
  unsigned int v34; // ebx
  unsigned int v35; // ebx
  unsigned int v36; // ebx
  unsigned int v37; // ebx
  unsigned int v38; // ebx
  unsigned int v39; // ebx
  int HeapInformation; // [rsp+34h] [rbp-64h] BYREF
  char v41[48]; // [rsp+38h] [rbp-60h] BYREF

  strcpy(v41, "System\\CurrentControlSet\\Services\\W3Svc\\ASP");
  if ( (int)InitializeResourceDll() < 0 )
    return 0;
  v0 = 1;
  g_pDebug = PuCreateDebugPrintsObject(&g_pszASPModuleName, 1);
  if ( !g_pDebug )
    OutputDebugStringA("Unable to Create Debug Print Object \n");
  if ( !g_pDebug || !*(_DWORD *)(g_pDebug + 640) )
    goto LABEL_120;
  DebugFlagsFromRegStr = PuLoadDebugFlagsFromRegStr(v41, 0);
  g_dwDebugFlags = DebugFlagsFromRegStr;
  if ( (DebugFlagsFromRegStr & 0x1000) != 0 )
  {
    CTemplate::gm_pTraceLog = (struct _TRACE_LOG *)CreateRefTraceLog(5000, 0);
    DebugFlagsFromRegStr = g_dwDebugFlags;
  }
  if ( (DebugFlagsFromRegStr & 0x100000) != 0 )
  {
    CSession::gm_pTraceLog = (struct _TRACE_LOG *)CreateRefTraceLog(5000, 0);
    DebugFlagsFromRegStr = g_dwDebugFlags;
  }
  if ( (DebugFlagsFromRegStr & 0x80000) != 0 )
  {
    CAppln::gm_pTraceLog = (struct _TRACE_LOG *)CreateRefTraceLog(5000, 0);
    DebugFlagsFromRegStr = g_dwDebugFlags;
  }
  if ( (DebugFlagsFromRegStr & 0x800) != 0 )
  {
    CASPDirMonitorEntry::gm_pTraceLog = (struct _TRACE_LOG *)CreateRefTraceLog(500, 0);
    DebugFlagsFromRegStr = g_dwDebugFlags;
  }
  if ( (DebugFlagsFromRegStr & 0x80000) != 0 )
    CAppConfig::gm_pTraceLog = (struct _TRACE_LOG *)CreateRefTraceLog(500, 0);
  v0 = 3;
  if ( (int)CPerfProcBlock::InitCriticalSections(v4) < 0 )
    goto LABEL_120;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
      459,
      "DllInit",
      "ASP Init -- PerfMon Data PreInit\n");
  v5 = 0;
  if ( !(unsigned int)IISInitializeCriticalSection(&g_csEventlogLock) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
  }
  v0 = 4;
  if ( v5 < 0 )
    goto LABEL_120;
  v7 = 0;
  if ( !(unsigned int)IISInitializeCriticalSection(&g_csFirstHitLock) )
  {
    v8 = GetLastError();
    v7 = v8;
    if ( v8 > 0 )
      v7 = (unsigned __int16)v8 | 0x80070000;
  }
  v0 = 5;
  if ( v7 < 0 )
    goto LABEL_120;
  v9 = 0;
  if ( !(unsigned int)IISInitializeCriticalSection(&g_csFirstMTAHitLock) )
  {
    v10 = GetLastError();
    v9 = v10;
    if ( v10 > 0 )
      v9 = (unsigned __int16)v10 | 0x80070000;
  }
  v0 = 6;
  if ( v9 < 0 )
    goto LABEL_120;
  v11 = 0;
  if ( !(unsigned int)IISInitializeCriticalSection(&g_csFirstSTAHitLock) )
  {
    v12 = GetLastError();
    v11 = v12;
    if ( v12 > 0 )
      v11 = (unsigned __int16)v12 | 0x80070000;
  }
  v0 = 7;
  if ( v11 < 0 )
    goto LABEL_120;
  v0 = 8;
  v13 = HeapCreate(0, 0, 0);
  g_hDenaliHeap = v13;
  if ( v13 )
  {
    HeapInformation = 2;
    HeapSetInformation(v13, HeapCompatibilityInformation, &HeapInformation, 4u);
  }
  if ( !g_hDenaliHeap )
    goto LABEL_120;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(g_pDebug, "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp", 492, "DllInit", "ASP Init -- Denali Memory Init\n");
  v0 = 9;
  v14 = (CDirMonitor *)HeapAlloc(g_hDenaliHeap, 0, 0x78u);
  if ( v14 )
    v14 = CDirMonitor::CDirMonitor(v14);
  g_pDirMonitor = v14;
  if ( !v14 )
    goto LABEL_120;
  v0 = 10;
  ATL::CComModule::Init(v2, v1, v15, v16);
  if ( (int)GlobInit() < 0 )
    goto LABEL_120;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(g_pDebug, "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp", 508, "DllInit", "ASP Init -- Glob Init\n");
  v0 = 11;
  if ( (g_AspRegistryParams & 0x400) != 0 )
    g_fOOMRecycleDisabled = *(_DWORD *)&dword_18007D85C;
  if ( (g_AspRegistryParams & 0x800) != 0 )
    g_fLazyContentPropDisabled = *(_DWORD *)&dword_18007D860;
  if ( (g_AspRegistryParams & 0x20) != 0 )
    g_fUNCChangeNotificationEnabled = *(_DWORD *)&dword_18007D848;
  if ( (g_AspRegistryParams & 0x80u) != 0 )
    g_dwFileMonitoringTimeoutSecs = *(_DWORD *)&dword_18007D850;
  if ( (g_AspRegistryParams & 0x4000) != 0 )
    g_dwDisableCertificateBlobAsArray = *(_DWORD *)&dword_18007D878;
  if ( (int)InitMemCls() < 0 )
    goto LABEL_120;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
      533,
      "DllInit",
      "ASP Init -- Per-Class Cache Init\n");
  v0 = 12;
  if ( (int)InitCachedBSTRs() < 0 )
    goto LABEL_120;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(g_pDebug, "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp", 539, "DllInit", "ASP Init -- Cached BSTRs Init\n");
  v0 = 13;
  if ( (int)CacheStdTypeInfos() < 0 )
    goto LABEL_120;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
      545,
      "DllInit",
      "ASP Init -- Cache Std TypeInfos\n");
  v0 = 14;
  if ( (int)CTypelibCache::Init(v2) < 0 )
    goto LABEL_120;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(g_pDebug, "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp", 551, "DllInit", "ASP Init -- Typelib Cache Init\n");
  v0 = 15;
  if ( (int)ErrHandleInit() < 0 )
    goto LABEL_120;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(g_pDebug, "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp", 557, "DllInit", "ASP Init -- Err Handler Init\n");
  v0 = 16;
  v17 = time(0);
  srand(v17);
  if ( (int)CIdGenerator::Init(v18) < 0 || (int)CIdGenerator::Init(v2, v1) < 0 )
    goto LABEL_120;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
      568,
      "DllInit",
      "ASP Init -- SessionID Generator Init\n");
  if ( (int)InitRandGenerator() < 0 )
    goto LABEL_120;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(g_pDebug, "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp", 572, "DllInit", "ASP Init -- RandGen Init\n");
  v0 = 17;
  if ( (int)CApplnMgr::Init(v2) < 0 )
    goto LABEL_120;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(g_pDebug, "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp", 578, "DllInit", "ASP Init -- Appln Mgr Init\n");
  v0 = 18;
  v1 = (struct ATL::_ATL_OBJMAP_ENTRY30 *)LocalAlloc(0x40u, 0x10u);
  if ( v1 )
  {
    *(_QWORD *)v1 = &CConfigNotification::`vftable';
    *((_DWORD *)v1 + 2) = 1;
  }
  else
  {
    v1 = 0;
  }
  g_pNotifySink = v1;
  if ( !v1
    || (*(int (__fastcall **)(struct INativeConfigurationSystem *))(*(_QWORD *)g_pConfigSystem + 40LL))(g_pConfigSystem) < 0 )
  {
    goto LABEL_120;
  }
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
      589,
      "DllInit",
      "ASP Init -- Change Notification Init\n");
  v0 = 19;
  if ( (int)Init449() < 0 )
    goto LABEL_120;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(g_pDebug, "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp", 596, "DllInit", "ASP Init -- 449 Mgr Init\n");
  v0 = 20;
  if ( (int)CTemplateCacheManager::Init(v2) < 0 )
    goto LABEL_120;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
      603,
      "DllInit",
      "ASP Init -- Template Cache Init\n");
  v0 = 21;
  if ( (int)CIncFileMap::Init(v2) < 0 )
    goto LABEL_120;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
      609,
      "DllInit",
      "ASP Init -- Inc File Users Init\n");
  v0 = 22;
  if ( (int)CFileApplicationMap::Init(v2) < 0 )
    goto LABEL_120;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
      615,
      "DllInit",
      "ASP Init -- File-Application Map Init\n");
  v0 = 23;
  if ( (int)CScriptManager::Init(v2) < 0 )
    goto LABEL_120;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
      622,
      "DllInit",
      "ASP Init -- Script Manager Init\n");
  v0 = 24;
  if ( (int)CTemplate::InitClass() < 0 )
    goto LABEL_120;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
      628,
      "DllInit",
      "ASP Init -- CTemplate Init Class\n");
  v0 = 25;
  Instance = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &IID_IGlobalInterfaceTable, &ppv);
  if ( Instance < 0 )
    ppv = 0;
  else
    g_GIPAPI |= 1u;
  if ( Instance < 0 )
    goto LABEL_120;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
      634,
      "DllInit",
      "ASP Init -- Global Interface API Init\n");
  v0 = 26;
  if ( (int)CMTACallbackThread::Init(v2) < 0 )
  {
LABEL_120:
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
        663,
        "DllInit",
        "ASP Init -- Error in DllInit.  initStatus = %d\n",
        v0);
    if ( v0 <= 0xF )
    {
      if ( v0 != 15 )
      {
        if ( v0 <= 8 )
        {
          if ( v0 != 8 )
          {
            v21 = v0 - 1;
            if ( !v21 )
            {
LABEL_196:
              UninitializeResourceDll();
              return 0;
            }
            v22 = v21 - 1;
            if ( !v22 )
            {
LABEL_195:
              g_pDebug = PuDeleteDebugPrintsObject(g_pDebug);
              goto LABEL_196;
            }
            v23 = v22 - 1;
            if ( !v23 )
            {
LABEL_186:
              if ( (g_dwDebugFlags & 0x1000) != 0 )
                DestroyRefTraceLog(CTemplate::gm_pTraceLog);
              if ( (g_dwDebugFlags & 0x100000) != 0 )
                DestroyRefTraceLog(CSession::gm_pTraceLog);
              if ( (g_dwDebugFlags & 0x80000) != 0 )
                DestroyRefTraceLog(CAppln::gm_pTraceLog);
              if ( (g_dwDebugFlags & 0x800) != 0 )
                DestroyRefTraceLog(CASPDirMonitorEntry::gm_pTraceLog);
              DestroyRefTraceLog(CAppConfig::gm_pTraceLog);
              goto LABEL_195;
            }
            v24 = v23 - 2;
            if ( !v24 )
            {
LABEL_185:
              DeleteCriticalSection(&g_csEventlogLock);
              goto LABEL_186;
            }
            v25 = v24 - 1;
            if ( !v25 )
            {
LABEL_184:
              DeleteCriticalSection(&g_csFirstHitLock);
              goto LABEL_185;
            }
            if ( v25 != 1 )
              return 0;
LABEL_183:
            DeleteCriticalSection(&g_csFirstMTAHitLock);
            goto LABEL_184;
          }
LABEL_182:
          DeleteCriticalSection(&g_csFirstSTAHitLock);
          goto LABEL_183;
        }
        v26 = v0 - 9;
        if ( !v26 )
        {
LABEL_180:
          if ( g_hDenaliHeap )
          {
            HeapDestroy(g_hDenaliHeap);
            g_hDenaliHeap = 0;
          }
          goto LABEL_182;
        }
        v27 = v26 - 1;
        if ( !v27 )
        {
LABEL_177:
          if ( g_pDirMonitor )
            CDirMonitor::`scalar deleting destructor'(g_pDirMonitor, (unsigned int)v1);
          g_pDirMonitor = 0;
          goto LABEL_180;
        }
        v28 = v27 - 1;
        if ( !v28 )
        {
LABEL_174:
          if ( g_pConfigSystem )
          {
            (*(void (__fastcall **)(struct INativeConfigurationSystem *))(*(_QWORD *)g_pConfigSystem + 16LL))(g_pConfigSystem);
            g_pConfigSystem = 0;
          }
          DeleteCriticalSection(&stru_180079FC0);
          goto LABEL_177;
        }
        v29 = v28 - 1;
        if ( !v29 )
        {
LABEL_173:
          UnInitMemCls();
          goto LABEL_174;
        }
        v30 = v29 - 1;
        if ( !v30 )
        {
LABEL_172:
          UnInitCachedBSTRs();
          goto LABEL_173;
        }
        if ( v30 != 1 )
          return 0;
LABEL_171:
        UnCacheStdTypeInfos();
        goto LABEL_172;
      }
LABEL_170:
      CTypelibCache::UnInit((CTypelibCache *)&g_TypelibCache);
      goto LABEL_171;
    }
    if ( v0 > 0x16 )
    {
      v36 = v0 - 23;
      if ( v36 )
      {
        v37 = v36 - 1;
        if ( v37 )
        {
          v38 = v37 - 1;
          if ( v38 )
          {
            v39 = v38 - 1;
            if ( v39 )
            {
              if ( v39 != 1 )
                return 0;
              CMTACallbackThread::UnInit(v2);
            }
            CGlobalInterfaceAPI::UnInit((CGlobalInterfaceAPI *)&g_GIPAPI);
          }
          CTemplate::UnInitClass();
        }
        CScriptManager::UnInit(v2);
      }
      CFileApplicationMap::UnInit((CFileApplicationMap *)&g_FileAppMap);
      if ( g_pDirMonitor )
        CDirMonitor::Cleanup(v2);
    }
    else if ( v0 != 22 )
    {
      v31 = v0 - 16;
      if ( !v31 )
      {
LABEL_169:
        ErrHandleUnInit();
        goto LABEL_170;
      }
      v32 = v31 - 1;
      if ( !v32 )
      {
LABEL_168:
        UnInitRandGenerator();
        goto LABEL_169;
      }
      v33 = v32 - 1;
      if ( !v33 )
      {
LABEL_167:
        CApplnMgr::UnInit((CApplnMgr *)&g_ApplnMgr);
        goto LABEL_168;
      }
      v34 = v33 - 1;
      if ( !v34 )
      {
LABEL_163:
        if ( g_pConfigSystem )
          (*(void (__fastcall **)(struct INativeConfigurationSystem *, struct CConfigNotification *))(*(_QWORD *)g_pConfigSystem + 48LL))(
            g_pConfigSystem,
            g_pNotifySink);
        if ( g_pNotifySink )
        {
          (*(void (__fastcall **)(struct CConfigNotification *))(*(_QWORD *)g_pNotifySink + 16LL))(g_pNotifySink);
          g_pNotifySink = 0;
        }
        goto LABEL_167;
      }
      v35 = v34 - 1;
      if ( !v35 )
      {
LABEL_162:
        UnInit449();
        goto LABEL_163;
      }
      if ( v35 != 1 )
        return 0;
LABEL_161:
      CTemplateCacheManager::UnInit(v2);
      goto LABEL_162;
    }
    CIncFileMap::UnInit(v2);
    goto LABEL_161;
  }
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    PuDbgPrint(g_pDebug, "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp", 641, "DllInit", "ASP Init -- MTA Callbacks Init\n");
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
        647,
        "DllInit",
        "ASP Init -- Request Support Init\n");
  }
  AdjustProcessSecurityToAllowPowerUsersToWait();
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cpp",
      651,
      "DllInit",
      "ASP Init -- Denali DLL Initialized\n");
  return 1;
}

```

## disassembly

```asm
0x180004a64  push    rbx
0x180004a66  push    rsi
0x180004a67  push    rdi
0x180004a68  push    r14
0x180004a6a  sub     rsp, 78h
0x180004a6e  mov     rax, cs:__security_cookie
0x180004a75  xor     rax, rsp
0x180004a78  mov     [rsp+98h+var_30], rax
0x180004a7d  movups  xmm0, xmmword ptr cs:aSystemCurrentc; "System\\CurrentControlSet\\Services\\W3"...
0x180004a84  movups  xmmword ptr [rsp+98h+var_60], xmm0
0x180004a89  movups  xmm1, xmmword ptr cs:aSystemCurrentc+10h; "ntrolSet\\Services\\W3Svc\\ASP"
0x180004a90  movups  xmmword ptr [rsp+98h+var_60+10h], xmm1
0x180004a95  movups  xmm0, xmmword ptr cs:aSystemCurrentc+1Ch; "vices\\W3Svc\\ASP"
0x180004a9c  movups  xmmword ptr [rsp+98h+var_60+1Ch], xmm0
0x180004aa1  call    ?InitializeResourceDll@@YAJXZ; InitializeResourceDll(void)
0x180004aa6  test    eax, eax
0x180004aa8  js      loc_180005059
0x180004aae  mov     ebx, 1
0x180004ab3  mov     edx, ebx
0x180004ab5  lea     rcx, ?g_pszASPModuleName@@3PADA; char near * g_pszASPModuleName
0x180004abc  call    cs:__imp_PuCreateDebugPrintsObject
0x180004ac2  mov     cs:g_pDebug, rax
0x180004ac9  test    rax, rax
0x180004acc  jz      loc_180025C0E
0x180004ad2  mov     rax, cs:g_pDebug
0x180004ad9  test    rax, rax
0x180004adc  jz      loc_1800260DC
0x180004ae2  cmp     dword ptr [rax+280h], 0
0x180004ae9  jz      loc_1800260DC
0x180004aef  xor     edx, edx
0x180004af1  lea     rcx, [rsp+98h+var_60]
0x180004af6  call    cs:__imp_PuLoadDebugFlagsFromRegStr
0x180004afc  mov     cs:g_dwDebugFlags, eax
0x180004b02  bt      eax, 0Ch
0x180004b06  jb      loc_180025C21
0x180004b0c  bt      eax, 14h
0x180004b10  jb      loc_180025C40
0x180004b16  bt      eax, 13h
0x180004b1a  jb      loc_180025C5F
0x180004b20  bt      eax, 0Bh
0x180004b24  jb      loc_180025C7E
0x180004b2a  bt      eax, 13h
0x180004b2e  jb      loc_180025C9D
0x180004b34  mov     ebx, 3
0x180004b39  call    ?InitCriticalSections@CPerfProcBlock@@QEAAJXZ; CPerfProcBlock::InitCriticalSections(void)
0x180004b3e  test    eax, eax
0x180004b40  js      loc_1800260DC
0x180004b46  lea     rsi, aDllinit; "DllInit"
0x180004b4d  lea     r14, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cp"...
0x180004b54  test    byte ptr cs:g_dwDebugFlags, bl
0x180004b5a  jnz     loc_180025CB6
0x180004b60  xor     edi, edi
0x180004b62  lea     rcx, ?g_csEventlogLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csEventlogLock
0x180004b69  call    cs:__imp_IISInitializeCriticalSection
0x180004b6f  test    eax, eax
0x180004b71  jnz     short loc_180004B8C
0x180004b73  call    cs:__imp_GetLastError
0x180004b79  mov     edi, eax
0x180004b7b  test    eax, eax
0x180004b7d  jle     short loc_180004B88
0x180004b7f  movzx   edi, ax
0x180004b82  or      edi, 80070000h
0x180004b88  mov     [rsp+98h+var_68], edi
0x180004b8c  jmp     short loc_180004BA5
0x180004b8e  mov     edi, 8000FFFFh
0x180004b93  mov     [rsp+98h+var_68], edi
0x180004b97  lea     rsi, aDllinit; "DllInit"
0x180004b9e  lea     r14, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cp"...
0x180004ba5  mov     ebx, 4
0x180004baa  test    edi, edi
0x180004bac  js      loc_1800260EA
0x180004bb2  xor     edi, edi
0x180004bb4  lea     rcx, ?g_csFirstHitLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csFirstHitLock
0x180004bbb  call    cs:__imp_IISInitializeCriticalSection
0x180004bc1  test    eax, eax
0x180004bc3  jnz     short loc_180004BDE
0x180004bc5  call    cs:__imp_GetLastError
0x180004bcb  mov     edi, eax
0x180004bcd  test    eax, eax
0x180004bcf  jle     short loc_180004BDA
0x180004bd1  movzx   edi, ax
0x180004bd4  or      edi, 80070000h
0x180004bda  mov     [rsp+98h+var_68], edi
0x180004bde  jmp     short loc_180004BF7
0x180004be0  mov     edi, 8000FFFFh
0x180004be5  mov     [rsp+98h+var_68], edi
0x180004be9  lea     rsi, aDllinit; "DllInit"
0x180004bf0  lea     r14, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cp"...
0x180004bf7  mov     ebx, 5
0x180004bfc  test    edi, edi
0x180004bfe  js      loc_1800260EA
0x180004c04  xor     edi, edi
0x180004c06  lea     rcx, ?g_csFirstMTAHitLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csFirstMTAHitLock
0x180004c0d  call    cs:__imp_IISInitializeCriticalSection
0x180004c13  test    eax, eax
0x180004c15  jnz     short loc_180004C30
0x180004c17  call    cs:__imp_GetLastError
0x180004c1d  mov     edi, eax
0x180004c1f  test    eax, eax
0x180004c21  jle     short loc_180004C2C
0x180004c23  movzx   edi, ax
0x180004c26  or      edi, 80070000h
0x180004c2c  mov     [rsp+98h+var_68], edi
0x180004c30  jmp     short loc_180004C49
0x180004c32  mov     edi, 8000FFFFh
0x180004c37  mov     [rsp+98h+var_68], edi
0x180004c3b  lea     rsi, aDllinit; "DllInit"
0x180004c42  lea     r14, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cp"...
0x180004c49  mov     ebx, 6
0x180004c4e  test    edi, edi
0x180004c50  js      loc_1800260EA
0x180004c56  xor     edi, edi
0x180004c58  lea     rcx, ?g_csFirstSTAHitLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csFirstSTAHitLock
0x180004c5f  call    cs:__imp_IISInitializeCriticalSection
0x180004c65  test    eax, eax
0x180004c67  jnz     short loc_180004C82
0x180004c69  call    cs:__imp_GetLastError
0x180004c6f  mov     edi, eax
0x180004c71  test    eax, eax
0x180004c73  jle     short loc_180004C7E
0x180004c75  movzx   edi, ax
0x180004c78  or      edi, 80070000h
0x180004c7e  mov     [rsp+98h+var_68], edi
0x180004c82  jmp     short loc_180004C9B
0x180004c84  mov     edi, 8000FFFFh
0x180004c89  mov     [rsp+98h+var_68], edi
0x180004c8d  lea     rsi, aDllinit; "DllInit"
0x180004c94  lea     r14, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\cmp\\asp\\denali.cp"...
0x180004c9b  mov     ebx, 7
0x180004ca0  test    edi, edi
0x180004ca2  js      loc_1800260EA
0x180004ca8  mov     ebx, 8
0x180004cad  xor     r8d, r8d; dwMaximumSize
0x180004cb0  xor     edx, edx; dwInitialSize
0x180004cb2  xor     ecx, ecx; flOptions
0x180004cb4  call    cs:__imp_HeapCreate
0x180004cba  mov     cs:?g_hDenaliHeap@@3PEAXEA, rax; void * g_hDenaliHeap
0x180004cc1  test    rax, rax
0x180004cc4  jz      short loc_180004CE2
0x180004cc6  mov     [rsp+98h+HeapInformation], 2
0x180004cce  lea     r9d, [rbx-4]; HeapInformationLength
0x180004cd2  lea     r8, [rsp+98h+HeapInformation]; HeapInformation
0x180004cd7  xor     edx, edx; HeapInformationClass
0x180004cd9  mov     rcx, rax; HeapHandle
0x180004cdc  call    cs:__imp_HeapSetInformation
0x180004ce2  cmp     cs:?g_hDenaliHeap@@3PEAXEA, 0; void * g_hDenaliHeap
0x180004cea  jz      loc_1800260EA
0x180004cf0  test    byte ptr cs:g_dwDebugFlags, 3
0x180004cf7  jnz     loc_180025CE1
0x180004cfd  mov     ebx, 9
0x180004d02  xor     edx, edx; dwFlags
0x180004d04  lea     r8d, [rbx+6Fh]; dwBytes
0x180004d08  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180004d0f  call    cs:__imp_HeapAlloc
0x180004d15  test    rax, rax
0x180004d18  jz      short loc_180004D22
0x180004d1a  mov     rcx, rax; this
0x180004d1d  call    ??0CDirMonitor@@QEAA@XZ; CDirMonitor::CDirMonitor(void)
0x180004d22  mov     cs:?g_pDirMonitor@@3PEAVCDirMonitor@@EA, rax; CDirMonitor * g_pDirMonitor
0x180004d29  test    rax, rax
0x180004d2c  jz      loc_1800260EA
0x180004d32  mov     ebx, 0Ah
0x180004d37  call    ?Init@CComModule@ATL@@QEAAJPEAU_ATL_OBJMAP_ENTRY30@2@PEAUHINSTANCE__@@PEBU_GUID@@@Z; ATL::CComModule::Init(ATL::_ATL_OBJMAP_ENTRY30 *,HINSTANCE__ *,_GUID const *)
0x180004d3c  call    ?GlobInit@@YAJXZ; GlobInit(void)
0x180004d41  test    eax, eax
0x180004d43  js      loc_1800260EA
0x180004d49  test    byte ptr cs:g_dwDebugFlags, 3
0x180004d50  jnz     loc_180025D0C
0x180004d56  mov     ebx, 0Bh
0x180004d5b  mov     ecx, cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A; CAspRegistryParams g_AspRegistryParams
0x180004d61  bt      ecx, 0Ah
0x180004d65  jb      loc_180025D37
0x180004d6b  bt      ecx, 0Bh
0x180004d6f  jb      loc_180025D48
0x180004d75  test    cl, 20h
0x180004d78  jnz     loc_180025D59
0x180004d7e  test    cl, cl
0x180004d80  js      loc_180025D6A
0x180004d86  bt      ecx, 0Eh
0x180004d8a  jb      loc_180025D7B
0x180004d90  call    ?InitMemCls@@YAJXZ; InitMemCls(void)
0x180004d95  test    eax, eax
0x180004d97  js      loc_1800260EA
0x180004d9d  test    byte ptr cs:g_dwDebugFlags, 3
0x180004da4  jnz     loc_180025D8C
0x180004daa  mov     ebx, 0Ch
0x180004daf  call    ?InitCachedBSTRs@@YAJXZ; InitCachedBSTRs(void)
0x180004db4  test    eax, eax
0x180004db6  js      loc_1800260EA
0x180004dbc  test    byte ptr cs:g_dwDebugFlags, 3
0x180004dc3  jnz     loc_180025DB7
0x180004dc9  mov     ebx, 0Dh
0x180004dce  call    ?CacheStdTypeInfos@@YAJXZ; CacheStdTypeInfos(void)
0x180004dd3  test    eax, eax
0x180004dd5  js      loc_1800260EA
0x180004ddb  test    byte ptr cs:g_dwDebugFlags, 3
0x180004de2  jnz     loc_180025DE2
0x180004de8  mov     ebx, 0Eh
0x180004ded  call    ?Init@CTypelibCache@@QEAAJXZ; CTypelibCache::Init(void)
0x180004df2  test    eax, eax
0x180004df4  js      loc_1800260EA
0x180004dfa  test    byte ptr cs:g_dwDebugFlags, 3
0x180004e01  jnz     loc_180025E0D
0x180004e07  mov     ebx, 0Fh
0x180004e0c  call    ?ErrHandleInit@@YAJXZ; ErrHandleInit(void)
0x180004e11  test    eax, eax
0x180004e13  js      loc_1800260EA
0x180004e19  test    byte ptr cs:g_dwDebugFlags, 3
0x180004e20  jnz     loc_180025E38
0x180004e26  mov     ebx, 10h
0x180004e2b  xor     ecx, ecx; Time
0x180004e2d  call    cs:__imp_time
0x180004e33  mov     rcx, rax; Seed
0x180004e36  call    cs:__imp_srand
0x180004e3c  call    ?Init@CIdGenerator@@QEAAJXZ; CIdGenerator::Init(void)
0x180004e41  test    eax, eax
0x180004e43  js      loc_1800260EA
0x180004e49  call    ?Init@CIdGenerator@@QEAAJAEAV1@@Z; CIdGenerator::Init(CIdGenerator &)
0x180004e4e  test    eax, eax
0x180004e50  js      loc_1800260EA
0x180004e56  test    byte ptr cs:g_dwDebugFlags, 3
0x180004e5d  jnz     loc_180025E63
0x180004e63  call    ?InitRandGenerator@@YAJXZ; InitRandGenerator(void)
0x180004e68  test    eax, eax
0x180004e6a  js      loc_1800260EA
0x180004e70  test    byte ptr cs:g_dwDebugFlags, 3
0x180004e77  jnz     loc_180025E8E
0x180004e7d  mov     ebx, 11h
0x180004e82  call    ?Init@CApplnMgr@@QEAAJXZ; CApplnMgr::Init(void)
0x180004e87  test    eax, eax
0x180004e89  js      loc_1800260EA
0x180004e8f  test    byte ptr cs:g_dwDebugFlags, 3
0x180004e96  jnz     loc_180025EB9
0x180004e9c  mov     ebx, 12h
0x180004ea1  lea     edx, [rbx-2]; uBytes
0x180004ea4  lea     ecx, [rbx+2Eh]; uFlags
0x180004ea7  call    cs:__imp_LocalAlloc
0x180004ead  mov     rdx, rax
0x180004eb0  test    rax, rax
0x180004eb3  jz      loc_180025EE4
0x180004eb9  lea     rax, ??_7CConfigNotification@@6B@; const CConfigNotification::`vftable'
0x180004ec0  mov     [rdx], rax
0x180004ec3  mov     dword ptr [rdx+8], 1
0x180004eca  mov     cs:?g_pNotifySink@@3PEAVCConfigNotification@@EA, rdx; CConfigNotification * g_pNotifySink
0x180004ed1  test    rdx, rdx
0x180004ed4  jz      loc_1800260EA
0x180004eda  mov     rcx, cs:?g_pConfigSystem@@3PEAVINativeConfigurationSystem@@EA; INativeConfigurationSystem * g_pConfigSystem
0x180004ee1  mov     rax, [rcx]
0x180004ee4  mov     rax, [rax+28h]
0x180004ee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004eed  test    eax, eax
0x180004eef  js      loc_1800260EA
0x180004ef5  test    byte ptr cs:g_dwDebugFlags, 3
0x180004efc  jnz     loc_180025EEB
0x180004f02  mov     ebx, 13h
0x180004f07  call    ?Init449@@YAJXZ; Init449(void)
0x180004f0c  test    eax, eax
0x180004f0e  js      loc_1800260EA
0x180004f14  test    byte ptr cs:g_dwDebugFlags, 3
0x180004f1b  jnz     loc_180025F16
0x180004f21  mov     ebx, 14h
0x180004f26  call    ?Init@CTemplateCacheManager@@QEAAJXZ; CTemplateCacheManager::Init(void)
0x180004f2b  test    eax, eax
0x180004f2d  js      loc_1800260EA
0x180004f33  test    byte ptr cs:g_dwDebugFlags, 3
0x180004f3a  jnz     loc_180025F41
0x180004f40  mov     ebx, 15h
0x180004f45  call    ?Init@CIncFileMap@@QEAAJXZ; CIncFileMap::Init(void)
0x180004f4a  test    eax, eax
0x180004f4c  js      loc_1800260EA
0x180004f52  test    byte ptr cs:g_dwDebugFlags, 3
0x180004f59  jnz     loc_180025F6C
0x180004f5f  mov     ebx, 16h
0x180004f64  call    ?Init@CFileApplicationMap@@QEAAJXZ; CFileApplicationMap::Init(void)
0x180004f69  test    eax, eax
0x180004f6b  js      loc_1800260EA
0x180004f71  test    byte ptr cs:g_dwDebugFlags, 3
0x180004f78  jnz     loc_180025F97
0x180004f7e  mov     ebx, 17h
0x180004f83  call    ?Init@CScriptManager@@QEAAJXZ; CScriptManager::Init(void)
0x180004f88  test    eax, eax
0x180004f8a  js      loc_1800260EA
0x180004f90  test    byte ptr cs:g_dwDebugFlags, 3
0x180004f97  jnz     loc_180025FC2
0x180004f9d  mov     ebx, 18h
0x180004fa2  call    ?InitClass@CTemplate@@SAJXZ; CTemplate::InitClass(void)
0x180004fa7  test    eax, eax
0x180004fa9  js      loc_1800260EA
0x180004faf  test    byte ptr cs:g_dwDebugFlags, 3
0x180004fb6  jnz     loc_180025FED
0x180004fbc  mov     ebx, 19h
0x180004fc1  lea     rax, ppv
0x180004fc8  mov     [rsp+98h+ppv], rax; ppv
0x180004fcd  lea     r9, IID_IGlobalInterfaceTable; riid
0x180004fd4  xor     edx, edx; pUnkOuter
0x180004fd6  lea     r8d, [rbx-18h]; dwClsContext
0x180004fda  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180004fe1  call    cs:__imp_CoCreateInstance
0x180004fe7  test    eax, eax
0x180004fe9  js      loc_180026018
  ... truncated ...
```
