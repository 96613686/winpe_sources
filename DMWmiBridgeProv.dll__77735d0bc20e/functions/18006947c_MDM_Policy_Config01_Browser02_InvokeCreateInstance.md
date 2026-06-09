# MDM_Policy_Config01_Browser02_InvokeCreateInstance

- ea: `0x18006947c`
- end: `0x18006a71b`
- name: `MDM_Policy_Config01_Browser02_InvokeCreateInstance`
- size: `4767`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180069380`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x18006947c`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x1800696bf`: `AllowConfigurationUpdateForBooksLibrary`
- `0x1800697bc`: `AllowExtensions`
- `0x1800698fc`: `AllowMicrosoftCompatibilityList`
- `0x180069afc`: `AllowSideloadingOfExtensions`
- `0x180069c7c`: `ConfigureAdditionalSearchEngines`
- `0x180069cbc`: `ConfigureFavoritesBar`
- `0x180069cfc`: `ConfigureHomeButton`
- `0x180069d3c`: `ConfigureKioskMode`
- `0x180069d7c`: `ConfigureKioskResetAfterIdleTimeout`
- `0x180069dbc`: `ConfigureOpenMicrosoftEdgeWith`
- `0x180069dfc`: `ConfigureTelemetryForMicrosoft365Analytics`
- `0x18006a07c`: `EnterpriseSiteListServiceUrl`
- `0x18006a13c`: `PreventAccessToAboutFlagsInMicrosoftEdge`
- `0x18006a2bc`: `PreventTurningOffRequiredExtensions`
- `0x18006a47c`: `ShowMessageWhenOpeningSitesInInternetExplorer`
- `0x1800695a5`: `CreateInstanceStart`
- `0x18006a682`: `CreateInstanceEnd`
- `0x1800694ec`: `MDM_Policy_Config01_Browser02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_Browser02_InvokeCreateInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  unsigned int inserted; // edi
  WmiRequestHandler *v6; // r14
  WmiRequestHandler *v8; // [rsp+40h] [rbp-358h] BYREF
  char v9; // [rsp+48h] [rbp-350h]
  _QWORD v10[5]; // [rsp+50h] [rbp-348h] BYREF
  char v11; // [rsp+78h] [rbp-320h]
  int v12; // [rsp+80h] [rbp-318h] BYREF
  char v13; // [rsp+84h] [rbp-314h]
  _BYTE v14[16]; // [rsp+88h] [rbp-310h] BYREF
  _DWORD v15[6]; // [rsp+98h] [rbp-300h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-2E8h] BYREF

  memset_0(&instance, 0, 0x2C0u);
  v12 = 0;
  v13 = 0;
  v10[0] = &TelemetryEventWriter::`vftable';
  v10[1] = &v12;
  v10[2] = "MDM_Policy_Config01_Browser02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v12);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v13 && (v15[0] || v15[1] || v15[2] || v15[3]) )
      v4 = v15;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_18033AAC1,
      v14,
      v4);
  }
  if ( !LOBYTE(a2[1].classDecl) || (v9 = 0, !LOBYTE(a2[1].nameSpace)) )
  {
    inserted = 4;
    goto LABEL_273;
  }
  TelemetryEventWriter::WriteStart(
    (TelemetryEventWriter *)v10,
    "CreateInstanceStart",
    a2[1].serverName,
    (const unsigned __int16 *)a2[1].ft);
  v8 = 0;
  inserted = CreateRequestHandlerInstance(
               (__int64)self,
               (wchar_t *)a2[1].serverName,
               (const unsigned __int16 *)a2[1].ft,
               (struct WmiNodeInfo *)&MDM_Policy_Config01_Browser02_NodeList,
               0x3Fu,
               4,
               &v8);
  if ( !inserted )
  {
    v10[4] = &v8;
    v11 = 1;
    v6 = v8;
    if ( !v8 )
    {
      inserted = 1;
      goto LABEL_273;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v8,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_Browser02_NodeList,
      0x3Fu);
    if ( BYTE4(a2[1].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowAddressBarDropdown", (LONG *)a2[1].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
LABEL_268:
        (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        goto LABEL_273;
      }
    }
    if ( BYTE4(a2[1].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowAutofill", (LONG *)&a2[1].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[1].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AllowConfigurationUpdateForBooksLibrary",
                   (LONG *)&a2[1].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[1].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowCookies", (LONG *)&a2[1].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[2].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowDeveloperTools", (LONG *)&a2[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[2].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowDoNotTrack", (LONG *)&a2[2].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[2].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowExtensions", (LONG *)&a2[2].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[2].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowFlash", (LONG *)&a2[2].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[2].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowFlashClickToRun", (LONG *)a2[2].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[2].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowFullScreenMode", (LONG *)&a2[2].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[2].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowInPrivate", (LONG *)&a2[2].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[2].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AllowMicrosoftCompatibilityList",
                   (LONG *)&a2[2].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[3].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPasswordManager", (LONG *)&a2[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[3].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPopups", (LONG *)&a2[3].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[3].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPrelaunch", (LONG *)&a2[3].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[3].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPrinting", (LONG *)&a2[3].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[3].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowSavingHistory", (LONG *)a2[3].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[3].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AllowSearchEngineCustomization",
                   (LONG *)&a2[3].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[3].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AllowSearchSuggestionsinAddressBar",
                   (LONG *)&a2[3].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[3].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"AllowSideloadingOfExtensions",
                   (LONG *)&a2[3].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[4].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowSmartScreen", (LONG *)&a2[4]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[4].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowTabPreloading", (LONG *)&a2[4].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[4].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowWebContentOnNewTabPage", (LONG *)&a2[4].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[4].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AlwaysEnableBooksLibrary", (LONG *)&a2[4].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[4].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ClearBrowsingDataOnExit", (LONG *)a2[4].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( LOBYTE(a2[4].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigureAdditionalSearchEngines",
                   (LONG *)&a2[4].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[4].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureFavoritesBar", (LONG *)&a2[4].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[5].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureHomeButton", (LONG *)&a2[5]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[5].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureKioskMode", (LONG *)&a2[5].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[5].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigureKioskResetAfterIdleTimeout",
                   (LONG *)&a2[5].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[5].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigureOpenMicrosoftEdgeWith",
                   (LONG *)&a2[5].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[5].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ConfigureTelemetryForMicrosoft365Analytics",
                   (LONG *)a2[5].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( LOBYTE(a2[5].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DefaultFavoriteBarItem1Name", (LONG *)&a2[5].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( LOBYTE(a2[6].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DefaultFavoriteBarItem1Url", (LONG *)&a2[5].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( LOBYTE(a2[6].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DefaultFavoriteBarItem2Name", (LONG *)&a2[6].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( LOBYTE(a2[6].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DefaultFavoriteBarItem2Url", (LONG *)&a2[6].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( LOBYTE(a2[6].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DefaultFavoriteBarItem3Name", (LONG *)&a2[6].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( LOBYTE(a2[7].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DefaultFavoriteBarItem3Url", (LONG *)&a2[6].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[7].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DisableLockdownOfStartPages", (LONG *)&a2[7].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[7].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnableExtendedBooksTelemetry", (LONG *)&a2[7].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( LOBYTE(a2[7].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnterpriseModeSiteList", (LONG *)&a2[7].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( LOBYTE(a2[7].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"EnterpriseSiteListServiceUrl",
                   (LONG *)&a2[7].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( LOBYTE(a2[8].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"HomePages", (LONG *)&a2[7].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[8].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"LockdownFavorites", (LONG *)&a2[8].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[8].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"PreventAccessToAboutFlagsInMicrosoftEdge",
                   (LONG *)&a2[8].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[8].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PreventCertErrorOverrides", (LONG *)&a2[8].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[8].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PreventFirstRunPage", (LONG *)a2[8].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[8].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"PreventLiveTileDataCollection",
                   (LONG *)&a2[8].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[8].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"PreventSmartScreenPromptOverride",
                   (LONG *)&a2[8].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[8].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"PreventSmartScreenPromptOverrideForFiles",
                   (LONG *)&a2[8].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( LOBYTE(a2[9].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PreventTurningOffRequiredExtensions", (LONG *)&a2[9]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[9].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"PreventUsingLocalHostIPAddressForWebRTC",
                   (LONG *)&a2[9].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( LOBYTE(a2[9].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ProvisionFavorites", (LONG *)&a2[9].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[9].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"SendIntranetTraffictoInternetExplorer",
                   (LONG *)&a2[9].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( LOBYTE(a2[9].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetDefaultSearchEngine", (LONG *)&a2[9].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( LOBYTE(a2[10].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetHomeButtonURL", (LONG *)&a2[10]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( LOBYTE(a2[10].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetNewTabPageURL", (LONG *)&a2[10].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[10].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ShowMessageWhenOpeningSitesInInternetExplorer",
                   (LONG *)a2[10].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[10].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"SyncFavoritesBetweenIEAndMicrosoftEdge",
                   (LONG *)&a2[10].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[10].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"UnlockHomeButton", (LONG *)&a2[10].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[10].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"UseSharedFolderForBooks", (LONG *)&a2[10].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_273;
      goto LABEL_268;
    }
    inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_273;
      goto LABEL_268;
    }
    inserted = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_Browser02_rtti, &instance);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_273;
      goto LABEL_268;
    }
    v9 = 1;
    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, a2[1].ft);
    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, a2[1].serverName);
    MI_Instance_Destruct((MI_Instance *)self);
    if ( v8 )
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
    MI_Instance_Destruct(&instance);
  }
LABEL_273:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v10, "CreateInstanceEnd", inserted);
  v12 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      word_180339AD2,
      v14,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v12);
  return inserted;
}

```

