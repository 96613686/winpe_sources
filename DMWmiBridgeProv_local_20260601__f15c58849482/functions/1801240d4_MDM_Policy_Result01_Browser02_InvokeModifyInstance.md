# MDM_Policy_Result01_Browser02_InvokeModifyInstance

- ea: `0x1801240d4`
- end: `0x1801252a8`
- name: `MDM_Policy_Result01_Browser02_InvokeModifyInstance`
- size: `4564`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801252b0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x18000a768`
- `0x1801240d4`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x1801242e5`: `AllowConfigurationUpdateForBooksLibrary`
- `0x1801243e2`: `AllowExtensions`
- `0x180124522`: `AllowMicrosoftCompatibilityList`
- `0x180124722`: `AllowSideloadingOfExtensions`
- `0x1801248a2`: `ConfigureAdditionalSearchEngines`
- `0x1801248e2`: `ConfigureFavoritesBar`
- `0x180124922`: `ConfigureHomeButton`
- `0x180124962`: `ConfigureKioskMode`
- `0x1801249a2`: `ConfigureKioskResetAfterIdleTimeout`
- `0x1801249e2`: `ConfigureOpenMicrosoftEdgeWith`
- `0x180124a22`: `ConfigureTelemetryForMicrosoft365Analytics`
- `0x180124ca2`: `EnterpriseSiteListServiceUrl`
- `0x180124d62`: `PreventAccessToAboutFlagsInMicrosoftEdge`
- `0x180124ee2`: `PreventTurningOffRequiredExtensions`
- `0x1801250a2`: `ShowMessageWhenOpeningSitesInInternetExplorer`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_Browser02_InvokeModifyInstance(__int64 a1, __int64 a2)
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
  v9[2] = "MDM_Policy_Result01_Browser02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v11);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v12 && (v14[0] || v14[1] || v14[2] || v14[3]) )
      v4 = v14;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &word_18035E3EE,
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
                               &MDM_Policy_Result01_Browser02_NodeList,
                               63,
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
          (struct WmiNodeInfo *)&MDM_Policy_Result01_Browser02_NodeList,
          0x3Fu);
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
        else if ( *(_BYTE *)(a2 + 368) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DefaultFavoriteBarItem1Name",
                                (void *)(a2 + 360))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 384) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DefaultFavoriteBarItem1Url",
                                (void *)(a2 + 376))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 400) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DefaultFavoriteBarItem2Name",
                                (void *)(a2 + 392))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 416) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DefaultFavoriteBarItem2Url",
                                (void *)(a2 + 408))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 432) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DefaultFavoriteBarItem3Name",
                                (void *)(a2 + 424))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 448) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DefaultFavoriteBarItem3Url",
                                (void *)(a2 + 440))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 460) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DisableLockdownOfStartPages",
                                (void *)(a2 + 456))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 468) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"EnableExtendedBooksTelemetry",
                                (void *)(a2 + 464))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 480) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnterpriseModeSiteList", (void *)(a2 + 472))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 496) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"EnterpriseSiteListServiceUrl",
                                (void *)(a2 + 488))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 512) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"HomePages", (void *)(a2 + 504))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 524) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"LockdownFavorites", (void *)(a2 + 520))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 532) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventAccessToAboutFlagsInMicrosoftEdge",
                                (void *)(a2 + 528))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 540) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventCertErrorOverrides",
                                (void *)(a2 + 536))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 548) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PreventFirstRunPage", (void *)(a2 + 544))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 556) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventLiveTileDataCollection",
                                (void *)(a2 + 552))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 564) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventSmartScreenPromptOverride",
                                (void *)(a2 + 560))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 572) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventSmartScreenPromptOverrideForFiles",
                                (void *)(a2 + 568))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 584) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventTurningOffRequiredExtensions",
                                (void *)(a2 + 576))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 596) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventUsingLocalHostIPAddressForWebRTC",
                                (void *)(a2 + 592))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 608) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ProvisionFavorites", (void *)(a2 + 600))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 620) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SendIntranetTraffictoInternetExplorer",
                                (void *)(a2 + 616))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 632) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetDefaultSearchEngine", (void *)(a2 + 624))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 648) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetHomeButtonURL", (void *)(a2 + 640))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 664) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetNewTabPageURL", (void *)(a2 + 656))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 676) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ShowMessageWhenOpeningSitesInInternetExplorer",
                                (void *)(a2 + 672))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 684) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SyncFavoritesBetweenIEAndMicrosoftEdge",
                                (void *)(a2 + 680))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 692) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"UnlockHomeButton", (void *)(a2 + 688))) != MI_RESULT_OK )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 700) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UseSharedFolderForBooks",
                                (void *)(a2 + 696))) != MI_RESULT_OK )
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
      &dword_18034FF5C,
      v13,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v11);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1801240d4  mov     r11, rsp
