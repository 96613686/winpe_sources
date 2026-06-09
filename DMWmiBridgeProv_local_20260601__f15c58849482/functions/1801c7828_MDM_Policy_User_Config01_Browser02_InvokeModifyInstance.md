# MDM_Policy_User_Config01_Browser02_InvokeModifyInstance

- ea: `0x1801c7828`
- end: `0x1801c887c`
- name: `MDM_Policy_User_Config01_Browser02_InvokeModifyInstance`
- size: `4180`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801c8890`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x18000a768`
- `0x1801c7828`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x1801c7a39`: `AllowConfigurationUpdateForBooksLibrary`
- `0x1801c7b36`: `AllowExtensions`
- `0x1801c7c76`: `AllowMicrosoftCompatibilityList`
- `0x1801c7e76`: `AllowSideloadingOfExtensions`
- `0x1801c7ff6`: `ConfigureAdditionalSearchEngines`
- `0x1801c8036`: `ConfigureFavoritesBar`
- `0x1801c8076`: `ConfigureHomeButton`
- `0x1801c80b6`: `ConfigureKioskMode`
- `0x1801c80f6`: `ConfigureKioskResetAfterIdleTimeout`
- `0x1801c8136`: `ConfigureOpenMicrosoftEdgeWith`
- `0x1801c8176`: `ConfigureTelemetryForMicrosoft365Analytics`
- `0x1801c8276`: `EnterpriseSiteListServiceUrl`
- `0x1801c8336`: `PreventAccessToAboutFlagsInMicrosoftEdge`
- `0x1801c84b6`: `PreventTurningOffRequiredExtensions`
- `0x1801c8676`: `ShowMessageWhenOpeningSitesInInternetExplorer`
- `0x1801c7873`: `MDM_Policy_User_Config01_Browser02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_User_Config01_Browser02_InvokeModifyInstance(__int64 a1, __int64 a2)
{
  _DWORD *v4; // r9
  wil *v5; // rcx
  enum _MI_Result inserted; // edi
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
      inserted = (unsigned int)CreateRequestHandlerInstance(
                                 a1,
                                 *(_QWORD *)(a2 + 80),
                                 *(_QWORD *)(a2 + 64),
                                 &MDM_Policy_User_Config01_Browser02_NodeList,
                                 57,
                                 3,
                                 &v11);
      if ( inserted == MI_RESULT_OK )
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
            && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowAddressBarDropdown", (void *)(a2 + 96))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 108) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowAutofill", (void *)(a2 + 104))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 116) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowConfigurationUpdateForBooksLibrary",
                                  (void *)(a2 + 112))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 124) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowCookies", (void *)(a2 + 120))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 132) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowDeveloperTools", (void *)(a2 + 128))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 140) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowDoNotTrack", (void *)(a2 + 136))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 148) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowExtensions", (void *)(a2 + 144))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 156) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowFlash", (void *)(a2 + 152))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 164) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowFlashClickToRun", (void *)(a2 + 160))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 172) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowFullScreenMode", (void *)(a2 + 168))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 180) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowInPrivate", (void *)(a2 + 176))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 188) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowMicrosoftCompatibilityList",
                                  (void *)(a2 + 184))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 196) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowPasswordManager", (void *)(a2 + 192))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 204) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowPopups", (void *)(a2 + 200))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 212) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowPrelaunch", (void *)(a2 + 208))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 220) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowPrinting", (void *)(a2 + 216))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 228) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowSavingHistory", (void *)(a2 + 224))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 236) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowSearchEngineCustomization",
                                  (void *)(a2 + 232))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 244) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowSearchSuggestionsinAddressBar",
                                  (void *)(a2 + 240))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 252) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowSideloadingOfExtensions",
                                  (void *)(a2 + 248))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 260) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowSmartScreen", (void *)(a2 + 256))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 268) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"AllowTabPreloading", (void *)(a2 + 264))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 276) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AllowWebContentOnNewTabPage",
                                  (void *)(a2 + 272))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 284) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"AlwaysEnableBooksLibrary",
                                  (void *)(a2 + 280))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 292) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ClearBrowsingDataOnExit",
                                  (void *)(a2 + 288))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 304) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureAdditionalSearchEngines",
                                  (void *)(a2 + 296))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 316) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureFavoritesBar",
                                  (void *)(a2 + 312))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 324) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ConfigureHomeButton", (void *)(a2 + 320))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 332) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ConfigureKioskMode", (void *)(a2 + 328))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 340) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureKioskResetAfterIdleTimeout",
                                  (void *)(a2 + 336))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 348) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureOpenMicrosoftEdgeWith",
                                  (void *)(a2 + 344))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 356) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ConfigureTelemetryForMicrosoft365Analytics",
                                  (void *)(a2 + 352))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 364) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DisableLockdownOfStartPages",
                                  (void *)(a2 + 360))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 372) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"EnableExtendedBooksTelemetry",
                                  (void *)(a2 + 368))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 384) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"EnterpriseModeSiteList",
                                  (void *)(a2 + 376))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 400) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"EnterpriseSiteListServiceUrl",
                                  (void *)(a2 + 392))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 416) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"HomePages", (void *)(a2 + 408))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 428) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"LockdownFavorites", (void *)(a2 + 424))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 436) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PreventAccessToAboutFlagsInMicrosoftEdge",
                                  (void *)(a2 + 432))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 444) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PreventCertErrorOverrides",
                                  (void *)(a2 + 440))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 452) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"PreventFirstRunPage", (void *)(a2 + 448))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 460) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PreventLiveTileDataCollection",
                                  (void *)(a2 + 456))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 468) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PreventSmartScreenPromptOverride",
                                  (void *)(a2 + 464))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 476) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PreventSmartScreenPromptOverrideForFiles",
                                  (void *)(a2 + 472))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 488) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PreventTurningOffRequiredExtensions",
                                  (void *)(a2 + 480))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 500) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PreventUsingLocalHostIPAddressForWebRTC",
                                  (void *)(a2 + 496))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 512) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ProvisionFavorites", (void *)(a2 + 504))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 524) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SendIntranetTraffictoInternetExplorer",
                                  (void *)(a2 + 520))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 536) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SetDefaultSearchEngine",
                                  (void *)(a2 + 528))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 552) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"SetHomeButtonURL", (void *)(a2 + 544))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 568) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"SetNewTabPageURL", (void *)(a2 + 560))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 580) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ShowMessageWhenOpeningSitesInInternetExplorer",
                                  (void *)(a2 + 576))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 588) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SyncFavoritesBetweenIEAndMicrosoftEdge",
                                  (void *)(a2 + 584))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 596) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"UnlockHomeButton", (void *)(a2 + 592))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 604) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"UseSharedFolderForBooks",
                                  (void *)(a2 + 600))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else
          {
            inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v7 + 16LL))(v7);
            if ( inserted )
            {
              v5 = v11;
              if ( v11 )
                (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
            }
            else
            {
              inserted = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v7 + 8LL))(v7);
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
          inserted = MI_RESULT_FAILED;
        }
      }
    }
    catch ( const exception *v13 )
    {
      v9 = (const char *)(*(__int64 (__fastcall **)(const exception *))(*(_QWORD *)v13[0] + 8LL))(v13[0]);
      TelemetryEventWriter::WriteStdException((TelemetryEventWriter *)v12, v9);
      LODWORD(v11) = 1;
      inserted = MI_RESULT_FAILED;
    }
    catch ( ... )
    {
      v10 = wil::ResultFromCaughtException(v5);
      TelemetryEventWriter::WriteDefaultExceptionHr((TelemetryEventWriter *)v12, v10);
      LODWORD(v11) = 1;
      inserted = MI_RESULT_FAILED;
    }
  }
  else
  {
    inserted = MI_RESULT_INVALID_PARAMETER;
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
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1801c7828  mov     r11, rsp
0x1801c782b  mov     [r11+18h], rsi
0x1801c782f  push    rdi
0x1801c7830  push    r14
0x1801c7832  push    r15
0x1801c7834  sub     rsp, 0B0h
0x1801c783b  mov     rax, cs:__security_cookie
0x1801c7842  xor     rax, rsp
0x1801c7845  mov     [rsp+0C8h+var_28], rax
0x1801c784d  mov     rsi, rdx
0x1801c7850  mov     rdi, rcx
0x1801c7853  mov     [rsp+0C8h+var_50], 0
0x1801c785b  mov     [rsp+0C8h+var_4C], 0
0x1801c7860  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801c7867  mov     [r11-80h], rax
0x1801c786b  lea     rax, [r11-50h]
0x1801c786f  mov     [r11-78h], rax
0x1801c7873  lea     rax, aMdmPolicyUserC_19; "MDM_Policy_User_Config01_Browser02"
0x1801c787a  mov     [r11-70h], rax
0x1801c787e  lea     rcx, [r11-50h]
0x1801c7882  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801c7887  mov     eax, cs:dword_180380B68
0x1801c788d  cmp     eax, 5
0x1801c7890  jbe     short loc_1801C7903
0x1801c7892  mov     rdx, 200000000000h
0x1801c789c  lea     rcx, dword_180380B68
0x1801c78a3  call    _tlgKeywordOn
0x1801c78a8  test    al, al
0x1801c78aa  jz      short loc_1801C7903
0x1801c78ac  cmp     [rsp+0C8h+var_4C], 0
0x1801c78b1  jz      short loc_1801C78E5
0x1801c78b3  cmp     [rsp+0C8h+var_38], 0
0x1801c78bb  jnz     short loc_1801C78DB
0x1801c78bd  cmp     [rsp+0C8h+var_34], 0
0x1801c78c5  jnz     short loc_1801C78DB
0x1801c78c7  cmp     [rsp+0C8h+var_30], 0
0x1801c78cf  jnz     short loc_1801C78DB
0x1801c78d1  cmp     [rsp+0C8h+var_2C], 0
0x1801c78d9  jz      short loc_1801C78E5
0x1801c78db  lea     r9, [rsp+0C8h+var_38]
0x1801c78e3  jmp     short loc_1801C78E8
0x1801c78e5  xor     r9d, r9d
0x1801c78e8  lea     r8, [rsp+0C8h+var_48]
0x1801c78f0  lea     rdx, word_180337D0E
0x1801c78f7  lea     rcx, dword_180380B68
0x1801c78fe  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801c7903  cmp     byte ptr [rsi+48h], 0
0x1801c7907  jz      loc_1801C87E5
0x1801c790d  cmp     byte ptr [rsi+58h], 0
0x1801c7911  jz      loc_1801C87E5
0x1801c7917  mov     r9, [rsi+40h]; unsigned __int16 *
0x1801c791b  mov     r8, [rsi+50h]; unsigned __int16 *
0x1801c791f  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x1801c7926  lea     rcx, [rsp+0C8h+var_80]; this
0x1801c792b  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1801c7930  nop
0x1801c7931  mov     [rsp+0C8h+var_88], 0
0x1801c793a  lea     rax, [rsp+0C8h+var_88]
0x1801c793f  mov     [rsp+0C8h+var_98], rax
0x1801c7944  mov     [rsp+0C8h+var_A0], 3
0x1801c794c  mov     [rsp+0C8h+var_A8], 39h ; '9'
0x1801c7954  lea     r9, ?MDM_Policy_User_Config01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_User_Config01_Browser02_NodeList
0x1801c795b  mov     r8, [rsi+40h]
0x1801c795f  mov     rdx, [rsi+50h]
0x1801c7963  mov     rcx, rdi
0x1801c7966  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801c796b  mov     edi, eax
0x1801c796d  test    eax, eax
0x1801c796f  jz      short loc_1801C7976
0x1801c7971  jmp     loc_1801C87EA
0x1801c7976  lea     rax, [rsp+0C8h+var_88]
0x1801c797b  mov     [rsp+0C8h+var_60], rax
0x1801c7980  mov     r15d, 1
0x1801c7986  mov     [rsp+0C8h+var_58], r15b
0x1801c798b  mov     r14, [rsp+0C8h+var_88]
0x1801c7990  test    r14, r14
0x1801c7993  jnz     short loc_1801C799D
0x1801c7995  mov     edi, r15d
0x1801c7998  jmp     loc_1801C87EA
0x1801c799d  mov     r9d, 39h ; '9'; unsigned int
0x1801c79a3  lea     r8, ?MDM_Policy_User_Config01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1801c79aa  mov     rdx, rsi; struct _MI_Instance *
0x1801c79ad  mov     rcx, r14; this
0x1801c79b0  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1801c79b5  lea     r8, [rsi+60h]; void *
0x1801c79b9  cmp     [r8+4], r15b
0x1801c79bd  jnz     short loc_1801C79F2
0x1801c79bf  lea     rdx, aAllowaddressba; "AllowAddressBarDropdown"
0x1801c79c6  mov     rcx, r14; this
0x1801c79c9  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c79ce  mov     edi, eax
0x1801c79d0  test    eax, eax
0x1801c79d2  jz      short loc_1801C79F2
0x1801c79d4  mov     rcx, [rsp+0C8h+var_88]
0x1801c79d9  test    rcx, rcx
0x1801c79dc  jz      short loc_1801C79ED
0x1801c79de  mov     rax, [rcx]
0x1801c79e1  mov     edx, r15d
0x1801c79e4  mov     rax, [rax]
0x1801c79e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c79ec  nop
0x1801c79ed  jmp     loc_1801C87EA
0x1801c79f2  lea     r8, [rsi+68h]; void *
0x1801c79f6  cmp     [r8+4], r15b
0x1801c79fa  jnz     short loc_1801C7A2F
0x1801c79fc  lea     rdx, aAllowautofill; "AllowAutofill"
0x1801c7a03  mov     rcx, r14; this
0x1801c7a06  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c7a0b  mov     edi, eax
0x1801c7a0d  test    eax, eax
0x1801c7a0f  jz      short loc_1801C7A2F
0x1801c7a11  mov     rcx, [rsp+0C8h+var_88]
0x1801c7a16  test    rcx, rcx
0x1801c7a19  jz      short loc_1801C7A2A
0x1801c7a1b  mov     rax, [rcx]
0x1801c7a1e  mov     edx, r15d
0x1801c7a21  mov     rax, [rax]
0x1801c7a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c7a29  nop
0x1801c7a2a  jmp     loc_1801C87EA
0x1801c7a2f  lea     r8, [rsi+70h]; void *
0x1801c7a33  cmp     [r8+4], r15b
0x1801c7a37  jnz     short loc_1801C7A6C
0x1801c7a39  lea     rdx, aAllowconfigura; "AllowConfigurationUpdateForBooksLibrary"
0x1801c7a40  mov     rcx, r14; this
0x1801c7a43  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c7a48  mov     edi, eax
0x1801c7a4a  test    eax, eax
0x1801c7a4c  jz      short loc_1801C7A6C
0x1801c7a4e  mov     rcx, [rsp+0C8h+var_88]
0x1801c7a53  test    rcx, rcx
0x1801c7a56  jz      short loc_1801C7A67
0x1801c7a58  mov     rax, [rcx]
0x1801c7a5b  mov     edx, r15d
0x1801c7a5e  mov     rax, [rax]
0x1801c7a61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c7a66  nop
0x1801c7a67  jmp     loc_1801C87EA
0x1801c7a6c  lea     r8, [rsi+78h]; void *
0x1801c7a70  cmp     [r8+4], r15b
0x1801c7a74  jnz     short loc_1801C7AA9
0x1801c7a76  lea     rdx, aAllowcookies; "AllowCookies"
0x1801c7a7d  mov     rcx, r14; this
0x1801c7a80  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c7a85  mov     edi, eax
0x1801c7a87  test    eax, eax
0x1801c7a89  jz      short loc_1801C7AA9
0x1801c7a8b  mov     rcx, [rsp+0C8h+var_88]
0x1801c7a90  test    rcx, rcx
0x1801c7a93  jz      short loc_1801C7AA4
0x1801c7a95  mov     rax, [rcx]
0x1801c7a98  mov     edx, r15d
0x1801c7a9b  mov     rax, [rax]
0x1801c7a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c7aa3  nop
0x1801c7aa4  jmp     loc_1801C87EA
0x1801c7aa9  lea     r8, [rsi+80h]; void *
0x1801c7ab0  cmp     [r8+4], r15b
0x1801c7ab4  jnz     short loc_1801C7AE9
0x1801c7ab6  lea     rdx, aAllowdeveloper; "AllowDeveloperTools"
0x1801c7abd  mov     rcx, r14; this
0x1801c7ac0  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c7ac5  mov     edi, eax
0x1801c7ac7  test    eax, eax
0x1801c7ac9  jz      short loc_1801C7AE9
0x1801c7acb  mov     rcx, [rsp+0C8h+var_88]
0x1801c7ad0  test    rcx, rcx
0x1801c7ad3  jz      short loc_1801C7AE4
0x1801c7ad5  mov     rax, [rcx]
0x1801c7ad8  mov     edx, r15d
0x1801c7adb  mov     rax, [rax]
0x1801c7ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c7ae3  nop
0x1801c7ae4  jmp     loc_1801C87EA
0x1801c7ae9  lea     r8, [rsi+88h]; void *
0x1801c7af0  cmp     [r8+4], r15b
0x1801c7af4  jnz     short loc_1801C7B29
0x1801c7af6  lea     rdx, aAllowdonottrac; "AllowDoNotTrack"
0x1801c7afd  mov     rcx, r14; this
0x1801c7b00  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c7b05  mov     edi, eax
0x1801c7b07  test    eax, eax
0x1801c7b09  jz      short loc_1801C7B29
0x1801c7b0b  mov     rcx, [rsp+0C8h+var_88]
0x1801c7b10  test    rcx, rcx
0x1801c7b13  jz      short loc_1801C7B24
0x1801c7b15  mov     rax, [rcx]
0x1801c7b18  mov     edx, r15d
0x1801c7b1b  mov     rax, [rax]
0x1801c7b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c7b23  nop
0x1801c7b24  jmp     loc_1801C87EA
0x1801c7b29  lea     r8, [rsi+90h]; void *
0x1801c7b30  cmp     [r8+4], r15b
0x1801c7b34  jnz     short loc_1801C7B69
0x1801c7b36  lea     rdx, aAllowextension; "AllowExtensions"
0x1801c7b3d  mov     rcx, r14; this
0x1801c7b40  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c7b45  mov     edi, eax
0x1801c7b47  test    eax, eax
0x1801c7b49  jz      short loc_1801C7B69
0x1801c7b4b  mov     rcx, [rsp+0C8h+var_88]
0x1801c7b50  test    rcx, rcx
0x1801c7b53  jz      short loc_1801C7B64
0x1801c7b55  mov     rax, [rcx]
0x1801c7b58  mov     edx, r15d
0x1801c7b5b  mov     rax, [rax]
0x1801c7b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c7b63  nop
0x1801c7b64  jmp     loc_1801C87EA
0x1801c7b69  lea     r8, [rsi+98h]; void *
0x1801c7b70  cmp     [r8+4], r15b
0x1801c7b74  jnz     short loc_1801C7BA9
0x1801c7b76  lea     rdx, aAllowflash; "AllowFlash"
0x1801c7b7d  mov     rcx, r14; this
0x1801c7b80  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c7b85  mov     edi, eax
0x1801c7b87  test    eax, eax
0x1801c7b89  jz      short loc_1801C7BA9
0x1801c7b8b  mov     rcx, [rsp+0C8h+var_88]
0x1801c7b90  test    rcx, rcx
0x1801c7b93  jz      short loc_1801C7BA4
0x1801c7b95  mov     rax, [rcx]
0x1801c7b98  mov     edx, r15d
0x1801c7b9b  mov     rax, [rax]
0x1801c7b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c7ba3  nop
0x1801c7ba4  jmp     loc_1801C87EA
0x1801c7ba9  lea     r8, [rsi+0A0h]; void *
0x1801c7bb0  cmp     [r8+4], r15b
0x1801c7bb4  jnz     short loc_1801C7BE9
0x1801c7bb6  lea     rdx, aAllowflashclic; "AllowFlashClickToRun"
0x1801c7bbd  mov     rcx, r14; this
0x1801c7bc0  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c7bc5  mov     edi, eax
0x1801c7bc7  test    eax, eax
0x1801c7bc9  jz      short loc_1801C7BE9
0x1801c7bcb  mov     rcx, [rsp+0C8h+var_88]
0x1801c7bd0  test    rcx, rcx
0x1801c7bd3  jz      short loc_1801C7BE4
0x1801c7bd5  mov     rax, [rcx]
0x1801c7bd8  mov     edx, r15d
0x1801c7bdb  mov     rax, [rax]
0x1801c7bde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c7be3  nop
0x1801c7be4  jmp     loc_1801C87EA
0x1801c7be9  lea     r8, [rsi+0A8h]; void *
0x1801c7bf0  cmp     [r8+4], r15b
0x1801c7bf4  jnz     short loc_1801C7C29
0x1801c7bf6  lea     rdx, aAllowfullscree; "AllowFullScreenMode"
0x1801c7bfd  mov     rcx, r14; this
0x1801c7c00  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c7c05  mov     edi, eax
0x1801c7c07  test    eax, eax
0x1801c7c09  jz      short loc_1801C7C29
0x1801c7c0b  mov     rcx, [rsp+0C8h+var_88]
0x1801c7c10  test    rcx, rcx
0x1801c7c13  jz      short loc_1801C7C24
0x1801c7c15  mov     rax, [rcx]
0x1801c7c18  mov     edx, r15d
0x1801c7c1b  mov     rax, [rax]
0x1801c7c1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c7c23  nop
0x1801c7c24  jmp     loc_1801C87EA
0x1801c7c29  lea     r8, [rsi+0B0h]; void *
0x1801c7c30  cmp     [r8+4], r15b
0x1801c7c34  jnz     short loc_1801C7C69
0x1801c7c36  lea     rdx, aAllowinprivate; "AllowInPrivate"
0x1801c7c3d  mov     rcx, r14; this
0x1801c7c40  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c7c45  mov     edi, eax
0x1801c7c47  test    eax, eax
0x1801c7c49  jz      short loc_1801C7C69
0x1801c7c4b  mov     rcx, [rsp+0C8h+var_88]
0x1801c7c50  test    rcx, rcx
0x1801c7c53  jz      short loc_1801C7C64
0x1801c7c55  mov     rax, [rcx]
0x1801c7c58  mov     edx, r15d
0x1801c7c5b  mov     rax, [rax]
0x1801c7c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c7c63  nop
0x1801c7c64  jmp     loc_1801C87EA
0x1801c7c69  lea     r8, [rsi+0B8h]; void *
0x1801c7c70  cmp     [r8+4], r15b
0x1801c7c74  jnz     short loc_1801C7CA9
0x1801c7c76  lea     rdx, aAllowmicrosoft_2; "AllowMicrosoftCompatibilityList"
0x1801c7c7d  mov     rcx, r14; this
0x1801c7c80  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x1801c7c85  mov     edi, eax
0x1801c7c87  test    eax, eax
0x1801c7c89  jz      short loc_1801C7CA9
0x1801c7c8b  mov     rcx, [rsp+0C8h+var_88]
0x1801c7c90  test    rcx, rcx
0x1801c7c93  jz      short loc_1801C7CA4
0x1801c7c95  mov     rax, [rcx]
0x1801c7c98  mov     edx, r15d
0x1801c7c9b  mov     rax, [rax]
0x1801c7c9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c7ca3  nop
0x1801c7ca4  jmp     loc_1801C87EA
  ... truncated ...
```
