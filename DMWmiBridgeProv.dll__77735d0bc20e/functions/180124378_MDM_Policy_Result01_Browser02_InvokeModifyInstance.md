# MDM_Policy_Result01_Browser02_InvokeModifyInstance

- ea: `0x180124378`
- end: `0x18012554b`
- name: `MDM_Policy_Result01_Browser02_InvokeModifyInstance`
- size: `4563`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180125560`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x18000a280`
- `0x180124378`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x180124589`: `AllowConfigurationUpdateForBooksLibrary`
- `0x180124686`: `AllowExtensions`
- `0x1801247c6`: `AllowMicrosoftCompatibilityList`
- `0x1801249c6`: `AllowSideloadingOfExtensions`
- `0x180124b46`: `ConfigureAdditionalSearchEngines`
- `0x180124b86`: `ConfigureFavoritesBar`
- `0x180124bc6`: `ConfigureHomeButton`
- `0x180124c06`: `ConfigureKioskMode`
- `0x180124c46`: `ConfigureKioskResetAfterIdleTimeout`
- `0x180124c86`: `ConfigureOpenMicrosoftEdgeWith`
- `0x180124cc6`: `ConfigureTelemetryForMicrosoft365Analytics`
- `0x180124f46`: `EnterpriseSiteListServiceUrl`
- `0x180125006`: `PreventAccessToAboutFlagsInMicrosoftEdge`
- `0x180125186`: `PreventTurningOffRequiredExtensions`
- `0x180125346`: `ShowMessageWhenOpeningSitesInInternetExplorer`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_Browser02_InvokeModifyInstance(__int64 a1, __int64 a2)
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
    inserted = CreateRequestHandlerInstance(
                 a1,
                 *(wchar_t **)(a2 + 80),
                 *(const unsigned __int16 **)(a2 + 64),
                 (struct WmiNodeInfo *)&MDM_Policy_Result01_Browser02_NodeList,
                 0x3Fu,
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
          (struct WmiNodeInfo *)&MDM_Policy_Result01_Browser02_NodeList,
          0x3Fu);
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
        else if ( *(_BYTE *)(a2 + 368) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DefaultFavoriteBarItem1Name",
                                (LONG *)(a2 + 360))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 384) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DefaultFavoriteBarItem1Url",
                                (LONG *)(a2 + 376))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 400) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DefaultFavoriteBarItem2Name",
                                (LONG *)(a2 + 392))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 416) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DefaultFavoriteBarItem2Url",
                                (LONG *)(a2 + 408))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 432) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DefaultFavoriteBarItem3Name",
                                (LONG *)(a2 + 424))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 448) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DefaultFavoriteBarItem3Url",
                                (LONG *)(a2 + 440))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 460) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"DisableLockdownOfStartPages",
                                (LONG *)(a2 + 456))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 468) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"EnableExtendedBooksTelemetry",
                                (LONG *)(a2 + 464))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 480) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"EnterpriseModeSiteList", (LONG *)(a2 + 472))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 496) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"EnterpriseSiteListServiceUrl",
                                (LONG *)(a2 + 488))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 512) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"HomePages", (LONG *)(a2 + 504))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 524) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"LockdownFavorites", (LONG *)(a2 + 520))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 532) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventAccessToAboutFlagsInMicrosoftEdge",
                                (LONG *)(a2 + 528))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 540) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventCertErrorOverrides",
                                (LONG *)(a2 + 536))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 548) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"PreventFirstRunPage", (LONG *)(a2 + 544))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 556) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventLiveTileDataCollection",
                                (LONG *)(a2 + 552))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 564) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventSmartScreenPromptOverride",
                                (LONG *)(a2 + 560))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 572) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventSmartScreenPromptOverrideForFiles",
                                (LONG *)(a2 + 568))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 584) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventTurningOffRequiredExtensions",
                                (LONG *)(a2 + 576))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 596) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"PreventUsingLocalHostIPAddressForWebRTC",
                                (LONG *)(a2 + 592))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 608) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"ProvisionFavorites", (LONG *)(a2 + 600))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 620) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SendIntranetTraffictoInternetExplorer",
                                (LONG *)(a2 + 616))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 632) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetDefaultSearchEngine", (LONG *)(a2 + 624))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 648) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetHomeButtonURL", (LONG *)(a2 + 640))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 664) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"SetNewTabPageURL", (LONG *)(a2 + 656))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 676) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"ShowMessageWhenOpeningSitesInInternetExplorer",
                                (LONG *)(a2 + 672))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 684) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"SyncFavoritesBetweenIEAndMicrosoftEdge",
                                (LONG *)(a2 + 680))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 692) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v6, L"UnlockHomeButton", (LONG *)(a2 + 688))) != 0 )
        {
          if ( v8 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v8)(v8, 1);
        }
        else if ( *(_BYTE *)(a2 + 700) == 1
               && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                v6,
                                L"UseSharedFolderForBooks",
                                (LONG *)(a2 + 696))) != 0 )
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
      &dword_18034FF5C,
      v13,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v11);
  return inserted;
}

```

