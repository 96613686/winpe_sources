# MDM_Policy_User_Result01_Browser02_InvokeCreateInstance

- ea: `0x1801f205c`
- end: `0x1801f317c`
- name: `MDM_Policy_User_Result01_Browser02_InvokeCreateInstance`
- size: `4384`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801f1fa0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x1801f205c`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x1801f229f`: `AllowConfigurationUpdateForBooksLibrary`
- `0x1801f239c`: `AllowExtensions`
- `0x1801f24dc`: `AllowMicrosoftCompatibilityList`
- `0x1801f26dc`: `AllowSideloadingOfExtensions`
- `0x1801f285c`: `ConfigureAdditionalSearchEngines`
- `0x1801f289c`: `ConfigureFavoritesBar`
- `0x1801f28dc`: `ConfigureHomeButton`
- `0x1801f291c`: `ConfigureKioskMode`
- `0x1801f295c`: `ConfigureKioskResetAfterIdleTimeout`
- `0x1801f299c`: `ConfigureOpenMicrosoftEdgeWith`
- `0x1801f29dc`: `ConfigureTelemetryForMicrosoft365Analytics`
- `0x1801f2adc`: `EnterpriseSiteListServiceUrl`
- `0x1801f2b9c`: `PreventAccessToAboutFlagsInMicrosoftEdge`
- `0x1801f2d1c`: `PreventTurningOffRequiredExtensions`
- `0x1801f2edc`: `ShowMessageWhenOpeningSitesInInternetExplorer`
- `0x1801f2185`: `CreateInstanceStart`
- `0x1801f30e2`: `CreateInstanceEnd`

## pseudocode