## disassembly

```asm
0x18006947c  mov     [rsp+arg_10], rsi
0x180069481  mov     [rsp+arg_18], rdi
0x180069486  push    r12
0x180069488  push    r14
0x18006948a  push    r15
0x18006948c  sub     rsp, 380h
0x180069493  mov     rax, cs:__security_cookie
0x18006949a  xor     rax, rsp
0x18006949d  mov     [rsp+398h+var_28], rax
0x1800694a5  mov     rsi, rdx
0x1800694a8  mov     r15, rcx
0x1800694ab  xor     edx, edx; Val
0x1800694ad  mov     r8d, 2C0h; Size
0x1800694b3  lea     rcx, [rsp+398h+instance]; void *
0x1800694bb  call    memset_0
0x1800694c0  mov     [rsp+398h+var_318], 0
0x1800694cb  mov     [rsp+398h+var_314], 0
0x1800694d3  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800694da  mov     [rsp+398h+var_348], rax
0x1800694df  lea     rax, [rsp+398h+var_318]
0x1800694e7  mov     [rsp+398h+var_340], rax
0x1800694ec  lea     rax, aMdmPolicyConfi_161; "MDM_Policy_Config01_Browser02"
0x1800694f3  mov     [rsp+398h+var_338], rax
0x1800694f8  lea     rcx, [rsp+398h+var_318]
0x180069500  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180069505  mov     eax, cs:dword_180380B68
0x18006950b  cmp     eax, 5
0x18006950e  jbe     short loc_180069584
0x180069510  mov     rdx, 200000000000h
0x18006951a  lea     rcx, dword_180380B68
0x180069521  call    _tlgKeywordOn
0x180069526  test    al, al
0x180069528  jz      short loc_180069584
0x18006952a  cmp     [rsp+398h+var_314], 0
0x180069532  jz      short loc_180069566
0x180069534  cmp     [rsp+398h+var_300], 0
0x18006953c  jnz     short loc_18006955C
0x18006953e  cmp     [rsp+398h+var_2FC], 0
0x180069546  jnz     short loc_18006955C
0x180069548  cmp     [rsp+398h+var_2F8], 0
0x180069550  jnz     short loc_18006955C
0x180069552  cmp     [rsp+398h+var_2F4], 0
0x18006955a  jz      short loc_180069566
0x18006955c  lea     r9, [rsp+398h+var_300]
0x180069564  jmp     short loc_180069569
0x180069566  xor     r9d, r9d
0x180069569  lea     r8, [rsp+398h+var_310]
0x180069571  lea     rdx, byte_18033AAC1
0x180069578  lea     rcx, dword_180380B68
0x18006957f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180069584  cmp     byte ptr [rsi+48h], 0
0x180069588  jz      loc_18006A67A
0x18006958e  mov     [rsp+398h+var_350], 0
0x180069593  cmp     byte ptr [rsi+58h], 0
0x180069597  jz      loc_18006A67A
0x18006959d  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800695a1  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800695a5  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x1800695ac  lea     rcx, [rsp+398h+var_348]; this
0x1800695b1  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800695b6  nop
0x1800695b7  mov     [rsp+398h+var_358], 0
0x1800695c0  lea     rax, [rsp+398h+var_358]
0x1800695c5  mov     [rsp+398h+var_368], rax
0x1800695ca  mov     [rsp+398h+var_370], 4
0x1800695d2  mov     [rsp+398h+var_378], 3Fh ; '?'
0x1800695da  lea     r9, ?MDM_Policy_Config01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Browser02_NodeList
0x1800695e1  mov     r8, [rsi+40h]
0x1800695e5  mov     rdx, [rsi+50h]
0x1800695e9  mov     rcx, r15
0x1800695ec  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800695f1  mov     edi, eax
0x1800695f3  test    eax, eax
0x1800695f5  jz      short loc_1800695FC
0x1800695f7  jmp     loc_18006A67F
0x1800695fc  lea     rax, [rsp+398h+var_358]
0x180069601  mov     [rsp+398h+var_328], rax
0x180069606  mov     r12d, 1
0x18006960c  mov     [rsp+398h+var_320], r12b
0x180069611  mov     r14, [rsp+398h+var_358]
0x180069616  test    r14, r14
0x180069619  jnz     short loc_180069623
0x18006961b  mov     edi, r12d
0x18006961e  jmp     loc_18006A67F
0x180069623  mov     r9d, 3Fh ; '?'; unsigned int
0x180069629  lea     r8, ?MDM_Policy_Config01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x180069630  mov     rdx, rsi; struct _MI_Instance *
0x180069633  mov     rcx, r14; this
0x180069636  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18006963b  lea     r8, [rsi+60h]; void *
0x18006963f  cmp     [r8+4], r12b
0x180069643  jnz     short loc_180069678
0x180069645  lea     rdx, aAllowaddressba; "AllowAddressBarDropdown"
0x18006964c  mov     rcx, r14; this
0x18006964f  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180069654  mov     edi, eax
0x180069656  test    eax, eax
0x180069658  jz      short loc_180069678
0x18006965a  mov     rcx, [rsp+398h+var_358]
0x18006965f  test    rcx, rcx
0x180069662  jz      short loc_180069673
0x180069664  mov     rax, [rcx]
0x180069667  mov     edx, r12d
0x18006966a  mov     rax, [rax]
0x18006966d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069672  nop
0x180069673  jmp     loc_18006A67F
0x180069678  lea     r8, [rsi+68h]; void *
0x18006967c  cmp     [r8+4], r12b
0x180069680  jnz     short loc_1800696B5
0x180069682  lea     rdx, aAllowautofill; "AllowAutofill"
0x180069689  mov     rcx, r14; this
0x18006968c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180069691  mov     edi, eax
0x180069693  test    eax, eax
0x180069695  jz      short loc_1800696B5
0x180069697  mov     rcx, [rsp+398h+var_358]
0x18006969c  test    rcx, rcx
0x18006969f  jz      short loc_1800696B0
0x1800696a1  mov     rax, [rcx]
0x1800696a4  mov     edx, r12d
0x1800696a7  mov     rax, [rax]
0x1800696aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800696af  nop
0x1800696b0  jmp     loc_18006A67F
0x1800696b5  lea     r8, [rsi+70h]; void *
0x1800696b9  cmp     [r8+4], r12b
0x1800696bd  jnz     short loc_1800696F2
0x1800696bf  lea     rdx, aAllowconfigura; "AllowConfigurationUpdateForBooksLibrary"
0x1800696c6  mov     rcx, r14; this
0x1800696c9  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800696ce  mov     edi, eax
0x1800696d0  test    eax, eax
0x1800696d2  jz      short loc_1800696F2
0x1800696d4  mov     rcx, [rsp+398h+var_358]
0x1800696d9  test    rcx, rcx
0x1800696dc  jz      short loc_1800696ED
0x1800696de  mov     rax, [rcx]
0x1800696e1  mov     edx, r12d
0x1800696e4  mov     rax, [rax]
0x1800696e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800696ec  nop
0x1800696ed  jmp     loc_18006A67F
0x1800696f2  lea     r8, [rsi+78h]; void *
0x1800696f6  cmp     [r8+4], r12b
0x1800696fa  jnz     short loc_18006972F
0x1800696fc  lea     rdx, aAllowcookies; "AllowCookies"
0x180069703  mov     rcx, r14; this
0x180069706  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006970b  mov     edi, eax
0x18006970d  test    eax, eax
0x18006970f  jz      short loc_18006972F
0x180069711  mov     rcx, [rsp+398h+var_358]
0x180069716  test    rcx, rcx
0x180069719  jz      short loc_18006972A
0x18006971b  mov     rax, [rcx]
0x18006971e  mov     edx, r12d
0x180069721  mov     rax, [rax]
0x180069724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069729  nop
0x18006972a  jmp     loc_18006A67F
0x18006972f  lea     r8, [rsi+80h]; void *
0x180069736  cmp     [r8+4], r12b
0x18006973a  jnz     short loc_18006976F
0x18006973c  lea     rdx, aAllowdeveloper; "AllowDeveloperTools"
0x180069743  mov     rcx, r14; this
0x180069746  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006974b  mov     edi, eax
0x18006974d  test    eax, eax
0x18006974f  jz      short loc_18006976F
0x180069751  mov     rcx, [rsp+398h+var_358]
0x180069756  test    rcx, rcx
0x180069759  jz      short loc_18006976A
0x18006975b  mov     rax, [rcx]
0x18006975e  mov     edx, r12d
0x180069761  mov     rax, [rax]
0x180069764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069769  nop
0x18006976a  jmp     loc_18006A67F
0x18006976f  lea     r8, [rsi+88h]; void *
0x180069776  cmp     [r8+4], r12b
0x18006977a  jnz     short loc_1800697AF
0x18006977c  lea     rdx, aAllowdonottrac; "AllowDoNotTrack"
0x180069783  mov     rcx, r14; this
0x180069786  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006978b  mov     edi, eax
0x18006978d  test    eax, eax
0x18006978f  jz      short loc_1800697AF
0x180069791  mov     rcx, [rsp+398h+var_358]
0x180069796  test    rcx, rcx
0x180069799  jz      short loc_1800697AA
0x18006979b  mov     rax, [rcx]
0x18006979e  mov     edx, r12d
0x1800697a1  mov     rax, [rax]
0x1800697a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800697a9  nop
0x1800697aa  jmp     loc_18006A67F
0x1800697af  lea     r8, [rsi+90h]; void *
0x1800697b6  cmp     [r8+4], r12b
0x1800697ba  jnz     short loc_1800697EF
0x1800697bc  lea     rdx, aAllowextension; "AllowExtensions"
0x1800697c3  mov     rcx, r14; this
0x1800697c6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800697cb  mov     edi, eax
0x1800697cd  test    eax, eax
0x1800697cf  jz      short loc_1800697EF
0x1800697d1  mov     rcx, [rsp+398h+var_358]
0x1800697d6  test    rcx, rcx
0x1800697d9  jz      short loc_1800697EA
0x1800697db  mov     rax, [rcx]
0x1800697de  mov     edx, r12d
0x1800697e1  mov     rax, [rax]
0x1800697e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800697e9  nop
0x1800697ea  jmp     loc_18006A67F
0x1800697ef  lea     r8, [rsi+98h]; void *
0x1800697f6  cmp     [r8+4], r12b
0x1800697fa  jnz     short loc_18006982F
0x1800697fc  lea     rdx, aAllowflash; "AllowFlash"
0x180069803  mov     rcx, r14; this
0x180069806  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006980b  mov     edi, eax
0x18006980d  test    eax, eax
0x18006980f  jz      short loc_18006982F
0x180069811  mov     rcx, [rsp+398h+var_358]
0x180069816  test    rcx, rcx
0x180069819  jz      short loc_18006982A
0x18006981b  mov     rax, [rcx]
0x18006981e  mov     edx, r12d
0x180069821  mov     rax, [rax]
0x180069824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069829  nop
0x18006982a  jmp     loc_18006A67F
0x18006982f  lea     r8, [rsi+0A0h]; void *
0x180069836  cmp     [r8+4], r12b
0x18006983a  jnz     short loc_18006986F
0x18006983c  lea     rdx, aAllowflashclic; "AllowFlashClickToRun"
0x180069843  mov     rcx, r14; this
0x180069846  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006984b  mov     edi, eax
0x18006984d  test    eax, eax
0x18006984f  jz      short loc_18006986F
0x180069851  mov     rcx, [rsp+398h+var_358]
0x180069856  test    rcx, rcx
0x180069859  jz      short loc_18006986A
0x18006985b  mov     rax, [rcx]
0x18006985e  mov     edx, r12d
0x180069861  mov     rax, [rax]
0x180069864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069869  nop
0x18006986a  jmp     loc_18006A67F
0x18006986f  lea     r8, [rsi+0A8h]; void *
0x180069876  cmp     [r8+4], r12b
0x18006987a  jnz     short loc_1800698AF
0x18006987c  lea     rdx, aAllowfullscree; "AllowFullScreenMode"
0x180069883  mov     rcx, r14; this
0x180069886  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006988b  mov     edi, eax
0x18006988d  test    eax, eax
0x18006988f  jz      short loc_1800698AF
0x180069891  mov     rcx, [rsp+398h+var_358]
0x180069896  test    rcx, rcx
0x180069899  jz      short loc_1800698AA
0x18006989b  mov     rax, [rcx]
0x18006989e  mov     edx, r12d
0x1800698a1  mov     rax, [rax]
0x1800698a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800698a9  nop
0x1800698aa  jmp     loc_18006A67F
0x1800698af  lea     r8, [rsi+0B0h]; void *
0x1800698b6  cmp     [r8+4], r12b
0x1800698ba  jnz     short loc_1800698EF
0x1800698bc  lea     rdx, aAllowinprivate; "AllowInPrivate"
0x1800698c3  mov     rcx, r14; this
0x1800698c6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800698cb  mov     edi, eax
0x1800698cd  test    eax, eax
0x1800698cf  jz      short loc_1800698EF
0x1800698d1  mov     rcx, [rsp+398h+var_358]
0x1800698d6  test    rcx, rcx
0x1800698d9  jz      short loc_1800698EA
0x1800698db  mov     rax, [rcx]
0x1800698de  mov     edx, r12d
0x1800698e1  mov     rax, [rax]
0x1800698e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800698e9  nop
0x1800698ea  jmp     loc_18006A67F
0x1800698ef  lea     r8, [rsi+0B8h]; void *
0x1800698f6  cmp     [r8+4], r12b
0x1800698fa  jnz     short loc_18006992F
0x1800698fc  lea     rdx, aAllowmicrosoft_2; "AllowMicrosoftCompatibilityList"
0x180069903  mov     rcx, r14; this
0x180069906  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006990b  mov     edi, eax
0x18006990d  test    eax, eax
0x18006990f  jz      short loc_18006992F
0x180069911  mov     rcx, [rsp+398h+var_358]
0x180069916  test    rcx, rcx
0x180069919  jz      short loc_18006992A
0x18006991b  mov     rax, [rcx]
  ... truncated ...
```
