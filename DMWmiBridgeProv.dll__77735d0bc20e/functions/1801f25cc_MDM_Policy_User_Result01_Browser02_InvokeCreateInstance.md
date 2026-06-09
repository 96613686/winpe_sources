# MDM_Policy_User_Result01_Browser02_InvokeCreateInstance

- ea: `0x1801f25cc`
- end: `0x1801f36eb`
- name: `MDM_Policy_User_Result01_Browser02_InvokeCreateInstance`
- size: `4383`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801f24d0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x1801f25cc`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x1801f280f`: `AllowConfigurationUpdateForBooksLibrary`
- `0x1801f290c`: `AllowExtensions`
- `0x1801f2a4c`: `AllowMicrosoftCompatibilityList`
- `0x1801f2c4c`: `AllowSideloadingOfExtensions`
- `0x1801f2dcc`: `ConfigureAdditionalSearchEngines`
- `0x1801f2e0c`: `ConfigureFavoritesBar`
- `0x1801f2e4c`: `ConfigureHomeButton`
- `0x1801f2e8c`: `ConfigureKioskMode`
- `0x1801f2ecc`: `ConfigureKioskResetAfterIdleTimeout`
- `0x1801f2f0c`: `ConfigureOpenMicrosoftEdgeWith`
- `0x1801f2f4c`: `ConfigureTelemetryForMicrosoft365Analytics`
- `0x1801f304c`: `EnterpriseSiteListServiceUrl`
- `0x1801f310c`: `PreventAccessToAboutFlagsInMicrosoftEdge`
- `0x1801f328c`: `PreventTurningOffRequiredExtensions`
- `0x1801f344c`: `ShowMessageWhenOpeningSitesInInternetExplorer`
- `0x1801f26f5`: `CreateInstanceStart`
- `0x1801f3652`: `CreateInstanceEnd`

## pseudocode

```c
__int64 __fastcall MDM_Policy_User_Result01_Browser02_InvokeCreateInstance(MI_Context *self, struct _MI_Instance *a2)
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
    inserted = CreateRequestHandlerInstance(
                 (__int64)self,
                 (wchar_t *)a2[1].serverName,
                 (const unsigned __int16 *)a2[1].ft,
                 (struct WmiNodeInfo *)&MDM_Policy_User_Result01_Browser02_NodeList,
                 0x39u,
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
          (struct WmiNodeInfo *)&MDM_Policy_User_Result01_Browser02_NodeList,
          0x39u);
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
        else if ( BYTE4(a2[5].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DisableLockdownOfStartPages",
                                (LONG *)&a2[5].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[5].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"EnableExtendedBooksTelemetry",
                                (LONG *)&a2[5].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[6].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"EnterpriseModeSiteList",
                                (LONG *)&a2[5].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[6].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"EnterpriseSiteListServiceUrl",
                                (LONG *)&a2[6].classDecl)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[6].reserved[0]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"HomePages", (LONG *)&a2[6].nameSpace)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"LockdownFavorites",
                                (LONG *)&a2[6].reserved[1])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventAccessToAboutFlagsInMicrosoftEdge",
                                (LONG *)&a2[6].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[6].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventCertErrorOverrides",
                                (LONG *)&a2[6].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PreventFirstRunPage", (LONG *)&a2[7])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventLiveTileDataCollection",
                                (LONG *)&a2[7].classDecl)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventSmartScreenPromptOverride",
                                (LONG *)&a2[7].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventSmartScreenPromptOverrideForFiles",
                                (LONG *)&a2[7].nameSpace)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[7].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventTurningOffRequiredExtensions",
                                (LONG *)a2[7].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[7].reserved[2]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventUsingLocalHostIPAddressForWebRTC",
                                (LONG *)&a2[7].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[8].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ProvisionFavorites",
                                (LONG *)&a2[7].reserved[3])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[8].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SendIntranetTraffictoInternetExplorer",
                                (LONG *)&a2[8].classDecl)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[8].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SetDefaultSearchEngine",
                                (LONG *)&a2[8].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[8].reserved[1]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetHomeButtonURL", (LONG *)a2[8].reserved)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( LOBYTE(a2[8].reserved[3]) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SetNewTabPageURL",
                                (LONG *)&a2[8].reserved[2])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[9].ft) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ShowMessageWhenOpeningSitesInInternetExplorer",
                                (LONG *)&a2[9])) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[9].classDecl) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SyncFavoritesBetweenIEAndMicrosoftEdge",
                                (LONG *)&a2[9].classDecl)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[9].serverName) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UnlockHomeButton",
                                (LONG *)&a2[9].serverName)) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( BYTE4(a2[9].nameSpace) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UseSharedFolderForBooks",
                                (LONG *)&a2[9].nameSpace)) != 0 )
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
      &word_18034212E,
      v14,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v12);
  return inserted;
}

```