```c
__int64 __fastcall MDM_Policy_User_Result01_Browser02_InvokeCreateInstance(MI_Context *self, struct _MI_Instance *a2)
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
  v10[2] = "MDM_Policy_User_Result01_Browser02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v12);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v13 && (v15[0] || v15[1] || v15[2] || v15[3]) )
      v4 = v15;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_180353453,
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
                               &MDM_Policy_User_Result01_Browser02_NodeList,
                               57,
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
          (struct WmiNodeInfo *)&MDM_Policy_User_Result01_Browser02_NodeList,
          0x39u);
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
        else if ( BYTE4(a2[5].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DisableLockdownOfStartPages",
                                &a2[5].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"EnableExtendedBooksTelemetry",
                                &a2[5].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[6].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnterpriseModeSiteList", &a2[5].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[6].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"EnterpriseSiteListServiceUrl",
                                &a2[6].classDecl)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[6].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"HomePages", &a2[6].nameSpace)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"LockdownFavorites", &a2[6].reserved[1])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventAccessToAboutFlagsInMicrosoftEdge",
                                &a2[6].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventCertErrorOverrides",
                                &a2[6].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PreventFirstRunPage", &a2[7])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventLiveTileDataCollection",
                                &a2[7].classDecl)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventSmartScreenPromptOverride",
                                &a2[7].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventSmartScreenPromptOverrideForFiles",
                                &a2[7].nameSpace)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[7].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventTurningOffRequiredExtensions",
                                a2[7].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventUsingLocalHostIPAddressForWebRTC",
                                &a2[7].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[8].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ProvisionFavorites", &a2[7].reserved[3])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SendIntranetTraffictoInternetExplorer",
                                &a2[8].classDecl)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[8].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetDefaultSearchEngine", &a2[8].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[8].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetHomeButtonURL", a2[8].reserved)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[8].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetNewTabPageURL", &a2[8].reserved[2])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[9].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ShowMessageWhenOpeningSitesInInternetExplorer",
                                &a2[9])) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[9].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SyncFavoritesBetweenIEAndMicrosoftEdge",
                                &a2[9].classDecl)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[9].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"UnlockHomeButton", &a2[9].serverName)) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[9].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"UseSharedFolderForBooks", &a2[9].nameSpace)) != MI_RESULT_OK )
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
              inserted = MI_Context_ConstructInstance(self, &MDM_Policy_User_Result01_Browser02_rtti, &instance);
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
      &word_18034212E,
      v14,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v12);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1801f205c  mov     [rsp+arg_10], rsi
0x1801f2061  mov     [rsp+arg_18], rdi
0x1801f2066  push    r12
0x1801f2068  push    r14
0x1801f206a  push    r15
0x1801f206c  sub     rsp, 320h
0x1801f2073  mov     rax, cs:__security_cookie
0x1801f207a  xor     rax, rsp
0x1801f207d  mov     [rsp+338h+var_28], rax
0x1801f2085  mov     rsi, rdx
0x1801f2088  mov     r15, rcx
0x1801f208b  xor     edx, edx; Val
0x1801f208d  mov     r8d, 260h; Size
0x1801f2093  lea     rcx, [rsp+338h+instance]; void *
0x1801f209b  call    memset_0
0x1801f20a0  mov     [rsp+338h+var_2B8], 0
0x1801f20ab  mov     [rsp+338h+var_2B4], 0
0x1801f20b3  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801f20ba  mov     [rsp+338h+var_2E8], rax
0x1801f20bf  lea     rax, [rsp+338h+var_2B8]
0x1801f20c7  mov     [rsp+338h+var_2E0], rax
0x1801f20cc  lea     rax, aMdmPolicyUserR_29; "MDM_Policy_User_Result01_Browser02"
0x1801f20d3  mov     [rsp+338h+var_2D8], rax
0x1801f20d8  lea     rcx, [rsp+338h+var_2B8]
0x1801f20e0  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801f20e5  mov     eax, cs:dword_180380B68
0x1801f20eb  cmp     eax, 5
0x1801f20ee  jbe     short loc_1801F2164
0x1801f20f0  mov     rdx, 200000000000h
0x1801f20fa  lea     rcx, dword_180380B68
0x1801f2101  call    _tlgKeywordOn
0x1801f2106  test    al, al
0x1801f2108  jz      short loc_1801F2164
0x1801f210a  cmp     [rsp+338h+var_2B4], 0
0x1801f2112  jz      short loc_1801F2146
0x1801f2114  cmp     [rsp+338h+var_2A0], 0
0x1801f211c  jnz     short loc_1801F213C
0x1801f211e  cmp     [rsp+338h+var_29C], 0
0x1801f2126  jnz     short loc_1801F213C
0x1801f2128  cmp     [rsp+338h+var_298], 0
0x1801f2130  jnz     short loc_1801F213C
0x1801f2132  cmp     [rsp+338h+var_294], 0
0x1801f213a  jz      short loc_1801F2146
0x1801f213c  lea     r9, [rsp+338h+var_2A0]
0x1801f2144  jmp     short loc_1801F2149
0x1801f2146  xor     r9d, r9d
0x1801f2149  lea     r8, [rsp+338h+var_2B0]
0x1801f2151  lea     rdx, byte_180353453
0x1801f2158  lea     rcx, dword_180380B68
0x1801f215f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801f2164  cmp     byte ptr [rsi+48h], 0
0x1801f2168  jz      loc_1801F30DA
0x1801f216e  mov     [rsp+338h+var_2F0], 0
0x1801f2173  cmp     byte ptr [rsi+58h], 0
0x1801f2177  jz      loc_1801F30DA
0x1801f217d  mov     r9, [rsi+40h]; unsigned __int16 *
0x1801f2181  mov     r8, [rsi+50h]; unsigned __int16 *
0x1801f2185  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x1801f218c  lea     rcx, [rsp+338h+var_2E8]; this
0x1801f2191  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1801f2196  nop
0x1801f2197  mov     [rsp+338h+var_2F8], 0
0x1801f21a0  lea     rax, [rsp+338h+var_2F8]
0x1801f21a5  mov     [rsp+338h+var_308], rax
0x1801f21aa  mov     [rsp+338h+var_310], 4
0x1801f21b2  mov     [rsp+338h+var_318], 39h ; '9'
0x1801f21ba  lea     r9, ?MDM_Policy_User_Result01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_User_Result01_Browser02_NodeList
0x1801f21c1  mov     r8, [rsi+40h]
0x1801f21c5  mov     rdx, [rsi+50h]
0x1801f21c9  mov     rcx, r15
0x1801f21cc  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801f21d1  mov     edi, eax
0x1801f21d3  test    eax, eax
0x1801f21d5  jz      short loc_1801F21DC
0x1801f21d7  jmp     loc_1801F30DF
0x1801f21dc  lea     rax, [rsp+338h+var_2F8]
0x1801f21e1  mov     [rsp+338h+var_2C8], rax
0x1801f21e6  mov     r12d, 1
0x1801f21ec  mov     [rsp+338h+var_2C0], r12b
0x1801f21f1  mov     r14, [rsp+338h+var_2F8]
0x1801f21f6  test    r14, r14
0x1801f21f9  jnz     short loc_1801F2203
0x1801f21fb  mov     edi, r12d
0x1801f21fe  jmp     loc_1801F30DF
0x1801f2203  mov     r9d, 39h ; '9'; unsigned int
0x1801f2209  lea     r8, ?MDM_Policy_User_Result01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1801f2210  mov     rdx, rsi; struct _MI_Instance *
0x1801f2213  mov     rcx, r14; this
0x1801f2216  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1801f221b  lea     r8, [rsi+60h]; void *
0x1801f221f  cmp     [r8+4], r12b
0x1801f2223  jnz     short loc_1801F2258
0x1801f2225  lea     rdx, aAllowaddressba; "AllowAddressBarDropdown"
0x1801f222c  mov     rcx, r14; this
0x1801f222f  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f2234  mov     edi, eax
0x1801f2236  test    eax, eax
0x1801f2238  jz      short loc_1801F2258
0x1801f223a  mov     rcx, [rsp+338h+var_2F8]
0x1801f223f  test    rcx, rcx
0x1801f2242  jz      short loc_1801F2253
0x1801f2244  mov     rax, [rcx]
0x1801f2247  mov     edx, r12d
0x1801f224a  mov     rax, [rax]
0x1801f224d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f2252  nop
0x1801f2253  jmp     loc_1801F30DF
0x1801f2258  lea     r8, [rsi+68h]; void *
0x1801f225c  cmp     [r8+4], r12b
0x1801f2260  jnz     short loc_1801F2295
0x1801f2262  lea     rdx, aAllowautofill; "AllowAutofill"
0x1801f2269  mov     rcx, r14; this
0x1801f226c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f2271  mov     edi, eax
0x1801f2273  test    eax, eax
0x1801f2275  jz      short loc_1801F2295
0x1801f2277  mov     rcx, [rsp+338h+var_2F8]
0x1801f227c  test    rcx, rcx
0x1801f227f  jz      short loc_1801F2290
0x1801f2281  mov     rax, [rcx]
0x1801f2284  mov     edx, r12d
0x1801f2287  mov     rax, [rax]
0x1801f228a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f228f  nop
0x1801f2290  jmp     loc_1801F30DF
0x1801f2295  lea     r8, [rsi+70h]; void *
0x1801f2299  cmp     [r8+4], r12b
0x1801f229d  jnz     short loc_1801F22D2
0x1801f229f  lea     rdx, aAllowconfigura; "AllowConfigurationUpdateForBooksLibrary"
0x1801f22a6  mov     rcx, r14; this
0x1801f22a9  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f22ae  mov     edi, eax
0x1801f22b0  test    eax, eax
0x1801f22b2  jz      short loc_1801F22D2
0x1801f22b4  mov     rcx, [rsp+338h+var_2F8]
0x1801f22b9  test    rcx, rcx
0x1801f22bc  jz      short loc_1801F22CD
0x1801f22be  mov     rax, [rcx]
0x1801f22c1  mov     edx, r12d
0x1801f22c4  mov     rax, [rax]
0x1801f22c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f22cc  nop
0x1801f22cd  jmp     loc_1801F30DF
0x1801f22d2  lea     r8, [rsi+78h]; void *
0x1801f22d6  cmp     [r8+4], r12b
0x1801f22da  jnz     short loc_1801F230F
0x1801f22dc  lea     rdx, aAllowcookies; "AllowCookies"
0x1801f22e3  mov     rcx, r14; this
0x1801f22e6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f22eb  mov     edi, eax
0x1801f22ed  test    eax, eax
0x1801f22ef  jz      short loc_1801F230F
0x1801f22f1  mov     rcx, [rsp+338h+var_2F8]
0x1801f22f6  test    rcx, rcx
0x1801f22f9  jz      short loc_1801F230A
0x1801f22fb  mov     rax, [rcx]
0x1801f22fe  mov     edx, r12d
0x1801f2301  mov     rax, [rax]
0x1801f2304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f2309  nop
0x1801f230a  jmp     loc_1801F30DF
0x1801f230f  lea     r8, [rsi+80h]; void *
0x1801f2316  cmp     [r8+4], r12b
0x1801f231a  jnz     short loc_1801F234F
0x1801f231c  lea     rdx, aAllowdeveloper; "AllowDeveloperTools"
0x1801f2323  mov     rcx, r14; this
0x1801f2326  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f232b  mov     edi, eax
0x1801f232d  test    eax, eax
0x1801f232f  jz      short loc_1801F234F
0x1801f2331  mov     rcx, [rsp+338h+var_2F8]
0x1801f2336  test    rcx, rcx
0x1801f2339  jz      short loc_1801F234A
0x1801f233b  mov     rax, [rcx]
0x1801f233e  mov     edx, r12d
0x1801f2341  mov     rax, [rax]
0x1801f2344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f2349  nop
0x1801f234a  jmp     loc_1801F30DF
0x1801f234f  lea     r8, [rsi+88h]; void *
0x1801f2356  cmp     [r8+4], r12b
0x1801f235a  jnz     short loc_1801F238F
0x1801f235c  lea     rdx, aAllowdonottrac; "AllowDoNotTrack"
0x1801f2363  mov     rcx, r14; this
0x1801f2366  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f236b  mov     edi, eax
0x1801f236d  test    eax, eax
0x1801f236f  jz      short loc_1801F238F
0x1801f2371  mov     rcx, [rsp+338h+var_2F8]
0x1801f2376  test    rcx, rcx
0x1801f2379  jz      short loc_1801F238A
0x1801f237b  mov     rax, [rcx]
0x1801f237e  mov     edx, r12d
0x1801f2381  mov     rax, [rax]
0x1801f2384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f2389  nop
0x1801f238a  jmp     loc_1801F30DF
0x1801f238f  lea     r8, [rsi+90h]; void *
0x1801f2396  cmp     [r8+4], r12b
0x1801f239a  jnz     short loc_1801F23CF
0x1801f239c  lea     rdx, aAllowextension; "AllowExtensions"
0x1801f23a3  mov     rcx, r14; this
0x1801f23a6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f23ab  mov     edi, eax
0x1801f23ad  test    eax, eax
0x1801f23af  jz      short loc_1801F23CF
0x1801f23b1  mov     rcx, [rsp+338h+var_2F8]
0x1801f23b6  test    rcx, rcx
0x1801f23b9  jz      short loc_1801F23CA
0x1801f23bb  mov     rax, [rcx]
0x1801f23be  mov     edx, r12d
0x1801f23c1  mov     rax, [rax]
0x1801f23c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f23c9  nop
0x1801f23ca  jmp     loc_1801F30DF
0x1801f23cf  lea     r8, [rsi+98h]; void *
0x1801f23d6  cmp     [r8+4], r12b
0x1801f23da  jnz     short loc_1801F240F
0x1801f23dc  lea     rdx, aAllowflash; "AllowFlash"
0x1801f23e3  mov     rcx, r14; this
0x1801f23e6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f23eb  mov     edi, eax
0x1801f23ed  test    eax, eax
0x1801f23ef  jz      short loc_1801F240F
0x1801f23f1  mov     rcx, [rsp+338h+var_2F8]
0x1801f23f6  test    rcx, rcx
0x1801f23f9  jz      short loc_1801F240A
0x1801f23fb  mov     rax, [rcx]
0x1801f23fe  mov     edx, r12d
0x1801f2401  mov     rax, [rax]
0x1801f2404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f2409  nop
0x1801f240a  jmp     loc_1801F30DF
0x1801f240f  lea     r8, [rsi+0A0h]; void *
0x1801f2416  cmp     [r8+4], r12b
0x1801f241a  jnz     short loc_1801F244F
0x1801f241c  lea     rdx, aAllowflashclic; "AllowFlashClickToRun"
0x1801f2423  mov     rcx, r14; this
0x1801f2426  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f242b  mov     edi, eax
0x1801f242d  test    eax, eax
0x1801f242f  jz      short loc_1801F244F
0x1801f2431  mov     rcx, [rsp+338h+var_2F8]
0x1801f2436  test    rcx, rcx
0x1801f2439  jz      short loc_1801F244A
0x1801f243b  mov     rax, [rcx]
0x1801f243e  mov     edx, r12d
0x1801f2441  mov     rax, [rax]
0x1801f2444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f2449  nop
0x1801f244a  jmp     loc_1801F30DF
0x1801f244f  lea     r8, [rsi+0A8h]; void *
0x1801f2456  cmp     [r8+4], r12b
0x1801f245a  jnz     short loc_1801F248F
0x1801f245c  lea     rdx, aAllowfullscree; "AllowFullScreenMode"
0x1801f2463  mov     rcx, r14; this
0x1801f2466  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f246b  mov     edi, eax
0x1801f246d  test    eax, eax
0x1801f246f  jz      short loc_1801F248F
0x1801f2471  mov     rcx, [rsp+338h+var_2F8]
0x1801f2476  test    rcx, rcx
0x1801f2479  jz      short loc_1801F248A
0x1801f247b  mov     rax, [rcx]
0x1801f247e  mov     edx, r12d
0x1801f2481  mov     rax, [rax]
0x1801f2484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f2489  nop
0x1801f248a  jmp     loc_1801F30DF
0x1801f248f  lea     r8, [rsi+0B0h]; void *
0x1801f2496  cmp     [r8+4], r12b
0x1801f249a  jnz     short loc_1801F24CF
0x1801f249c  lea     rdx, aAllowinprivate; "AllowInPrivate"
0x1801f24a3  mov     rcx, r14; this
0x1801f24a6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f24ab  mov     edi, eax
0x1801f24ad  test    eax, eax
0x1801f24af  jz      short loc_1801F24CF
0x1801f24b1  mov     rcx, [rsp+338h+var_2F8]
0x1801f24b6  test    rcx, rcx
0x1801f24b9  jz      short loc_1801F24CA
0x1801f24bb  mov     rax, [rcx]
0x1801f24be  mov     edx, r12d
0x1801f24c1  mov     rax, [rax]
0x1801f24c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f24c9  nop
0x1801f24ca  jmp     loc_1801F30DF
0x1801f24cf  lea     r8, [rsi+0B8h]; void *
0x1801f24d6  cmp     [r8+4], r12b
0x1801f24da  jnz     short loc_1801F250F
0x1801f24dc  lea     rdx, aAllowmicrosoft_2; "AllowMicrosoftCompatibilityList"
0x1801f24e3  mov     rcx, r14; this
0x1801f24e6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f24eb  mov     edi, eax
0x1801f24ed  test    eax, eax
0x1801f24ef  jz      short loc_1801F250F
0x1801f24f1  mov     rcx, [rsp+338h+var_2F8]
0x1801f24f6  test    rcx, rcx
0x1801f24f9  jz      short loc_1801F250A
0x1801f24fb  mov     rax, [rcx]
  ... truncated ...
```
