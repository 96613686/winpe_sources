# MDM_Policy_User_Config01_Browser02_InvokeCreateInstance

- ea: `0x1801c419c`
- end: `0x1801c52bc`
- name: `MDM_Policy_User_Config01_Browser02_InvokeCreateInstance`
- size: `4384`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801c40e0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x1801c419c`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x1801c43df`: `AllowConfigurationUpdateForBooksLibrary`
- `0x1801c44dc`: `AllowExtensions`
- `0x1801c461c`: `AllowMicrosoftCompatibilityList`
- `0x1801c481c`: `AllowSideloadingOfExtensions`
- `0x1801c499c`: `ConfigureAdditionalSearchEngines`
- `0x1801c49dc`: `ConfigureFavoritesBar`
- `0x1801c4a1c`: `ConfigureHomeButton`
- `0x1801c4a5c`: `ConfigureKioskMode`
- `0x1801c4a9c`: `ConfigureKioskResetAfterIdleTimeout`
- `0x1801c4adc`: `ConfigureOpenMicrosoftEdgeWith`
- `0x1801c4b1c`: `ConfigureTelemetryForMicrosoft365Analytics`
- `0x1801c4c1c`: `EnterpriseSiteListServiceUrl`
- `0x1801c4cdc`: `PreventAccessToAboutFlagsInMicrosoftEdge`
- `0x1801c4e5c`: `PreventTurningOffRequiredExtensions`
- `0x1801c501c`: `ShowMessageWhenOpeningSitesInInternetExplorer`
- `0x1801c42c5`: `CreateInstanceStart`
- `0x1801c5222`: `CreateInstanceEnd`
- `0x1801c420c`: `MDM_Policy_User_Config01_Browser02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_User_Config01_Browser02_InvokeCreateInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  enum _MI_Result inserted; // edi
  WmiRequestHandler *v6; // r14
  WmiRequestHandler *v8; // [rsp+40h] [rbp-2F8h] BYREF
  char v9; // [rsp+48h] [rbp-2F0h]
  _QWORD v10[5]; // [rsp+50h] [rbp-2E8h] BYREF
  char v11; // [rsp+78h] [rbp-2C0h]
  int v12; // [rsp+80h] [rbp-2B8h] BYREF
  char v13; // [rsp+84h] [rbp-2B4h]
  _BYTE v14[16]; // [rsp+88h] [rbp-2B0h] BYREF
  _DWORD v15[6]; // [rsp+98h] [rbp-2A0h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-288h] BYREF

  memset_0(&instance, 0, 0x260u);
  v12 = 0;
  v13 = 0;
  v10[0] = &TelemetryEventWriter::`vftable';
  v10[1] = &v12;
  v10[2] = "MDM_Policy_User_Config01_Browser02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v12);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v13 && (v15[0] || v15[1] || v15[2] || v15[3]) )
      v4 = v15;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_180369813,
      v14,
      v4);
  }
  if ( !LOBYTE(a2[1].classDecl) || (v9 = 0, !LOBYTE(a2[1].nameSpace)) )
  {
    inserted = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_249;
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
                             &MDM_Policy_User_Config01_Browser02_NodeList,
                             57,
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
      goto LABEL_249;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v8,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_User_Config01_Browser02_NodeList,
      0x39u);
    if ( BYTE4(a2[1].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowAddressBarDropdown", a2[1].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
LABEL_244:
        (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        goto LABEL_249;
      }
    }
    if ( BYTE4(a2[1].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowAutofill", &a2[1].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
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
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[1].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowCookies", &a2[1].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[2].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowDeveloperTools", &a2[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[2].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowDoNotTrack", &a2[2].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[2].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowExtensions", &a2[2].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[2].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowFlash", &a2[2].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[2].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowFlashClickToRun", a2[2].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[2].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowFullScreenMode", &a2[2].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[2].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowInPrivate", &a2[2].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[2].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowMicrosoftCompatibilityList", &a2[2].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[3].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPasswordManager", &a2[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[3].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPopups", &a2[3].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[3].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPrelaunch", &a2[3].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[3].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPrinting", &a2[3].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[3].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowSavingHistory", a2[3].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[3].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowSearchEngineCustomization", &a2[3].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[3].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowSearchSuggestionsinAddressBar", &a2[3].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[3].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowSideloadingOfExtensions", &a2[3].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[4].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowSmartScreen", &a2[4]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[4].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowTabPreloading", &a2[4].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[4].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowWebContentOnNewTabPage", &a2[4].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[4].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AlwaysEnableBooksLibrary", &a2[4].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[4].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ClearBrowsingDataOnExit", a2[4].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( LOBYTE(a2[4].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureAdditionalSearchEngines", &a2[4].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[4].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureFavoritesBar", &a2[4].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[5].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureHomeButton", &a2[5]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[5].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureKioskMode", &a2[5].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[5].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureKioskResetAfterIdleTimeout", &a2[5].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[5].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureOpenMicrosoftEdgeWith", &a2[5].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
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
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[5].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DisableLockdownOfStartPages", &a2[5].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[5].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnableExtendedBooksTelemetry", &a2[5].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( LOBYTE(a2[6].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnterpriseModeSiteList", &a2[5].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( LOBYTE(a2[6].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnterpriseSiteListServiceUrl", &a2[6].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( LOBYTE(a2[6].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"HomePages", &a2[6].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[6].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"LockdownFavorites", &a2[6].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[6].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"PreventAccessToAboutFlagsInMicrosoftEdge",
                   &a2[6].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[6].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PreventCertErrorOverrides", &a2[6].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[7].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PreventFirstRunPage", &a2[7]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[7].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PreventLiveTileDataCollection", &a2[7].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[7].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PreventSmartScreenPromptOverride", &a2[7].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[7].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"PreventSmartScreenPromptOverrideForFiles",
                   &a2[7].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( LOBYTE(a2[7].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PreventTurningOffRequiredExtensions", a2[7].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[7].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"PreventUsingLocalHostIPAddressForWebRTC",
                   &a2[7].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( LOBYTE(a2[8].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ProvisionFavorites", &a2[7].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[8].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SendIntranetTraffictoInternetExplorer", &a2[8].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( LOBYTE(a2[8].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetDefaultSearchEngine", &a2[8].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( LOBYTE(a2[8].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetHomeButtonURL", a2[8].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( LOBYTE(a2[8].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetNewTabPageURL", &a2[8].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[9].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ShowMessageWhenOpeningSitesInInternetExplorer", &a2[9]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[9].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"SyncFavoritesBetweenIEAndMicrosoftEdge",
                   &a2[9].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[9].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"UnlockHomeButton", &a2[9].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[9].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"UseSharedFolderForBooks", &a2[9].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_249;
      goto LABEL_244;
    }
    inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_249;
      goto LABEL_244;
    }
    inserted = MI_Context_ConstructInstance(self, &MDM_Policy_User_Config01_Browser02_rtti, &instance);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_249;
      goto LABEL_244;
    }
    v9 = 1;
    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, a2[1].ft);
    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, a2[1].serverName);
    MI_Instance_Destruct((MI_Instance *)self);
    if ( v8 )
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
    MI_Instance_Destruct(&instance);
  }
LABEL_249:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v10, "CreateInstanceEnd", inserted);
  v12 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_1803512F1,
      v14,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v12);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1801c419c  mov     [rsp+arg_10], rsi
0x1801c41a1  mov     [rsp+arg_18], rdi
0x1801c41a6  push    r12
0x1801c41a8  push    r14
0x1801c41aa  push    r15
0x1801c41ac  sub     rsp, 320h
0x1801c41b3  mov     rax, cs:__security_cookie
0x1801c41ba  xor     rax, rsp
0x1801c41bd  mov     [rsp+338h+var_28], rax
0x1801c41c5  mov     rsi, rdx
0x1801c41c8  mov     r15, rcx
0x1801c41cb  xor     edx, edx; Val
0x1801c41cd  mov     r8d, 260h; Size
0x1801c41d3  lea     rcx, [rsp+338h+instance]; void *
0x1801c41db  call    memset_0
0x1801c41e0  mov     [rsp+338h+var_2B8], 0
0x1801c41eb  mov     [rsp+338h+var_2B4], 0
0x1801c41f3  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801c41fa  mov     [rsp+338h+var_2E8], rax
0x1801c41ff  lea     rax, [rsp+338h+var_2B8]
0x1801c4207  mov     [rsp+338h+var_2E0], rax
0x1801c420c  lea     rax, aMdmPolicyUserC_19; "MDM_Policy_User_Config01_Browser02"
0x1801c4213  mov     [rsp+338h+var_2D8], rax
0x1801c4218  lea     rcx, [rsp+338h+var_2B8]
0x1801c4220  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801c4225  mov     eax, cs:dword_180380B68
0x1801c422b  cmp     eax, 5
0x1801c422e  jbe     short loc_1801C42A4
0x1801c4230  mov     rdx, 200000000000h
0x1801c423a  lea     rcx, dword_180380B68
0x1801c4241  call    _tlgKeywordOn
0x1801c4246  test    al, al
0x1801c4248  jz      short loc_1801C42A4
0x1801c424a  cmp     [rsp+338h+var_2B4], 0
0x1801c4252  jz      short loc_1801C4286
0x1801c4254  cmp     [rsp+338h+var_2A0], 0
0x1801c425c  jnz     short loc_1801C427C
0x1801c425e  cmp     [rsp+338h+var_29C], 0
0x1801c4266  jnz     short loc_1801C427C
0x1801c4268  cmp     [rsp+338h+var_298], 0
0x1801c4270  jnz     short loc_1801C427C
0x1801c4272  cmp     [rsp+338h+var_294], 0
0x1801c427a  jz      short loc_1801C4286
0x1801c427c  lea     r9, [rsp+338h+var_2A0]
0x1801c4284  jmp     short loc_1801C4289
0x1801c4286  xor     r9d, r9d
0x1801c4289  lea     r8, [rsp+338h+var_2B0]
0x1801c4291  lea     rdx, byte_180369813
0x1801c4298  lea     rcx, dword_180380B68
0x1801c429f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801c42a4  cmp     byte ptr [rsi+48h], 0
0x1801c42a8  jz      loc_1801C521A
0x1801c42ae  mov     [rsp+338h+var_2F0], 0
0x1801c42b3  cmp     byte ptr [rsi+58h], 0
0x1801c42b7  jz      loc_1801C521A
0x1801c42bd  mov     r9, [rsi+40h]; unsigned __int16 *
0x1801c42c1  mov     r8, [rsi+50h]; unsigned __int16 *
0x1801c42c5  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x1801c42cc  lea     rcx, [rsp+338h+var_2E8]; this
0x1801c42d1  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1801c42d6  nop
0x1801c42d7  mov     [rsp+338h+var_2F8], 0
0x1801c42e0  lea     rax, [rsp+338h+var_2F8]
0x1801c42e5  mov     [rsp+338h+var_308], rax
0x1801c42ea  mov     [rsp+338h+var_310], 4
0x1801c42f2  mov     [rsp+338h+var_318], 39h ; '9'
0x1801c42fa  lea     r9, ?MDM_Policy_User_Config01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_User_Config01_Browser02_NodeList
0x1801c4301  mov     r8, [rsi+40h]
0x1801c4305  mov     rdx, [rsi+50h]
0x1801c4309  mov     rcx, r15
0x1801c430c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801c4311  mov     edi, eax
0x1801c4313  test    eax, eax
0x1801c4315  jz      short loc_1801C431C
0x1801c4317  jmp     loc_1801C521F
0x1801c431c  lea     rax, [rsp+338h+var_2F8]
0x1801c4321  mov     [rsp+338h+var_2C8], rax
0x1801c4326  mov     r12d, 1
0x1801c432c  mov     [rsp+338h+var_2C0], r12b
0x1801c4331  mov     r14, [rsp+338h+var_2F8]
0x1801c4336  test    r14, r14
0x1801c4339  jnz     short loc_1801C4343
0x1801c433b  mov     edi, r12d
0x1801c433e  jmp     loc_1801C521F
0x1801c4343  mov     r9d, 39h ; '9'; unsigned int
0x1801c4349  lea     r8, ?MDM_Policy_User_Config01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1801c4350  mov     rdx, rsi; struct _MI_Instance *
0x1801c4353  mov     rcx, r14; this
0x1801c4356  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1801c435b  lea     r8, [rsi+60h]; void *
0x1801c435f  cmp     [r8+4], r12b
0x1801c4363  jnz     short loc_1801C4398
0x1801c4365  lea     rdx, aAllowaddressba; "AllowAddressBarDropdown"
0x1801c436c  mov     rcx, r14; this
0x1801c436f  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c4374  mov     edi, eax
0x1801c4376  test    eax, eax
0x1801c4378  jz      short loc_1801C4398
0x1801c437a  mov     rcx, [rsp+338h+var_2F8]
0x1801c437f  test    rcx, rcx
0x1801c4382  jz      short loc_1801C4393
0x1801c4384  mov     rax, [rcx]
0x1801c4387  mov     edx, r12d
0x1801c438a  mov     rax, [rax]
0x1801c438d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c4392  nop
0x1801c4393  jmp     loc_1801C521F
0x1801c4398  lea     r8, [rsi+68h]; void *
0x1801c439c  cmp     [r8+4], r12b
0x1801c43a0  jnz     short loc_1801C43D5
0x1801c43a2  lea     rdx, aAllowautofill; "AllowAutofill"
0x1801c43a9  mov     rcx, r14; this
0x1801c43ac  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c43b1  mov     edi, eax
0x1801c43b3  test    eax, eax
0x1801c43b5  jz      short loc_1801C43D5
0x1801c43b7  mov     rcx, [rsp+338h+var_2F8]
0x1801c43bc  test    rcx, rcx
0x1801c43bf  jz      short loc_1801C43D0
0x1801c43c1  mov     rax, [rcx]
0x1801c43c4  mov     edx, r12d
0x1801c43c7  mov     rax, [rax]
0x1801c43ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c43cf  nop
0x1801c43d0  jmp     loc_1801C521F
0x1801c43d5  lea     r8, [rsi+70h]; void *
0x1801c43d9  cmp     [r8+4], r12b
0x1801c43dd  jnz     short loc_1801C4412
0x1801c43df  lea     rdx, aAllowconfigura; "AllowConfigurationUpdateForBooksLibrary"
0x1801c43e6  mov     rcx, r14; this
0x1801c43e9  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c43ee  mov     edi, eax
0x1801c43f0  test    eax, eax
0x1801c43f2  jz      short loc_1801C4412
0x1801c43f4  mov     rcx, [rsp+338h+var_2F8]
0x1801c43f9  test    rcx, rcx
0x1801c43fc  jz      short loc_1801C440D
0x1801c43fe  mov     rax, [rcx]
0x1801c4401  mov     edx, r12d
0x1801c4404  mov     rax, [rax]
0x1801c4407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c440c  nop
0x1801c440d  jmp     loc_1801C521F
0x1801c4412  lea     r8, [rsi+78h]; void *
0x1801c4416  cmp     [r8+4], r12b
0x1801c441a  jnz     short loc_1801C444F
0x1801c441c  lea     rdx, aAllowcookies; "AllowCookies"
0x1801c4423  mov     rcx, r14; this
0x1801c4426  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c442b  mov     edi, eax
0x1801c442d  test    eax, eax
0x1801c442f  jz      short loc_1801C444F
0x1801c4431  mov     rcx, [rsp+338h+var_2F8]
0x1801c4436  test    rcx, rcx
0x1801c4439  jz      short loc_1801C444A
0x1801c443b  mov     rax, [rcx]
0x1801c443e  mov     edx, r12d
0x1801c4441  mov     rax, [rax]
0x1801c4444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c4449  nop
0x1801c444a  jmp     loc_1801C521F
0x1801c444f  lea     r8, [rsi+80h]; void *
0x1801c4456  cmp     [r8+4], r12b
0x1801c445a  jnz     short loc_1801C448F
0x1801c445c  lea     rdx, aAllowdeveloper; "AllowDeveloperTools"
0x1801c4463  mov     rcx, r14; this
0x1801c4466  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c446b  mov     edi, eax
0x1801c446d  test    eax, eax
0x1801c446f  jz      short loc_1801C448F
0x1801c4471  mov     rcx, [rsp+338h+var_2F8]
0x1801c4476  test    rcx, rcx
0x1801c4479  jz      short loc_1801C448A
0x1801c447b  mov     rax, [rcx]
0x1801c447e  mov     edx, r12d
0x1801c4481  mov     rax, [rax]
0x1801c4484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c4489  nop
0x1801c448a  jmp     loc_1801C521F
0x1801c448f  lea     r8, [rsi+88h]; void *
0x1801c4496  cmp     [r8+4], r12b
0x1801c449a  jnz     short loc_1801C44CF
0x1801c449c  lea     rdx, aAllowdonottrac; "AllowDoNotTrack"
0x1801c44a3  mov     rcx, r14; this
0x1801c44a6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c44ab  mov     edi, eax
0x1801c44ad  test    eax, eax
0x1801c44af  jz      short loc_1801C44CF
0x1801c44b1  mov     rcx, [rsp+338h+var_2F8]
0x1801c44b6  test    rcx, rcx
0x1801c44b9  jz      short loc_1801C44CA
0x1801c44bb  mov     rax, [rcx]
0x1801c44be  mov     edx, r12d
0x1801c44c1  mov     rax, [rax]
0x1801c44c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c44c9  nop
0x1801c44ca  jmp     loc_1801C521F
0x1801c44cf  lea     r8, [rsi+90h]; void *
0x1801c44d6  cmp     [r8+4], r12b
0x1801c44da  jnz     short loc_1801C450F
0x1801c44dc  lea     rdx, aAllowextension; "AllowExtensions"
0x1801c44e3  mov     rcx, r14; this
0x1801c44e6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c44eb  mov     edi, eax
0x1801c44ed  test    eax, eax
0x1801c44ef  jz      short loc_1801C450F
0x1801c44f1  mov     rcx, [rsp+338h+var_2F8]
0x1801c44f6  test    rcx, rcx
0x1801c44f9  jz      short loc_1801C450A
0x1801c44fb  mov     rax, [rcx]
0x1801c44fe  mov     edx, r12d
0x1801c4501  mov     rax, [rax]
0x1801c4504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c4509  nop
0x1801c450a  jmp     loc_1801C521F
0x1801c450f  lea     r8, [rsi+98h]; void *
0x1801c4516  cmp     [r8+4], r12b
0x1801c451a  jnz     short loc_1801C454F
0x1801c451c  lea     rdx, aAllowflash; "AllowFlash"
0x1801c4523  mov     rcx, r14; this
0x1801c4526  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c452b  mov     edi, eax
0x1801c452d  test    eax, eax
0x1801c452f  jz      short loc_1801C454F
0x1801c4531  mov     rcx, [rsp+338h+var_2F8]
0x1801c4536  test    rcx, rcx
0x1801c4539  jz      short loc_1801C454A
0x1801c453b  mov     rax, [rcx]
0x1801c453e  mov     edx, r12d
0x1801c4541  mov     rax, [rax]
0x1801c4544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c4549  nop
0x1801c454a  jmp     loc_1801C521F
0x1801c454f  lea     r8, [rsi+0A0h]; void *
0x1801c4556  cmp     [r8+4], r12b
0x1801c455a  jnz     short loc_1801C458F
0x1801c455c  lea     rdx, aAllowflashclic; "AllowFlashClickToRun"
0x1801c4563  mov     rcx, r14; this
0x1801c4566  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c456b  mov     edi, eax
0x1801c456d  test    eax, eax
0x1801c456f  jz      short loc_1801C458F
0x1801c4571  mov     rcx, [rsp+338h+var_2F8]
0x1801c4576  test    rcx, rcx
0x1801c4579  jz      short loc_1801C458A
0x1801c457b  mov     rax, [rcx]
0x1801c457e  mov     edx, r12d
0x1801c4581  mov     rax, [rax]
0x1801c4584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c4589  nop
0x1801c458a  jmp     loc_1801C521F
0x1801c458f  lea     r8, [rsi+0A8h]; void *
0x1801c4596  cmp     [r8+4], r12b
0x1801c459a  jnz     short loc_1801C45CF
0x1801c459c  lea     rdx, aAllowfullscree; "AllowFullScreenMode"
0x1801c45a3  mov     rcx, r14; this
0x1801c45a6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c45ab  mov     edi, eax
0x1801c45ad  test    eax, eax
0x1801c45af  jz      short loc_1801C45CF
0x1801c45b1  mov     rcx, [rsp+338h+var_2F8]
0x1801c45b6  test    rcx, rcx
0x1801c45b9  jz      short loc_1801C45CA
0x1801c45bb  mov     rax, [rcx]
0x1801c45be  mov     edx, r12d
0x1801c45c1  mov     rax, [rax]
0x1801c45c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c45c9  nop
0x1801c45ca  jmp     loc_1801C521F
0x1801c45cf  lea     r8, [rsi+0B0h]; void *
0x1801c45d6  cmp     [r8+4], r12b
0x1801c45da  jnz     short loc_1801C460F
0x1801c45dc  lea     rdx, aAllowinprivate; "AllowInPrivate"
0x1801c45e3  mov     rcx, r14; this
0x1801c45e6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c45eb  mov     edi, eax
0x1801c45ed  test    eax, eax
0x1801c45ef  jz      short loc_1801C460F
0x1801c45f1  mov     rcx, [rsp+338h+var_2F8]
0x1801c45f6  test    rcx, rcx
0x1801c45f9  jz      short loc_1801C460A
0x1801c45fb  mov     rax, [rcx]
0x1801c45fe  mov     edx, r12d
0x1801c4601  mov     rax, [rax]
0x1801c4604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c4609  nop
0x1801c460a  jmp     loc_1801C521F
0x1801c460f  lea     r8, [rsi+0B8h]; void *
0x1801c4616  cmp     [r8+4], r12b
0x1801c461a  jnz     short loc_1801C464F
0x1801c461c  lea     rdx, aAllowmicrosoft_2; "AllowMicrosoftCompatibilityList"
0x1801c4623  mov     rcx, r14; this
0x1801c4626  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c462b  mov     edi, eax
0x1801c462d  test    eax, eax
0x1801c462f  jz      short loc_1801C464F
0x1801c4631  mov     rcx, [rsp+338h+var_2F8]
0x1801c4636  test    rcx, rcx
0x1801c4639  jz      short loc_1801C464A
0x1801c463b  mov     rax, [rcx]
  ... truncated ...
```