## disassembly

```asm
0x1801f25cc  mov     [rsp+arg_10], rsi
0x1801f25d1  mov     [rsp+arg_18], rdi
0x1801f25d6  push    r12
0x1801f25d8  push    r14
0x1801f25da  push    r15
0x1801f25dc  sub     rsp, 320h
0x1801f25e3  mov     rax, cs:__security_cookie
0x1801f25ea  xor     rax, rsp
0x1801f25ed  mov     [rsp+338h+var_28], rax
0x1801f25f5  mov     rsi, rdx
0x1801f25f8  mov     r15, rcx
0x1801f25fb  xor     edx, edx; Val
0x1801f25fd  mov     r8d, 260h; Size
0x1801f2603  lea     rcx, [rsp+338h+instance]; void *
0x1801f260b  call    memset_0
0x1801f2610  mov     [rsp+338h+var_2B8], 0
0x1801f261b  mov     [rsp+338h+var_2B4], 0
0x1801f2623  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801f262a  mov     [rsp+338h+var_2E8], rax
0x1801f262f  lea     rax, [rsp+338h+var_2B8]
0x1801f2637  mov     [rsp+338h+var_2E0], rax
0x1801f263c  lea     rax, aMdmPolicyUserR_29; "MDM_Policy_User_Result01_Browser02"
0x1801f2643  mov     [rsp+338h+var_2D8], rax
0x1801f2648  lea     rcx, [rsp+338h+var_2B8]
0x1801f2650  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801f2655  mov     eax, cs:dword_180380B68
0x1801f265b  cmp     eax, 5
0x1801f265e  jbe     short loc_1801F26D4
0x1801f2660  mov     rdx, 200000000000h
0x1801f266a  lea     rcx, dword_180380B68
0x1801f2671  call    _tlgKeywordOn
0x1801f2676  test    al, al
0x1801f2678  jz      short loc_1801F26D4
0x1801f267a  cmp     [rsp+338h+var_2B4], 0
0x1801f2682  jz      short loc_1801F26B6
0x1801f2684  cmp     [rsp+338h+var_2A0], 0
0x1801f268c  jnz     short loc_1801F26AC
0x1801f268e  cmp     [rsp+338h+var_29C], 0
0x1801f2696  jnz     short loc_1801F26AC
0x1801f2698  cmp     [rsp+338h+var_298], 0
0x1801f26a0  jnz     short loc_1801F26AC
0x1801f26a2  cmp     [rsp+338h+var_294], 0
0x1801f26aa  jz      short loc_1801F26B6
0x1801f26ac  lea     r9, [rsp+338h+var_2A0]
0x1801f26b4  jmp     short loc_1801F26B9
0x1801f26b6  xor     r9d, r9d
0x1801f26b9  lea     r8, [rsp+338h+var_2B0]
0x1801f26c1  lea     rdx, byte_180353453
0x1801f26c8  lea     rcx, dword_180380B68
0x1801f26cf  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801f26d4  cmp     byte ptr [rsi+48h], 0
0x1801f26d8  jz      loc_1801F364A
0x1801f26de  mov     [rsp+338h+var_2F0], 0
0x1801f26e3  cmp     byte ptr [rsi+58h], 0
0x1801f26e7  jz      loc_1801F364A
0x1801f26ed  mov     r9, [rsi+40h]; unsigned __int16 *
0x1801f26f1  mov     r8, [rsi+50h]; unsigned __int16 *
0x1801f26f5  lea     rdx, aCreateinstance_0; "CreateInstanceStart"
0x1801f26fc  lea     rcx, [rsp+338h+var_2E8]; this
0x1801f2701  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1801f2706  nop
0x1801f2707  mov     [rsp+338h+var_2F8], 0
0x1801f2710  lea     rax, [rsp+338h+var_2F8]
0x1801f2715  mov     [rsp+338h+var_308], rax
0x1801f271a  mov     [rsp+338h+var_310], 4
0x1801f2722  mov     [rsp+338h+var_318], 39h ; '9'
0x1801f272a  lea     r9, ?MDM_Policy_User_Result01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_User_Result01_Browser02_NodeList
0x1801f2731  mov     r8, [rsi+40h]
0x1801f2735  mov     rdx, [rsi+50h]
0x1801f2739  mov     rcx, r15
0x1801f273c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801f2741  mov     edi, eax
0x1801f2743  test    eax, eax
0x1801f2745  jz      short loc_1801F274C
0x1801f2747  jmp     loc_1801F364F
0x1801f274c  lea     rax, [rsp+338h+var_2F8]
0x1801f2751  mov     [rsp+338h+var_2C8], rax
0x1801f2756  mov     r12d, 1
0x1801f275c  mov     [rsp+338h+var_2C0], r12b
0x1801f2761  mov     r14, [rsp+338h+var_2F8]
0x1801f2766  test    r14, r14
0x1801f2769  jnz     short loc_1801F2773
0x1801f276b  mov     edi, r12d
0x1801f276e  jmp     loc_1801F364F
0x1801f2773  mov     r9d, 39h ; '9'; unsigned int
0x1801f2779  lea     r8, ?MDM_Policy_User_Result01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1801f2780  mov     rdx, rsi; struct _MI_Instance *
0x1801f2783  mov     rcx, r14; this
0x1801f2786  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1801f278b  lea     r8, [rsi+60h]; void *
0x1801f278f  cmp     [r8+4], r12b
0x1801f2793  jnz     short loc_1801F27C8
0x1801f2795  lea     rdx, aAllowaddressba; "AllowAddressBarDropdown"
0x1801f279c  mov     rcx, r14; this
0x1801f279f  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f27a4  mov     edi, eax
0x1801f27a6  test    eax, eax
0x1801f27a8  jz      short loc_1801F27C8
0x1801f27aa  mov     rcx, [rsp+338h+var_2F8]
0x1801f27af  test    rcx, rcx
0x1801f27b2  jz      short loc_1801F27C3
0x1801f27b4  mov     rax, [rcx]
0x1801f27b7  mov     edx, r12d
0x1801f27ba  mov     rax, [rax]
0x1801f27bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f27c2  nop
0x1801f27c3  jmp     loc_1801F364F
0x1801f27c8  lea     r8, [rsi+68h]; void *
0x1801f27cc  cmp     [r8+4], r12b
0x1801f27d0  jnz     short loc_1801F2805
0x1801f27d2  lea     rdx, aAllowautofill; "AllowAutofill"
0x1801f27d9  mov     rcx, r14; this
0x1801f27dc  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f27e1  mov     edi, eax
0x1801f27e3  test    eax, eax
0x1801f27e5  jz      short loc_1801F2805
0x1801f27e7  mov     rcx, [rsp+338h+var_2F8]
0x1801f27ec  test    rcx, rcx
0x1801f27ef  jz      short loc_1801F2800
0x1801f27f1  mov     rax, [rcx]
0x1801f27f4  mov     edx, r12d
0x1801f27f7  mov     rax, [rax]
0x1801f27fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f27ff  nop
0x1801f2800  jmp     loc_1801F364F
0x1801f2805  lea     r8, [rsi+70h]; void *
0x1801f2809  cmp     [r8+4], r12b
0x1801f280d  jnz     short loc_1801F2842
0x1801f280f  lea     rdx, aAllowconfigura; "AllowConfigurationUpdateForBooksLibrary"
0x1801f2816  mov     rcx, r14; this
0x1801f2819  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f281e  mov     edi, eax
0x1801f2820  test    eax, eax
0x1801f2822  jz      short loc_1801F2842
0x1801f2824  mov     rcx, [rsp+338h+var_2F8]
0x1801f2829  test    rcx, rcx
0x1801f282c  jz      short loc_1801F283D
0x1801f282e  mov     rax, [rcx]
0x1801f2831  mov     edx, r12d
0x1801f2834  mov     rax, [rax]
0x1801f2837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f283c  nop
0x1801f283d  jmp     loc_1801F364F
0x1801f2842  lea     r8, [rsi+78h]; void *
0x1801f2846  cmp     [r8+4], r12b
0x1801f284a  jnz     short loc_1801F287F
0x1801f284c  lea     rdx, aAllowcookies; "AllowCookies"
0x1801f2853  mov     rcx, r14; this
0x1801f2856  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f285b  mov     edi, eax
0x1801f285d  test    eax, eax
0x1801f285f  jz      short loc_1801F287F
0x1801f2861  mov     rcx, [rsp+338h+var_2F8]
0x1801f2866  test    rcx, rcx
0x1801f2869  jz      short loc_1801F287A
0x1801f286b  mov     rax, [rcx]
0x1801f286e  mov     edx, r12d
0x1801f2871  mov     rax, [rax]
0x1801f2874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f2879  nop
0x1801f287a  jmp     loc_1801F364F
0x1801f287f  lea     r8, [rsi+80h]; void *
0x1801f2886  cmp     [r8+4], r12b
0x1801f288a  jnz     short loc_1801F28BF
0x1801f288c  lea     rdx, aAllowdeveloper; "AllowDeveloperTools"
0x1801f2893  mov     rcx, r14; this
0x1801f2896  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f289b  mov     edi, eax
0x1801f289d  test    eax, eax
0x1801f289f  jz      short loc_1801F28BF
0x1801f28a1  mov     rcx, [rsp+338h+var_2F8]
0x1801f28a6  test    rcx, rcx
0x1801f28a9  jz      short loc_1801F28BA
0x1801f28ab  mov     rax, [rcx]
0x1801f28ae  mov     edx, r12d
0x1801f28b1  mov     rax, [rax]
0x1801f28b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f28b9  nop
0x1801f28ba  jmp     loc_1801F364F
0x1801f28bf  lea     r8, [rsi+88h]; void *
0x1801f28c6  cmp     [r8+4], r12b
0x1801f28ca  jnz     short loc_1801F28FF
0x1801f28cc  lea     rdx, aAllowdonottrac; "AllowDoNotTrack"
0x1801f28d3  mov     rcx, r14; this
0x1801f28d6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f28db  mov     edi, eax
0x1801f28dd  test    eax, eax
0x1801f28df  jz      short loc_1801F28FF
0x1801f28e1  mov     rcx, [rsp+338h+var_2F8]
0x1801f28e6  test    rcx, rcx
0x1801f28e9  jz      short loc_1801F28FA
0x1801f28eb  mov     rax, [rcx]
0x1801f28ee  mov     edx, r12d
0x1801f28f1  mov     rax, [rax]
0x1801f28f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f28f9  nop
0x1801f28fa  jmp     loc_1801F364F
0x1801f28ff  lea     r8, [rsi+90h]; void *
0x1801f2906  cmp     [r8+4], r12b
0x1801f290a  jnz     short loc_1801F293F
0x1801f290c  lea     rdx, aAllowextension; "AllowExtensions"
0x1801f2913  mov     rcx, r14; this
0x1801f2916  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f291b  mov     edi, eax
0x1801f291d  test    eax, eax
0x1801f291f  jz      short loc_1801F293F
0x1801f2921  mov     rcx, [rsp+338h+var_2F8]
0x1801f2926  test    rcx, rcx
0x1801f2929  jz      short loc_1801F293A
0x1801f292b  mov     rax, [rcx]
0x1801f292e  mov     edx, r12d
0x1801f2931  mov     rax, [rax]
0x1801f2934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f2939  nop
0x1801f293a  jmp     loc_1801F364F
0x1801f293f  lea     r8, [rsi+98h]; void *
0x1801f2946  cmp     [r8+4], r12b
0x1801f294a  jnz     short loc_1801F297F
0x1801f294c  lea     rdx, aAllowflash; "AllowFlash"
0x1801f2953  mov     rcx, r14; this
0x1801f2956  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f295b  mov     edi, eax
0x1801f295d  test    eax, eax
0x1801f295f  jz      short loc_1801F297F
0x1801f2961  mov     rcx, [rsp+338h+var_2F8]
0x1801f2966  test    rcx, rcx
0x1801f2969  jz      short loc_1801F297A
0x1801f296b  mov     rax, [rcx]
0x1801f296e  mov     edx, r12d
0x1801f2971  mov     rax, [rax]
0x1801f2974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f2979  nop
0x1801f297a  jmp     loc_1801F364F
0x1801f297f  lea     r8, [rsi+0A0h]; void *
0x1801f2986  cmp     [r8+4], r12b
0x1801f298a  jnz     short loc_1801F29BF
0x1801f298c  lea     rdx, aAllowflashclic; "AllowFlashClickToRun"
0x1801f2993  mov     rcx, r14; this
0x1801f2996  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f299b  mov     edi, eax
0x1801f299d  test    eax, eax
0x1801f299f  jz      short loc_1801F29BF
0x1801f29a1  mov     rcx, [rsp+338h+var_2F8]
0x1801f29a6  test    rcx, rcx
0x1801f29a9  jz      short loc_1801F29BA
0x1801f29ab  mov     rax, [rcx]
0x1801f29ae  mov     edx, r12d
0x1801f29b1  mov     rax, [rax]
0x1801f29b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f29b9  nop
0x1801f29ba  jmp     loc_1801F364F
0x1801f29bf  lea     r8, [rsi+0A8h]; void *
0x1801f29c6  cmp     [r8+4], r12b
0x1801f29ca  jnz     short loc_1801F29FF
0x1801f29cc  lea     rdx, aAllowfullscree; "AllowFullScreenMode"
0x1801f29d3  mov     rcx, r14; this
0x1801f29d6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f29db  mov     edi, eax
0x1801f29dd  test    eax, eax
0x1801f29df  jz      short loc_1801F29FF
0x1801f29e1  mov     rcx, [rsp+338h+var_2F8]
0x1801f29e6  test    rcx, rcx
0x1801f29e9  jz      short loc_1801F29FA
0x1801f29eb  mov     rax, [rcx]
0x1801f29ee  mov     edx, r12d
0x1801f29f1  mov     rax, [rax]
0x1801f29f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f29f9  nop
0x1801f29fa  jmp     loc_1801F364F
0x1801f29ff  lea     r8, [rsi+0B0h]; void *
0x1801f2a06  cmp     [r8+4], r12b
0x1801f2a0a  jnz     short loc_1801F2A3F
0x1801f2a0c  lea     rdx, aAllowinprivate; "AllowInPrivate"
0x1801f2a13  mov     rcx, r14; this
0x1801f2a16  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f2a1b  mov     edi, eax
0x1801f2a1d  test    eax, eax
0x1801f2a1f  jz      short loc_1801F2A3F
0x1801f2a21  mov     rcx, [rsp+338h+var_2F8]
0x1801f2a26  test    rcx, rcx
0x1801f2a29  jz      short loc_1801F2A3A
0x1801f2a2b  mov     rax, [rcx]
0x1801f2a2e  mov     edx, r12d
0x1801f2a31  mov     rax, [rax]
0x1801f2a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f2a39  nop
0x1801f2a3a  jmp     loc_1801F364F
0x1801f2a3f  lea     r8, [rsi+0B8h]; void *
0x1801f2a46  cmp     [r8+4], r12b
0x1801f2a4a  jnz     short loc_1801F2A7F
0x1801f2a4c  lea     rdx, aAllowmicrosoft_2; "AllowMicrosoftCompatibilityList"
0x1801f2a53  mov     rcx, r14; this
0x1801f2a56  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f2a5b  mov     edi, eax
0x1801f2a5d  test    eax, eax
0x1801f2a5f  jz      short loc_1801F2A7F
0x1801f2a61  mov     rcx, [rsp+338h+var_2F8]
0x1801f2a66  test    rcx, rcx
0x1801f2a69  jz      short loc_1801F2A7A
0x1801f2a6b  mov     rax, [rcx]
  ... truncated ...
```
