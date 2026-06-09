# MDM_Policy_Config01_Browser02_InvokeCreateInstance

- ea: `0x180068c4c`
- end: `0x180069eec`
- name: `MDM_Policy_Config01_Browser02_InvokeCreateInstance`
- size: `4768`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180068b90`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x180068c4c`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x180068e8f`: `AllowConfigurationUpdateForBooksLibrary`
- `0x180068f8c`: `AllowExtensions`
- `0x1800690cc`: `AllowMicrosoftCompatibilityList`
- `0x1800692cc`: `AllowSideloadingOfExtensions`
- `0x18006944c`: `ConfigureAdditionalSearchEngines`
- `0x18006948c`: `ConfigureFavoritesBar`
- `0x1800694cc`: `ConfigureHomeButton`
- `0x18006950c`: `ConfigureKioskMode`
- `0x18006954c`: `ConfigureKioskResetAfterIdleTimeout`
- `0x18006958c`: `ConfigureOpenMicrosoftEdgeWith`
- `0x1800695cc`: `ConfigureTelemetryForMicrosoft365Analytics`
- `0x18006984c`: `EnterpriseSiteListServiceUrl`
- `0x18006990c`: `PreventAccessToAboutFlagsInMicrosoftEdge`
- `0x180069a8c`: `PreventTurningOffRequiredExtensions`
- `0x180069c4c`: `ShowMessageWhenOpeningSitesInInternetExplorer`
- `0x180068d75`: `CreateInstanceStart`
- `0x180069e52`: `CreateInstanceEnd`
- `0x180068cbc`: `MDM_Policy_Config01_Browser02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_Browser02_InvokeCreateInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  enum _MI_Result inserted; // edi
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
    inserted = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_273;
  }
  TelemetryEventWriter::WriteStart(
    (TelemetryEventWriter *)v10,
    "CreateInstanceStart",
    a2[1].serverName,
    (const unsigned __int16 *)a2[1].ft);
  v8 = 0;
  inserted = (unsigned int)CreateRequestHandlerInstance(
                             self,
                             a2[1].serverName,
                             a2[1].ft,
                             &MDM_Policy_Config01_Browser02_NodeList,
                             63,
                             4,
                             &v8);
  if ( inserted == MI_RESULT_OK )
  {
    v10[4] = &v8;
    v11 = 1;
    v6 = v8;
    if ( !v8 )
    {
      inserted = MI_RESULT_FAILED;
      goto LABEL_273;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v8,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_Browser02_NodeList,
      0x3Fu);
    if ( BYTE4(a2[1].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowAddressBarDropdown", a2[1].reserved);
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
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowAutofill", &a2[1].reserved[1]);
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
                   &a2[1].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[1].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowCookies", &a2[1].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[2].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowDeveloperTools", &a2[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[2].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowDoNotTrack", &a2[2].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[2].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowExtensions", &a2[2].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[2].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowFlash", &a2[2].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[2].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowFlashClickToRun", a2[2].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[2].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowFullScreenMode", &a2[2].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[2].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowInPrivate", &a2[2].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[2].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowMicrosoftCompatibilityList", &a2[2].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[3].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPasswordManager", &a2[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[3].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPopups", &a2[3].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[3].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPrelaunch", &a2[3].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[3].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPrinting", &a2[3].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[3].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowSavingHistory", a2[3].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[3].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowSearchEngineCustomization", &a2[3].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[3].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowSearchSuggestionsinAddressBar", &a2[3].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[3].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowSideloadingOfExtensions", &a2[3].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[4].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowSmartScreen", &a2[4]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[4].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowTabPreloading", &a2[4].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[4].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowWebContentOnNewTabPage", &a2[4].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[4].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AlwaysEnableBooksLibrary", &a2[4].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[4].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ClearBrowsingDataOnExit", a2[4].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( LOBYTE(a2[4].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureAdditionalSearchEngines", &a2[4].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[4].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureFavoritesBar", &a2[4].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[5].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureHomeButton", &a2[5]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[5].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureKioskMode", &a2[5].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[5].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureKioskResetAfterIdleTimeout", &a2[5].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[5].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureOpenMicrosoftEdgeWith", &a2[5].nameSpace);
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
                   a2[5].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( LOBYTE(a2[5].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DefaultFavoriteBarItem1Name", &a2[5].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( LOBYTE(a2[6].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DefaultFavoriteBarItem1Url", &a2[5].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( LOBYTE(a2[6].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DefaultFavoriteBarItem2Name", &a2[6].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( LOBYTE(a2[6].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DefaultFavoriteBarItem2Url", &a2[6].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( LOBYTE(a2[6].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DefaultFavoriteBarItem3Name", &a2[6].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( LOBYTE(a2[7].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DefaultFavoriteBarItem3Url", &a2[6].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[7].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DisableLockdownOfStartPages", &a2[7].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[7].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnableExtendedBooksTelemetry", &a2[7].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( LOBYTE(a2[7].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnterpriseModeSiteList", &a2[7].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( LOBYTE(a2[7].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnterpriseSiteListServiceUrl", &a2[7].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( LOBYTE(a2[8].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"HomePages", &a2[7].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[8].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"LockdownFavorites", &a2[8].classDecl);
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
                   &a2[8].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[8].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PreventCertErrorOverrides", &a2[8].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[8].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PreventFirstRunPage", a2[8].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[8].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PreventLiveTileDataCollection", &a2[8].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[8].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PreventSmartScreenPromptOverride", &a2[8].reserved[2]);
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
                   &a2[8].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( LOBYTE(a2[9].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PreventTurningOffRequiredExtensions", &a2[9]);
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
                   &a2[9].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( LOBYTE(a2[9].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ProvisionFavorites", &a2[9].nameSpace);
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
                   &a2[9].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( LOBYTE(a2[9].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetDefaultSearchEngine", &a2[9].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( LOBYTE(a2[10].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetHomeButtonURL", &a2[10]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( LOBYTE(a2[10].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetNewTabPageURL", &a2[10].serverName);
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
                   a2[10].reserved);
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
                   &a2[10].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[10].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"UnlockHomeButton", &a2[10].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    if ( BYTE4(a2[10].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"UseSharedFolderForBooks", &a2[10].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_273;
        goto LABEL_268;
      }
    }
    inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_273;
      goto LABEL_268;
    }
    inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x180068c4c  mov     [rsp+arg_10], rsi
0x180068c51  mov     [rsp+arg_18], rdi
0x180068c56  push    r12
0x180068c58  push    r14
0x180068c5a  push    r15
0x180068c5c  sub     rsp, 380h
0x180068c63  mov     rax, cs:__security_cookie
0x180068c6a  xor     rax, rsp
0x180068c6d  mov     [rsp+398h+var_28], rax
0x180068c75  mov     rsi, rdx
0x180068c78  mov     r15, rcx
0x180068c7b  xor     edx, edx; Val
0x180068c7d  mov     r8d, 2C0h; Size
0x180068c83  lea     rcx, [rsp+398h+instance]; void *
0x180068c8b  call    memset_0
0x180068c90  mov     [rsp+398h+var_318], 0
0x180068c9b  mov     [rsp+398h+var_314], 0
0x180068ca3  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180068caa  mov     [rsp+398h+var_348], rax
0x180068caf  lea     rax, [rsp+398h+var_318]
0x180068cb7  mov     [rsp+398h+var_340], rax
0x180068cbc  lea     rax, aMdmPolicyConfi_161; "MDM_Policy_Config01_Browser02"
0x180068cc3  mov     [rsp+398h+var_338], rax
0x180068cc8  lea     rcx, [rsp+398h+var_318]
0x180068cd0  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180068cd5  mov     eax, cs:dword_180380B68
0x180068cdb  cmp     eax, 5
0x180068cde  jbe     short loc_180068D54
0x180068ce0  mov     rdx, 200000000000h
0x180068cea  lea     rcx, dword_180380B68
0x180068cf1  call    _tlgKeywordOn
0x180068cf6  test    al, al
0x180068cf8  jz      short loc_180068D54
0x180068cfa  cmp     [rsp+398h+var_314], 0
0x180068d02  jz      short loc_180068D36
0x180068d04  cmp     [rsp+398h+var_300], 0
0x180068d0c  jnz     short loc_180068D2C
0x180068d0e  cmp     [rsp+398h+var_2FC], 0
0x180068d16  jnz     short loc_180068D2C
0x180068d18  cmp     [rsp+398h+var_2F8], 0
0x180068d20  jnz     short loc_180068D2C
0x180068d22  cmp     [rsp+398h+var_2F4], 0
0x180068d2a  jz      short loc_180068D36
0x180068d2c  lea     r9, [rsp+398h+var_300]
0x180068d34  jmp     short loc_180068D39
0x180068d36  xor     r9d, r9d
0x180068d39  lea     r8, [rsp+398h+var_310]
0x180068d41  lea     rdx, byte_18033AAC1
0x180068d48  lea     rcx, dword_180380B68
0x180068d4f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180068d54  cmp     byte ptr [rsi+48h], 0
0x180068d58  jz      loc_180069E4A
0x180068d5e  mov     [rsp+398h+var_350], 0
0x180068d63  cmp     byte ptr [rsi+58h], 0
0x180068d67  jz      loc_180069E4A
0x180068d6d  mov     r9, [rsi+40h]; unsigned __int16 *
0x180068d71  mov     r8, [rsi+50h]; unsigned __int16 *
0x180068d75  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x180068d7c  lea     rcx, [rsp+398h+var_348]; this
0x180068d81  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x180068d86  nop
0x180068d87  mov     [rsp+398h+var_358], 0
0x180068d90  lea     rax, [rsp+398h+var_358]
0x180068d95  mov     [rsp+398h+var_368], rax
0x180068d9a  mov     [rsp+398h+var_370], 4
0x180068da2  mov     [rsp+398h+var_378], 3Fh ; '?'
0x180068daa  lea     r9, ?MDM_Policy_Config01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Browser02_NodeList
0x180068db1  mov     r8, [rsi+40h]
0x180068db5  mov     rdx, [rsi+50h]
0x180068db9  mov     rcx, r15
0x180068dbc  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180068dc1  mov     edi, eax
0x180068dc3  test    eax, eax
0x180068dc5  jz      short loc_180068DCC
0x180068dc7  jmp     loc_180069E4F
0x180068dcc  lea     rax, [rsp+398h+var_358]
0x180068dd1  mov     [rsp+398h+var_328], rax
0x180068dd6  mov     r12d, 1
0x180068ddc  mov     [rsp+398h+var_320], r12b
0x180068de1  mov     r14, [rsp+398h+var_358]
0x180068de6  test    r14, r14
0x180068de9  jnz     short loc_180068DF3
0x180068deb  mov     edi, r12d
0x180068dee  jmp     loc_180069E4F
0x180068df3  mov     r9d, 3Fh ; '?'; unsigned int
0x180068df9  lea     r8, ?MDM_Policy_Config01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x180068e00  mov     rdx, rsi; struct _MI_Instance *
0x180068e03  mov     rcx, r14; this
0x180068e06  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x180068e0b  lea     r8, [rsi+60h]; void *
0x180068e0f  cmp     [r8+4], r12b
0x180068e13  jnz     short loc_180068E48
0x180068e15  lea     rdx, aAllowaddressba; "AllowAddressBarDropdown"
0x180068e1c  mov     rcx, r14; this
0x180068e1f  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180068e24  mov     edi, eax
0x180068e26  test    eax, eax
0x180068e28  jz      short loc_180068E48
0x180068e2a  mov     rcx, [rsp+398h+var_358]
0x180068e2f  test    rcx, rcx
0x180068e32  jz      short loc_180068E43
0x180068e34  mov     rax, [rcx]
0x180068e37  mov     edx, r12d
0x180068e3a  mov     rax, [rax]
0x180068e3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068e42  nop
0x180068e43  jmp     loc_180069E4F
0x180068e48  lea     r8, [rsi+68h]; void *
0x180068e4c  cmp     [r8+4], r12b
0x180068e50  jnz     short loc_180068E85
0x180068e52  lea     rdx, aAllowautofill; "AllowAutofill"
0x180068e59  mov     rcx, r14; this
0x180068e5c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180068e61  mov     edi, eax
0x180068e63  test    eax, eax
0x180068e65  jz      short loc_180068E85
0x180068e67  mov     rcx, [rsp+398h+var_358]
0x180068e6c  test    rcx, rcx
0x180068e6f  jz      short loc_180068E80
0x180068e71  mov     rax, [rcx]
0x180068e74  mov     edx, r12d
0x180068e77  mov     rax, [rax]
0x180068e7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068e7f  nop
0x180068e80  jmp     loc_180069E4F
0x180068e85  lea     r8, [rsi+70h]; void *
0x180068e89  cmp     [r8+4], r12b
0x180068e8d  jnz     short loc_180068EC2
0x180068e8f  lea     rdx, aAllowconfigura; "AllowConfigurationUpdateForBooksLibrary"
0x180068e96  mov     rcx, r14; this
0x180068e99  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180068e9e  mov     edi, eax
0x180068ea0  test    eax, eax
0x180068ea2  jz      short loc_180068EC2
0x180068ea4  mov     rcx, [rsp+398h+var_358]
0x180068ea9  test    rcx, rcx
0x180068eac  jz      short loc_180068EBD
0x180068eae  mov     rax, [rcx]
0x180068eb1  mov     edx, r12d
0x180068eb4  mov     rax, [rax]
0x180068eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068ebc  nop
0x180068ebd  jmp     loc_180069E4F
0x180068ec2  lea     r8, [rsi+78h]; void *
0x180068ec6  cmp     [r8+4], r12b
0x180068eca  jnz     short loc_180068EFF
0x180068ecc  lea     rdx, aAllowcookies; "AllowCookies"
0x180068ed3  mov     rcx, r14; this
0x180068ed6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180068edb  mov     edi, eax
0x180068edd  test    eax, eax
0x180068edf  jz      short loc_180068EFF
0x180068ee1  mov     rcx, [rsp+398h+var_358]
0x180068ee6  test    rcx, rcx
0x180068ee9  jz      short loc_180068EFA
0x180068eeb  mov     rax, [rcx]
0x180068eee  mov     edx, r12d
0x180068ef1  mov     rax, [rax]
0x180068ef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068ef9  nop
0x180068efa  jmp     loc_180069E4F
0x180068eff  lea     r8, [rsi+80h]; void *
0x180068f06  cmp     [r8+4], r12b
0x180068f0a  jnz     short loc_180068F3F
0x180068f0c  lea     rdx, aAllowdeveloper; "AllowDeveloperTools"
0x180068f13  mov     rcx, r14; this
0x180068f16  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180068f1b  mov     edi, eax
0x180068f1d  test    eax, eax
0x180068f1f  jz      short loc_180068F3F
0x180068f21  mov     rcx, [rsp+398h+var_358]
0x180068f26  test    rcx, rcx
0x180068f29  jz      short loc_180068F3A
0x180068f2b  mov     rax, [rcx]
0x180068f2e  mov     edx, r12d
0x180068f31  mov     rax, [rax]
0x180068f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068f39  nop
0x180068f3a  jmp     loc_180069E4F
0x180068f3f  lea     r8, [rsi+88h]; void *
0x180068f46  cmp     [r8+4], r12b
0x180068f4a  jnz     short loc_180068F7F
0x180068f4c  lea     rdx, aAllowdonottrac; "AllowDoNotTrack"
0x180068f53  mov     rcx, r14; this
0x180068f56  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180068f5b  mov     edi, eax
0x180068f5d  test    eax, eax
0x180068f5f  jz      short loc_180068F7F
0x180068f61  mov     rcx, [rsp+398h+var_358]
0x180068f66  test    rcx, rcx
0x180068f69  jz      short loc_180068F7A
0x180068f6b  mov     rax, [rcx]
0x180068f6e  mov     edx, r12d
0x180068f71  mov     rax, [rax]
0x180068f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068f79  nop
0x180068f7a  jmp     loc_180069E4F
0x180068f7f  lea     r8, [rsi+90h]; void *
0x180068f86  cmp     [r8+4], r12b
0x180068f8a  jnz     short loc_180068FBF
0x180068f8c  lea     rdx, aAllowextension; "AllowExtensions"
0x180068f93  mov     rcx, r14; this
0x180068f96  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180068f9b  mov     edi, eax
0x180068f9d  test    eax, eax
0x180068f9f  jz      short loc_180068FBF
0x180068fa1  mov     rcx, [rsp+398h+var_358]
0x180068fa6  test    rcx, rcx
0x180068fa9  jz      short loc_180068FBA
0x180068fab  mov     rax, [rcx]
0x180068fae  mov     edx, r12d
0x180068fb1  mov     rax, [rax]
0x180068fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068fb9  nop
0x180068fba  jmp     loc_180069E4F
0x180068fbf  lea     r8, [rsi+98h]; void *
0x180068fc6  cmp     [r8+4], r12b
0x180068fca  jnz     short loc_180068FFF
0x180068fcc  lea     rdx, aAllowflash; "AllowFlash"
0x180068fd3  mov     rcx, r14; this
0x180068fd6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180068fdb  mov     edi, eax
0x180068fdd  test    eax, eax
0x180068fdf  jz      short loc_180068FFF
0x180068fe1  mov     rcx, [rsp+398h+var_358]
0x180068fe6  test    rcx, rcx
0x180068fe9  jz      short loc_180068FFA
0x180068feb  mov     rax, [rcx]
0x180068fee  mov     edx, r12d
0x180068ff1  mov     rax, [rax]
0x180068ff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068ff9  nop
0x180068ffa  jmp     loc_180069E4F
0x180068fff  lea     r8, [rsi+0A0h]; void *
0x180069006  cmp     [r8+4], r12b
0x18006900a  jnz     short loc_18006903F
0x18006900c  lea     rdx, aAllowflashclic; "AllowFlashClickToRun"
0x180069013  mov     rcx, r14; this
0x180069016  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006901b  mov     edi, eax
0x18006901d  test    eax, eax
0x18006901f  jz      short loc_18006903F
0x180069021  mov     rcx, [rsp+398h+var_358]
0x180069026  test    rcx, rcx
0x180069029  jz      short loc_18006903A
0x18006902b  mov     rax, [rcx]
0x18006902e  mov     edx, r12d
0x180069031  mov     rax, [rax]
0x180069034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069039  nop
0x18006903a  jmp     loc_180069E4F
0x18006903f  lea     r8, [rsi+0A8h]; void *
0x180069046  cmp     [r8+4], r12b
0x18006904a  jnz     short loc_18006907F
0x18006904c  lea     rdx, aAllowfullscree; "AllowFullScreenMode"
0x180069053  mov     rcx, r14; this
0x180069056  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006905b  mov     edi, eax
0x18006905d  test    eax, eax
0x18006905f  jz      short loc_18006907F
0x180069061  mov     rcx, [rsp+398h+var_358]
0x180069066  test    rcx, rcx
0x180069069  jz      short loc_18006907A
0x18006906b  mov     rax, [rcx]
0x18006906e  mov     edx, r12d
0x180069071  mov     rax, [rax]
0x180069074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069079  nop
0x18006907a  jmp     loc_180069E4F
0x18006907f  lea     r8, [rsi+0B0h]; void *
0x180069086  cmp     [r8+4], r12b
0x18006908a  jnz     short loc_1800690BF
0x18006908c  lea     rdx, aAllowinprivate; "AllowInPrivate"
0x180069093  mov     rcx, r14; this
0x180069096  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006909b  mov     edi, eax
0x18006909d  test    eax, eax
0x18006909f  jz      short loc_1800690BF
0x1800690a1  mov     rcx, [rsp+398h+var_358]
0x1800690a6  test    rcx, rcx
0x1800690a9  jz      short loc_1800690BA
0x1800690ab  mov     rax, [rcx]
0x1800690ae  mov     edx, r12d
0x1800690b1  mov     rax, [rax]
0x1800690b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800690b9  nop
0x1800690ba  jmp     loc_180069E4F
0x1800690bf  lea     r8, [rsi+0B8h]; void *
0x1800690c6  cmp     [r8+4], r12b
0x1800690ca  jnz     short loc_1800690FF
0x1800690cc  lea     rdx, aAllowmicrosoft_2; "AllowMicrosoftCompatibilityList"
0x1800690d3  mov     rcx, r14; this
0x1800690d6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1800690db  mov     edi, eax
0x1800690dd  test    eax, eax
0x1800690df  jz      short loc_1800690FF
0x1800690e1  mov     rcx, [rsp+398h+var_358]
0x1800690e6  test    rcx, rcx
0x1800690e9  jz      short loc_1800690FA
0x1800690eb  mov     rax, [rcx]
  ... truncated ...
```
