# MDM_Policy_User_Config01_Browser02_InvokeModifyInstance

- ea: `0x1801c793c`
- end: `0x1801c898f`
- name: `MDM_Policy_User_Config01_Browser02_InvokeModifyInstance`
- size: `4179`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801c89a0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x18000a280`
- `0x1801c793c`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x1801c7b4d`: `AllowConfigurationUpdateForBooksLibrary`
- `0x1801c7c4a`: `AllowExtensions`
- `0x1801c7d8a`: `AllowMicrosoftCompatibilityList`
- `0x1801c7f8a`: `AllowSideloadingOfExtensions`
- `0x1801c810a`: `ConfigureAdditionalSearchEngines`
- `0x1801c814a`: `ConfigureFavoritesBar`
- `0x1801c818a`: `ConfigureHomeButton`
- `0x1801c81ca`: `ConfigureKioskMode`
- `0x1801c820a`: `ConfigureKioskResetAfterIdleTimeout`
- `0x1801c824a`: `ConfigureOpenMicrosoftEdgeWith`
- `0x1801c828a`: `ConfigureTelemetryForMicrosoft365Analytics`
- `0x1801c838a`: `EnterpriseSiteListServiceUrl`
- `0x1801c844a`: `PreventAccessToAboutFlagsInMicrosoftEdge`
- `0x1801c85ca`: `PreventTurningOffRequiredExtensions`
- `0x1801c878a`: `ShowMessageWhenOpeningSitesInInternetExplorer`
- `0x1801c7987`: `MDM_Policy_User_Config01_Browser02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_User_Config01_Browser02_InvokeModifyInstance(__int64 a1, __int64 a2)
{
  _DWORD *v4; // r9
  wil *v5; // rcx
  unsigned int inserted; // edi
  WmiRequestHandler *v7; // r14
  const char *v9; // rax
  int v10; // eax
  WmiRequestHandler *v11; // [rsp+40h] [rbp-88h] BYREF
  _QWORD v12[3]; // [rsp+48h] [rbp-80h] BYREF
  const exception *v13[2]; // [rsp+60h] [rbp-68h] BYREF
  char v14; // [rsp+70h] [rbp-58h]
  int v15; // [rsp+78h] [rbp-50h] BYREF
  char v16; // [rsp+7Ch] [rbp-4Ch]
  _BYTE v17[16]; // [rsp+80h] [rbp-48h] BYREF
  _DWORD v18[4]; // [rsp+90h] [rbp-38h] BYREF

  v15 = 0;
  v16 = 0;
  v12[0] = &TelemetryEventWriter::`vftable';
  v12[1] = &v15;
  v12[2] = "MDM_Policy_User_Config01_Browser02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v15);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v16 && (v18[0] || v18[1] || v18[2] || v18[3]) )
      v4 = v18;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &word_180337D0E,
      v17,
      v4);
  }
  if ( *(_BYTE *)(a2 + 72) && *(_BYTE *)(a2 + 88) )
  {
    TelemetryEventWriter::WriteStart(
      (TelemetryEventWriter *)v12,
      "ModifyInstanceStart",
      *(const unsigned __int16 **)(a2 + 80),
      *(const unsigned __int16 **)(a2 + 64));
    try
    {
      v11 = 0;
      inserted = CreateRequestHandlerInstance(
                   a1,
                   *(wchar_t **)(a2 + 80),
                   *(const unsigned __int16 **)(a2 + 64),
                   (struct WmiNodeInfo *)&MDM_Policy_User_Config01_Browser02_NodeList,
                   0x39u,
                   3,
                   &v11);
      if ( !inserted )
      {
        v13[1] = (const exception *)&v11;
        v14 = 1;
        v7 = v11;
        if ( v11 )
        {
          WmiRequestHandler::SetRequestMIInstance(
            v11,
            (const struct _MI_Instance *)a2,
            (struct WmiNodeInfo *)&MDM_Policy_User_Config01_Browser02_NodeList,
            0x39u);
          if ( *(_BYTE *)(a2 + 100) == 1
            && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowAddressBarDropdown", (LONG *)(a2 + 96))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 108) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowAutofill", (LONG *)(a2 + 104))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 116) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowConfigurationUpdateForBooksLibrary",
                                  (LONG *)(a2 + 112))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 124) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowCookies", (LONG *)(a2 + 120))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 132) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowDeveloperTools", (LONG *)(a2 + 128))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 140) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowDoNotTrack", (LONG *)(a2 + 136))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 148) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowExtensions", (LONG *)(a2 + 144))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 156) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowFlash", (LONG *)(a2 + 152))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 164) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowFlashClickToRun", (LONG *)(a2 + 160))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 172) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowFullScreenMode", (LONG *)(a2 + 168))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 180) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowInPrivate", (LONG *)(a2 + 176))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 188) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowMicrosoftCompatibilityList",
                                  (LONG *)(a2 + 184))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 196) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowPasswordManager", (LONG *)(a2 + 192))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 204) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowPopups", (LONG *)(a2 + 200))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 212) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowPrelaunch", (LONG *)(a2 + 208))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 220) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowPrinting", (LONG *)(a2 + 216))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 228) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowSavingHistory", (LONG *)(a2 + 224))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 236) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowSearchEngineCustomization",
                                  (LONG *)(a2 + 232))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 244) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowSearchSuggestionsinAddressBar",
                                  (LONG *)(a2 + 240))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 252) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowSideloadingOfExtensions",
                                  (LONG *)(a2 + 248))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 260) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowSmartScreen", (LONG *)(a2 + 256))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 268) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowTabPreloading", (LONG *)(a2 + 264))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 276) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowWebContentOnNewTabPage",
                                  (LONG *)(a2 + 272))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 284) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AlwaysEnableBooksLibrary",
                                  (LONG *)(a2 + 280))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 292) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ClearBrowsingDataOnExit",
                                  (LONG *)(a2 + 288))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 304) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureAdditionalSearchEngines",
                                  (LONG *)(a2 + 296))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 316) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureFavoritesBar",
                                  (LONG *)(a2 + 312))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 324) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ConfigureHomeButton", (LONG *)(a2 + 320))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 332) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ConfigureKioskMode", (LONG *)(a2 + 328))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 340) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureKioskResetAfterIdleTimeout",
                                  (LONG *)(a2 + 336))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 348) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureOpenMicrosoftEdgeWith",
                                  (LONG *)(a2 + 344))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 356) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureTelemetryForMicrosoft365Analytics",
                                  (LONG *)(a2 + 352))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 364) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DisableLockdownOfStartPages",
                                  (LONG *)(a2 + 360))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 372) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"EnableExtendedBooksTelemetry",
                                  (LONG *)(a2 + 368))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 384) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"EnterpriseModeSiteList",
                                  (LONG *)(a2 + 376))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 400) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"EnterpriseSiteListServiceUrl",
                                  (LONG *)(a2 + 392))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 416) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"HomePages", (LONG *)(a2 + 408))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 428) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"LockdownFavorites", (LONG *)(a2 + 424))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 436) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PreventAccessToAboutFlagsInMicrosoftEdge",
                                  (LONG *)(a2 + 432))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 444) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PreventCertErrorOverrides",
                                  (LONG *)(a2 + 440))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 452) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"PreventFirstRunPage", (LONG *)(a2 + 448))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 460) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PreventLiveTileDataCollection",
                                  (LONG *)(a2 + 456))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 468) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PreventSmartScreenPromptOverride",
                                  (LONG *)(a2 + 464))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 476) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PreventSmartScreenPromptOverrideForFiles",
                                  (LONG *)(a2 + 472))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 488) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PreventTurningOffRequiredExtensions",
                                  (LONG *)(a2 + 480))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 500) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PreventUsingLocalHostIPAddressForWebRTC",
                                  (LONG *)(a2 + 496))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 512) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ProvisionFavorites", (LONG *)(a2 + 504))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 524) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SendIntranetTraffictoInternetExplorer",
                                  (LONG *)(a2 + 520))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 536) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SetDefaultSearchEngine",
                                  (LONG *)(a2 + 528))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 552) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"SetHomeButtonURL", (LONG *)(a2 + 544))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 568) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"SetNewTabPageURL", (LONG *)(a2 + 560))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 580) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ShowMessageWhenOpeningSitesInInternetExplorer",
                                  (LONG *)(a2 + 576))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 588) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SyncFavoritesBetweenIEAndMicrosoftEdge",
                                  (LONG *)(a2 + 584))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 596) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"UnlockHomeButton", (LONG *)(a2 + 592))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 604) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"UseSharedFolderForBooks",
                                  (LONG *)(a2 + 600))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else
          {
            inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v7 + 16LL))(v7);
            if ( inserted )
            {
              v5 = v11;
              if ( v11 )
                (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
            }
            else
            {
              inserted = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v7 + 8LL))(v7);
              v5 = v11;
              if ( inserted )
              {
                if ( v11 )
                  (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
              }
              else if ( v11 )
              {
                (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
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
    catch ( const exception *v13 )
    {
      v9 = (const char *)(*(__int64 (__fastcall **)(const exception *))(*(_QWORD *)v13[0] + 8LL))(v13[0]);
      TelemetryEventWriter::WriteStdException((TelemetryEventWriter *)v12, v9);
      LODWORD(v11) = 1;
      inserted = 1;
    }
    catch ( ... )
    {
      v10 = wil::ResultFromCaughtException(v5);
      TelemetryEventWriter::WriteDefaultExceptionHr((TelemetryEventWriter *)v12, v10);
      LODWORD(v11) = 1;
      inserted = 1;
    }
  }
  else
  {
    inserted = 4;
  }
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v12, "ModifyInstanceEnd", inserted);
  v15 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_18033A0B3,
      v17,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v15);
  return inserted;
}

