# MDM_Policy_Result01_Browser02_InvokeCreateInstance

- ea: `0x180120b2c`
- end: `0x180121dcb`
- name: `MDM_Policy_Result01_Browser02_InvokeCreateInstance`
- size: `4767`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180120a30`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x180120b2c`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x180120d6f`: `AllowConfigurationUpdateForBooksLibrary`
- `0x180120e6c`: `AllowExtensions`
- `0x180120fac`: `AllowMicrosoftCompatibilityList`
- `0x1801211ac`: `AllowSideloadingOfExtensions`
- `0x18012132c`: `ConfigureAdditionalSearchEngines`
- `0x18012136c`: `ConfigureFavoritesBar`
- `0x1801213ac`: `ConfigureHomeButton`
- `0x1801213ec`: `ConfigureKioskMode`
- `0x18012142c`: `ConfigureKioskResetAfterIdleTimeout`
- `0x18012146c`: `ConfigureOpenMicrosoftEdgeWith`
- `0x1801214ac`: `ConfigureTelemetryForMicrosoft365Analytics`
- `0x18012172c`: `EnterpriseSiteListServiceUrl`
- `0x1801217ec`: `PreventAccessToAboutFlagsInMicrosoftEdge`
- `0x18012196c`: `PreventTurningOffRequiredExtensions`
- `0x180121b2c`: `ShowMessageWhenOpeningSitesInInternetExplorer`
- `0x180120c55`: `CreateInstanceStart`
- `0x180121d32`: `CreateInstanceEnd`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_Browser02_InvokeCreateInstance(MI_Context *self, struct _MI_Instance *a2)
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
    inserted = CreateRequestHandlerInstance(
                 (__int64)self,
                 (wchar_t *)a2[1].serverName,
                 (const unsigned __int16 *)a2[1].ft,
                 (struct WmiNodeInfo *)&MDM_Policy_Result01_Browser02_NodeList,
                 0x3Fu,
                 4,
                 &v8);
    if ( !inserted )
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
          && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowAddressBarDropdown", (LONG *)a2[1].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[1].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowAutofill", (LONG *)&a2[1].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[1].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowConfigurationUpdateForBooksLibrary",
                                (LONG *)&a2[1].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[1].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowCookies", (LONG *)&a2[1].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowDeveloperTools", (LONG *)&a2[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowDoNotTrack", (LONG *)&a2[2].classDecl)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowExtensions", (LONG *)&a2[2].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowFlash", (LONG *)&a2[2].nameSpace)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowFlashClickToRun",
                                (LONG *)a2[2].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowFullScreenMode",
                                (LONG *)&a2[2].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowInPrivate", (LONG *)&a2[2].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[2].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowMicrosoftCompatibilityList",
                                (LONG *)&a2[2].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPasswordManager", (LONG *)&a2[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPopups", (LONG *)&a2[3].classDecl)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPrelaunch", (LONG *)&a2[3].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPrinting", (LONG *)&a2[3].nameSpace)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowSavingHistory", (LONG *)a2[3].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowSearchEngineCustomization",
                                (LONG *)&a2[3].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowSearchSuggestionsinAddressBar",
                                (LONG *)&a2[3].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[3].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowSideloadingOfExtensions",
                                (LONG *)&a2[3].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowSmartScreen", (LONG *)&a2[4])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowTabPreloading",
                                (LONG *)&a2[4].classDecl)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowWebContentOnNewTabPage",
                                (LONG *)&a2[4].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AlwaysEnableBooksLibrary",
                                (LONG *)&a2[4].nameSpace)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ClearBrowsingDataOnExit",
                                (LONG *)a2[4].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[4].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureAdditionalSearchEngines",
                                (LONG *)&a2[4].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[4].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureFavoritesBar",
                                (LONG *)&a2[4].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureHomeButton", (LONG *)&a2[5])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureKioskMode",
                                (LONG *)&a2[5].classDecl)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureKioskResetAfterIdleTimeout",
                                (LONG *)&a2[5].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureOpenMicrosoftEdgeWith",
                                (LONG *)&a2[5].nameSpace)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureTelemetryForMicrosoft365Analytics",
                                (LONG *)a2[5].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[5].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DefaultFavoriteBarItem1Name",
                                (LONG *)&a2[5].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[6].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DefaultFavoriteBarItem1Url",
                                (LONG *)&a2[5].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[6].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DefaultFavoriteBarItem2Name",
                                (LONG *)&a2[6].classDecl)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[6].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DefaultFavoriteBarItem2Url",
                                (LONG *)&a2[6].nameSpace)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[6].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DefaultFavoriteBarItem3Name",
                                (LONG *)&a2[6].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[7].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DefaultFavoriteBarItem3Url",
                                (LONG *)&a2[6].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DisableLockdownOfStartPages",
                                (LONG *)&a2[7].classDecl)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"EnableExtendedBooksTelemetry",
                                (LONG *)&a2[7].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[7].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"EnterpriseModeSiteList",
                                (LONG *)&a2[7].nameSpace)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[7].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"EnterpriseSiteListServiceUrl",
                                (LONG *)&a2[7].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[8].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"HomePages", (LONG *)&a2[7].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"LockdownFavorites",
                                (LONG *)&a2[8].classDecl)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventAccessToAboutFlagsInMicrosoftEdge",
                                (LONG *)&a2[8].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventCertErrorOverrides",
                                (LONG *)&a2[8].nameSpace)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventFirstRunPage",
                                (LONG *)a2[8].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventLiveTileDataCollection",
                                (LONG *)&a2[8].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventSmartScreenPromptOverride",
                                (LONG *)&a2[8].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventSmartScreenPromptOverrideForFiles",
                                (LONG *)&a2[8].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[9].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventTurningOffRequiredExtensions",
                                (LONG *)&a2[9])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[9].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventUsingLocalHostIPAddressForWebRTC",
                                (LONG *)&a2[9].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[9].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ProvisionFavorites",
                                (LONG *)&a2[9].nameSpace)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[9].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SendIntranetTraffictoInternetExplorer",
                                (LONG *)&a2[9].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[9].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SetDefaultSearchEngine",
                                (LONG *)&a2[9].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[10].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetHomeButtonURL", (LONG *)&a2[10])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[10].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SetNewTabPageURL",
                                (LONG *)&a2[10].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[10].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ShowMessageWhenOpeningSitesInInternetExplorer",
                                (LONG *)a2[10].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[10].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SyncFavoritesBetweenIEAndMicrosoftEdge",
                                (LONG *)&a2[10].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[10].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UnlockHomeButton",
                                (LONG *)&a2[10].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[10].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UseSharedFolderForBooks",
                                (LONG *)&a2[10].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else
        {
          inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
          if ( inserted )
          {
            if ( v8 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
          }
          else
          {
            inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
        inserted = 1;
      }
    }
  }
  else
  {
    inserted = 4;
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
  return inserted;
}

```