## disassembly

```asm
0x180124378  mov     r11, rsp
0x18012437b  mov     [r11+18h], rsi
0x18012437f  push    rdi
0x180124380  push    r14
0x180124382  push    r15
0x180124384  sub     rsp, 0B0h
0x18012438b  mov     rax, cs:__security_cookie
0x180124392  xor     rax, rsp
0x180124395  mov     [rsp+0C8h+var_28], rax
0x18012439d  mov     rsi, rdx
0x1801243a0  mov     rdi, rcx
0x1801243a3  mov     [rsp+0C8h+var_50], 0
0x1801243ab  mov     [rsp+0C8h+var_4C], 0
0x1801243b0  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801243b7  mov     [r11-80h], rax
0x1801243bb  lea     rax, [r11-50h]
0x1801243bf  mov     [r11-78h], rax
0x1801243c3  lea     rax, aMdmPolicyResul_101; "MDM_Policy_Result01_Browser02"
0x1801243ca  mov     [r11-70h], rax
0x1801243ce  lea     rcx, [r11-50h]
0x1801243d2  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801243d7  mov     eax, cs:dword_180380B68
0x1801243dd  cmp     eax, 5
0x1801243e0  jbe     short loc_180124453
0x1801243e2  mov     rdx, 200000000000h
0x1801243ec  lea     rcx, dword_180380B68
0x1801243f3  call    _tlgKeywordOn
0x1801243f8  test    al, al
0x1801243fa  jz      short loc_180124453
0x1801243fc  cmp     [rsp+0C8h+var_4C], 0
0x180124401  jz      short loc_180124435
0x180124403  cmp     [rsp+0C8h+var_38], 0
0x18012440b  jnz     short loc_18012442B
0x18012440d  cmp     [rsp+0C8h+var_34], 0
0x180124415  jnz     short loc_18012442B
0x180124417  cmp     [rsp+0C8h+var_30], 0
0x18012441f  jnz     short loc_18012442B
0x180124421  cmp     [rsp+0C8h+var_2C], 0
0x180124429  jz      short loc_180124435
0x18012442b  lea     r9, [rsp+0C8h+var_38]
0x180124433  jmp     short loc_180124438
0x180124435  xor     r9d, r9d
0x180124438  lea     r8, [rsp+0C8h+var_48]
0x180124440  lea     rdx, word_18035E3EE
0x180124447  lea     rcx, dword_180380B68
0x18012444e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180124453  cmp     byte ptr [rsi+48h], 0
0x180124457  jz      loc_1801254B5
0x18012445d  cmp     byte ptr [rsi+58h], 0
0x180124461  jz      loc_1801254B5
0x180124467  mov     r9, [rsi+40h]; unsigned __int16 *
0x18012446b  mov     r8, [rsi+50h]; unsigned __int16 *
0x18012446f  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x180124476  lea     rcx, [rsp+0C8h+var_80]; this
0x18012447b  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x180124480  nop
0x180124481  mov     [rsp+0C8h+var_88], 0
0x18012448a  lea     rax, [rsp+0C8h+var_88]
0x18012448f  mov     [rsp+0C8h+var_98], rax
0x180124494  mov     [rsp+0C8h+var_A0], 3
0x18012449c  mov     [rsp+0C8h+var_A8], 3Fh ; '?'
0x1801244a4  lea     r9, ?MDM_Policy_Result01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_Browser02_NodeList
0x1801244ab  mov     r8, [rsi+40h]
0x1801244af  mov     rdx, [rsi+50h]
0x1801244b3  mov     rcx, rdi
0x1801244b6  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801244bb  mov     edi, eax
0x1801244bd  test    eax, eax
0x1801244bf  jz      short loc_1801244C6
0x1801244c1  jmp     loc_1801254BA
0x1801244c6  lea     rax, [rsp+0C8h+var_88]
0x1801244cb  mov     [rsp+0C8h+var_60], rax
0x1801244d0  mov     r15d, 1
0x1801244d6  mov     [rsp+0C8h+var_58], r15b
0x1801244db  mov     r14, [rsp+0C8h+var_88]
0x1801244e0  test    r14, r14
0x1801244e3  jnz     short loc_1801244ED
0x1801244e5  mov     edi, r15d
0x1801244e8  jmp     loc_1801254BA
0x1801244ed  mov     r9d, 3Fh ; '?'; unsigned int
0x1801244f3  lea     r8, ?MDM_Policy_Result01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1801244fa  mov     rdx, rsi; struct _MI_Instance *
0x1801244fd  mov     rcx, r14; this
0x180124500  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x180124505  lea     r8, [rsi+60h]; void *
0x180124509  cmp     [r8+4], r15b
0x18012450d  jnz     short loc_180124542
0x18012450f  lea     rdx, aAllowaddressba; "AllowAddressBarDropdown"
0x180124516  mov     rcx, r14; this
0x180124519  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18012451e  mov     edi, eax
0x180124520  test    eax, eax
0x180124522  jz      short loc_180124542
0x180124524  mov     rcx, [rsp+0C8h+var_88]
0x180124529  test    rcx, rcx
0x18012452c  jz      short loc_18012453D
0x18012452e  mov     rax, [rcx]
0x180124531  mov     edx, r15d
0x180124534  mov     rax, [rax]
0x180124537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012453c  nop
0x18012453d  jmp     loc_1801254BA
0x180124542  lea     r8, [rsi+68h]; void *
0x180124546  cmp     [r8+4], r15b
0x18012454a  jnz     short loc_18012457F
0x18012454c  lea     rdx, aAllowautofill; "AllowAutofill"
0x180124553  mov     rcx, r14; this
0x180124556  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18012455b  mov     edi, eax
0x18012455d  test    eax, eax
0x18012455f  jz      short loc_18012457F
0x180124561  mov     rcx, [rsp+0C8h+var_88]
0x180124566  test    rcx, rcx
0x180124569  jz      short loc_18012457A
0x18012456b  mov     rax, [rcx]
0x18012456e  mov     edx, r15d
0x180124571  mov     rax, [rax]
0x180124574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180124579  nop
0x18012457a  jmp     loc_1801254BA
0x18012457f  lea     r8, [rsi+70h]; void *
0x180124583  cmp     [r8+4], r15b
0x180124587  jnz     short loc_1801245BC
0x180124589  lea     rdx, aAllowconfigura; "AllowConfigurationUpdateForBooksLibrary"
0x180124590  mov     rcx, r14; this
0x180124593  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180124598  mov     edi, eax
0x18012459a  test    eax, eax
0x18012459c  jz      short loc_1801245BC
0x18012459e  mov     rcx, [rsp+0C8h+var_88]
0x1801245a3  test    rcx, rcx
0x1801245a6  jz      short loc_1801245B7
0x1801245a8  mov     rax, [rcx]
0x1801245ab  mov     edx, r15d
0x1801245ae  mov     rax, [rax]
0x1801245b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801245b6  nop
0x1801245b7  jmp     loc_1801254BA
0x1801245bc  lea     r8, [rsi+78h]; void *
0x1801245c0  cmp     [r8+4], r15b
0x1801245c4  jnz     short loc_1801245F9
0x1801245c6  lea     rdx, aAllowcookies; "AllowCookies"
0x1801245cd  mov     rcx, r14; this
0x1801245d0  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801245d5  mov     edi, eax
0x1801245d7  test    eax, eax
0x1801245d9  jz      short loc_1801245F9
0x1801245db  mov     rcx, [rsp+0C8h+var_88]
0x1801245e0  test    rcx, rcx
0x1801245e3  jz      short loc_1801245F4
0x1801245e5  mov     rax, [rcx]
0x1801245e8  mov     edx, r15d
0x1801245eb  mov     rax, [rax]
0x1801245ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801245f3  nop
0x1801245f4  jmp     loc_1801254BA
0x1801245f9  lea     r8, [rsi+80h]; void *
0x180124600  cmp     [r8+4], r15b
0x180124604  jnz     short loc_180124639
0x180124606  lea     rdx, aAllowdeveloper; "AllowDeveloperTools"
0x18012460d  mov     rcx, r14; this
0x180124610  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180124615  mov     edi, eax
0x180124617  test    eax, eax
0x180124619  jz      short loc_180124639
0x18012461b  mov     rcx, [rsp+0C8h+var_88]
0x180124620  test    rcx, rcx
0x180124623  jz      short loc_180124634
0x180124625  mov     rax, [rcx]
0x180124628  mov     edx, r15d
0x18012462b  mov     rax, [rax]
0x18012462e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180124633  nop
0x180124634  jmp     loc_1801254BA
0x180124639  lea     r8, [rsi+88h]; void *
0x180124640  cmp     [r8+4], r15b
0x180124644  jnz     short loc_180124679
0x180124646  lea     rdx, aAllowdonottrac; "AllowDoNotTrack"
0x18012464d  mov     rcx, r14; this
0x180124650  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180124655  mov     edi, eax
0x180124657  test    eax, eax
0x180124659  jz      short loc_180124679
0x18012465b  mov     rcx, [rsp+0C8h+var_88]
0x180124660  test    rcx, rcx
0x180124663  jz      short loc_180124674
0x180124665  mov     rax, [rcx]
0x180124668  mov     edx, r15d
0x18012466b  mov     rax, [rax]
0x18012466e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180124673  nop
0x180124674  jmp     loc_1801254BA
0x180124679  lea     r8, [rsi+90h]; void *
0x180124680  cmp     [r8+4], r15b
0x180124684  jnz     short loc_1801246B9
0x180124686  lea     rdx, aAllowextension; "AllowExtensions"
0x18012468d  mov     rcx, r14; this
0x180124690  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180124695  mov     edi, eax
0x180124697  test    eax, eax
0x180124699  jz      short loc_1801246B9
0x18012469b  mov     rcx, [rsp+0C8h+var_88]
0x1801246a0  test    rcx, rcx
0x1801246a3  jz      short loc_1801246B4
0x1801246a5  mov     rax, [rcx]
0x1801246a8  mov     edx, r15d
0x1801246ab  mov     rax, [rax]
0x1801246ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801246b3  nop
0x1801246b4  jmp     loc_1801254BA
0x1801246b9  lea     r8, [rsi+98h]; void *
0x1801246c0  cmp     [r8+4], r15b
0x1801246c4  jnz     short loc_1801246F9
0x1801246c6  lea     rdx, aAllowflash; "AllowFlash"
0x1801246cd  mov     rcx, r14; this
0x1801246d0  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801246d5  mov     edi, eax
0x1801246d7  test    eax, eax
0x1801246d9  jz      short loc_1801246F9
0x1801246db  mov     rcx, [rsp+0C8h+var_88]
0x1801246e0  test    rcx, rcx
0x1801246e3  jz      short loc_1801246F4
0x1801246e5  mov     rax, [rcx]
0x1801246e8  mov     edx, r15d
0x1801246eb  mov     rax, [rax]
0x1801246ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801246f3  nop
0x1801246f4  jmp     loc_1801254BA
0x1801246f9  lea     r8, [rsi+0A0h]; void *
0x180124700  cmp     [r8+4], r15b
0x180124704  jnz     short loc_180124739
0x180124706  lea     rdx, aAllowflashclic; "AllowFlashClickToRun"
0x18012470d  mov     rcx, r14; this
0x180124710  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180124715  mov     edi, eax
0x180124717  test    eax, eax
0x180124719  jz      short loc_180124739
0x18012471b  mov     rcx, [rsp+0C8h+var_88]
0x180124720  test    rcx, rcx
0x180124723  jz      short loc_180124734
0x180124725  mov     rax, [rcx]
0x180124728  mov     edx, r15d
0x18012472b  mov     rax, [rax]
0x18012472e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180124733  nop
0x180124734  jmp     loc_1801254BA
0x180124739  lea     r8, [rsi+0A8h]; void *
0x180124740  cmp     [r8+4], r15b
0x180124744  jnz     short loc_180124779
0x180124746  lea     rdx, aAllowfullscree; "AllowFullScreenMode"
0x18012474d  mov     rcx, r14; this
0x180124750  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180124755  mov     edi, eax
0x180124757  test    eax, eax
0x180124759  jz      short loc_180124779
0x18012475b  mov     rcx, [rsp+0C8h+var_88]
0x180124760  test    rcx, rcx
0x180124763  jz      short loc_180124774
0x180124765  mov     rax, [rcx]
0x180124768  mov     edx, r15d
0x18012476b  mov     rax, [rax]
0x18012476e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180124773  nop
0x180124774  jmp     loc_1801254BA
0x180124779  lea     r8, [rsi+0B0h]; void *
0x180124780  cmp     [r8+4], r15b
0x180124784  jnz     short loc_1801247B9
0x180124786  lea     rdx, aAllowinprivate; "AllowInPrivate"
0x18012478d  mov     rcx, r14; this
0x180124790  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x180124795  mov     edi, eax
0x180124797  test    eax, eax
0x180124799  jz      short loc_1801247B9
0x18012479b  mov     rcx, [rsp+0C8h+var_88]
0x1801247a0  test    rcx, rcx
0x1801247a3  jz      short loc_1801247B4
0x1801247a5  mov     rax, [rcx]
0x1801247a8  mov     edx, r15d
0x1801247ab  mov     rax, [rax]
0x1801247ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801247b3  nop
0x1801247b4  jmp     loc_1801254BA
0x1801247b9  lea     r8, [rsi+0B8h]; void *
0x1801247c0  cmp     [r8+4], r15b
0x1801247c4  jnz     short loc_1801247F9
0x1801247c6  lea     rdx, aAllowmicrosoft_2; "AllowMicrosoftCompatibilityList"
0x1801247cd  mov     rcx, r14; this
0x1801247d0  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801247d5  mov     edi, eax
0x1801247d7  test    eax, eax
0x1801247d9  jz      short loc_1801247F9
0x1801247db  mov     rcx, [rsp+0C8h+var_88]
0x1801247e0  test    rcx, rcx
0x1801247e3  jz      short loc_1801247F4
0x1801247e5  mov     rax, [rcx]
0x1801247e8  mov     edx, r15d
0x1801247eb  mov     rax, [rax]
0x1801247ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801247f3  nop
0x1801247f4  jmp     loc_1801254BA
  ... truncated ...
```
