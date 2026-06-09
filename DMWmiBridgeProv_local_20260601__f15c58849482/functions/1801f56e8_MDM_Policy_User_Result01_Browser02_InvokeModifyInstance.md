# MDM_Policy_User_Result01_Browser02_InvokeModifyInstance

- ea: `0x1801f56e8`
- end: `0x1801f673c`
- name: `MDM_Policy_User_Result01_Browser02_InvokeModifyInstance`
- size: `4180`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801f6750`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x18000a768`
- `0x1801f56e8`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x1801f58f9`: `AllowConfigurationUpdateForBooksLibrary`
- `0x1801f59f6`: `AllowExtensions`
- `0x1801f5b36`: `AllowMicrosoftCompatibilityList`
- `0x1801f5d36`: `AllowSideloadingOfExtensions`
- `0x1801f5eb6`: `ConfigureAdditionalSearchEngines`
- `0x1801f5ef6`: `ConfigureFavoritesBar`
- `0x1801f5f36`: `ConfigureHomeButton`
- `0x1801f5f76`: `ConfigureKioskMode`
- `0x1801f5fb6`: `ConfigureKioskResetAfterIdleTimeout`
- `0x1801f5ff6`: `ConfigureOpenMicrosoftEdgeWith`
- `0x1801f6036`: `ConfigureTelemetryForMicrosoft365Analytics`
- `0x1801f6136`: `EnterpriseSiteListServiceUrl`
- `0x1801f61f6`: `PreventAccessToAboutFlagsInMicrosoftEdge`
- `0x1801f6376`: `PreventTurningOffRequiredExtensions`
- `0x1801f6536`: `ShowMessageWhenOpeningSitesInInternetExplorer`

## pseudocode

```c
__int64 __fastcall MDM_Policy_User_Result01_Browser02_InvokeModifyInstance(__int64 a1, __int64 a2)
{
  _DWORD *v4; // r9
  enum _MI_Result inserted; // edi
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
    inserted = (unsigned int)CreateRequestHandlerInstance(
                               a1,
                               *(_QWORD *)(a2 + 80),
                               *(_QWORD *)(a2 + 64),
                               &MDM_Policy_User_Result01_Browser02_NodeList,
                               57,
                               3,
                               &v8);
    if ( inserted == MI_RESULT_OK )
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
          && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowAddressBarDropdown", (void *)(a2 + 96))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 108) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowAutofill", (void *)(a2 + 104))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 116) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowConfigurationUpdateForBooksLibrary",
                                (void *)(a2 + 112))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 124) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowCookies", (void *)(a2 + 120))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 132) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowDeveloperTools", (void *)(a2 + 128))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 140) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowDoNotTrack", (void *)(a2 + 136))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 148) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowExtensions", (void *)(a2 + 144))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 156) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowFlash", (void *)(a2 + 152))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 164) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowFlashClickToRun", (void *)(a2 + 160))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 172) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowFullScreenMode", (void *)(a2 + 168))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 180) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowInPrivate", (void *)(a2 + 176))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 188) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowMicrosoftCompatibilityList",
                                (void *)(a2 + 184))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 196) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPasswordManager", (void *)(a2 + 192))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 204) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPopups", (void *)(a2 + 200))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 212) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPrelaunch", (void *)(a2 + 208))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 220) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowPrinting", (void *)(a2 + 216))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 228) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowSavingHistory", (void *)(a2 + 224))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 236) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowSearchEngineCustomization",
                                (void *)(a2 + 232))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 244) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowSearchSuggestionsinAddressBar",
                                (void *)(a2 + 240))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 252) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowSideloadingOfExtensions",
                                (void *)(a2 + 248))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 260) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowSmartScreen", (void *)(a2 + 256))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 268) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"AllowTabPreloading", (void *)(a2 + 264))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 276) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AllowWebContentOnNewTabPage",
                                (void *)(a2 + 272))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 284) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"AlwaysEnableBooksLibrary",
                                (void *)(a2 + 280))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 292) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ClearBrowsingDataOnExit",
                                (void *)(a2 + 288))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 304) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureAdditionalSearchEngines",
                                (void *)(a2 + 296))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 316) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureFavoritesBar", (void *)(a2 + 312))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 324) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureHomeButton", (void *)(a2 + 320))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 332) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ConfigureKioskMode", (void *)(a2 + 328))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 340) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureKioskResetAfterIdleTimeout",
                                (void *)(a2 + 336))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 348) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureOpenMicrosoftEdgeWith",
                                (void *)(a2 + 344))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 356) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ConfigureTelemetryForMicrosoft365Analytics",
                                (void *)(a2 + 352))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 364) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DisableLockdownOfStartPages",
                                (void *)(a2 + 360))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 372) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"EnableExtendedBooksTelemetry",
                                (void *)(a2 + 368))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 384) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnterpriseModeSiteList", (void *)(a2 + 376))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 400) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"EnterpriseSiteListServiceUrl",
                                (void *)(a2 + 392))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 416) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"HomePages", (void *)(a2 + 408))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 428) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"LockdownFavorites", (void *)(a2 + 424))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 436) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventAccessToAboutFlagsInMicrosoftEdge",
                                (void *)(a2 + 432))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 444) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventCertErrorOverrides",
                                (void *)(a2 + 440))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 452) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PreventFirstRunPage", (void *)(a2 + 448))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 460) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventLiveTileDataCollection",
                                (void *)(a2 + 456))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 468) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventSmartScreenPromptOverride",
                                (void *)(a2 + 464))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 476) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventSmartScreenPromptOverrideForFiles",
                                (void *)(a2 + 472))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 488) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventTurningOffRequiredExtensions",
                                (void *)(a2 + 480))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 500) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventUsingLocalHostIPAddressForWebRTC",
                                (void *)(a2 + 496))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 512) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ProvisionFavorites", (void *)(a2 + 504))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 524) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SendIntranetTraffictoInternetExplorer",
                                (void *)(a2 + 520))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 536) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetDefaultSearchEngine", (void *)(a2 + 528))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 552) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetHomeButtonURL", (void *)(a2 + 544))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 568) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetNewTabPageURL", (void *)(a2 + 560))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 580) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ShowMessageWhenOpeningSitesInInternetExplorer",
                                (void *)(a2 + 576))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 588) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SyncFavoritesBetweenIEAndMicrosoftEdge",
                                (void *)(a2 + 584))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 596) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"UnlockHomeButton", (void *)(a2 + 592))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 604) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UseSharedFolderForBooks",
                                (void *)(a2 + 600))) != MI_RESULT_OK )
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
            else if ( v8 )
            {
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
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
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v9, "ModifyInstanceEnd", inserted);
  v11 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_180352265,
      v13,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v11);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1801f56e8  mov     r11, rsp