## disassembly

```asm
0x180120b2c  mov     [rsp+arg_10], rsi
0x180120b31  mov     [rsp+arg_18], rdi
0x180120b36  push    r12
0x180120b38  push    r14
0x180120b3a  push    r15
0x180120b3c  sub     rsp, 380h
0x180120b43  mov     rax, cs:__security_cookie
0x180120b4a  xor     rax, rsp
0x180120b4d  mov     [rsp+398h+var_28], rax
0x180120b55  mov     rsi, rdx
0x180120b58  mov     r15, rcx
0x180120b5b  xor     edx, edx; Val
0x180120b5d  mov     r8d, 2C0h; Size
0x180120b63  lea     rcx, [rsp+398h+instance]; void *
0x180120b6b  call    memset_0
0x180120b70  mov     [rsp+398h+var_318], 0
0x180120b7b  mov     [rsp+398h+var_314], 0
0x180120b83  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180120b8a  mov     [rsp+398h+var_348], rax
0x180120b8f  lea     rax, [rsp+398h+var_318]
0x180120b97  mov     [rsp+398h+var_340], rax
0x180120b9c  lea     rax, aMdmPolicyResul_101; "MDM_Policy_Result01_Browser02"
0x180120ba3  mov     [rsp+398h+var_338], rax
0x180120ba8  lea     rcx, [rsp+398h+var_318]
0x180120bb0  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180120bb5  mov     eax, cs:dword_180380B68
0x180120bbb  cmp     eax, 5
0x180120bbe  jbe     short loc_180120C34
0x180120bc0  mov     rdx, 200000000000h
0x180120bca  lea     rcx, dword_180380B68
0x180120bd1  call    _tlgKeywordOn
0x180120bd6  test    al, al
0x180120bd8  jz      short loc_180120C34
0x180120bda  cmp     [rsp+398h+var_314], 0
0x180120be2  jz      short loc_180120C16
0x180120be4  cmp     [rsp+398h+var_300], 0
0x180120bec  jnz     short loc_180120C0C
0x180120bee  cmp     [rsp+398h+var_2FC], 0
0x180120bf6  jnz     short loc_180120C0C
0x180120bf8  cmp     [rsp+398h+var_2F8], 0
0x180120c00  jnz     short loc_180120C0C
0x180120c02  cmp     [rsp+398h+var_2F4], 0
0x180120c0a  jz      short loc_180120C16
0x180120c0c  lea     r9, [rsp+398h+var_300]
0x180120c14  jmp     short loc_180120C19
0x180120c16  xor     r9d, r9d
0x180120c19  lea     r8, [rsp+398h+var_310]
0x180120c21  lea     rdx, byte_180353AEB
0x180120c28  lea     rcx, dword_180380B68
0x180120c2f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180120c34  cmp     byte ptr [rsi+48h], 0
0x180120c38  jz      loc_180121D2A
0x180120c3e  mov     [rsp+398h+var_350], 0
0x180120c43  cmp     byte ptr [rsi+58h], 0
0x180120c47  jz      loc_180121D2A
0x180120c4d  mov     r9, [rsi+40h]; unsigned __int16 *
0x180120c51  mov     r8, [rsi+50h]; unsigned __int16 *
0x180120c55  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x180120c5c  lea     rcx, [rsp+398h+var_348]; this
0x180120c61  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x180120c66  nop
0x180120c67  mov     [rsp+398h+var_358], 0
0x180120c70  lea     rax, [rsp+398h+var_358]
0x180120c75  mov     [rsp+398h+var_368], rax
0x180120c7a  mov     [rsp+398h+var_370], 4
0x180120c82  mov     [rsp+398h+var_378], 3Fh ; '?'
0x180120c8a  lea     r9, ?MDM_Policy_Result01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_Browser02_NodeList
0x180120c91  mov     r8, [rsi+40h]
0x180120c95  mov     rdx, [rsi+50h]
0x180120c99  mov     rcx, r15
0x180120c9c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180120ca1  mov     edi, eax
0x180120ca3  test    eax, eax
0x180120ca5  jz      short loc_180120CAC
0x180120ca7  jmp     loc_180121D2F
0x180120cac  lea     rax, [rsp+398h+var_358]
0x180120cb1  mov     [rsp+398h+var_328], rax
0x180120cb6  mov     r12d, 1
0x180120cbc  mov     [rsp+398h+var_320], r12b
0x180120cc1  mov     r14, [rsp+398h+var_358]
0x180120cc6  test    r14, r14
0x180120cc9  jnz     short loc_180120CD3
0x180120ccb  mov     edi, r12d
0x180120cce  jmp     loc_180121D2F
0x180120cd3  mov     r9d, 3Fh ; '?'; unsigned int
0x180120cd9  lea     r8, ?MDM_Policy_Result01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x180120ce0  mov     rdx, rsi; struct _MI_Instance *
0x180120ce3  mov     rcx, r14; this
0x180120ce6  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x180120ceb  lea     r8, [rsi+60h]; void *
0x180120cef  cmp     [r8+4], r12b
0x180120cf3  jnz     short loc_180120D28
0x180120cf5  lea     rdx, aAllowaddressba; "AllowAddressBarDropdown"
0x180120cfc  mov     rcx, r14; this
0x180120cff  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180120d04  mov     edi, eax
0x180120d06  test    eax, eax
0x180120d08  jz      short loc_180120D28
0x180120d0a  mov     rcx, [rsp+398h+var_358]
0x180120d0f  test    rcx, rcx
0x180120d12  jz      short loc_180120D23
0x180120d14  mov     rax, [rcx]
0x180120d17  mov     edx, r12d
0x180120d1a  mov     rax, [rax]
0x180120d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120d22  nop
0x180120d23  jmp     loc_180121D2F
0x180120d28  lea     r8, [rsi+68h]; void *
0x180120d2c  cmp     [r8+4], r12b
0x180120d30  jnz     short loc_180120D65
0x180120d32  lea     rdx, aAllowautofill; "AllowAutofill"
0x180120d39  mov     rcx, r14; this
0x180120d3c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180120d41  mov     edi, eax
0x180120d43  test    eax, eax
0x180120d45  jz      short loc_180120D65
0x180120d47  mov     rcx, [rsp+398h+var_358]
0x180120d4c  test    rcx, rcx
0x180120d4f  jz      short loc_180120D60
0x180120d51  mov     rax, [rcx]
0x180120d54  mov     edx, r12d
0x180120d57  mov     rax, [rax]
0x180120d5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120d5f  nop
0x180120d60  jmp     loc_180121D2F
0x180120d65  lea     r8, [rsi+70h]; void *
0x180120d69  cmp     [r8+4], r12b
0x180120d6d  jnz     short loc_180120DA2
0x180120d6f  lea     rdx, aAllowconfigura; "AllowConfigurationUpdateForBooksLibrary"
0x180120d76  mov     rcx, r14; this
0x180120d79  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180120d7e  mov     edi, eax
0x180120d80  test    eax, eax
0x180120d82  jz      short loc_180120DA2
0x180120d84  mov     rcx, [rsp+398h+var_358]
0x180120d89  test    rcx, rcx
0x180120d8c  jz      short loc_180120D9D
0x180120d8e  mov     rax, [rcx]
0x180120d91  mov     edx, r12d
0x180120d94  mov     rax, [rax]
0x180120d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120d9c  nop
0x180120d9d  jmp     loc_180121D2F
0x180120da2  lea     r8, [rsi+78h]; void *
0x180120da6  cmp     [r8+4], r12b
0x180120daa  jnz     short loc_180120DDF
0x180120dac  lea     rdx, aAllowcookies; "AllowCookies"
0x180120db3  mov     rcx, r14; this
0x180120db6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180120dbb  mov     edi, eax
0x180120dbd  test    eax, eax
0x180120dbf  jz      short loc_180120DDF
0x180120dc1  mov     rcx, [rsp+398h+var_358]
0x180120dc6  test    rcx, rcx
0x180120dc9  jz      short loc_180120DDA
0x180120dcb  mov     rax, [rcx]
0x180120dce  mov     edx, r12d
0x180120dd1  mov     rax, [rax]
0x180120dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120dd9  nop
0x180120dda  jmp     loc_180121D2F
0x180120ddf  lea     r8, [rsi+80h]; void *
0x180120de6  cmp     [r8+4], r12b
0x180120dea  jnz     short loc_180120E1F
0x180120dec  lea     rdx, aAllowdeveloper; "AllowDeveloperTools"
0x180120df3  mov     rcx, r14; this
0x180120df6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180120dfb  mov     edi, eax
0x180120dfd  test    eax, eax
0x180120dff  jz      short loc_180120E1F
0x180120e01  mov     rcx, [rsp+398h+var_358]
0x180120e06  test    rcx, rcx
0x180120e09  jz      short loc_180120E1A
0x180120e0b  mov     rax, [rcx]
0x180120e0e  mov     edx, r12d
0x180120e11  mov     rax, [rax]
0x180120e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120e19  nop
0x180120e1a  jmp     loc_180121D2F
0x180120e1f  lea     r8, [rsi+88h]; void *
0x180120e26  cmp     [r8+4], r12b
0x180120e2a  jnz     short loc_180120E5F
0x180120e2c  lea     rdx, aAllowdonottrac; "AllowDoNotTrack"
0x180120e33  mov     rcx, r14; this
0x180120e36  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180120e3b  mov     edi, eax
0x180120e3d  test    eax, eax
0x180120e3f  jz      short loc_180120E5F
0x180120e41  mov     rcx, [rsp+398h+var_358]
0x180120e46  test    rcx, rcx
0x180120e49  jz      short loc_180120E5A
0x180120e4b  mov     rax, [rcx]
0x180120e4e  mov     edx, r12d
0x180120e51  mov     rax, [rax]
0x180120e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120e59  nop
0x180120e5a  jmp     loc_180121D2F
0x180120e5f  lea     r8, [rsi+90h]; void *
0x180120e66  cmp     [r8+4], r12b
0x180120e6a  jnz     short loc_180120E9F
0x180120e6c  lea     rdx, aAllowextension; "AllowExtensions"
0x180120e73  mov     rcx, r14; this
0x180120e76  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180120e7b  mov     edi, eax
0x180120e7d  test    eax, eax
0x180120e7f  jz      short loc_180120E9F
0x180120e81  mov     rcx, [rsp+398h+var_358]
0x180120e86  test    rcx, rcx
0x180120e89  jz      short loc_180120E9A
0x180120e8b  mov     rax, [rcx]
0x180120e8e  mov     edx, r12d
0x180120e91  mov     rax, [rax]
0x180120e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120e99  nop
0x180120e9a  jmp     loc_180121D2F
0x180120e9f  lea     r8, [rsi+98h]; void *
0x180120ea6  cmp     [r8+4], r12b
0x180120eaa  jnz     short loc_180120EDF
0x180120eac  lea     rdx, aAllowflash; "AllowFlash"
0x180120eb3  mov     rcx, r14; this
0x180120eb6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180120ebb  mov     edi, eax
0x180120ebd  test    eax, eax
0x180120ebf  jz      short loc_180120EDF
0x180120ec1  mov     rcx, [rsp+398h+var_358]
0x180120ec6  test    rcx, rcx
0x180120ec9  jz      short loc_180120EDA
0x180120ecb  mov     rax, [rcx]
0x180120ece  mov     edx, r12d
0x180120ed1  mov     rax, [rax]
0x180120ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120ed9  nop
0x180120eda  jmp     loc_180121D2F
0x180120edf  lea     r8, [rsi+0A0h]; void *
0x180120ee6  cmp     [r8+4], r12b
0x180120eea  jnz     short loc_180120F1F
0x180120eec  lea     rdx, aAllowflashclic; "AllowFlashClickToRun"
0x180120ef3  mov     rcx, r14; this
0x180120ef6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180120efb  mov     edi, eax
0x180120efd  test    eax, eax
0x180120eff  jz      short loc_180120F1F
0x180120f01  mov     rcx, [rsp+398h+var_358]
0x180120f06  test    rcx, rcx
0x180120f09  jz      short loc_180120F1A
0x180120f0b  mov     rax, [rcx]
0x180120f0e  mov     edx, r12d
0x180120f11  mov     rax, [rax]
0x180120f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120f19  nop
0x180120f1a  jmp     loc_180121D2F
0x180120f1f  lea     r8, [rsi+0A8h]; void *
0x180120f26  cmp     [r8+4], r12b
0x180120f2a  jnz     short loc_180120F5F
0x180120f2c  lea     rdx, aAllowfullscree; "AllowFullScreenMode"
0x180120f33  mov     rcx, r14; this
0x180120f36  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180120f3b  mov     edi, eax
0x180120f3d  test    eax, eax
0x180120f3f  jz      short loc_180120F5F
0x180120f41  mov     rcx, [rsp+398h+var_358]
0x180120f46  test    rcx, rcx
0x180120f49  jz      short loc_180120F5A
0x180120f4b  mov     rax, [rcx]
0x180120f4e  mov     edx, r12d
0x180120f51  mov     rax, [rax]
0x180120f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120f59  nop
0x180120f5a  jmp     loc_180121D2F
0x180120f5f  lea     r8, [rsi+0B0h]; void *
0x180120f66  cmp     [r8+4], r12b
0x180120f6a  jnz     short loc_180120F9F
0x180120f6c  lea     rdx, aAllowinprivate; "AllowInPrivate"
0x180120f73  mov     rcx, r14; this
0x180120f76  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180120f7b  mov     edi, eax
0x180120f7d  test    eax, eax
0x180120f7f  jz      short loc_180120F9F
0x180120f81  mov     rcx, [rsp+398h+var_358]
0x180120f86  test    rcx, rcx
0x180120f89  jz      short loc_180120F9A
0x180120f8b  mov     rax, [rcx]
0x180120f8e  mov     edx, r12d
0x180120f91  mov     rax, [rax]
0x180120f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120f99  nop
0x180120f9a  jmp     loc_180121D2F
0x180120f9f  lea     r8, [rsi+0B8h]; void *
0x180120fa6  cmp     [r8+4], r12b
0x180120faa  jnz     short loc_180120FDF
0x180120fac  lea     rdx, aAllowmicrosoft_2; "AllowMicrosoftCompatibilityList"
0x180120fb3  mov     rcx, r14; this
0x180120fb6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180120fbb  mov     edi, eax
0x180120fbd  test    eax, eax
0x180120fbf  jz      short loc_180120FDF
0x180120fc1  mov     rcx, [rsp+398h+var_358]
0x180120fc6  test    rcx, rcx
0x180120fc9  jz      short loc_180120FDA
0x180120fcb  mov     rax, [rcx]
  ... truncated ...
```
