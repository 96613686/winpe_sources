# MDM_Policy_User_Config01_Browser02_InvokeCreateInstance

- ea: `0x1801c44dc`
- end: `0x1801c55fb`
- name: `MDM_Policy_User_Config01_Browser02_InvokeCreateInstance`
- size: `4383`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801c43e0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x1801c44dc`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x1801c471f`: `AllowConfigurationUpdateForBooksLibrary`
- `0x1801c481c`: `AllowExtensions`
- `0x1801c495c`: `AllowMicrosoftCompatibilityList`
- `0x1801c4b5c`: `AllowSideloadingOfExtensions`
- `0x1801c4cdc`: `ConfigureAdditionalSearchEngines`
- `0x1801c4d1c`: `ConfigureFavoritesBar`
- `0x1801c4d5c`: `ConfigureHomeButton`
- `0x1801c4d9c`: `ConfigureKioskMode`
- `0x1801c4ddc`: `ConfigureKioskResetAfterIdleTimeout`
- `0x1801c4e1c`: `ConfigureOpenMicrosoftEdgeWith`
- `0x1801c4e5c`: `ConfigureTelemetryForMicrosoft365Analytics`
- `0x1801c4f5c`: `EnterpriseSiteListServiceUrl`
- `0x1801c501c`: `PreventAccessToAboutFlagsInMicrosoftEdge`
- `0x1801c519c`: `PreventTurningOffRequiredExtensions`
- `0x1801c535c`: `ShowMessageWhenOpeningSitesInInternetExplorer`
- `0x1801c4605`: `CreateInstanceStart`
- `0x1801c5562`: `CreateInstanceEnd`
- `0x1801c454c`: `MDM_Policy_User_Config01_Browser02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_User_Config01_Browser02_InvokeCreateInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  unsigned int inserted; // edi
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
    inserted = 4;
    goto LABEL_249;
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
               (struct WmiNodeInfo *)&MDM_Policy_User_Config01_Browser02_NodeList,
               0x39u,
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
      goto LABEL_249;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v8,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_User_Config01_Browser02_NodeList,
      0x39u);
    if ( BYTE4(a2[1].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowAddressBarDropdown", (LONG *)a2[1].reserved);
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
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowAutofill", (LONG *)&a2[1].reserved[1]);
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
                   (LONG *)&a2[1].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[1].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowCookies", (LONG *)&a2[1].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[2].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowDeveloperTools", (LONG *)&a2[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[2].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowDoNotTrack", (LONG *)&a2[2].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[2].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowExtensions", (LONG *)&a2[2].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[2].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowFlash", (LONG *)&a2[2].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[2].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowFlashClickToRun", (LONG *)a2[2].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[2].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowFullScreenMode", (LONG *)&a2[2].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[2].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowInPrivate", (LONG *)&a2[2].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
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
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[3].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPasswordManager", (LONG *)&a2[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[3].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPopups", (LONG *)&a2[3].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[3].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPrelaunch", (LONG *)&a2[3].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[3].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPrinting", (LONG *)&a2[3].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[3].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowSavingHistory", (LONG *)a2[3].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
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
          goto LABEL_249;
        goto LABEL_244;
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
          goto LABEL_249;
        goto LABEL_244;
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
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[4].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowSmartScreen", (LONG *)&a2[4]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[4].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowTabPreloading", (LONG *)&a2[4].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[4].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowWebContentOnNewTabPage", (LONG *)&a2[4].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[4].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AlwaysEnableBooksLibrary", (LONG *)&a2[4].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[4].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ClearBrowsingDataOnExit", (LONG *)a2[4].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
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
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[4].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureFavoritesBar", (LONG *)&a2[4].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[5].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureHomeButton", (LONG *)&a2[5]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[5].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureKioskMode", (LONG *)&a2[5].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
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
          goto LABEL_249;
        goto LABEL_244;
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
          goto LABEL_249;
        goto LABEL_244;
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
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[5].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"DisableLockdownOfStartPages", (LONG *)&a2[5].reserved[1]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[5].reserved[2]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"EnableExtendedBooksTelemetry",
                   (LONG *)&a2[5].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( LOBYTE(a2[6].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnterpriseModeSiteList", (LONG *)&a2[5].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( LOBYTE(a2[6].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnterpriseSiteListServiceUrl", (LONG *)&a2[6].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( LOBYTE(a2[6].reserved[0]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"HomePages", (LONG *)&a2[6].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[6].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"LockdownFavorites", (LONG *)&a2[6].reserved[1]);
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
                   (LONG *)&a2[6].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[6].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PreventCertErrorOverrides", (LONG *)&a2[6].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[7].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PreventFirstRunPage", (LONG *)&a2[7]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[7].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PreventLiveTileDataCollection", (LONG *)&a2[7].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[7].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"PreventSmartScreenPromptOverride",
                   (LONG *)&a2[7].serverName);
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
                   (LONG *)&a2[7].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( LOBYTE(a2[7].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"PreventTurningOffRequiredExtensions",
                   (LONG *)a2[7].reserved);
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
                   (LONG *)&a2[7].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( LOBYTE(a2[8].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ProvisionFavorites", (LONG *)&a2[7].reserved[3]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[8].classDecl) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"SendIntranetTraffictoInternetExplorer",
                   (LONG *)&a2[8].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( LOBYTE(a2[8].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetDefaultSearchEngine", (LONG *)&a2[8].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( LOBYTE(a2[8].reserved[1]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetHomeButtonURL", (LONG *)a2[8].reserved);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( LOBYTE(a2[8].reserved[3]) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetNewTabPageURL", (LONG *)&a2[8].reserved[2]);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[9].ft) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(
                   v6,
                   L"ShowMessageWhenOpeningSitesInInternetExplorer",
                   (LONG *)&a2[9]);
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
                   (LONG *)&a2[9].classDecl);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[9].serverName) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"UnlockHomeButton", (LONG *)&a2[9].serverName);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    if ( BYTE4(a2[9].nameSpace) == 1 )
    {
      inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"UseSharedFolderForBooks", (LONG *)&a2[9].nameSpace);
      if ( inserted )
      {
        if ( !v8 )
          goto LABEL_249;
        goto LABEL_244;
      }
    }
    inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( inserted )
    {
      if ( !v8 )
        goto LABEL_249;
      goto LABEL_244;
    }
    inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
  return inserted;
}

```