0x1801f56eb  mov     [r11+18h], rsi
0x1801f56ef  push    rdi
0x1801f56f0  push    r14
0x1801f56f2  push    r15
0x1801f56f4  sub     rsp, 0B0h
0x1801f56fb  mov     rax, cs:__security_cookie
0x1801f5702  xor     rax, rsp
0x1801f5705  mov     [rsp+0C8h+var_28], rax
0x1801f570d  mov     rsi, rdx
0x1801f5710  mov     rdi, rcx
0x1801f5713  mov     [rsp+0C8h+var_50], 0
0x1801f571b  mov     [rsp+0C8h+var_4C], 0
0x1801f5720  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801f5727  mov     [r11-80h], rax
0x1801f572b  lea     rax, [r11-50h]
0x1801f572f  mov     [r11-78h], rax
0x1801f5733  lea     rax, aMdmPolicyUserR_29; "MDM_Policy_User_Result01_Browser02"
0x1801f573a  mov     [r11-70h], rax
0x1801f573e  lea     rcx, [r11-50h]
0x1801f5742  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801f5747  mov     eax, cs:dword_180380B68
0x1801f574d  cmp     eax, 5
0x1801f5750  jbe     short loc_1801F57C3
0x1801f5752  mov     rdx, 200000000000h
0x1801f575c  lea     rcx, dword_180380B68
0x1801f5763  call    _tlgKeywordOn
0x1801f5768  test    al, al
0x1801f576a  jz      short loc_1801F57C3
0x1801f576c  cmp     [rsp+0C8h+var_4C], 0
0x1801f5771  jz      short loc_1801F57A5
0x1801f5773  cmp     [rsp+0C8h+var_38], 0
0x1801f577b  jnz     short loc_1801F579B
0x1801f577d  cmp     [rsp+0C8h+var_34], 0
0x1801f5785  jnz     short loc_1801F579B
0x1801f5787  cmp     [rsp+0C8h+var_30], 0
0x1801f578f  jnz     short loc_1801F579B
0x1801f5791  cmp     [rsp+0C8h+var_2C], 0
0x1801f5799  jz      short loc_1801F57A5
0x1801f579b  lea     r9, [rsp+0C8h+var_38]
0x1801f57a3  jmp     short loc_1801F57A8
0x1801f57a5  xor     r9d, r9d
0x1801f57a8  lea     r8, [rsp+0C8h+var_48]
0x1801f57b0  lea     rdx, byte_180363FE9
0x1801f57b7  lea     rcx, dword_180380B68
0x1801f57be  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801f57c3  cmp     byte ptr [rsi+48h], 0
0x1801f57c7  jz      loc_1801F66A5
0x1801f57cd  cmp     byte ptr [rsi+58h], 0
0x1801f57d1  jz      loc_1801F66A5
0x1801f57d7  mov     r9, [rsi+40h]; unsigned __int16 *
0x1801f57db  mov     r8, [rsi+50h]; unsigned __int16 *
0x1801f57df  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x1801f57e6  lea     rcx, [rsp+0C8h+var_80]; this
0x1801f57eb  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1801f57f0  nop
0x1801f57f1  mov     [rsp+0C8h+var_88], 0
0x1801f57fa  lea     rax, [rsp+0C8h+var_88]
0x1801f57ff  mov     [rsp+0C8h+var_98], rax
0x1801f5804  mov     [rsp+0C8h+var_A0], 3
0x1801f580c  mov     [rsp+0C8h+var_A8], 39h ; '9'
0x1801f5814  lea     r9, ?MDM_Policy_User_Result01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_User_Result01_Browser02_NodeList
0x1801f581b  mov     r8, [rsi+40h]
0x1801f581f  mov     rdx, [rsi+50h]
0x1801f5823  mov     rcx, rdi
0x1801f5826  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801f582b  mov     edi, eax
0x1801f582d  test    eax, eax
0x1801f582f  jz      short loc_1801F5836
0x1801f5831  jmp     loc_1801F66AA
0x1801f5836  lea     rax, [rsp+0C8h+var_88]
0x1801f583b  mov     [rsp+0C8h+var_60], rax
0x1801f5840  mov     r15d, 1
0x1801f5846  mov     [rsp+0C8h+var_58], r15b
0x1801f584b  mov     r14, [rsp+0C8h+var_88]
0x1801f5850  test    r14, r14
0x1801f5853  jnz     short loc_1801F585D
0x1801f5855  mov     edi, r15d
0x1801f5858  jmp     loc_1801F66AA
0x1801f585d  mov     r9d, 39h ; '9'; unsigned int
0x1801f5863  lea     r8, ?MDM_Policy_User_Result01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1801f586a  mov     rdx, rsi; struct _MI_Instance *
0x1801f586d  mov     rcx, r14; this
0x1801f5870  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1801f5875  lea     r8, [rsi+60h]; void *
0x1801f5879  cmp     [r8+4], r15b
0x1801f587d  jnz     short loc_1801F58B2
0x1801f587f  lea     rdx, aAllowaddressba; "AllowAddressBarDropdown"
0x1801f5886  mov     rcx, r14; this
0x1801f5889  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f588e  mov     edi, eax
0x1801f5890  test    eax, eax
0x1801f5892  jz      short loc_1801F58B2
0x1801f5894  mov     rcx, [rsp+0C8h+var_88]
0x1801f5899  test    rcx, rcx
0x1801f589c  jz      short loc_1801F58AD
0x1801f589e  mov     rax, [rcx]
0x1801f58a1  mov     edx, r15d
0x1801f58a4  mov     rax, [rax]
0x1801f58a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f58ac  nop
0x1801f58ad  jmp     loc_1801F66AA
0x1801f58b2  lea     r8, [rsi+68h]; void *
0x1801f58b6  cmp     [r8+4], r15b
0x1801f58ba  jnz     short loc_1801F58EF
0x1801f58bc  lea     rdx, aAllowautofill; "AllowAutofill"
0x1801f58c3  mov     rcx, r14; this
0x1801f58c6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f58cb  mov     edi, eax
0x1801f58cd  test    eax, eax
0x1801f58cf  jz      short loc_1801F58EF
0x1801f58d1  mov     rcx, [rsp+0C8h+var_88]
0x1801f58d6  test    rcx, rcx
0x1801f58d9  jz      short loc_1801F58EA
0x1801f58db  mov     rax, [rcx]
0x1801f58de  mov     edx, r15d
0x1801f58e1  mov     rax, [rax]
0x1801f58e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f58e9  nop
0x1801f58ea  jmp     loc_1801F66AA
0x1801f58ef  lea     r8, [rsi+70h]; void *
0x1801f58f3  cmp     [r8+4], r15b
0x1801f58f7  jnz     short loc_1801F592C
0x1801f58f9  lea     rdx, aAllowconfigura; "AllowConfigurationUpdateForBooksLibrary"
0x1801f5900  mov     rcx, r14; this
0x1801f5903  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f5908  mov     edi, eax
0x1801f590a  test    eax, eax
0x1801f590c  jz      short loc_1801F592C
0x1801f590e  mov     rcx, [rsp+0C8h+var_88]
0x1801f5913  test    rcx, rcx
0x1801f5916  jz      short loc_1801F5927
0x1801f5918  mov     rax, [rcx]
0x1801f591b  mov     edx, r15d
0x1801f591e  mov     rax, [rax]
0x1801f5921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f5926  nop
0x1801f5927  jmp     loc_1801F66AA
0x1801f592c  lea     r8, [rsi+78h]; void *
0x1801f5930  cmp     [r8+4], r15b
0x1801f5934  jnz     short loc_1801F5969
0x1801f5936  lea     rdx, aAllowcookies; "AllowCookies"
0x1801f593d  mov     rcx, r14; this
0x1801f5940  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f5945  mov     edi, eax
0x1801f5947  test    eax, eax
0x1801f5949  jz      short loc_1801F5969
0x1801f594b  mov     rcx, [rsp+0C8h+var_88]
0x1801f5950  test    rcx, rcx
0x1801f5953  jz      short loc_1801F5964
0x1801f5955  mov     rax, [rcx]
0x1801f5958  mov     edx, r15d
0x1801f595b  mov     rax, [rax]
0x1801f595e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f5963  nop
0x1801f5964  jmp     loc_1801F66AA
0x1801f5969  lea     r8, [rsi+80h]; void *
0x1801f5970  cmp     [r8+4], r15b
0x1801f5974  jnz     short loc_1801F59A9
0x1801f5976  lea     rdx, aAllowdeveloper; "AllowDeveloperTools"
0x1801f597d  mov     rcx, r14; this
0x1801f5980  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f5985  mov     edi, eax
0x1801f5987  test    eax, eax
0x1801f5989  jz      short loc_1801F59A9
0x1801f598b  mov     rcx, [rsp+0C8h+var_88]
0x1801f5990  test    rcx, rcx
0x1801f5993  jz      short loc_1801F59A4
0x1801f5995  mov     rax, [rcx]
0x1801f5998  mov     edx, r15d
0x1801f599b  mov     rax, [rax]
0x1801f599e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f59a3  nop
0x1801f59a4  jmp     loc_1801F66AA
0x1801f59a9  lea     r8, [rsi+88h]; void *
0x1801f59b0  cmp     [r8+4], r15b
0x1801f59b4  jnz     short loc_1801F59E9
0x1801f59b6  lea     rdx, aAllowdonottrac; "AllowDoNotTrack"
0x1801f59bd  mov     rcx, r14; this
0x1801f59c0  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f59c5  mov     edi, eax
0x1801f59c7  test    eax, eax
0x1801f59c9  jz      short loc_1801F59E9
0x1801f59cb  mov     rcx, [rsp+0C8h+var_88]
0x1801f59d0  test    rcx, rcx
0x1801f59d3  jz      short loc_1801F59E4
0x1801f59d5  mov     rax, [rcx]
0x1801f59d8  mov     edx, r15d
0x1801f59db  mov     rax, [rax]
0x1801f59de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f59e3  nop
0x1801f59e4  jmp     loc_1801F66AA
0x1801f59e9  lea     r8, [rsi+90h]; void *
0x1801f59f0  cmp     [r8+4], r15b
0x1801f59f4  jnz     short loc_1801F5A29
0x1801f59f6  lea     rdx, aAllowextension; "AllowExtensions"
0x1801f59fd  mov     rcx, r14; this
0x1801f5a00  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f5a05  mov     edi, eax
0x1801f5a07  test    eax, eax
0x1801f5a09  jz      short loc_1801F5A29
0x1801f5a0b  mov     rcx, [rsp+0C8h+var_88]
0x1801f5a10  test    rcx, rcx
0x1801f5a13  jz      short loc_1801F5A24
0x1801f5a15  mov     rax, [rcx]
0x1801f5a18  mov     edx, r15d
0x1801f5a1b  mov     rax, [rax]
0x1801f5a1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f5a23  nop
0x1801f5a24  jmp     loc_1801F66AA
0x1801f5a29  lea     r8, [rsi+98h]; void *
0x1801f5a30  cmp     [r8+4], r15b
0x1801f5a34  jnz     short loc_1801F5A69
0x1801f5a36  lea     rdx, aAllowflash; "AllowFlash"
0x1801f5a3d  mov     rcx, r14; this
0x1801f5a40  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f5a45  mov     edi, eax
0x1801f5a47  test    eax, eax
0x1801f5a49  jz      short loc_1801F5A69
0x1801f5a4b  mov     rcx, [rsp+0C8h+var_88]
0x1801f5a50  test    rcx, rcx
0x1801f5a53  jz      short loc_1801F5A64
0x1801f5a55  mov     rax, [rcx]
0x1801f5a58  mov     edx, r15d
0x1801f5a5b  mov     rax, [rax]
0x1801f5a5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f5a63  nop
0x1801f5a64  jmp     loc_1801F66AA
0x1801f5a69  lea     r8, [rsi+0A0h]; void *
0x1801f5a70  cmp     [r8+4], r15b
0x1801f5a74  jnz     short loc_1801F5AA9
0x1801f5a76  lea     rdx, aAllowflashclic; "AllowFlashClickToRun"
0x1801f5a7d  mov     rcx, r14; this
0x1801f5a80  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f5a85  mov     edi, eax
0x1801f5a87  test    eax, eax
0x1801f5a89  jz      short loc_1801F5AA9
0x1801f5a8b  mov     rcx, [rsp+0C8h+var_88]
0x1801f5a90  test    rcx, rcx
0x1801f5a93  jz      short loc_1801F5AA4
0x1801f5a95  mov     rax, [rcx]
0x1801f5a98  mov     edx, r15d
0x1801f5a9b  mov     rax, [rax]
0x1801f5a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f5aa3  nop
0x1801f5aa4  jmp     loc_1801F66AA
0x1801f5aa9  lea     r8, [rsi+0A8h]; void *
0x1801f5ab0  cmp     [r8+4], r15b
0x1801f5ab4  jnz     short loc_1801F5AE9
0x1801f5ab6  lea     rdx, aAllowfullscree; "AllowFullScreenMode"
0x1801f5abd  mov     rcx, r14; this
0x1801f5ac0  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f5ac5  mov     edi, eax
0x1801f5ac7  test    eax, eax
0x1801f5ac9  jz      short loc_1801F5AE9
0x1801f5acb  mov     rcx, [rsp+0C8h+var_88]
0x1801f5ad0  test    rcx, rcx
0x1801f5ad3  jz      short loc_1801F5AE4
0x1801f5ad5  mov     rax, [rcx]
0x1801f5ad8  mov     edx, r15d
0x1801f5adb  mov     rax, [rax]
0x1801f5ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f5ae3  nop
0x1801f5ae4  jmp     loc_1801F66AA
0x1801f5ae9  lea     r8, [rsi+0B0h]; void *
0x1801f5af0  cmp     [r8+4], r15b
0x1801f5af4  jnz     short loc_1801F5B29
0x1801f5af6  lea     rdx, aAllowinprivate; "AllowInPrivate"
0x1801f5afd  mov     rcx, r14; this
0x1801f5b00  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f5b05  mov     edi, eax
0x1801f5b07  test    eax, eax
0x1801f5b09  jz      short loc_1801F5B29
0x1801f5b0b  mov     rcx, [rsp+0C8h+var_88]
0x1801f5b10  test    rcx, rcx
0x1801f5b13  jz      short loc_1801F5B24
0x1801f5b15  mov     rax, [rcx]
0x1801f5b18  mov     edx, r15d
0x1801f5b1b  mov     rax, [rax]
0x1801f5b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f5b23  nop
0x1801f5b24  jmp     loc_1801F66AA
0x1801f5b29  lea     r8, [rsi+0B8h]; void *
0x1801f5b30  cmp     [r8+4], r15b
0x1801f5b34  jnz     short loc_1801F5B69
0x1801f5b36  lea     rdx, aAllowmicrosoft_2; "AllowMicrosoftCompatibilityList"
0x1801f5b3d  mov     rcx, r14; this
0x1801f5b40  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801f5b45  mov     edi, eax
0x1801f5b47  test    eax, eax
0x1801f5b49  jz      short loc_1801F5B69
0x1801f5b4b  mov     rcx, [rsp+0C8h+var_88]
0x1801f5b50  test    rcx, rcx
0x1801f5b53  jz      short loc_1801F5B64
0x1801f5b55  mov     rax, [rcx]
0x1801f5b58  mov     edx, r15d
0x1801f5b5b  mov     rax, [rax]
0x1801f5b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f5b63  nop
0x1801f5b64  jmp     loc_1801F66AA
  ... truncated ...
```
