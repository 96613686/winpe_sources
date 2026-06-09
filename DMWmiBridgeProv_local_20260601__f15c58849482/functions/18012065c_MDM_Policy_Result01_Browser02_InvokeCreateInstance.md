# MDM_Policy_Result01_Browser02_InvokeCreateInstance

- ea: `0x18012065c`
- end: `0x1801218fc`
- name: `MDM_Policy_Result01_Browser02_InvokeCreateInstance`
- size: `4768`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801205a0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x18012065c`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x18012089f`: `AllowConfigurationUpdateForBooksLibrary`
- `0x18012099c`: `AllowExtensions`
- `0x180120adc`: `AllowMicrosoftCompatibilityList`
- `0x180120cdc`: `AllowSideloadingOfExtensions`
- `0x180120e5c`: `ConfigureAdditionalSearchEngines`
- `0x180120e9c`: `ConfigureFavoritesBar`
- `0x180120edc`: `ConfigureHomeButton`
- `0x180120f1c`: `ConfigureKioskMode`
- `0x180120f5c`: `ConfigureKioskResetAfterIdleTimeout`
- `0x180120f9c`: `ConfigureOpenMicrosoftEdgeWith`
- `0x180120fdc`: `ConfigureTelemetryForMicrosoft365Analytics`
- `0x18012125c`: `EnterpriseSiteListServiceUrl`
- `0x18012131c`: `PreventAccessToAboutFlagsInMicrosoftEdge`
- `0x18012149c`: `PreventTurningOffRequiredExtensions`
- `0x18012165c`: `ShowMessageWhenOpeningSitesInInternetExplorer`
- `0x180120785`: `CreateInstanceStart`
- `0x180121862`: `CreateInstanceEnd`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_Browser02_InvokeCreateInstance(MI_Context *self, struct _MI_Instance *a2)
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
  v10[2] = "MDM_Policy_Result01_Browser02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v12);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v13 && (v15[0] || v15[1] || v15[2] || v15[3]) )
      v4 = v15;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_180353AEB,
      v14,
      v4);
  }
  if ( LOBYTE(a2[1].classDecl) && (v9 = 0, LOBYTE(a2[1].nameSpace)) )
  {
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
                               &MDM_Policy_Result01_Browser02_NodeList,
                               63,
                               4,
                               &v8);
    if ( inserted == MI_RESULT_OK )
    {
      v10[4] = &v8;
      v11 = 1;
      v6 = v8;
      if ( v8 )
      {
        WmiRequestHandler::SetRequestMIInstance(
          v8,
          a2,
          (struct WmiNodeInfo *)&MDM_Policy_Result01_Browser02_NodeList,
          0x3Fu);
        if ( BYTE4(a2[1].reserved[0]) == 1
          && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowAddressBarDropdown", a2[1].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[1].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowAutofill", &a2[1].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[1].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowConfigurationUpdateForBooksLibrary",
                                &a2[1].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[1].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowCookies", &a2[1].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowDeveloperTools", &a2[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowDoNotTrack", &a2[2].classDecl)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowExtensions", &a2[2].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowFlash", &a2[2].nameSpace)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowFlashClickToRun", a2[2].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowFullScreenMode", &a2[2].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowInPrivate", &a2[2].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowMicrosoftCompatibilityList",
                                &a2[2].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPasswordManager", &a2[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPopups", &a2[3].classDecl)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPrelaunch", &a2[3].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPrinting", &a2[3].nameSpace)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowSavingHistory", a2[3].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowSearchEngineCustomization",
                                &a2[3].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowSearchSuggestionsinAddressBar",
                                &a2[3].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowSideloadingOfExtensions",
                                &a2[3].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowSmartScreen", &a2[4])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowTabPreloading", &a2[4].classDecl)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowWebContentOnNewTabPage",
                                &a2[4].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AlwaysEnableBooksLibrary", &a2[4].nameSpace)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ClearBrowsingDataOnExit", a2[4].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[4].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureAdditionalSearchEngines",
                                &a2[4].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureFavoritesBar", &a2[4].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureHomeButton", &a2[5])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureKioskMode", &a2[5].classDecl)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureKioskResetAfterIdleTimeout",
                                &a2[5].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureOpenMicrosoftEdgeWith",
                                &a2[5].nameSpace)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureTelemetryForMicrosoft365Analytics",
                                a2[5].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[5].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DefaultFavoriteBarItem1Name",
                                &a2[5].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[6].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DefaultFavoriteBarItem1Url",
                                &a2[5].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[6].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DefaultFavoriteBarItem2Name",
                                &a2[6].classDecl)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[6].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DefaultFavoriteBarItem2Url",
                                &a2[6].nameSpace)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[6].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DefaultFavoriteBarItem3Name",
                                &a2[6].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[7].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DefaultFavoriteBarItem3Url",
                                &a2[6].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DisableLockdownOfStartPages",
                                &a2[7].classDecl)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"EnableExtendedBooksTelemetry",
                                &a2[7].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[7].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnterpriseModeSiteList", &a2[7].nameSpace)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[7].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"EnterpriseSiteListServiceUrl",
                                &a2[7].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[8].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"HomePages", &a2[7].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"LockdownFavorites", &a2[8].classDecl)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventAccessToAboutFlagsInMicrosoftEdge",
                                &a2[8].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventCertErrorOverrides",
                                &a2[8].nameSpace)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PreventFirstRunPage", a2[8].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventLiveTileDataCollection",
                                &a2[8].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventSmartScreenPromptOverride",
                                &a2[8].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventSmartScreenPromptOverrideForFiles",
                                &a2[8].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[9].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventTurningOffRequiredExtensions",
                                &a2[9])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[9].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventUsingLocalHostIPAddressForWebRTC",
                                &a2[9].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[9].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ProvisionFavorites", &a2[9].nameSpace)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[9].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SendIntranetTraffictoInternetExplorer",
                                &a2[9].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[9].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetDefaultSearchEngine", &a2[9].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[10].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetHomeButtonURL", &a2[10])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[10].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetNewTabPageURL", &a2[10].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[10].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ShowMessageWhenOpeningSitesInInternetExplorer",
                                a2[10].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[10].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SyncFavoritesBetweenIEAndMicrosoftEdge",
                                &a2[10].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[10].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"UnlockHomeButton", &a2[10].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[10].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UseSharedFolderForBooks",
                                &a2[10].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else
        {
          inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
          if ( inserted )
          {
            if ( v8 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
          }
          else
          {
            inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
            if ( inserted )
            {
              if ( v8 )
                (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
            }
            else
            {
              inserted = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_Browser02_rtti, &instance);
              if ( inserted )
              {
                if ( v8 )
                  (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
              }
              else
              {
                v9 = 1;
                MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, a2[1].ft);
                MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, a2[1].serverName);
                MI_Instance_Destruct((MI_Instance *)self);
                if ( v8 )
                  (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
                MI_Instance_Destruct(&instance);
              }
            }
          }
        }
      }
      else
      {
        inserted = MI_RESULT_FAILED;
      }
    }
  }
  else
  {
    inserted = MI_RESULT_INVALID_PARAMETER;
  }
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v10, "CreateInstanceEnd", inserted);
  v12 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      qword_180348B88,
      v14,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v12);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x18012065c  mov     [rsp+arg_10], rsi