## disassembly

```asm
0x1801c44dc  mov     [rsp+arg_10], rsi
0x1801c44e1  mov     [rsp+arg_18], rdi
0x1801c44e6  push    r12
0x1801c44e8  push    r14
0x1801c44ea  push    r15
0x1801c44ec  sub     rsp, 320h
0x1801c44f3  mov     rax, cs:__security_cookie
0x1801c44fa  xor     rax, rsp
0x1801c44fd  mov     [rsp+338h+var_28], rax
0x1801c4505  mov     rsi, rdx
0x1801c4508  mov     r15, rcx
0x1801c450b  xor     edx, edx; Val
0x1801c450d  mov     r8d, 260h; Size
0x1801c4513  lea     rcx, [rsp+338h+instance]; void *
0x1801c451b  call    memset_0
0x1801c4520  mov     [rsp+338h+var_2B8], 0
0x1801c452b  mov     [rsp+338h+var_2B4], 0
0x1801c4533  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801c453a  mov     [rsp+338h+var_2E8], rax
0x1801c453f  lea     rax, [rsp+338h+var_2B8]
0x1801c4547  mov     [rsp+338h+var_2E0], rax
0x1801c454c  lea     rax, aMdmPolicyUserC_19; "MDM_Policy_User_Config01_Browser02"
0x1801c4553  mov     [rsp+338h+var_2D8], rax
0x1801c4558  lea     rcx, [rsp+338h+var_2B8]
0x1801c4560  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801c4565  mov     eax, cs:dword_180380B68
0x1801c456b  cmp     eax, 5
0x1801c456e  jbe     short loc_1801C45E4
0x1801c4570  mov     rdx, 200000000000h
0x1801c457a  lea     rcx, dword_180380B68
0x1801c4581  call    _tlgKeywordOn
0x1801c4586  test    al, al
0x1801c4588  jz      short loc_1801C45E4
0x1801c458a  cmp     [rsp+338h+var_2B4], 0
0x1801c4592  jz      short loc_1801C45C6
0x1801c4594  cmp     [rsp+338h+var_2A0], 0
0x1801c459c  jnz     short loc_1801C45BC
0x1801c459e  cmp     [rsp+338h+var_29C], 0
0x1801c45a6  jnz     short loc_1801C45BC
0x1801c45a8  cmp     [rsp+338h+var_298], 0
0x1801c45b0  jnz     short loc_1801C45BC
0x1801c45b2  cmp     [rsp+338h+var_294], 0
0x1801c45ba  jz      short loc_1801C45C6
0x1801c45bc  lea     r9, [rsp+338h+var_2A0]
0x1801c45c4  jmp     short loc_1801C45C9
0x1801c45c6  xor     r9d, r9d
0x1801c45c9  lea     r8, [rsp+338h+var_2B0]
0x1801c45d1  lea     rdx, byte_180369813
0x1801c45d8  lea     rcx, dword_180380B68
0x1801c45df  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801c45e4  cmp     byte ptr [rsi+48h], 0
0x1801c45e8  jz      loc_1801C555A
0x1801c45ee  mov     [rsp+338h+var_2F0], 0
0x1801c45f3  cmp     byte ptr [rsi+58h], 0
0x1801c45f7  jz      loc_1801C555A
0x1801c45fd  mov     r9, [rsi+40h]; unsigned __int16 *
0x1801c4601  mov     r8, [rsi+50h]; unsigned __int16 *
0x1801c4605  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x1801c460c  lea     rcx, [rsp+338h+var_2E8]; this
0x1801c4611  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1801c4616  nop
0x1801c4617  mov     [rsp+338h+var_2F8], 0
0x1801c4620  lea     rax, [rsp+338h+var_2F8]
0x1801c4625  mov     [rsp+338h+var_308], rax
0x1801c462a  mov     [rsp+338h+var_310], 4
0x1801c4632  mov     [rsp+338h+var_318], 39h ; '9'
0x1801c463a  lea     r9, ?MDM_Policy_User_Config01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_User_Config01_Browser02_NodeList
0x1801c4641  mov     r8, [rsi+40h]
0x1801c4645  mov     rdx, [rsi+50h]
0x1801c4649  mov     rcx, r15
0x1801c464c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801c4651  mov     edi, eax
0x1801c4653  test    eax, eax
0x1801c4655  jz      short loc_1801C465C
0x1801c4657  jmp     loc_1801C555F
0x1801c465c  lea     rax, [rsp+338h+var_2F8]
0x1801c4661  mov     [rsp+338h+var_2C8], rax
0x1801c4666  mov     r12d, 1
0x1801c466c  mov     [rsp+338h+var_2C0], r12b
0x1801c4671  mov     r14, [rsp+338h+var_2F8]
0x1801c4676  test    r14, r14
0x1801c4679  jnz     short loc_1801C4683
0x1801c467b  mov     edi, r12d
0x1801c467e  jmp     loc_1801C555F
0x1801c4683  mov     r9d, 39h ; '9'; unsigned int
0x1801c4689  lea     r8, ?MDM_Policy_User_Config01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1801c4690  mov     rdx, rsi; struct _MI_Instance *
0x1801c4693  mov     rcx, r14; this
0x1801c4696  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1801c469b  lea     r8, [rsi+60h]; void *
0x1801c469f  cmp     [r8+4], r12b
0x1801c46a3  jnz     short loc_1801C46D8
0x1801c46a5  lea     rdx, aAllowaddressba; "AllowAddressBarDropdown"
0x1801c46ac  mov     rcx, r14; this
0x1801c46af  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c46b4  mov     edi, eax
0x1801c46b6  test    eax, eax
0x1801c46b8  jz      short loc_1801C46D8
0x1801c46ba  mov     rcx, [rsp+338h+var_2F8]
0x1801c46bf  test    rcx, rcx
0x1801c46c2  jz      short loc_1801C46D3
0x1801c46c4  mov     rax, [rcx]
0x1801c46c7  mov     edx, r12d
0x1801c46ca  mov     rax, [rax]
0x1801c46cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c46d2  nop
0x1801c46d3  jmp     loc_1801C555F
0x1801c46d8  lea     r8, [rsi+68h]; void *
0x1801c46dc  cmp     [r8+4], r12b
0x1801c46e0  jnz     short loc_1801C4715
0x1801c46e2  lea     rdx, aAllowautofill; "AllowAutofill"
0x1801c46e9  mov     rcx, r14; this
0x1801c46ec  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c46f1  mov     edi, eax
0x1801c46f3  test    eax, eax
0x1801c46f5  jz      short loc_1801C4715
0x1801c46f7  mov     rcx, [rsp+338h+var_2F8]
0x1801c46fc  test    rcx, rcx
0x1801c46ff  jz      short loc_1801C4710
0x1801c4701  mov     rax, [rcx]
0x1801c4704  mov     edx, r12d
0x1801c4707  mov     rax, [rax]
0x1801c470a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c470f  nop
0x1801c4710  jmp     loc_1801C555F
0x1801c4715  lea     r8, [rsi+70h]; void *
0x1801c4719  cmp     [r8+4], r12b
0x1801c471d  jnz     short loc_1801C4752
0x1801c471f  lea     rdx, aAllowconfigura; "AllowConfigurationUpdateForBooksLibrary"
0x1801c4726  mov     rcx, r14; this
0x1801c4729  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c472e  mov     edi, eax
0x1801c4730  test    eax, eax
0x1801c4732  jz      short loc_1801C4752
0x1801c4734  mov     rcx, [rsp+338h+var_2F8]
0x1801c4739  test    rcx, rcx
0x1801c473c  jz      short loc_1801C474D
0x1801c473e  mov     rax, [rcx]
0x1801c4741  mov     edx, r12d
0x1801c4744  mov     rax, [rax]
0x1801c4747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c474c  nop
0x1801c474d  jmp     loc_1801C555F
0x1801c4752  lea     r8, [rsi+78h]; void *
0x1801c4756  cmp     [r8+4], r12b
0x1801c475a  jnz     short loc_1801C478F
0x1801c475c  lea     rdx, aAllowcookies; "AllowCookies"
0x1801c4763  mov     rcx, r14; this
0x1801c4766  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c476b  mov     edi, eax
0x1801c476d  test    eax, eax
0x1801c476f  jz      short loc_1801C478F
0x1801c4771  mov     rcx, [rsp+338h+var_2F8]
0x1801c4776  test    rcx, rcx
0x1801c4779  jz      short loc_1801C478A
0x1801c477b  mov     rax, [rcx]
0x1801c477e  mov     edx, r12d
0x1801c4781  mov     rax, [rax]
0x1801c4784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c4789  nop
0x1801c478a  jmp     loc_1801C555F
0x1801c478f  lea     r8, [rsi+80h]; void *
0x1801c4796  cmp     [r8+4], r12b
0x1801c479a  jnz     short loc_1801C47CF
0x1801c479c  lea     rdx, aAllowdeveloper; "AllowDeveloperTools"
0x1801c47a3  mov     rcx, r14; this
0x1801c47a6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c47ab  mov     edi, eax
0x1801c47ad  test    eax, eax
0x1801c47af  jz      short loc_1801C47CF
0x1801c47b1  mov     rcx, [rsp+338h+var_2F8]
0x1801c47b6  test    rcx, rcx
0x1801c47b9  jz      short loc_1801C47CA
0x1801c47bb  mov     rax, [rcx]
0x1801c47be  mov     edx, r12d
0x1801c47c1  mov     rax, [rax]
0x1801c47c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c47c9  nop
0x1801c47ca  jmp     loc_1801C555F
0x1801c47cf  lea     r8, [rsi+88h]; void *
0x1801c47d6  cmp     [r8+4], r12b
0x1801c47da  jnz     short loc_1801C480F
0x1801c47dc  lea     rdx, aAllowdonottrac; "AllowDoNotTrack"
0x1801c47e3  mov     rcx, r14; this
0x1801c47e6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c47eb  mov     edi, eax
0x1801c47ed  test    eax, eax
0x1801c47ef  jz      short loc_1801C480F
0x1801c47f1  mov     rcx, [rsp+338h+var_2F8]
0x1801c47f6  test    rcx, rcx
0x1801c47f9  jz      short loc_1801C480A
0x1801c47fb  mov     rax, [rcx]
0x1801c47fe  mov     edx, r12d
0x1801c4801  mov     rax, [rax]
0x1801c4804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c4809  nop
0x1801c480a  jmp     loc_1801C555F
0x1801c480f  lea     r8, [rsi+90h]; void *
0x1801c4816  cmp     [r8+4], r12b
0x1801c481a  jnz     short loc_1801C484F
0x1801c481c  lea     rdx, aAllowextension; "AllowExtensions"
0x1801c4823  mov     rcx, r14; this
0x1801c4826  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c482b  mov     edi, eax
0x1801c482d  test    eax, eax
0x1801c482f  jz      short loc_1801C484F
0x1801c4831  mov     rcx, [rsp+338h+var_2F8]
0x1801c4836  test    rcx, rcx
0x1801c4839  jz      short loc_1801C484A
0x1801c483b  mov     rax, [rcx]
0x1801c483e  mov     edx, r12d
0x1801c4841  mov     rax, [rax]
0x1801c4844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c4849  nop
0x1801c484a  jmp     loc_1801C555F
0x1801c484f  lea     r8, [rsi+98h]; void *
0x1801c4856  cmp     [r8+4], r12b
0x1801c485a  jnz     short loc_1801C488F
0x1801c485c  lea     rdx, aAllowflash; "AllowFlash"
0x1801c4863  mov     rcx, r14; this
0x1801c4866  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c486b  mov     edi, eax
0x1801c486d  test    eax, eax
0x1801c486f  jz      short loc_1801C488F
0x1801c4871  mov     rcx, [rsp+338h+var_2F8]
0x1801c4876  test    rcx, rcx
0x1801c4879  jz      short loc_1801C488A
0x1801c487b  mov     rax, [rcx]
0x1801c487e  mov     edx, r12d
0x1801c4881  mov     rax, [rax]
0x1801c4884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c4889  nop
0x1801c488a  jmp     loc_1801C555F
0x1801c488f  lea     r8, [rsi+0A0h]; void *
0x1801c4896  cmp     [r8+4], r12b
0x1801c489a  jnz     short loc_1801C48CF
0x1801c489c  lea     rdx, aAllowflashclic; "AllowFlashClickToRun"
0x1801c48a3  mov     rcx, r14; this
0x1801c48a6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c48ab  mov     edi, eax
0x1801c48ad  test    eax, eax
0x1801c48af  jz      short loc_1801C48CF
0x1801c48b1  mov     rcx, [rsp+338h+var_2F8]
0x1801c48b6  test    rcx, rcx
0x1801c48b9  jz      short loc_1801C48CA
0x1801c48bb  mov     rax, [rcx]
0x1801c48be  mov     edx, r12d
0x1801c48c1  mov     rax, [rax]
0x1801c48c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c48c9  nop
0x1801c48ca  jmp     loc_1801C555F
0x1801c48cf  lea     r8, [rsi+0A8h]; void *
0x1801c48d6  cmp     [r8+4], r12b
0x1801c48da  jnz     short loc_1801C490F
0x1801c48dc  lea     rdx, aAllowfullscree; "AllowFullScreenMode"
0x1801c48e3  mov     rcx, r14; this
0x1801c48e6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c48eb  mov     edi, eax
0x1801c48ed  test    eax, eax
0x1801c48ef  jz      short loc_1801C490F
0x1801c48f1  mov     rcx, [rsp+338h+var_2F8]
0x1801c48f6  test    rcx, rcx
0x1801c48f9  jz      short loc_1801C490A
0x1801c48fb  mov     rax, [rcx]
0x1801c48fe  mov     edx, r12d
0x1801c4901  mov     rax, [rax]
0x1801c4904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c4909  nop
0x1801c490a  jmp     loc_1801C555F
0x1801c490f  lea     r8, [rsi+0B0h]; void *
0x1801c4916  cmp     [r8+4], r12b
0x1801c491a  jnz     short loc_1801C494F
0x1801c491c  lea     rdx, aAllowinprivate; "AllowInPrivate"
0x1801c4923  mov     rcx, r14; this
0x1801c4926  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c492b  mov     edi, eax
0x1801c492d  test    eax, eax
0x1801c492f  jz      short loc_1801C494F
0x1801c4931  mov     rcx, [rsp+338h+var_2F8]
0x1801c4936  test    rcx, rcx
0x1801c4939  jz      short loc_1801C494A
0x1801c493b  mov     rax, [rcx]
0x1801c493e  mov     edx, r12d
0x1801c4941  mov     rax, [rax]
0x1801c4944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c4949  nop
0x1801c494a  jmp     loc_1801C555F
0x1801c494f  lea     r8, [rsi+0B8h]; void *
0x1801c4956  cmp     [r8+4], r12b
0x1801c495a  jnz     short loc_1801C498F
0x1801c495c  lea     rdx, aAllowmicrosoft_2; "AllowMicrosoftCompatibilityList"
0x1801c4963  mov     rcx, r14; this
0x1801c4966  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c496b  mov     edi, eax
0x1801c496d  test    eax, eax
0x1801c496f  jz      short loc_1801C498F
0x1801c4971  mov     rcx, [rsp+338h+var_2F8]
0x1801c4976  test    rcx, rcx
0x1801c4979  jz      short loc_1801C498A
0x1801c497b  mov     rax, [rcx]
  ... truncated ...
```