```

## disassembly

```asm
0x1801c793c  mov     r11, rsp
0x1801c793f  mov     [r11+18h], rsi
0x1801c7943  push    rdi
0x1801c7944  push    r14
0x1801c7946  push    r15
0x1801c7948  sub     rsp, 0B0h
0x1801c794f  mov     rax, cs:__security_cookie
0x1801c7956  xor     rax, rsp
0x1801c7959  mov     [rsp+0C8h+var_28], rax
0x1801c7961  mov     rsi, rdx
0x1801c7964  mov     rdi, rcx
0x1801c7967  mov     [rsp+0C8h+var_50], 0
0x1801c796f  mov     [rsp+0C8h+var_4C], 0
0x1801c7974  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801c797b  mov     [r11-80h], rax
0x1801c797f  lea     rax, [r11-50h]
0x1801c7983  mov     [r11-78h], rax
0x1801c7987  lea     rax, aMdmPolicyUserC_19; "MDM_Policy_User_Config01_Browser02"
0x1801c798e  mov     [r11-70h], rax
0x1801c7992  lea     rcx, [r11-50h]
0x1801c7996  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801c799b  mov     eax, cs:dword_180380B68
0x1801c79a1  cmp     eax, 5
0x1801c79a4  jbe     short loc_1801C7A17
0x1801c79a6  mov     rdx, 200000000000h
0x1801c79b0  lea     rcx, dword_180380B68
0x1801c79b7  call    _tlgKeywordOn
0x1801c79bc  test    al, al
0x1801c79be  jz      short loc_1801C7A17
0x1801c79c0  cmp     [rsp+0C8h+var_4C], 0
0x1801c79c5  jz      short loc_1801C79F9
0x1801c79c7  cmp     [rsp+0C8h+var_38], 0
0x1801c79cf  jnz     short loc_1801C79EF
0x1801c79d1  cmp     [rsp+0C8h+var_34], 0
0x1801c79d9  jnz     short loc_1801C79EF
0x1801c79db  cmp     [rsp+0C8h+var_30], 0
0x1801c79e3  jnz     short loc_1801C79EF
0x1801c79e5  cmp     [rsp+0C8h+var_2C], 0
0x1801c79ed  jz      short loc_1801C79F9
0x1801c79ef  lea     r9, [rsp+0C8h+var_38]
0x1801c79f7  jmp     short loc_1801C79FC
0x1801c79f9  xor     r9d, r9d
0x1801c79fc  lea     r8, [rsp+0C8h+var_48]
0x1801c7a04  lea     rdx, word_180337D0E
0x1801c7a0b  lea     rcx, dword_180380B68
0x1801c7a12  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801c7a17  cmp     byte ptr [rsi+48h], 0
0x1801c7a1b  jz      loc_1801C88F9
0x1801c7a21  cmp     byte ptr [rsi+58h], 0
0x1801c7a25  jz      loc_1801C88F9
0x1801c7a2b  mov     r9, [rsi+40h]; unsigned __int16 *
0x1801c7a2f  mov     r8, [rsi+50h]; unsigned __int16 *
0x1801c7a33  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x1801c7a3a  lea     rcx, [rsp+0C8h+var_80]; this
0x1801c7a3f  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1801c7a44  nop
0x1801c7a45  mov     [rsp+0C8h+var_88], 0
0x1801c7a4e  lea     rax, [rsp+0C8h+var_88]
0x1801c7a53  mov     [rsp+0C8h+var_98], rax
0x1801c7a58  mov     [rsp+0C8h+var_A0], 3
0x1801c7a60  mov     [rsp+0C8h+var_A8], 39h ; '9'
0x1801c7a68  lea     r9, ?MDM_Policy_User_Config01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_User_Config01_Browser02_NodeList
0x1801c7a6f  mov     r8, [rsi+40h]
0x1801c7a73  mov     rdx, [rsi+50h]
0x1801c7a77  mov     rcx, rdi
0x1801c7a7a  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801c7a7f  mov     edi, eax
0x1801c7a81  test    eax, eax
0x1801c7a83  jz      short loc_1801C7A8A
0x1801c7a85  jmp     loc_1801C88FE
0x1801c7a8a  lea     rax, [rsp+0C8h+var_88]
0x1801c7a8f  mov     [rsp+0C8h+var_60], rax
0x1801c7a94  mov     r15d, 1
0x1801c7a9a  mov     [rsp+0C8h+var_58], r15b
0x1801c7a9f  mov     r14, [rsp+0C8h+var_88]
0x1801c7aa4  test    r14, r14
0x1801c7aa7  jnz     short loc_1801C7AB1
0x1801c7aa9  mov     edi, r15d
0x1801c7aac  jmp     loc_1801C88FE
0x1801c7ab1  mov     r9d, 39h ; '9'; unsigned int
0x1801c7ab7  lea     r8, ?MDM_Policy_User_Config01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1801c7abe  mov     rdx, rsi; struct _MI_Instance *
0x1801c7ac1  mov     rcx, r14; this
0x1801c7ac4  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1801c7ac9  lea     r8, [rsi+60h]; void *
0x1801c7acd  cmp     [r8+4], r15b
0x1801c7ad1  jnz     short loc_1801C7B06
0x1801c7ad3  lea     rdx, aAllowaddressba; "AllowAddressBarDropdown"
0x1801c7ada  mov     rcx, r14; this
0x1801c7add  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c7ae2  mov     edi, eax
0x1801c7ae4  test    eax, eax
0x1801c7ae6  jz      short loc_1801C7B06
0x1801c7ae8  mov     rcx, [rsp+0C8h+var_88]
0x1801c7aed  test    rcx, rcx
0x1801c7af0  jz      short loc_1801C7B01
0x1801c7af2  mov     rax, [rcx]
0x1801c7af5  mov     edx, r15d
0x1801c7af8  mov     rax, [rax]
0x1801c7afb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c7b00  nop
0x1801c7b01  jmp     loc_1801C88FE
0x1801c7b06  lea     r8, [rsi+68h]; void *
0x1801c7b0a  cmp     [r8+4], r15b
0x1801c7b0e  jnz     short loc_1801C7B43
0x1801c7b10  lea     rdx, aAllowautofill; "AllowAutofill"
0x1801c7b17  mov     rcx, r14; this
0x1801c7b1a  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c7b1f  mov     edi, eax
0x1801c7b21  test    eax, eax
0x1801c7b23  jz      short loc_1801C7B43
0x1801c7b25  mov     rcx, [rsp+0C8h+var_88]
0x1801c7b2a  test    rcx, rcx
0x1801c7b2d  jz      short loc_1801C7B3E
0x1801c7b2f  mov     rax, [rcx]
0x1801c7b32  mov     edx, r15d
0x1801c7b35  mov     rax, [rax]
0x1801c7b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c7b3d  nop
0x1801c7b3e  jmp     loc_1801C88FE
0x1801c7b43  lea     r8, [rsi+70h]; void *
0x1801c7b47  cmp     [r8+4], r15b
0x1801c7b4b  jnz     short loc_1801C7B80
0x1801c7b4d  lea     rdx, aAllowconfigura; "AllowConfigurationUpdateForBooksLibrary"
0x1801c7b54  mov     rcx, r14; this
0x1801c7b57  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c7b5c  mov     edi, eax
0x1801c7b5e  test    eax, eax
0x1801c7b60  jz      short loc_1801C7B80
0x1801c7b62  mov     rcx, [rsp+0C8h+var_88]
0x1801c7b67  test    rcx, rcx
0x1801c7b6a  jz      short loc_1801C7B7B
0x1801c7b6c  mov     rax, [rcx]
0x1801c7b6f  mov     edx, r15d
0x1801c7b72  mov     rax, [rax]
0x1801c7b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c7b7a  nop
0x1801c7b7b  jmp     loc_1801C88FE
0x1801c7b80  lea     r8, [rsi+78h]; void *
0x1801c7b84  cmp     [r8+4], r15b
0x1801c7b88  jnz     short loc_1801C7BBD
0x1801c7b8a  lea     rdx, aAllowcookies; "AllowCookies"
0x1801c7b91  mov     rcx, r14; this
0x1801c7b94  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c7b99  mov     edi, eax
0x1801c7b9b  test    eax, eax
0x1801c7b9d  jz      short loc_1801C7BBD
0x1801c7b9f  mov     rcx, [rsp+0C8h+var_88]
0x1801c7ba4  test    rcx, rcx
0x1801c7ba7  jz      short loc_1801C7BB8
0x1801c7ba9  mov     rax, [rcx]
0x1801c7bac  mov     edx, r15d
0x1801c7baf  mov     rax, [rax]
0x1801c7bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c7bb7  nop
0x1801c7bb8  jmp     loc_1801C88FE
0x1801c7bbd  lea     r8, [rsi+80h]; void *
0x1801c7bc4  cmp     [r8+4], r15b
0x1801c7bc8  jnz     short loc_1801C7BFD
0x1801c7bca  lea     rdx, aAllowdeveloper; "AllowDeveloperTools"
0x1801c7bd1  mov     rcx, r14; this
0x1801c7bd4  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c7bd9  mov     edi, eax
0x1801c7bdb  test    eax, eax
0x1801c7bdd  jz      short loc_1801C7BFD
0x1801c7bdf  mov     rcx, [rsp+0C8h+var_88]
0x1801c7be4  test    rcx, rcx
0x1801c7be7  jz      short loc_1801C7BF8
0x1801c7be9  mov     rax, [rcx]
0x1801c7bec  mov     edx, r15d
0x1801c7bef  mov     rax, [rax]
0x1801c7bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c7bf7  nop
0x1801c7bf8  jmp     loc_1801C88FE
0x1801c7bfd  lea     r8, [rsi+88h]; void *
0x1801c7c04  cmp     [r8+4], r15b
0x1801c7c08  jnz     short loc_1801C7C3D
0x1801c7c0a  lea     rdx, aAllowdonottrac; "AllowDoNotTrack"
0x1801c7c11  mov     rcx, r14; this
0x1801c7c14  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c7c19  mov     edi, eax
0x1801c7c1b  test    eax, eax
0x1801c7c1d  jz      short loc_1801C7C3D
0x1801c7c1f  mov     rcx, [rsp+0C8h+var_88]
0x1801c7c24  test    rcx, rcx
0x1801c7c27  jz      short loc_1801C7C38
0x1801c7c29  mov     rax, [rcx]
0x1801c7c2c  mov     edx, r15d
0x1801c7c2f  mov     rax, [rax]
0x1801c7c32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c7c37  nop
0x1801c7c38  jmp     loc_1801C88FE
0x1801c7c3d  lea     r8, [rsi+90h]; void *
0x1801c7c44  cmp     [r8+4], r15b
0x1801c7c48  jnz     short loc_1801C7C7D
0x1801c7c4a  lea     rdx, aAllowextension; "AllowExtensions"
0x1801c7c51  mov     rcx, r14; this
0x1801c7c54  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c7c59  mov     edi, eax
0x1801c7c5b  test    eax, eax
0x1801c7c5d  jz      short loc_1801C7C7D
0x1801c7c5f  mov     rcx, [rsp+0C8h+var_88]
0x1801c7c64  test    rcx, rcx
0x1801c7c67  jz      short loc_1801C7C78
0x1801c7c69  mov     rax, [rcx]
0x1801c7c6c  mov     edx, r15d
0x1801c7c6f  mov     rax, [rax]
0x1801c7c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c7c77  nop
0x1801c7c78  jmp     loc_1801C88FE
0x1801c7c7d  lea     r8, [rsi+98h]; void *
0x1801c7c84  cmp     [r8+4], r15b
0x1801c7c88  jnz     short loc_1801C7CBD
0x1801c7c8a  lea     rdx, aAllowflash; "AllowFlash"
0x1801c7c91  mov     rcx, r14; this
0x1801c7c94  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c7c99  mov     edi, eax
0x1801c7c9b  test    eax, eax
0x1801c7c9d  jz      short loc_1801C7CBD
0x1801c7c9f  mov     rcx, [rsp+0C8h+var_88]
0x1801c7ca4  test    rcx, rcx
0x1801c7ca7  jz      short loc_1801C7CB8
0x1801c7ca9  mov     rax, [rcx]
0x1801c7cac  mov     edx, r15d
0x1801c7caf  mov     rax, [rax]
0x1801c7cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c7cb7  nop
0x1801c7cb8  jmp     loc_1801C88FE
0x1801c7cbd  lea     r8, [rsi+0A0h]; void *
0x1801c7cc4  cmp     [r8+4], r15b
0x1801c7cc8  jnz     short loc_1801C7CFD
0x1801c7cca  lea     rdx, aAllowflashclic; "AllowFlashClickToRun"
0x1801c7cd1  mov     rcx, r14; this
0x1801c7cd4  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c7cd9  mov     edi, eax
0x1801c7cdb  test    eax, eax
0x1801c7cdd  jz      short loc_1801C7CFD
0x1801c7cdf  mov     rcx, [rsp+0C8h+var_88]
0x1801c7ce4  test    rcx, rcx
0x1801c7ce7  jz      short loc_1801C7CF8
0x1801c7ce9  mov     rax, [rcx]
0x1801c7cec  mov     edx, r15d
0x1801c7cef  mov     rax, [rax]
0x1801c7cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c7cf7  nop
0x1801c7cf8  jmp     loc_1801C88FE
0x1801c7cfd  lea     r8, [rsi+0A8h]; void *
0x1801c7d04  cmp     [r8+4], r15b
0x1801c7d08  jnz     short loc_1801C7D3D
0x1801c7d0a  lea     rdx, aAllowfullscree; "AllowFullScreenMode"
0x1801c7d11  mov     rcx, r14; this
0x1801c7d14  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c7d19  mov     edi, eax
0x1801c7d1b  test    eax, eax
0x1801c7d1d  jz      short loc_1801C7D3D
0x1801c7d1f  mov     rcx, [rsp+0C8h+var_88]
0x1801c7d24  test    rcx, rcx
0x1801c7d27  jz      short loc_1801C7D38
0x1801c7d29  mov     rax, [rcx]
0x1801c7d2c  mov     edx, r15d
0x1801c7d2f  mov     rax, [rax]
0x1801c7d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c7d37  nop
0x1801c7d38  jmp     loc_1801C88FE
0x1801c7d3d  lea     r8, [rsi+0B0h]; void *
0x1801c7d44  cmp     [r8+4], r15b
0x1801c7d48  jnz     short loc_1801C7D7D
0x1801c7d4a  lea     rdx, aAllowinprivate; "AllowInPrivate"
0x1801c7d51  mov     rcx, r14; this
0x1801c7d54  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c7d59  mov     edi, eax
0x1801c7d5b  test    eax, eax
0x1801c7d5d  jz      short loc_1801C7D7D
0x1801c7d5f  mov     rcx, [rsp+0C8h+var_88]
0x1801c7d64  test    rcx, rcx
0x1801c7d67  jz      short loc_1801C7D78
0x1801c7d69  mov     rax, [rcx]
0x1801c7d6c  mov     edx, r15d
0x1801c7d6f  mov     rax, [rax]
0x1801c7d72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c7d77  nop
0x1801c7d78  jmp     loc_1801C88FE
0x1801c7d7d  lea     r8, [rsi+0B8h]; void *
0x1801c7d84  cmp     [r8+4], r15b
0x1801c7d88  jnz     short loc_1801C7DBD
0x1801c7d8a  lea     rdx, aAllowmicrosoft_2; "AllowMicrosoftCompatibilityList"
0x1801c7d91  mov     rcx, r14; this
0x1801c7d94  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c7d99  mov     edi, eax
0x1801c7d9b  test    eax, eax
0x1801c7d9d  jz      short loc_1801C7DBD
0x1801c7d9f  mov     rcx, [rsp+0C8h+var_88]
0x1801c7da4  test    rcx, rcx
0x1801c7da7  jz      short loc_1801C7DB8
0x1801c7da9  mov     rax, [rcx]
0x1801c7dac  mov     edx, r15d
0x1801c7daf  mov     rax, [rax]
0x1801c7db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c7db7  nop
0x1801c7db8  jmp     loc_1801C88FE
  ... truncated ...
```