0x1801240d7  mov     [r11+18h], rsi
0x1801240db  push    rdi
0x1801240dc  push    r14
0x1801240de  push    r15
0x1801240e0  sub     rsp, 0B0h
0x1801240e7  mov     rax, cs:__security_cookie
0x1801240ee  xor     rax, rsp
0x1801240f1  mov     [rsp+0C8h+var_28], rax
0x1801240f9  mov     rsi, rdx
0x1801240fc  mov     rdi, rcx
0x1801240ff  mov     [rsp+0C8h+var_50], 0
0x180124107  mov     [rsp+0C8h+var_4C], 0
0x18012410c  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180124113  mov     [r11-80h], rax
0x180124117  lea     rax, [r11-50h]
0x18012411b  mov     [r11-78h], rax
0x18012411f  lea     rax, aMdmPolicyResul_101; "MDM_Policy_Result01_Browser02"
0x180124126  mov     [r11-70h], rax
0x18012412a  lea     rcx, [r11-50h]
0x18012412e  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180124133  mov     eax, cs:dword_180380B68
0x180124139  cmp     eax, 5
0x18012413c  jbe     short loc_1801241AF
0x18012413e  mov     rdx, 200000000000h
0x180124148  lea     rcx, dword_180380B68
0x18012414f  call    _tlgKeywordOn
0x180124154  test    al, al
0x180124156  jz      short loc_1801241AF
0x180124158  cmp     [rsp+0C8h+var_4C], 0
0x18012415d  jz      short loc_180124191
0x18012415f  cmp     [rsp+0C8h+var_38], 0
0x180124167  jnz     short loc_180124187
0x180124169  cmp     [rsp+0C8h+var_34], 0
0x180124171  jnz     short loc_180124187
0x180124173  cmp     [rsp+0C8h+var_30], 0
0x18012417b  jnz     short loc_180124187
0x18012417d  cmp     [rsp+0C8h+var_2C], 0
0x180124185  jz      short loc_180124191
0x180124187  lea     r9, [rsp+0C8h+var_38]
0x18012418f  jmp     short loc_180124194
0x180124191  xor     r9d, r9d
0x180124194  lea     r8, [rsp+0C8h+var_48]
0x18012419c  lea     rdx, word_18035E3EE
0x1801241a3  lea     rcx, dword_180380B68
0x1801241aa  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801241af  cmp     byte ptr [rsi+48h], 0
0x1801241b3  jz      loc_180125211
0x1801241b9  cmp     byte ptr [rsi+58h], 0
0x1801241bd  jz      loc_180125211
0x1801241c3  mov     r9, [rsi+40h]; unsigned __int16 *
0x1801241c7  mov     r8, [rsi+50h]; unsigned __int16 *
0x1801241cb  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x1801241d2  lea     rcx, [rsp+0C8h+var_80]; this
0x1801241d7  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1801241dc  nop
0x1801241dd  mov     [rsp+0C8h+var_88], 0
0x1801241e6  lea     rax, [rsp+0C8h+var_88]
0x1801241eb  mov     [rsp+0C8h+var_98], rax
0x1801241f0  mov     [rsp+0C8h+var_A0], 3
0x1801241f8  mov     [rsp+0C8h+var_A8], 3Fh ; '?'
0x180124200  lea     r9, ?MDM_Policy_Result01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_Browser02_NodeList
0x180124207  mov     r8, [rsi+40h]
0x18012420b  mov     rdx, [rsi+50h]
0x18012420f  mov     rcx, rdi
0x180124212  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180124217  mov     edi, eax
0x180124219  test    eax, eax
0x18012421b  jz      short loc_180124222
0x18012421d  jmp     loc_180125216
0x180124222  lea     rax, [rsp+0C8h+var_88]
0x180124227  mov     [rsp+0C8h+var_60], rax
0x18012422c  mov     r15d, 1
0x180124232  mov     [rsp+0C8h+var_58], r15b
0x180124237  mov     r14, [rsp+0C8h+var_88]
0x18012423c  test    r14, r14
0x18012423f  jnz     short loc_180124249
0x180124241  mov     edi, r15d
0x180124244  jmp     loc_180125216
0x180124249  mov     r9d, 3Fh ; '?'; unsigned int
0x18012424f  lea     r8, ?MDM_Policy_Result01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x180124256  mov     rdx, rsi; struct _MI_Instance *
0x180124259  mov     rcx, r14; this
0x18012425c  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x180124261  lea     r8, [rsi+60h]; void *
0x180124265  cmp     [r8+4], r15b
0x180124269  jnz     short loc_18012429E
0x18012426b  lea     rdx, aAllowaddressba; "AllowAddressBarDropdown"
0x180124272  mov     rcx, r14; this
0x180124275  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18012427a  mov     edi, eax
0x18012427c  test    eax, eax
0x18012427e  jz      short loc_18012429E
0x180124280  mov     rcx, [rsp+0C8h+var_88]
0x180124285  test    rcx, rcx
0x180124288  jz      short loc_180124299
0x18012428a  mov     rax, [rcx]
0x18012428d  mov     edx, r15d
0x180124290  mov     rax, [rax]
0x180124293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180124298  nop
0x180124299  jmp     loc_180125216
0x18012429e  lea     r8, [rsi+68h]; void *
0x1801242a2  cmp     [r8+4], r15b
0x1801242a6  jnz     short loc_1801242DB
0x1801242a8  lea     rdx, aAllowautofill; "AllowAutofill"
0x1801242af  mov     rcx, r14; this
0x1801242b2  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801242b7  mov     edi, eax
0x1801242b9  test    eax, eax
0x1801242bb  jz      short loc_1801242DB
0x1801242bd  mov     rcx, [rsp+0C8h+var_88]
0x1801242c2  test    rcx, rcx
0x1801242c5  jz      short loc_1801242D6
0x1801242c7  mov     rax, [rcx]
0x1801242ca  mov     edx, r15d
0x1801242cd  mov     rax, [rax]
0x1801242d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801242d5  nop
0x1801242d6  jmp     loc_180125216
0x1801242db  lea     r8, [rsi+70h]; void *
0x1801242df  cmp     [r8+4], r15b
0x1801242e3  jnz     short loc_180124318
0x1801242e5  lea     rdx, aAllowconfigura; "AllowConfigurationUpdateForBooksLibrary"
0x1801242ec  mov     rcx, r14; this
0x1801242ef  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801242f4  mov     edi, eax
0x1801242f6  test    eax, eax
0x1801242f8  jz      short loc_180124318
0x1801242fa  mov     rcx, [rsp+0C8h+var_88]
0x1801242ff  test    rcx, rcx
0x180124302  jz      short loc_180124313
0x180124304  mov     rax, [rcx]
0x180124307  mov     edx, r15d
0x18012430a  mov     rax, [rax]
0x18012430d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180124312  nop
0x180124313  jmp     loc_180125216
0x180124318  lea     r8, [rsi+78h]; void *
0x18012431c  cmp     [r8+4], r15b
0x180124320  jnz     short loc_180124355
0x180124322  lea     rdx, aAllowcookies; "AllowCookies"
0x180124329  mov     rcx, r14; this
0x18012432c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180124331  mov     edi, eax
0x180124333  test    eax, eax
0x180124335  jz      short loc_180124355
0x180124337  mov     rcx, [rsp+0C8h+var_88]
0x18012433c  test    rcx, rcx
0x18012433f  jz      short loc_180124350
0x180124341  mov     rax, [rcx]
0x180124344  mov     edx, r15d
0x180124347  mov     rax, [rax]
0x18012434a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012434f  nop
0x180124350  jmp     loc_180125216
0x180124355  lea     r8, [rsi+80h]; void *
0x18012435c  cmp     [r8+4], r15b
0x180124360  jnz     short loc_180124395
0x180124362  lea     rdx, aAllowdeveloper; "AllowDeveloperTools"
0x180124369  mov     rcx, r14; this
0x18012436c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180124371  mov     edi, eax
0x180124373  test    eax, eax
0x180124375  jz      short loc_180124395
0x180124377  mov     rcx, [rsp+0C8h+var_88]
0x18012437c  test    rcx, rcx
0x18012437f  jz      short loc_180124390
0x180124381  mov     rax, [rcx]
0x180124384  mov     edx, r15d
0x180124387  mov     rax, [rax]
0x18012438a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012438f  nop
0x180124390  jmp     loc_180125216
0x180124395  lea     r8, [rsi+88h]; void *
0x18012439c  cmp     [r8+4], r15b
0x1801243a0  jnz     short loc_1801243D5
0x1801243a2  lea     rdx, aAllowdonottrac; "AllowDoNotTrack"
0x1801243a9  mov     rcx, r14; this
0x1801243ac  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801243b1  mov     edi, eax
0x1801243b3  test    eax, eax
0x1801243b5  jz      short loc_1801243D5
0x1801243b7  mov     rcx, [rsp+0C8h+var_88]
0x1801243bc  test    rcx, rcx
0x1801243bf  jz      short loc_1801243D0
0x1801243c1  mov     rax, [rcx]
0x1801243c4  mov     edx, r15d
0x1801243c7  mov     rax, [rax]
0x1801243ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801243cf  nop
0x1801243d0  jmp     loc_180125216
0x1801243d5  lea     r8, [rsi+90h]; void *
0x1801243dc  cmp     [r8+4], r15b
0x1801243e0  jnz     short loc_180124415
0x1801243e2  lea     rdx, aAllowextension; "AllowExtensions"
0x1801243e9  mov     rcx, r14; this
0x1801243ec  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801243f1  mov     edi, eax
0x1801243f3  test    eax, eax
0x1801243f5  jz      short loc_180124415
0x1801243f7  mov     rcx, [rsp+0C8h+var_88]
0x1801243fc  test    rcx, rcx
0x1801243ff  jz      short loc_180124410
0x180124401  mov     rax, [rcx]
0x180124404  mov     edx, r15d
0x180124407  mov     rax, [rax]
0x18012440a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012440f  nop
0x180124410  jmp     loc_180125216
0x180124415  lea     r8, [rsi+98h]; void *
0x18012441c  cmp     [r8+4], r15b
0x180124420  jnz     short loc_180124455
0x180124422  lea     rdx, aAllowflash; "AllowFlash"
0x180124429  mov     rcx, r14; this
0x18012442c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180124431  mov     edi, eax
0x180124433  test    eax, eax
0x180124435  jz      short loc_180124455
0x180124437  mov     rcx, [rsp+0C8h+var_88]
0x18012443c  test    rcx, rcx
0x18012443f  jz      short loc_180124450
0x180124441  mov     rax, [rcx]
0x180124444  mov     edx, r15d
0x180124447  mov     rax, [rax]
0x18012444a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012444f  nop
0x180124450  jmp     loc_180125216
0x180124455  lea     r8, [rsi+0A0h]; void *
0x18012445c  cmp     [r8+4], r15b
0x180124460  jnz     short loc_180124495
0x180124462  lea     rdx, aAllowflashclic; "AllowFlashClickToRun"
0x180124469  mov     rcx, r14; this
0x18012446c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180124471  mov     edi, eax
0x180124473  test    eax, eax
0x180124475  jz      short loc_180124495
0x180124477  mov     rcx, [rsp+0C8h+var_88]
0x18012447c  test    rcx, rcx
0x18012447f  jz      short loc_180124490
0x180124481  mov     rax, [rcx]
0x180124484  mov     edx, r15d
0x180124487  mov     rax, [rax]
0x18012448a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012448f  nop
0x180124490  jmp     loc_180125216
0x180124495  lea     r8, [rsi+0A8h]; void *
0x18012449c  cmp     [r8+4], r15b
0x1801244a0  jnz     short loc_1801244D5
0x1801244a2  lea     rdx, aAllowfullscree; "AllowFullScreenMode"
0x1801244a9  mov     rcx, r14; this
0x1801244ac  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801244b1  mov     edi, eax
0x1801244b3  test    eax, eax
0x1801244b5  jz      short loc_1801244D5
0x1801244b7  mov     rcx, [rsp+0C8h+var_88]
0x1801244bc  test    rcx, rcx
0x1801244bf  jz      short loc_1801244D0
0x1801244c1  mov     rax, [rcx]
0x1801244c4  mov     edx, r15d
0x1801244c7  mov     rax, [rax]
0x1801244ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801244cf  nop
0x1801244d0  jmp     loc_180125216
0x1801244d5  lea     r8, [rsi+0B0h]; void *
0x1801244dc  cmp     [r8+4], r15b
0x1801244e0  jnz     short loc_180124515
0x1801244e2  lea     rdx, aAllowinprivate; "AllowInPrivate"
0x1801244e9  mov     rcx, r14; this
0x1801244ec  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801244f1  mov     edi, eax
0x1801244f3  test    eax, eax
0x1801244f5  jz      short loc_180124515
0x1801244f7  mov     rcx, [rsp+0C8h+var_88]
0x1801244fc  test    rcx, rcx
0x1801244ff  jz      short loc_180124510
0x180124501  mov     rax, [rcx]
0x180124504  mov     edx, r15d
0x180124507  mov     rax, [rax]
0x18012450a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012450f  nop
0x180124510  jmp     loc_180125216
0x180124515  lea     r8, [rsi+0B8h]; void *
0x18012451c  cmp     [r8+4], r15b
0x180124520  jnz     short loc_180124555
0x180124522  lea     rdx, aAllowmicrosoft_2; "AllowMicrosoftCompatibilityList"
0x180124529  mov     rcx, r14; this
0x18012452c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180124531  mov     edi, eax
0x180124533  test    eax, eax
0x180124535  jz      short loc_180124555
0x180124537  mov     rcx, [rsp+0C8h+var_88]
0x18012453c  test    rcx, rcx
0x18012453f  jz      short loc_180124550
0x180124541  mov     rax, [rcx]
0x180124544  mov     edx, r15d
0x180124547  mov     rax, [rax]
0x18012454a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012454f  nop
0x180124550  jmp     loc_180125216
  ... truncated ...
```