0x180120661  mov     [rsp+arg_18], rdi
0x180120666  push    r12
0x180120668  push    r14
0x18012066a  push    r15
0x18012066c  sub     rsp, 380h
0x180120673  mov     rax, cs:__security_cookie
0x18012067a  xor     rax, rsp
0x18012067d  mov     [rsp+398h+var_28], rax
0x180120685  mov     rsi, rdx
0x180120688  mov     r15, rcx
0x18012068b  xor     edx, edx; Val
0x18012068d  mov     r8d, 2C0h; Size
0x180120693  lea     rcx, [rsp+398h+instance]; void *
0x18012069b  call    memset_0
0x1801206a0  mov     [rsp+398h+var_318], 0
0x1801206ab  mov     [rsp+398h+var_314], 0
0x1801206b3  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801206ba  mov     [rsp+398h+var_348], rax
0x1801206bf  lea     rax, [rsp+398h+var_318]
0x1801206c7  mov     [rsp+398h+var_340], rax
0x1801206cc  lea     rax, aMdmPolicyResul_101; "MDM_Policy_Result01_Browser02"
0x1801206d3  mov     [rsp+398h+var_338], rax
0x1801206d8  lea     rcx, [rsp+398h+var_318]
0x1801206e0  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801206e5  mov     eax, cs:dword_180380B68
0x1801206eb  cmp     eax, 5
0x1801206ee  jbe     short loc_180120764
0x1801206f0  mov     rdx, 200000000000h
0x1801206fa  lea     rcx, dword_180380B68
0x180120701  call    _tlgKeywordOn
0x180120706  test    al, al
0x180120708  jz      short loc_180120764
0x18012070a  cmp     [rsp+398h+var_314], 0
0x180120712  jz      short loc_180120746
0x180120714  cmp     [rsp+398h+var_300], 0
0x18012071c  jnz     short loc_18012073C
0x18012071e  cmp     [rsp+398h+var_2FC], 0
0x180120726  jnz     short loc_18012073C
0x180120728  cmp     [rsp+398h+var_2F8], 0
0x180120730  jnz     short loc_18012073C
0x180120732  cmp     [rsp+398h+var_2F4], 0
0x18012073a  jz      short loc_180120746
0x18012073c  lea     r9, [rsp+398h+var_300]
0x180120744  jmp     short loc_180120749
0x180120746  xor     r9d, r9d
0x180120749  lea     r8, [rsp+398h+var_310]
0x180120751  lea     rdx, byte_180353AEB
0x180120758  lea     rcx, dword_180380B68
0x18012075f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180120764  cmp     byte ptr [rsi+48h], 0
0x180120768  jz      loc_18012185A
0x18012076e  mov     [rsp+398h+var_350], 0
0x180120773  cmp     byte ptr [rsi+58h], 0
0x180120777  jz      loc_18012185A
0x18012077d  mov     r9, [rsi+40h]; unsigned __int16 *
0x180120781  mov     r8, [rsi+50h]; unsigned __int16 *
0x180120785  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x18012078c  lea     rcx, [rsp+398h+var_348]; this
0x180120791  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x180120796  nop
0x180120797  mov     [rsp+398h+var_358], 0
0x1801207a0  lea     rax, [rsp+398h+var_358]
0x1801207a5  mov     [rsp+398h+var_368], rax
0x1801207aa  mov     [rsp+398h+var_370], 4
0x1801207b2  mov     [rsp+398h+var_378], 3Fh ; '?'
0x1801207ba  lea     r9, ?MDM_Policy_Result01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_Browser02_NodeList
0x1801207c1  mov     r8, [rsi+40h]
0x1801207c5  mov     rdx, [rsi+50h]
0x1801207c9  mov     rcx, r15
0x1801207cc  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801207d1  mov     edi, eax
0x1801207d3  test    eax, eax
0x1801207d5  jz      short loc_1801207DC
0x1801207d7  jmp     loc_18012185F
0x1801207dc  lea     rax, [rsp+398h+var_358]
0x1801207e1  mov     [rsp+398h+var_328], rax
0x1801207e6  mov     r12d, 1
0x1801207ec  mov     [rsp+398h+var_320], r12b
0x1801207f1  mov     r14, [rsp+398h+var_358]
0x1801207f6  test    r14, r14
0x1801207f9  jnz     short loc_180120803
0x1801207fb  mov     edi, r12d
0x1801207fe  jmp     loc_18012185F
0x180120803  mov     r9d, 3Fh ; '?'; unsigned int
0x180120809  lea     r8, ?MDM_Policy_Result01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x180120810  mov     rdx, rsi; struct _MI_Instance *
0x180120813  mov     rcx, r14; this
0x180120816  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18012081b  lea     r8, [rsi+60h]; void *
0x18012081f  cmp     [r8+4], r12b
0x180120823  jnz     short loc_180120858
0x180120825  lea     rdx, aAllowaddressba; "AllowAddressBarDropdown"
0x18012082c  mov     rcx, r14; this
0x18012082f  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180120834  mov     edi, eax
0x180120836  test    eax, eax
0x180120838  jz      short loc_180120858
0x18012083a  mov     rcx, [rsp+398h+var_358]
0x18012083f  test    rcx, rcx
0x180120842  jz      short loc_180120853
0x180120844  mov     rax, [rcx]
0x180120847  mov     edx, r12d
0x18012084a  mov     rax, [rax]
0x18012084d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120852  nop
0x180120853  jmp     loc_18012185F
0x180120858  lea     r8, [rsi+68h]; void *
0x18012085c  cmp     [r8+4], r12b
0x180120860  jnz     short loc_180120895
0x180120862  lea     rdx, aAllowautofill; "AllowAutofill"
0x180120869  mov     rcx, r14; this
0x18012086c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180120871  mov     edi, eax
0x180120873  test    eax, eax
0x180120875  jz      short loc_180120895
0x180120877  mov     rcx, [rsp+398h+var_358]
0x18012087c  test    rcx, rcx
0x18012087f  jz      short loc_180120890
0x180120881  mov     rax, [rcx]
0x180120884  mov     edx, r12d
0x180120887  mov     rax, [rax]
0x18012088a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012088f  nop
0x180120890  jmp     loc_18012185F
0x180120895  lea     r8, [rsi+70h]; void *
0x180120899  cmp     [r8+4], r12b
0x18012089d  jnz     short loc_1801208D2
0x18012089f  lea     rdx, aAllowconfigura; "AllowConfigurationUpdateForBooksLibrary"
0x1801208a6  mov     rcx, r14; this
0x1801208a9  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801208ae  mov     edi, eax
0x1801208b0  test    eax, eax
0x1801208b2  jz      short loc_1801208D2
0x1801208b4  mov     rcx, [rsp+398h+var_358]
0x1801208b9  test    rcx, rcx
0x1801208bc  jz      short loc_1801208CD
0x1801208be  mov     rax, [rcx]
0x1801208c1  mov     edx, r12d
0x1801208c4  mov     rax, [rax]
0x1801208c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801208cc  nop
0x1801208cd  jmp     loc_18012185F
0x1801208d2  lea     r8, [rsi+78h]; void *
0x1801208d6  cmp     [r8+4], r12b
0x1801208da  jnz     short loc_18012090F
0x1801208dc  lea     rdx, aAllowcookies; "AllowCookies"
0x1801208e3  mov     rcx, r14; this
0x1801208e6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801208eb  mov     edi, eax
0x1801208ed  test    eax, eax
0x1801208ef  jz      short loc_18012090F
0x1801208f1  mov     rcx, [rsp+398h+var_358]
0x1801208f6  test    rcx, rcx
0x1801208f9  jz      short loc_18012090A
0x1801208fb  mov     rax, [rcx]
0x1801208fe  mov     edx, r12d
0x180120901  mov     rax, [rax]
0x180120904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120909  nop
0x18012090a  jmp     loc_18012185F
0x18012090f  lea     r8, [rsi+80h]; void *
0x180120916  cmp     [r8+4], r12b
0x18012091a  jnz     short loc_18012094F
0x18012091c  lea     rdx, aAllowdeveloper; "AllowDeveloperTools"
0x180120923  mov     rcx, r14; this
0x180120926  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18012092b  mov     edi, eax
0x18012092d  test    eax, eax
0x18012092f  jz      short loc_18012094F
0x180120931  mov     rcx, [rsp+398h+var_358]
0x180120936  test    rcx, rcx
0x180120939  jz      short loc_18012094A
0x18012093b  mov     rax, [rcx]
0x18012093e  mov     edx, r12d
0x180120941  mov     rax, [rax]
0x180120944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120949  nop
0x18012094a  jmp     loc_18012185F
0x18012094f  lea     r8, [rsi+88h]; void *
0x180120956  cmp     [r8+4], r12b
0x18012095a  jnz     short loc_18012098F
0x18012095c  lea     rdx, aAllowdonottrac; "AllowDoNotTrack"
0x180120963  mov     rcx, r14; this
0x180120966  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18012096b  mov     edi, eax
0x18012096d  test    eax, eax
0x18012096f  jz      short loc_18012098F
0x180120971  mov     rcx, [rsp+398h+var_358]
0x180120976  test    rcx, rcx
0x180120979  jz      short loc_18012098A
0x18012097b  mov     rax, [rcx]
0x18012097e  mov     edx, r12d
0x180120981  mov     rax, [rax]
0x180120984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120989  nop
0x18012098a  jmp     loc_18012185F
0x18012098f  lea     r8, [rsi+90h]; void *
0x180120996  cmp     [r8+4], r12b
0x18012099a  jnz     short loc_1801209CF
0x18012099c  lea     rdx, aAllowextension; "AllowExtensions"
0x1801209a3  mov     rcx, r14; this
0x1801209a6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801209ab  mov     edi, eax
0x1801209ad  test    eax, eax
0x1801209af  jz      short loc_1801209CF
0x1801209b1  mov     rcx, [rsp+398h+var_358]
0x1801209b6  test    rcx, rcx
0x1801209b9  jz      short loc_1801209CA
0x1801209bb  mov     rax, [rcx]
0x1801209be  mov     edx, r12d
0x1801209c1  mov     rax, [rax]
0x1801209c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801209c9  nop
0x1801209ca  jmp     loc_18012185F
0x1801209cf  lea     r8, [rsi+98h]; void *
0x1801209d6  cmp     [r8+4], r12b
0x1801209da  jnz     short loc_180120A0F
0x1801209dc  lea     rdx, aAllowflash; "AllowFlash"
0x1801209e3  mov     rcx, r14; this
0x1801209e6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801209eb  mov     edi, eax
0x1801209ed  test    eax, eax
0x1801209ef  jz      short loc_180120A0F
0x1801209f1  mov     rcx, [rsp+398h+var_358]
0x1801209f6  test    rcx, rcx
0x1801209f9  jz      short loc_180120A0A
0x1801209fb  mov     rax, [rcx]
0x1801209fe  mov     edx, r12d
0x180120a01  mov     rax, [rax]
0x180120a04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120a09  nop
0x180120a0a  jmp     loc_18012185F
0x180120a0f  lea     r8, [rsi+0A0h]; void *
0x180120a16  cmp     [r8+4], r12b
0x180120a1a  jnz     short loc_180120A4F
0x180120a1c  lea     rdx, aAllowflashclic; "AllowFlashClickToRun"
0x180120a23  mov     rcx, r14; this
0x180120a26  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180120a2b  mov     edi, eax
0x180120a2d  test    eax, eax
0x180120a2f  jz      short loc_180120A4F
0x180120a31  mov     rcx, [rsp+398h+var_358]
0x180120a36  test    rcx, rcx
0x180120a39  jz      short loc_180120A4A
0x180120a3b  mov     rax, [rcx]
0x180120a3e  mov     edx, r12d
0x180120a41  mov     rax, [rax]
0x180120a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120a49  nop
0x180120a4a  jmp     loc_18012185F
0x180120a4f  lea     r8, [rsi+0A8h]; void *
0x180120a56  cmp     [r8+4], r12b
0x180120a5a  jnz     short loc_180120A8F
0x180120a5c  lea     rdx, aAllowfullscree; "AllowFullScreenMode"
0x180120a63  mov     rcx, r14; this
0x180120a66  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180120a6b  mov     edi, eax
0x180120a6d  test    eax, eax
0x180120a6f  jz      short loc_180120A8F
0x180120a71  mov     rcx, [rsp+398h+var_358]
0x180120a76  test    rcx, rcx
0x180120a79  jz      short loc_180120A8A
0x180120a7b  mov     rax, [rcx]
0x180120a7e  mov     edx, r12d
0x180120a81  mov     rax, [rax]
0x180120a84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120a89  nop
0x180120a8a  jmp     loc_18012185F
0x180120a8f  lea     r8, [rsi+0B0h]; void *
0x180120a96  cmp     [r8+4], r12b
0x180120a9a  jnz     short loc_180120ACF
0x180120a9c  lea     rdx, aAllowinprivate; "AllowInPrivate"
0x180120aa3  mov     rcx, r14; this
0x180120aa6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180120aab  mov     edi, eax
0x180120aad  test    eax, eax
0x180120aaf  jz      short loc_180120ACF
0x180120ab1  mov     rcx, [rsp+398h+var_358]
0x180120ab6  test    rcx, rcx
0x180120ab9  jz      short loc_180120ACA
0x180120abb  mov     rax, [rcx]
0x180120abe  mov     edx, r12d
0x180120ac1  mov     rax, [rax]
0x180120ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120ac9  nop
0x180120aca  jmp     loc_18012185F
0x180120acf  lea     r8, [rsi+0B8h]; void *
0x180120ad6  cmp     [r8+4], r12b
0x180120ada  jnz     short loc_180120B0F
0x180120adc  lea     rdx, aAllowmicrosoft_2; "AllowMicrosoftCompatibilityList"
0x180120ae3  mov     rcx, r14; this
0x180120ae6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180120aeb  mov     edi, eax
0x180120aed  test    eax, eax
0x180120aef  jz      short loc_180120B0F
0x180120af1  mov     rcx, [rsp+398h+var_358]
0x180120af6  test    rcx, rcx
0x180120af9  jz      short loc_180120B0A
0x180120afb  mov     rax, [rcx]
  ... truncated ...
```
