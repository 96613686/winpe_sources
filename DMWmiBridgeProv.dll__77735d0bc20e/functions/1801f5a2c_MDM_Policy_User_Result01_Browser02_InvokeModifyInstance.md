# MDM_Policy_User_Result01_Browser02_InvokeModifyInstance

- ea: `0x1801f5a2c`
- end: `0x1801f6a7f`
- name: `MDM_Policy_User_Result01_Browser02_InvokeModifyInstance`
- size: `4179`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801f6a90`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x18000a280`
- `0x1801f5a2c`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x1801f5c3d`: `AllowConfigurationUpdateForBooksLibrary`
- `0x1801f5d3a`: `AllowExtensions`
- `0x1801f5e7a`: `AllowMicrosoftCompatibilityList`
- `0x1801f607a`: `AllowSideloadingOfExtensions`
- `0x1801f61fa`: `ConfigureAdditionalSearchEngines`
- `0x1801f623a`: `ConfigureFavoritesBar`
- `0x1801f627a`: `ConfigureHomeButton`
- `0x1801f62ba`: `ConfigureKioskMode`
- `0x1801f62fa`: `ConfigureKioskResetAfterIdleTimeout`
- `0x1801f633a`: `ConfigureOpenMicrosoftEdgeWith`
- `0x1801f637a`: `ConfigureTelemetryForMicrosoft365Analytics`
- `0x1801f647a`: `EnterpriseSiteListServiceUrl`
- `0x1801f653a`: `PreventAccessToAboutFlagsInMicrosoftEdge`
- `0x1801f66ba`: `PreventTurningOffRequiredExtensions`
- `0x1801f687a`: `ShowMessageWhenOpeningSitesInInternetExplorer`

## pseudocode

```c
__int64 __fastcall MDM_Policy_User_Result01_Browser02_InvokeModifyInstance(__int64 a1, __int64 a2)
{
  _DWORD *v4; // r9
  unsigned int inserted; // edi
  WmiRequestHandler *v6; // r14
  WmiRequestHandler *v8; // [rsp+40h] [rbp-88h] BYREF
  _QWORD v9[5]; // [rsp+48h] [rbp-80h] BYREF
  char v10; // [rsp+70h] [rbp-58h]
  int v11; // [rsp+78h] [rbp-50h] BYREF
  char v12; // [rsp+7Ch] [rbp-4Ch]
  _BYTE v13[16]; // [rsp+80h] [rbp-48h] BYREF
  _DWORD v14[4]; // [rsp+90h] [rbp-38h] BYREF

  v11 = 0;
  v12 = 0;
  v9[0] = &TelemetryEventWriter::`vftable';
  v9[1] = &v11;
  v9[2] = "MDM_Policy_User_Result01_Browser02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v11);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v12 && (v14[0] || v14[1] || v14[2] || v14[3]) )
      v4 = v14;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_180363FE9,
      v13,
      v4);
  }
  if ( *(_BYTE *)(a2 + 72) && *(_BYTE *)(a2 + 88) )
  {
    TelemetryEventWriter::WriteStart(
      (TelemetryEventWriter *)v9,
      "ModifyInstanceStart",
      *(const unsigned __int16 **)(a2 + 80),
      *(const unsigned __int16 **)(a2 + 64));
    v8 = 0;
    inserted = CreateRequestHandlerInstance(
                 a1,
                 *(wchar_t **)(a2 + 80),
                 *(const unsigned __int16 **)(a2 + 64),
                 (struct WmiNodeInfo *)&MDM_Policy_User_Result01_Browser02_NodeList,
                 0x39u,
                 3,
                 &v8);
    if ( !inserted )
    {
      v9[4] = &v8;
      v10 = 1;
      v6 = v8;
      if ( v8 )
      {
        WmiRequestHandler::SetRequestMIInstance(
          v8,
          (const struct _MI_Instance *)a2,
          (struct WmiNodeInfo *)&MDM_Policy_User_Result01_Browser02_NodeList,
          0x39u);
        if ( *(_BYTE *)(a2 + 100) == 1
          && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowAddressBarDropdown", (LONG *)(a2 + 96))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 108) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowAutofill", (LONG *)(a2 + 104))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 116) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowConfigurationUpdateForBooksLibrary",
                                (LONG *)(a2 + 112))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 124) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowCookies", (LONG *)(a2 + 120))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 132) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowDeveloperTools", (LONG *)(a2 + 128))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 140) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowDoNotTrack", (LONG *)(a2 + 136))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 148) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowExtensions", (LONG *)(a2 + 144))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 156) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowFlash", (LONG *)(a2 + 152))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 164) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowFlashClickToRun", (LONG *)(a2 + 160))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 172) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowFullScreenMode", (LONG *)(a2 + 168))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 180) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowInPrivate", (LONG *)(a2 + 176))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 188) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowMicrosoftCompatibilityList",
                                (LONG *)(a2 + 184))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 196) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPasswordManager", (LONG *)(a2 + 192))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 204) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPopups", (LONG *)(a2 + 200))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 212) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPrelaunch", (LONG *)(a2 + 208))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 220) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPrinting", (LONG *)(a2 + 216))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 228) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowSavingHistory", (LONG *)(a2 + 224))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 236) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowSearchEngineCustomization",
                                (LONG *)(a2 + 232))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 244) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowSearchSuggestionsinAddressBar",
                                (LONG *)(a2 + 240))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 252) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowSideloadingOfExtensions",
                                (LONG *)(a2 + 248))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 260) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowSmartScreen", (LONG *)(a2 + 256))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 268) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowTabPreloading", (LONG *)(a2 + 264))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 276) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowWebContentOnNewTabPage",
                                (LONG *)(a2 + 272))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 284) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AlwaysEnableBooksLibrary",
                                (LONG *)(a2 + 280))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 292) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ClearBrowsingDataOnExit",
                                (LONG *)(a2 + 288))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 304) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureAdditionalSearchEngines",
                                (LONG *)(a2 + 296))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 316) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureFavoritesBar", (LONG *)(a2 + 312))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 324) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureHomeButton", (LONG *)(a2 + 320))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 332) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureKioskMode", (LONG *)(a2 + 328))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 340) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureKioskResetAfterIdleTimeout",
                                (LONG *)(a2 + 336))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 348) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureOpenMicrosoftEdgeWith",
                                (LONG *)(a2 + 344))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 356) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureTelemetryForMicrosoft365Analytics",
                                (LONG *)(a2 + 352))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 364) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DisableLockdownOfStartPages",
                                (LONG *)(a2 + 360))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 372) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"EnableExtendedBooksTelemetry",
                                (LONG *)(a2 + 368))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 384) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnterpriseModeSiteList", (LONG *)(a2 + 376))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 400) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"EnterpriseSiteListServiceUrl",
                                (LONG *)(a2 + 392))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 416) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"HomePages", (LONG *)(a2 + 408))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 428) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"LockdownFavorites", (LONG *)(a2 + 424))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 436) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventAccessToAboutFlagsInMicrosoftEdge",
                                (LONG *)(a2 + 432))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 444) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventCertErrorOverrides",
                                (LONG *)(a2 + 440))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 452) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PreventFirstRunPage", (LONG *)(a2 + 448))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 460) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventLiveTileDataCollection",
                                (LONG *)(a2 + 456))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 468) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventSmartScreenPromptOverride",
                                (LONG *)(a2 + 464))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 476) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventSmartScreenPromptOverrideForFiles",
                                (LONG *)(a2 + 472))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 488) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventTurningOffRequiredExtensions",
                                (LONG *)(a2 + 480))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 500) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventUsingLocalHostIPAddressForWebRTC",
                                (LONG *)(a2 + 496))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 512) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ProvisionFavorites", (LONG *)(a2 + 504))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 524) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SendIntranetTraffictoInternetExplorer",
                                (LONG *)(a2 + 520))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 536) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetDefaultSearchEngine", (LONG *)(a2 + 528))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 552) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetHomeButtonURL", (LONG *)(a2 + 544))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 568) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetNewTabPageURL", (LONG *)(a2 + 560))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 580) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ShowMessageWhenOpeningSitesInInternetExplorer",
                                (LONG *)(a2 + 576))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 588) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SyncFavoritesBetweenIEAndMicrosoftEdge",
                                (LONG *)(a2 + 584))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 596) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"UnlockHomeButton", (LONG *)(a2 + 592))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 604) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UseSharedFolderForBooks",
                                (LONG *)(a2 + 600))) != 0 )
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
            else if ( v8 )
            {
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
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
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v9, "ModifyInstanceEnd", inserted);
  v11 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_180352265,
      v13,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v11);
  return inserted;
}

```

## disassembly

```asm
0x1801f5a2c  mov     r11, rsp
0x1801f5a2f  mov     [r11+18h], rsi
0x1801f5a33  push    rdi
0x1801f5a34  push    r14
0x1801f5a36  push    r15
0x1801f5a38  sub     rsp, 0B0h
0x1801f5a3f  mov     rax, cs:__security_cookie
0x1801f5a46  xor     rax, rsp
0x1801f5a49  mov     [rsp+0C8h+var_28], rax
0x1801f5a51  mov     rsi, rdx
0x1801f5a54  mov     rdi, rcx
0x1801f5a57  mov     [rsp+0C8h+var_50], 0
0x1801f5a5f  mov     [rsp+0C8h+var_4C], 0
0x1801f5a64  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801f5a6b  mov     [r11-80h], rax
0x1801f5a6f  lea     rax, [r11-50h]
0x1801f5a73  mov     [r11-78h], rax
0x1801f5a77  lea     rax, aMdmPolicyUserR_29; "MDM_Policy_User_Result01_Browser02"
0x1801f5a7e  mov     [r11-70h], rax
0x1801f5a82  lea     rcx, [r11-50h]
0x1801f5a86  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801f5a8b  mov     eax, cs:dword_180380B68
0x1801f5a91  cmp     eax, 5
0x1801f5a94  jbe     short loc_1801F5B07
0x1801f5a96  mov     rdx, 200000000000h
0x1801f5aa0  lea     rcx, dword_180380B68
0x1801f5aa7  call    _tlgKeywordOn
0x1801f5aac  test    al, al
0x1801f5aae  jz      short loc_1801F5B07
0x1801f5ab0  cmp     [rsp+0C8h+var_4C], 0
0x1801f5ab5  jz      short loc_1801F5AE9
0x1801f5ab7  cmp     [rsp+0C8h+var_38], 0
0x1801f5abf  jnz     short loc_1801F5ADF
0x1801f5ac1  cmp     [rsp+0C8h+var_34], 0
0x1801f5ac9  jnz     short loc_1801F5ADF
0x1801f5acb  cmp     [rsp+0C8h+var_30], 0
0x1801f5ad3  jnz     short loc_1801F5ADF
0x1801f5ad5  cmp     [rsp+0C8h+var_2C], 0
0x1801f5add  jz      short loc_1801F5AE9
0x1801f5adf  lea     r9, [rsp+0C8h+var_38]
0x1801f5ae7  jmp     short loc_1801F5AEC
0x1801f5ae9  xor     r9d, r9d
0x1801f5aec  lea     r8, [rsp+0C8h+var_48]
0x1801f5af4  lea     rdx, byte_180363FE9
0x1801f5afb  lea     rcx, dword_180380B68
0x1801f5b02  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801f5b07  cmp     byte ptr [rsi+48h], 0
0x1801f5b0b  jz      loc_1801F69E9
0x1801f5b11  cmp     byte ptr [rsi+58h], 0
0x1801f5b15  jz      loc_1801F69E9
0x1801f5b1b  mov     r9, [rsi+40h]; unsigned __int16 *
0x1801f5b1f  mov     r8, [rsi+50h]; unsigned __int16 *
0x1801f5b23  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x1801f5b2a  lea     rcx, [rsp+0C8h+var_80]; this
0x1801f5b2f  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1801f5b34  nop
0x1801f5b35  mov     [rsp+0C8h+var_88], 0
0x1801f5b3e  lea     rax, [rsp+0C8h+var_88]
0x1801f5b43  mov     [rsp+0C8h+var_98], rax
0x1801f5b48  mov     [rsp+0C8h+var_A0], 3
0x1801f5b50  mov     [rsp+0C8h+var_A8], 39h ; '9'
0x1801f5b58  lea     r9, ?MDM_Policy_User_Result01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_User_Result01_Browser02_NodeList
0x1801f5b5f  mov     r8, [rsi+40h]
0x1801f5b63  mov     rdx, [rsi+50h]
0x1801f5b67  mov     rcx, rdi
0x1801f5b6a  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801f5b6f  mov     edi, eax
0x1801f5b71  test    eax, eax
0x1801f5b73  jz      short loc_1801F5B7A
0x1801f5b75  jmp     loc_1801F69EE
0x1801f5b7a  lea     rax, [rsp+0C8h+var_88]
0x1801f5b7f  mov     [rsp+0C8h+var_60], rax
0x1801f5b84  mov     r15d, 1
0x1801f5b8a  mov     [rsp+0C8h+var_58], r15b
0x1801f5b8f  mov     r14, [rsp+0C8h+var_88]
0x1801f5b94  test    r14, r14
0x1801f5b97  jnz     short loc_1801F5BA1
0x1801f5b99  mov     edi, r15d
0x1801f5b9c  jmp     loc_1801F69EE
0x1801f5ba1  mov     r9d, 39h ; '9'; unsigned int
0x1801f5ba7  lea     r8, ?MDM_Policy_User_Result01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1801f5bae  mov     rdx, rsi; struct _MI_Instance *
0x1801f5bb1  mov     rcx, r14; this
0x1801f5bb4  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1801f5bb9  lea     r8, [rsi+60h]; void *
0x1801f5bbd  cmp     [r8+4], r15b
0x1801f5bc1  jnz     short loc_1801F5BF6
0x1801f5bc3  lea     rdx, aAllowaddressba; "AllowAddressBarDropdown"
0x1801f5bca  mov     rcx, r14; this
0x1801f5bcd  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f5bd2  mov     edi, eax
0x1801f5bd4  test    eax, eax
0x1801f5bd6  jz      short loc_1801F5BF6
0x1801f5bd8  mov     rcx, [rsp+0C8h+var_88]
0x1801f5bdd  test    rcx, rcx
0x1801f5be0  jz      short loc_1801F5BF1
0x1801f5be2  mov     rax, [rcx]
0x1801f5be5  mov     edx, r15d
0x1801f5be8  mov     rax, [rax]
0x1801f5beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f5bf0  nop
0x1801f5bf1  jmp     loc_1801F69EE
0x1801f5bf6  lea     r8, [rsi+68h]; void *
0x1801f5bfa  cmp     [r8+4], r15b
0x1801f5bfe  jnz     short loc_1801F5C33
0x1801f5c00  lea     rdx, aAllowautofill; "AllowAutofill"
0x1801f5c07  mov     rcx, r14; this
0x1801f5c0a  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f5c0f  mov     edi, eax
0x1801f5c11  test    eax, eax
0x1801f5c13  jz      short loc_1801F5C33
0x1801f5c15  mov     rcx, [rsp+0C8h+var_88]
0x1801f5c1a  test    rcx, rcx
0x1801f5c1d  jz      short loc_1801F5C2E
0x1801f5c1f  mov     rax, [rcx]
0x1801f5c22  mov     edx, r15d
0x1801f5c25  mov     rax, [rax]
0x1801f5c28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f5c2d  nop
0x1801f5c2e  jmp     loc_1801F69EE
0x1801f5c33  lea     r8, [rsi+70h]; void *
0x1801f5c37  cmp     [r8+4], r15b
0x1801f5c3b  jnz     short loc_1801F5C70
0x1801f5c3d  lea     rdx, aAllowconfigura; "AllowConfigurationUpdateForBooksLibrary"
0x1801f5c44  mov     rcx, r14; this
0x1801f5c47  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f5c4c  mov     edi, eax
0x1801f5c4e  test    eax, eax
0x1801f5c50  jz      short loc_1801F5C70
0x1801f5c52  mov     rcx, [rsp+0C8h+var_88]
0x1801f5c57  test    rcx, rcx
0x1801f5c5a  jz      short loc_1801F5C6B
0x1801f5c5c  mov     rax, [rcx]
0x1801f5c5f  mov     edx, r15d
0x1801f5c62  mov     rax, [rax]
0x1801f5c65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f5c6a  nop
0x1801f5c6b  jmp     loc_1801F69EE
0x1801f5c70  lea     r8, [rsi+78h]; void *
0x1801f5c74  cmp     [r8+4], r15b
0x1801f5c78  jnz     short loc_1801F5CAD
0x1801f5c7a  lea     rdx, aAllowcookies; "AllowCookies"
0x1801f5c81  mov     rcx, r14; this
0x1801f5c84  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f5c89  mov     edi, eax
0x1801f5c8b  test    eax, eax
0x1801f5c8d  jz      short loc_1801F5CAD
0x1801f5c8f  mov     rcx, [rsp+0C8h+var_88]
0x1801f5c94  test    rcx, rcx
0x1801f5c97  jz      short loc_1801F5CA8
0x1801f5c99  mov     rax, [rcx]
0x1801f5c9c  mov     edx, r15d
0x1801f5c9f  mov     rax, [rax]
0x1801f5ca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f5ca7  nop
0x1801f5ca8  jmp     loc_1801F69EE
0x1801f5cad  lea     r8, [rsi+80h]; void *
0x1801f5cb4  cmp     [r8+4], r15b
0x1801f5cb8  jnz     short loc_1801F5CED
0x1801f5cba  lea     rdx, aAllowdeveloper; "AllowDeveloperTools"
0x1801f5cc1  mov     rcx, r14; this
0x1801f5cc4  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f5cc9  mov     edi, eax
0x1801f5ccb  test    eax, eax
0x1801f5ccd  jz      short loc_1801F5CED
0x1801f5ccf  mov     rcx, [rsp+0C8h+var_88]
0x1801f5cd4  test    rcx, rcx
0x1801f5cd7  jz      short loc_1801F5CE8
0x1801f5cd9  mov     rax, [rcx]
0x1801f5cdc  mov     edx, r15d
0x1801f5cdf  mov     rax, [rax]
0x1801f5ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f5ce7  nop
0x1801f5ce8  jmp     loc_1801F69EE
0x1801f5ced  lea     r8, [rsi+88h]; void *
0x1801f5cf4  cmp     [r8+4], r15b
0x1801f5cf8  jnz     short loc_1801F5D2D
0x1801f5cfa  lea     rdx, aAllowdonottrac; "AllowDoNotTrack"
0x1801f5d01  mov     rcx, r14; this
0x1801f5d04  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f5d09  mov     edi, eax
0x1801f5d0b  test    eax, eax
0x1801f5d0d  jz      short loc_1801F5D2D
0x1801f5d0f  mov     rcx, [rsp+0C8h+var_88]
0x1801f5d14  test    rcx, rcx
0x1801f5d17  jz      short loc_1801F5D28
0x1801f5d19  mov     rax, [rcx]
0x1801f5d1c  mov     edx, r15d
0x1801f5d1f  mov     rax, [rax]
0x1801f5d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f5d27  nop
0x1801f5d28  jmp     loc_1801F69EE
0x1801f5d2d  lea     r8, [rsi+90h]; void *
0x1801f5d34  cmp     [r8+4], r15b
0x1801f5d38  jnz     short loc_1801F5D6D
0x1801f5d3a  lea     rdx, aAllowextension; "AllowExtensions"
0x1801f5d41  mov     rcx, r14; this
0x1801f5d44  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f5d49  mov     edi, eax
0x1801f5d4b  test    eax, eax
0x1801f5d4d  jz      short loc_1801F5D6D
0x1801f5d4f  mov     rcx, [rsp+0C8h+var_88]
0x1801f5d54  test    rcx, rcx
0x1801f5d57  jz      short loc_1801F5D68
0x1801f5d59  mov     rax, [rcx]
0x1801f5d5c  mov     edx, r15d
0x1801f5d5f  mov     rax, [rax]
0x1801f5d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f5d67  nop
0x1801f5d68  jmp     loc_1801F69EE
0x1801f5d6d  lea     r8, [rsi+98h]; void *
0x1801f5d74  cmp     [r8+4], r15b
0x1801f5d78  jnz     short loc_1801F5DAD
0x1801f5d7a  lea     rdx, aAllowflash; "AllowFlash"
0x1801f5d81  mov     rcx, r14; this
0x1801f5d84  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f5d89  mov     edi, eax
0x1801f5d8b  test    eax, eax
0x1801f5d8d  jz      short loc_1801F5DAD
0x1801f5d8f  mov     rcx, [rsp+0C8h+var_88]
0x1801f5d94  test    rcx, rcx
0x1801f5d97  jz      short loc_1801F5DA8
0x1801f5d99  mov     rax, [rcx]
0x1801f5d9c  mov     edx, r15d
0x1801f5d9f  mov     rax, [rax]
0x1801f5da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f5da7  nop
0x1801f5da8  jmp     loc_1801F69EE
0x1801f5dad  lea     r8, [rsi+0A0h]; void *
0x1801f5db4  cmp     [r8+4], r15b
0x1801f5db8  jnz     short loc_1801F5DED
0x1801f5dba  lea     rdx, aAllowflashclic; "AllowFlashClickToRun"
0x1801f5dc1  mov     rcx, r14; this
0x1801f5dc4  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f5dc9  mov     edi, eax
0x1801f5dcb  test    eax, eax
0x1801f5dcd  jz      short loc_1801F5DED
0x1801f5dcf  mov     rcx, [rsp+0C8h+var_88]
0x1801f5dd4  test    rcx, rcx
0x1801f5dd7  jz      short loc_1801F5DE8
0x1801f5dd9  mov     rax, [rcx]
0x1801f5ddc  mov     edx, r15d
0x1801f5ddf  mov     rax, [rax]
0x1801f5de2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f5de7  nop
0x1801f5de8  jmp     loc_1801F69EE
0x1801f5ded  lea     r8, [rsi+0A8h]; void *
0x1801f5df4  cmp     [r8+4], r15b
0x1801f5df8  jnz     short loc_1801F5E2D
0x1801f5dfa  lea     rdx, aAllowfullscree; "AllowFullScreenMode"
0x1801f5e01  mov     rcx, r14; this
0x1801f5e04  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f5e09  mov     edi, eax
0x1801f5e0b  test    eax, eax
0x1801f5e0d  jz      short loc_1801F5E2D
0x1801f5e0f  mov     rcx, [rsp+0C8h+var_88]
0x1801f5e14  test    rcx, rcx
0x1801f5e17  jz      short loc_1801F5E28
0x1801f5e19  mov     rax, [rcx]
0x1801f5e1c  mov     edx, r15d
0x1801f5e1f  mov     rax, [rax]
0x1801f5e22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f5e27  nop
0x1801f5e28  jmp     loc_1801F69EE
0x1801f5e2d  lea     r8, [rsi+0B0h]; void *
0x1801f5e34  cmp     [r8+4], r15b
0x1801f5e38  jnz     short loc_1801F5E6D
0x1801f5e3a  lea     rdx, aAllowinprivate; "AllowInPrivate"
0x1801f5e41  mov     rcx, r14; this
0x1801f5e44  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f5e49  mov     edi, eax
0x1801f5e4b  test    eax, eax
0x1801f5e4d  jz      short loc_1801F5E6D
0x1801f5e4f  mov     rcx, [rsp+0C8h+var_88]
0x1801f5e54  test    rcx, rcx
0x1801f5e57  jz      short loc_1801F5E68
0x1801f5e59  mov     rax, [rcx]
0x1801f5e5c  mov     edx, r15d
0x1801f5e5f  mov     rax, [rax]
0x1801f5e62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f5e67  nop
0x1801f5e68  jmp     loc_1801F69EE
0x1801f5e6d  lea     r8, [rsi+0B8h]; void *
0x1801f5e74  cmp     [r8+4], r15b
0x1801f5e78  jnz     short loc_1801F5EAD
0x1801f5e7a  lea     rdx, aAllowmicrosoft_2; "AllowMicrosoftCompatibilityList"
0x1801f5e81  mov     rcx, r14; this
0x1801f5e84  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f5e89  mov     edi, eax
0x1801f5e8b  test    eax, eax
0x1801f5e8d  jz      short loc_1801F5EAD
0x1801f5e8f  mov     rcx, [rsp+0C8h+var_88]
0x1801f5e94  test    rcx, rcx
0x1801f5e97  jz      short loc_1801F5EA8
0x1801f5e99  mov     rax, [rcx]
0x1801f5e9c  mov     edx, r15d
0x1801f5e9f  mov     rax, [rax]
0x1801f5ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f5ea7  nop
0x1801f5ea8  jmp     loc_1801F69EE
  ... truncated ...
```
