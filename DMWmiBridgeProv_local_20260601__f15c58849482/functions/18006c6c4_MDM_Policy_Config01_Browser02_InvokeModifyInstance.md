# MDM_Policy_Config01_Browser02_InvokeModifyInstance

- ea: `0x18006c6c4`
- end: `0x18006d898`
- name: `MDM_Policy_Config01_Browser02_InvokeModifyInstance`
- size: `4564`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18006d8a0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x18000a768`
- `0x18006c6c4`
- `0x18023f3ac`
- `0x180241010`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024cd20`
- `0x18024f010`

## string_xrefs

- `0x18006c8d5`: `AllowConfigurationUpdateForBooksLibrary`
- `0x18006c9d2`: `AllowExtensions`
- `0x18006cb12`: `AllowMicrosoftCompatibilityList`
- `0x18006cd12`: `AllowSideloadingOfExtensions`
- `0x18006ce92`: `ConfigureAdditionalSearchEngines`
- `0x18006ced2`: `ConfigureFavoritesBar`
- `0x18006cf12`: `ConfigureHomeButton`
- `0x18006cf52`: `ConfigureKioskMode`
- `0x18006cf92`: `ConfigureKioskResetAfterIdleTimeout`
- `0x18006cfd2`: `ConfigureOpenMicrosoftEdgeWith`
- `0x18006d012`: `ConfigureTelemetryForMicrosoft365Analytics`
- `0x18006d292`: `EnterpriseSiteListServiceUrl`
- `0x18006d352`: `PreventAccessToAboutFlagsInMicrosoftEdge`
- `0x18006d4d2`: `PreventTurningOffRequiredExtensions`
- `0x18006d692`: `ShowMessageWhenOpeningSitesInInternetExplorer`
- `0x18006c70f`: `MDM_Policy_Config01_Browser02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_Browser02_InvokeModifyInstance(__int64 a1, __int64 a2)
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
  v12[2] = "MDM_Policy_Config01_Browser02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v15);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v16 && (v18[0] || v18[1] || v18[2] || v18[3]) )
      v4 = v18;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &word_18034481E,
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
                                 &MDM_Policy_Config01_Browser02_NodeList,
                                 63,
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
            (struct WmiNodeInfo *)&MDM_Policy_Config01_Browser02_NodeList,
            0x3Fu);
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
          else if ( *(_BYTE *)(a2 + 368) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DefaultFavoriteBarItem1Name",
                                  (void *)(a2 + 360))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 384) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DefaultFavoriteBarItem1Url",
                                  (void *)(a2 + 376))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 400) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DefaultFavoriteBarItem2Name",
                                  (void *)(a2 + 392))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 416) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DefaultFavoriteBarItem2Url",
                                  (void *)(a2 + 408))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 432) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DefaultFavoriteBarItem3Name",
                                  (void *)(a2 + 424))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 448) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DefaultFavoriteBarItem3Url",
                                  (void *)(a2 + 440))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 460) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DisableLockdownOfStartPages",
                                  (void *)(a2 + 456))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 468) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"EnableExtendedBooksTelemetry",
                                  (void *)(a2 + 464))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 480) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"EnterpriseModeSiteList",
                                  (void *)(a2 + 472))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 496) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"EnterpriseSiteListServiceUrl",
                                  (void *)(a2 + 488))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 512) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"HomePages", (void *)(a2 + 504))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 524) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"LockdownFavorites", (void *)(a2 + 520))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 532) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PreventAccessToAboutFlagsInMicrosoftEdge",
                                  (void *)(a2 + 528))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 540) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PreventCertErrorOverrides",
                                  (void *)(a2 + 536))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 548) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"PreventFirstRunPage", (void *)(a2 + 544))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 556) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PreventLiveTileDataCollection",
                                  (void *)(a2 + 552))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 564) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PreventSmartScreenPromptOverride",
                                  (void *)(a2 + 560))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 572) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PreventSmartScreenPromptOverrideForFiles",
                                  (void *)(a2 + 568))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 584) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PreventTurningOffRequiredExtensions",
                                  (void *)(a2 + 576))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 596) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PreventUsingLocalHostIPAddressForWebRTC",
                                  (void *)(a2 + 592))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 608) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ProvisionFavorites", (void *)(a2 + 600))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 620) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SendIntranetTraffictoInternetExplorer",
                                  (void *)(a2 + 616))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 632) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SetDefaultSearchEngine",
                                  (void *)(a2 + 624))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 648) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"SetHomeButtonURL", (void *)(a2 + 640))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 664) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"SetNewTabPageURL", (void *)(a2 + 656))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 676) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ShowMessageWhenOpeningSitesInInternetExplorer",
                                  (void *)(a2 + 672))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 684) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SyncFavoritesBetweenIEAndMicrosoftEdge",
                                  (void *)(a2 + 680))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 692) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"UnlockHomeButton", (void *)(a2 + 688))) != MI_RESULT_OK )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 700) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"UseSharedFolderForBooks",
                                  (void *)(a2 + 696))) != MI_RESULT_OK )
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
      &word_18033F736,
      v17,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v15);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x18006c6c4  mov     r11, rsp
0x18006c6c7  mov     [r11+18h], rsi
0x18006c6cb  push    rdi
0x18006c6cc  push    r14
0x18006c6ce  push    r15
0x18006c6d0  sub     rsp, 0B0h
0x18006c6d7  mov     rax, cs:__security_cookie
0x18006c6de  xor     rax, rsp
0x18006c6e1  mov     [rsp+0C8h+var_28], rax
0x18006c6e9  mov     rsi, rdx
0x18006c6ec  mov     rdi, rcx
0x18006c6ef  mov     [rsp+0C8h+var_50], 0
0x18006c6f7  mov     [rsp+0C8h+var_4C], 0
0x18006c6fc  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18006c703  mov     [r11-80h], rax
0x18006c707  lea     rax, [r11-50h]
0x18006c70b  mov     [r11-78h], rax
0x18006c70f  lea     rax, aMdmPolicyConfi_161; "MDM_Policy_Config01_Browser02"
0x18006c716  mov     [r11-70h], rax
0x18006c71a  lea     rcx, [r11-50h]
0x18006c71e  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18006c723  mov     eax, cs:dword_180380B68
0x18006c729  cmp     eax, 5
0x18006c72c  jbe     short loc_18006C79F
0x18006c72e  mov     rdx, 200000000000h
0x18006c738  lea     rcx, dword_180380B68
0x18006c73f  call    _tlgKeywordOn
0x18006c744  test    al, al
0x18006c746  jz      short loc_18006C79F
0x18006c748  cmp     [rsp+0C8h+var_4C], 0
0x18006c74d  jz      short loc_18006C781
0x18006c74f  cmp     [rsp+0C8h+var_38], 0
0x18006c757  jnz     short loc_18006C777
0x18006c759  cmp     [rsp+0C8h+var_34], 0
0x18006c761  jnz     short loc_18006C777
0x18006c763  cmp     [rsp+0C8h+var_30], 0
0x18006c76b  jnz     short loc_18006C777
0x18006c76d  cmp     [rsp+0C8h+var_2C], 0
0x18006c775  jz      short loc_18006C781
0x18006c777  lea     r9, [rsp+0C8h+var_38]
0x18006c77f  jmp     short loc_18006C784
0x18006c781  xor     r9d, r9d
0x18006c784  lea     r8, [rsp+0C8h+var_48]
0x18006c78c  lea     rdx, word_18034481E
0x18006c793  lea     rcx, dword_180380B68
0x18006c79a  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18006c79f  cmp     byte ptr [rsi+48h], 0
0x18006c7a3  jz      loc_18006D801
0x18006c7a9  cmp     byte ptr [rsi+58h], 0
0x18006c7ad  jz      loc_18006D801
0x18006c7b3  mov     r9, [rsi+40h]; unsigned __int16 *
0x18006c7b7  mov     r8, [rsi+50h]; unsigned __int16 *
0x18006c7bb  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x18006c7c2  lea     rcx, [rsp+0C8h+var_80]; this
0x18006c7c7  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x18006c7cc  nop
0x18006c7cd  mov     [rsp+0C8h+var_88], 0
0x18006c7d6  lea     rax, [rsp+0C8h+var_88]
0x18006c7db  mov     [rsp+0C8h+var_98], rax
0x18006c7e0  mov     [rsp+0C8h+var_A0], 3
0x18006c7e8  mov     [rsp+0C8h+var_A8], 3Fh ; '?'
0x18006c7f0  lea     r9, ?MDM_Policy_Config01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Browser02_NodeList
0x18006c7f7  mov     r8, [rsi+40h]
0x18006c7fb  mov     rdx, [rsi+50h]
0x18006c7ff  mov     rcx, rdi
0x18006c802  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18006c807  mov     edi, eax
0x18006c809  test    eax, eax
0x18006c80b  jz      short loc_18006C812
0x18006c80d  jmp     loc_18006D806
0x18006c812  lea     rax, [rsp+0C8h+var_88]
0x18006c817  mov     [rsp+0C8h+var_60], rax
0x18006c81c  mov     r15d, 1
0x18006c822  mov     [rsp+0C8h+var_58], r15b
0x18006c827  mov     r14, [rsp+0C8h+var_88]
0x18006c82c  test    r14, r14
0x18006c82f  jnz     short loc_18006C839
0x18006c831  mov     edi, r15d
0x18006c834  jmp     loc_18006D806
0x18006c839  mov     r9d, 3Fh ; '?'; unsigned int
0x18006c83f  lea     r8, ?MDM_Policy_Config01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18006c846  mov     rdx, rsi; struct _MI_Instance *
0x18006c849  mov     rcx, r14; this
0x18006c84c  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18006c851  lea     r8, [rsi+60h]; void *
0x18006c855  cmp     [r8+4], r15b
0x18006c859  jnz     short loc_18006C88E
0x18006c85b  lea     rdx, aAllowaddressba; "AllowAddressBarDropdown"
0x18006c862  mov     rcx, r14; this
0x18006c865  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006c86a  mov     edi, eax
0x18006c86c  test    eax, eax
0x18006c86e  jz      short loc_18006C88E
0x18006c870  mov     rcx, [rsp+0C8h+var_88]
0x18006c875  test    rcx, rcx
0x18006c878  jz      short loc_18006C889
0x18006c87a  mov     rax, [rcx]
0x18006c87d  mov     edx, r15d
0x18006c880  mov     rax, [rax]
0x18006c883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c888  nop
0x18006c889  jmp     loc_18006D806
0x18006c88e  lea     r8, [rsi+68h]; void *
0x18006c892  cmp     [r8+4], r15b
0x18006c896  jnz     short loc_18006C8CB
0x18006c898  lea     rdx, aAllowautofill; "AllowAutofill"
0x18006c89f  mov     rcx, r14; this
0x18006c8a2  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006c8a7  mov     edi, eax
0x18006c8a9  test    eax, eax
0x18006c8ab  jz      short loc_18006C8CB
0x18006c8ad  mov     rcx, [rsp+0C8h+var_88]
0x18006c8b2  test    rcx, rcx
0x18006c8b5  jz      short loc_18006C8C6
0x18006c8b7  mov     rax, [rcx]
0x18006c8ba  mov     edx, r15d
0x18006c8bd  mov     rax, [rax]
0x18006c8c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c8c5  nop
0x18006c8c6  jmp     loc_18006D806
0x18006c8cb  lea     r8, [rsi+70h]; void *
0x18006c8cf  cmp     [r8+4], r15b
0x18006c8d3  jnz     short loc_18006C908
0x18006c8d5  lea     rdx, aAllowconfigura; "AllowConfigurationUpdateForBooksLibrary"
0x18006c8dc  mov     rcx, r14; this
0x18006c8df  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006c8e4  mov     edi, eax
0x18006c8e6  test    eax, eax
0x18006c8e8  jz      short loc_18006C908
0x18006c8ea  mov     rcx, [rsp+0C8h+var_88]
0x18006c8ef  test    rcx, rcx
0x18006c8f2  jz      short loc_18006C903
0x18006c8f4  mov     rax, [rcx]
0x18006c8f7  mov     edx, r15d
0x18006c8fa  mov     rax, [rax]
0x18006c8fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c902  nop
0x18006c903  jmp     loc_18006D806
0x18006c908  lea     r8, [rsi+78h]; void *
0x18006c90c  cmp     [r8+4], r15b
0x18006c910  jnz     short loc_18006C945
0x18006c912  lea     rdx, aAllowcookies; "AllowCookies"
0x18006c919  mov     rcx, r14; this
0x18006c91c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006c921  mov     edi, eax
0x18006c923  test    eax, eax
0x18006c925  jz      short loc_18006C945
0x18006c927  mov     rcx, [rsp+0C8h+var_88]
0x18006c92c  test    rcx, rcx
0x18006c92f  jz      short loc_18006C940
0x18006c931  mov     rax, [rcx]
0x18006c934  mov     edx, r15d
0x18006c937  mov     rax, [rax]
0x18006c93a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c93f  nop
0x18006c940  jmp     loc_18006D806
0x18006c945  lea     r8, [rsi+80h]; void *
0x18006c94c  cmp     [r8+4], r15b
0x18006c950  jnz     short loc_18006C985
0x18006c952  lea     rdx, aAllowdeveloper; "AllowDeveloperTools"
0x18006c959  mov     rcx, r14; this
0x18006c95c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006c961  mov     edi, eax
0x18006c963  test    eax, eax
0x18006c965  jz      short loc_18006C985
0x18006c967  mov     rcx, [rsp+0C8h+var_88]
0x18006c96c  test    rcx, rcx
0x18006c96f  jz      short loc_18006C980
0x18006c971  mov     rax, [rcx]
0x18006c974  mov     edx, r15d
0x18006c977  mov     rax, [rax]
0x18006c97a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c97f  nop
0x18006c980  jmp     loc_18006D806
0x18006c985  lea     r8, [rsi+88h]; void *
0x18006c98c  cmp     [r8+4], r15b
0x18006c990  jnz     short loc_18006C9C5
0x18006c992  lea     rdx, aAllowdonottrac; "AllowDoNotTrack"
0x18006c999  mov     rcx, r14; this
0x18006c99c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006c9a1  mov     edi, eax
0x18006c9a3  test    eax, eax
0x18006c9a5  jz      short loc_18006C9C5
0x18006c9a7  mov     rcx, [rsp+0C8h+var_88]
0x18006c9ac  test    rcx, rcx
0x18006c9af  jz      short loc_18006C9C0
0x18006c9b1  mov     rax, [rcx]
0x18006c9b4  mov     edx, r15d
0x18006c9b7  mov     rax, [rax]
0x18006c9ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c9bf  nop
0x18006c9c0  jmp     loc_18006D806
0x18006c9c5  lea     r8, [rsi+90h]; void *
0x18006c9cc  cmp     [r8+4], r15b
0x18006c9d0  jnz     short loc_18006CA05
0x18006c9d2  lea     rdx, aAllowextension; "AllowExtensions"
0x18006c9d9  mov     rcx, r14; this
0x18006c9dc  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006c9e1  mov     edi, eax
0x18006c9e3  test    eax, eax
0x18006c9e5  jz      short loc_18006CA05
0x18006c9e7  mov     rcx, [rsp+0C8h+var_88]
0x18006c9ec  test    rcx, rcx
0x18006c9ef  jz      short loc_18006CA00
0x18006c9f1  mov     rax, [rcx]
0x18006c9f4  mov     edx, r15d
0x18006c9f7  mov     rax, [rax]
0x18006c9fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c9ff  nop
0x18006ca00  jmp     loc_18006D806
0x18006ca05  lea     r8, [rsi+98h]; void *
0x18006ca0c  cmp     [r8+4], r15b
0x18006ca10  jnz     short loc_18006CA45
0x18006ca12  lea     rdx, aAllowflash; "AllowFlash"
0x18006ca19  mov     rcx, r14; this
0x18006ca1c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006ca21  mov     edi, eax
0x18006ca23  test    eax, eax
0x18006ca25  jz      short loc_18006CA45
0x18006ca27  mov     rcx, [rsp+0C8h+var_88]
0x18006ca2c  test    rcx, rcx
0x18006ca2f  jz      short loc_18006CA40
0x18006ca31  mov     rax, [rcx]
0x18006ca34  mov     edx, r15d
0x18006ca37  mov     rax, [rax]
0x18006ca3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ca3f  nop
0x18006ca40  jmp     loc_18006D806
0x18006ca45  lea     r8, [rsi+0A0h]; void *
0x18006ca4c  cmp     [r8+4], r15b
0x18006ca50  jnz     short loc_18006CA85
0x18006ca52  lea     rdx, aAllowflashclic; "AllowFlashClickToRun"
0x18006ca59  mov     rcx, r14; this
0x18006ca5c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006ca61  mov     edi, eax
0x18006ca63  test    eax, eax
0x18006ca65  jz      short loc_18006CA85
0x18006ca67  mov     rcx, [rsp+0C8h+var_88]
0x18006ca6c  test    rcx, rcx
0x18006ca6f  jz      short loc_18006CA80
0x18006ca71  mov     rax, [rcx]
0x18006ca74  mov     edx, r15d
0x18006ca77  mov     rax, [rax]
0x18006ca7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ca7f  nop
0x18006ca80  jmp     loc_18006D806
0x18006ca85  lea     r8, [rsi+0A8h]; void *
0x18006ca8c  cmp     [r8+4], r15b
0x18006ca90  jnz     short loc_18006CAC5
0x18006ca92  lea     rdx, aAllowfullscree; "AllowFullScreenMode"
0x18006ca99  mov     rcx, r14; this
0x18006ca9c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006caa1  mov     edi, eax
0x18006caa3  test    eax, eax
0x18006caa5  jz      short loc_18006CAC5
0x18006caa7  mov     rcx, [rsp+0C8h+var_88]
0x18006caac  test    rcx, rcx
0x18006caaf  jz      short loc_18006CAC0
0x18006cab1  mov     rax, [rcx]
0x18006cab4  mov     edx, r15d
0x18006cab7  mov     rax, [rax]
0x18006caba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cabf  nop
0x18006cac0  jmp     loc_18006D806
0x18006cac5  lea     r8, [rsi+0B0h]; void *
0x18006cacc  cmp     [r8+4], r15b
0x18006cad0  jnz     short loc_18006CB05
0x18006cad2  lea     rdx, aAllowinprivate; "AllowInPrivate"
0x18006cad9  mov     rcx, r14; this
0x18006cadc  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006cae1  mov     edi, eax
0x18006cae3  test    eax, eax
0x18006cae5  jz      short loc_18006CB05
0x18006cae7  mov     rcx, [rsp+0C8h+var_88]
0x18006caec  test    rcx, rcx
0x18006caef  jz      short loc_18006CB00
0x18006caf1  mov     rax, [rcx]
0x18006caf4  mov     edx, r15d
0x18006caf7  mov     rax, [rax]
0x18006cafa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006caff  nop
0x18006cb00  jmp     loc_18006D806
0x18006cb05  lea     r8, [rsi+0B8h]; void *
0x18006cb0c  cmp     [r8+4], r15b
0x18006cb10  jnz     short loc_18006CB45
0x18006cb12  lea     rdx, aAllowmicrosoft_2; "AllowMicrosoftCompatibilityList"
0x18006cb19  mov     rcx, r14; this
0x18006cb1c  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006cb21  mov     edi, eax
0x18006cb23  test    eax, eax
0x18006cb25  jz      short loc_18006CB45
0x18006cb27  mov     rcx, [rsp+0C8h+var_88]
0x18006cb2c  test    rcx, rcx
0x18006cb2f  jz      short loc_18006CB40
0x18006cb31  mov     rax, [rcx]
0x18006cb34  mov     edx, r15d
0x18006cb37  mov     rax, [rax]
0x18006cb3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cb3f  nop
0x18006cb40  jmp     loc_18006D806
  ... truncated ...
```
