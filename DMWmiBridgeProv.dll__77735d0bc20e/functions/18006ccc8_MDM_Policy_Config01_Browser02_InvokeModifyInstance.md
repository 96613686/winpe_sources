# MDM_Policy_Config01_Browser02_InvokeModifyInstance

- ea: `0x18006ccc8`
- end: `0x18006de9b`
- name: `MDM_Policy_Config01_Browser02_InvokeModifyInstance`
- size: `4563`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18006deb0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x18000a280`
- `0x18006ccc8`
- `0x180240078`
- `0x180241ce0`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d160`
- `0x18024f010`

## string_xrefs

- `0x18006ced9`: `AllowConfigurationUpdateForBooksLibrary`
- `0x18006cfd6`: `AllowExtensions`
- `0x18006d116`: `AllowMicrosoftCompatibilityList`
- `0x18006d316`: `AllowSideloadingOfExtensions`
- `0x18006d496`: `ConfigureAdditionalSearchEngines`
- `0x18006d4d6`: `ConfigureFavoritesBar`
- `0x18006d516`: `ConfigureHomeButton`
- `0x18006d556`: `ConfigureKioskMode`
- `0x18006d596`: `ConfigureKioskResetAfterIdleTimeout`
- `0x18006d5d6`: `ConfigureOpenMicrosoftEdgeWith`
- `0x18006d616`: `ConfigureTelemetryForMicrosoft365Analytics`
- `0x18006d896`: `EnterpriseSiteListServiceUrl`
- `0x18006d956`: `PreventAccessToAboutFlagsInMicrosoftEdge`
- `0x18006dad6`: `PreventTurningOffRequiredExtensions`
- `0x18006dc96`: `ShowMessageWhenOpeningSitesInInternetExplorer`
- `0x18006cd13`: `MDM_Policy_Config01_Browser02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_Browser02_InvokeModifyInstance(__int64 a1, __int64 a2)
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
      inserted = CreateRequestHandlerInstance(
                   a1,
                   *(wchar_t **)(a2 + 80),
                   *(const unsigned __int16 **)(a2 + 64),
                   (struct WmiNodeInfo *)&MDM_Policy_Config01_Browser02_NodeList,
                   0x3Fu,
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
            (struct WmiNodeInfo *)&MDM_Policy_Config01_Browser02_NodeList,
            0x3Fu);
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
          else if ( *(_BYTE *)(a2 + 368) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DefaultFavoriteBarItem1Name",
                                  (LONG *)(a2 + 360))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 384) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DefaultFavoriteBarItem1Url",
                                  (LONG *)(a2 + 376))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 400) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DefaultFavoriteBarItem2Name",
                                  (LONG *)(a2 + 392))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 416) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DefaultFavoriteBarItem2Url",
                                  (LONG *)(a2 + 408))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 432) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DefaultFavoriteBarItem3Name",
                                  (LONG *)(a2 + 424))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 448) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DefaultFavoriteBarItem3Url",
                                  (LONG *)(a2 + 440))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 460) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"DisableLockdownOfStartPages",
                                  (LONG *)(a2 + 456))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 468) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"EnableExtendedBooksTelemetry",
                                  (LONG *)(a2 + 464))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 480) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"EnterpriseModeSiteList",
                                  (LONG *)(a2 + 472))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 496) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"EnterpriseSiteListServiceUrl",
                                  (LONG *)(a2 + 488))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 512) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"HomePages", (LONG *)(a2 + 504))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 524) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"LockdownFavorites", (LONG *)(a2 + 520))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 532) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PreventAccessToAboutFlagsInMicrosoftEdge",
                                  (LONG *)(a2 + 528))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 540) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PreventCertErrorOverrides",
                                  (LONG *)(a2 + 536))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 548) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"PreventFirstRunPage", (LONG *)(a2 + 544))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 556) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PreventLiveTileDataCollection",
                                  (LONG *)(a2 + 552))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 564) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PreventSmartScreenPromptOverride",
                                  (LONG *)(a2 + 560))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 572) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PreventSmartScreenPromptOverrideForFiles",
                                  (LONG *)(a2 + 568))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 584) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PreventTurningOffRequiredExtensions",
                                  (LONG *)(a2 + 576))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 596) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"PreventUsingLocalHostIPAddressForWebRTC",
                                  (LONG *)(a2 + 592))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 608) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"ProvisionFavorites", (LONG *)(a2 + 600))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 620) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SendIntranetTraffictoInternetExplorer",
                                  (LONG *)(a2 + 616))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 632) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SetDefaultSearchEngine",
                                  (LONG *)(a2 + 624))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 648) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"SetHomeButtonURL", (LONG *)(a2 + 640))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 664) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"SetNewTabPageURL", (LONG *)(a2 + 656))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 676) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"ShowMessageWhenOpeningSitesInInternetExplorer",
                                  (LONG *)(a2 + 672))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 684) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"SyncFavoritesBetweenIEAndMicrosoftEdge",
                                  (LONG *)(a2 + 680))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 692) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(v7, L"UnlockHomeButton", (LONG *)(a2 + 688))) != 0 )
          {
            v5 = v11;
            if ( v11 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v11)(v11, 1);
          }
          else if ( *(_BYTE *)(a2 + 700) == 1
                 && (inserted = WmiRequestHandlerAdd::InsertDataForNode(
                                  v7,
                                  L"UseSharedFolderForBooks",
                                  (LONG *)(a2 + 696))) != 0 )
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
      &word_18033F736,
      v17,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v15);
  return inserted;
}

```

## disassembly

```asm
0x18006ccc8  mov     r11, rsp
0x18006cccb  mov     [r11+18h], rsi
0x18006cccf  push    rdi
0x18006ccd0  push    r14
0x18006ccd2  push    r15
0x18006ccd4  sub     rsp, 0B0h
0x18006ccdb  mov     rax, cs:__security_cookie
0x18006cce2  xor     rax, rsp
0x18006cce5  mov     [rsp+0C8h+var_28], rax
0x18006cced  mov     rsi, rdx
0x18006ccf0  mov     rdi, rcx
0x18006ccf3  mov     [rsp+0C8h+var_50], 0
0x18006ccfb  mov     [rsp+0C8h+var_4C], 0
0x18006cd00  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18006cd07  mov     [r11-80h], rax
0x18006cd0b  lea     rax, [r11-50h]
0x18006cd0f  mov     [r11-78h], rax
0x18006cd13  lea     rax, aMdmPolicyConfi_161; "MDM_Policy_Config01_Browser02"
0x18006cd1a  mov     [r11-70h], rax
0x18006cd1e  lea     rcx, [r11-50h]
0x18006cd22  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18006cd27  mov     eax, cs:dword_180380B68
0x18006cd2d  cmp     eax, 5
0x18006cd30  jbe     short loc_18006CDA3
0x18006cd32  mov     rdx, 200000000000h
0x18006cd3c  lea     rcx, dword_180380B68
0x18006cd43  call    _tlgKeywordOn
0x18006cd48  test    al, al
0x18006cd4a  jz      short loc_18006CDA3
0x18006cd4c  cmp     [rsp+0C8h+var_4C], 0
0x18006cd51  jz      short loc_18006CD85
0x18006cd53  cmp     [rsp+0C8h+var_38], 0
0x18006cd5b  jnz     short loc_18006CD7B
0x18006cd5d  cmp     [rsp+0C8h+var_34], 0
0x18006cd65  jnz     short loc_18006CD7B
0x18006cd67  cmp     [rsp+0C8h+var_30], 0
0x18006cd6f  jnz     short loc_18006CD7B
0x18006cd71  cmp     [rsp+0C8h+var_2C], 0
0x18006cd79  jz      short loc_18006CD85
0x18006cd7b  lea     r9, [rsp+0C8h+var_38]
0x18006cd83  jmp     short loc_18006CD88
0x18006cd85  xor     r9d, r9d
0x18006cd88  lea     r8, [rsp+0C8h+var_48]
0x18006cd90  lea     rdx, word_18034481E
0x18006cd97  lea     rcx, dword_180380B68
0x18006cd9e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18006cda3  cmp     byte ptr [rsi+48h], 0
0x18006cda7  jz      loc_18006DE05
0x18006cdad  cmp     byte ptr [rsi+58h], 0
0x18006cdb1  jz      loc_18006DE05
0x18006cdb7  mov     r9, [rsi+40h]; unsigned __int16 *
0x18006cdbb  mov     r8, [rsi+50h]; unsigned __int16 *
0x18006cdbf  lea     rdx, aModifyinstance; "ModifyInstanceStart"
0x18006cdc6  lea     rcx, [rsp+0C8h+var_80]; this
0x18006cdcb  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x18006cdd0  nop
0x18006cdd1  mov     [rsp+0C8h+var_88], 0
0x18006cdda  lea     rax, [rsp+0C8h+var_88]
0x18006cddf  mov     [rsp+0C8h+var_98], rax
0x18006cde4  mov     [rsp+0C8h+var_A0], 3
0x18006cdec  mov     [rsp+0C8h+var_A8], 3Fh ; '?'
0x18006cdf4  lea     r9, ?MDM_Policy_Config01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Browser02_NodeList
0x18006cdfb  mov     r8, [rsi+40h]
0x18006cdff  mov     rdx, [rsi+50h]
0x18006ce03  mov     rcx, rdi
0x18006ce06  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18006ce0b  mov     edi, eax
0x18006ce0d  test    eax, eax
0x18006ce0f  jz      short loc_18006CE16
0x18006ce11  jmp     loc_18006DE0A
0x18006ce16  lea     rax, [rsp+0C8h+var_88]
0x18006ce1b  mov     [rsp+0C8h+var_60], rax
0x18006ce20  mov     r15d, 1
0x18006ce26  mov     [rsp+0C8h+var_58], r15b
0x18006ce2b  mov     r14, [rsp+0C8h+var_88]
0x18006ce30  test    r14, r14
0x18006ce33  jnz     short loc_18006CE3D
0x18006ce35  mov     edi, r15d
0x18006ce38  jmp     loc_18006DE0A
0x18006ce3d  mov     r9d, 3Fh ; '?'; unsigned int
0x18006ce43  lea     r8, ?MDM_Policy_Config01_Browser02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18006ce4a  mov     rdx, rsi; struct _MI_Instance *
0x18006ce4d  mov     rcx, r14; this
0x18006ce50  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18006ce55  lea     r8, [rsi+60h]; void *
0x18006ce59  cmp     [r8+4], r15b
0x18006ce5d  jnz     short loc_18006CE92
0x18006ce5f  lea     rdx, aAllowaddressba; "AllowAddressBarDropdown"
0x18006ce66  mov     rcx, r14; this
0x18006ce69  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006ce6e  mov     edi, eax
0x18006ce70  test    eax, eax
0x18006ce72  jz      short loc_18006CE92
0x18006ce74  mov     rcx, [rsp+0C8h+var_88]
0x18006ce79  test    rcx, rcx
0x18006ce7c  jz      short loc_18006CE8D
0x18006ce7e  mov     rax, [rcx]
0x18006ce81  mov     edx, r15d
0x18006ce84  mov     rax, [rax]
0x18006ce87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ce8c  nop
0x18006ce8d  jmp     loc_18006DE0A
0x18006ce92  lea     r8, [rsi+68h]; void *
0x18006ce96  cmp     [r8+4], r15b
0x18006ce9a  jnz     short loc_18006CECF
0x18006ce9c  lea     rdx, aAllowautofill; "AllowAutofill"
0x18006cea3  mov     rcx, r14; this
0x18006cea6  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006ceab  mov     edi, eax
0x18006cead  test    eax, eax
0x18006ceaf  jz      short loc_18006CECF
0x18006ceb1  mov     rcx, [rsp+0C8h+var_88]
0x18006ceb6  test    rcx, rcx
0x18006ceb9  jz      short loc_18006CECA
0x18006cebb  mov     rax, [rcx]
0x18006cebe  mov     edx, r15d
0x18006cec1  mov     rax, [rax]
0x18006cec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cec9  nop
0x18006ceca  jmp     loc_18006DE0A
0x18006cecf  lea     r8, [rsi+70h]; void *
0x18006ced3  cmp     [r8+4], r15b
0x18006ced7  jnz     short loc_18006CF0C
0x18006ced9  lea     rdx, aAllowconfigura; "AllowConfigurationUpdateForBooksLibrary"
0x18006cee0  mov     rcx, r14; this
0x18006cee3  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006cee8  mov     edi, eax
0x18006ceea  test    eax, eax
0x18006ceec  jz      short loc_18006CF0C
0x18006ceee  mov     rcx, [rsp+0C8h+var_88]
0x18006cef3  test    rcx, rcx
0x18006cef6  jz      short loc_18006CF07
0x18006cef8  mov     rax, [rcx]
0x18006cefb  mov     edx, r15d
0x18006cefe  mov     rax, [rax]
0x18006cf01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cf06  nop
0x18006cf07  jmp     loc_18006DE0A
0x18006cf0c  lea     r8, [rsi+78h]; void *
0x18006cf10  cmp     [r8+4], r15b
0x18006cf14  jnz     short loc_18006CF49
0x18006cf16  lea     rdx, aAllowcookies; "AllowCookies"
0x18006cf1d  mov     rcx, r14; this
0x18006cf20  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006cf25  mov     edi, eax
0x18006cf27  test    eax, eax
0x18006cf29  jz      short loc_18006CF49
0x18006cf2b  mov     rcx, [rsp+0C8h+var_88]
0x18006cf30  test    rcx, rcx
0x18006cf33  jz      short loc_18006CF44
0x18006cf35  mov     rax, [rcx]
0x18006cf38  mov     edx, r15d
0x18006cf3b  mov     rax, [rax]
0x18006cf3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cf43  nop
0x18006cf44  jmp     loc_18006DE0A
0x18006cf49  lea     r8, [rsi+80h]; void *
0x18006cf50  cmp     [r8+4], r15b
0x18006cf54  jnz     short loc_18006CF89
0x18006cf56  lea     rdx, aAllowdeveloper; "AllowDeveloperTools"
0x18006cf5d  mov     rcx, r14; this
0x18006cf60  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006cf65  mov     edi, eax
0x18006cf67  test    eax, eax
0x18006cf69  jz      short loc_18006CF89
0x18006cf6b  mov     rcx, [rsp+0C8h+var_88]
0x18006cf70  test    rcx, rcx
0x18006cf73  jz      short loc_18006CF84
0x18006cf75  mov     rax, [rcx]
0x18006cf78  mov     edx, r15d
0x18006cf7b  mov     rax, [rax]
0x18006cf7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cf83  nop
0x18006cf84  jmp     loc_18006DE0A
0x18006cf89  lea     r8, [rsi+88h]; void *
0x18006cf90  cmp     [r8+4], r15b
0x18006cf94  jnz     short loc_18006CFC9
0x18006cf96  lea     rdx, aAllowdonottrac; "AllowDoNotTrack"
0x18006cf9d  mov     rcx, r14; this
0x18006cfa0  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006cfa5  mov     edi, eax
0x18006cfa7  test    eax, eax
0x18006cfa9  jz      short loc_18006CFC9
0x18006cfab  mov     rcx, [rsp+0C8h+var_88]
0x18006cfb0  test    rcx, rcx
0x18006cfb3  jz      short loc_18006CFC4
0x18006cfb5  mov     rax, [rcx]
0x18006cfb8  mov     edx, r15d
0x18006cfbb  mov     rax, [rax]
0x18006cfbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cfc3  nop
0x18006cfc4  jmp     loc_18006DE0A
0x18006cfc9  lea     r8, [rsi+90h]; void *
0x18006cfd0  cmp     [r8+4], r15b
0x18006cfd4  jnz     short loc_18006D009
0x18006cfd6  lea     rdx, aAllowextension; "AllowExtensions"
0x18006cfdd  mov     rcx, r14; this
0x18006cfe0  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006cfe5  mov     edi, eax
0x18006cfe7  test    eax, eax
0x18006cfe9  jz      short loc_18006D009
0x18006cfeb  mov     rcx, [rsp+0C8h+var_88]
0x18006cff0  test    rcx, rcx
0x18006cff3  jz      short loc_18006D004
0x18006cff5  mov     rax, [rcx]
0x18006cff8  mov     edx, r15d
0x18006cffb  mov     rax, [rax]
0x18006cffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d003  nop
0x18006d004  jmp     loc_18006DE0A
0x18006d009  lea     r8, [rsi+98h]; void *
0x18006d010  cmp     [r8+4], r15b
0x18006d014  jnz     short loc_18006D049
0x18006d016  lea     rdx, aAllowflash; "AllowFlash"
0x18006d01d  mov     rcx, r14; this
0x18006d020  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006d025  mov     edi, eax
0x18006d027  test    eax, eax
0x18006d029  jz      short loc_18006D049
0x18006d02b  mov     rcx, [rsp+0C8h+var_88]
0x18006d030  test    rcx, rcx
0x18006d033  jz      short loc_18006D044
0x18006d035  mov     rax, [rcx]
0x18006d038  mov     edx, r15d
0x18006d03b  mov     rax, [rax]
0x18006d03e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d043  nop
0x18006d044  jmp     loc_18006DE0A
0x18006d049  lea     r8, [rsi+0A0h]; void *
0x18006d050  cmp     [r8+4], r15b
0x18006d054  jnz     short loc_18006D089
0x18006d056  lea     rdx, aAllowflashclic; "AllowFlashClickToRun"
0x18006d05d  mov     rcx, r14; this
0x18006d060  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006d065  mov     edi, eax
0x18006d067  test    eax, eax
0x18006d069  jz      short loc_18006D089
0x18006d06b  mov     rcx, [rsp+0C8h+var_88]
0x18006d070  test    rcx, rcx
0x18006d073  jz      short loc_18006D084
0x18006d075  mov     rax, [rcx]
0x18006d078  mov     edx, r15d
0x18006d07b  mov     rax, [rax]
0x18006d07e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d083  nop
0x18006d084  jmp     loc_18006DE0A
0x18006d089  lea     r8, [rsi+0A8h]; void *
0x18006d090  cmp     [r8+4], r15b
0x18006d094  jnz     short loc_18006D0C9
0x18006d096  lea     rdx, aAllowfullscree; "AllowFullScreenMode"
0x18006d09d  mov     rcx, r14; this
0x18006d0a0  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006d0a5  mov     edi, eax
0x18006d0a7  test    eax, eax
0x18006d0a9  jz      short loc_18006D0C9
0x18006d0ab  mov     rcx, [rsp+0C8h+var_88]
0x18006d0b0  test    rcx, rcx
0x18006d0b3  jz      short loc_18006D0C4
0x18006d0b5  mov     rax, [rcx]
0x18006d0b8  mov     edx, r15d
0x18006d0bb  mov     rax, [rax]
0x18006d0be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d0c3  nop
0x18006d0c4  jmp     loc_18006DE0A
0x18006d0c9  lea     r8, [rsi+0B0h]; void *
0x18006d0d0  cmp     [r8+4], r15b
0x18006d0d4  jnz     short loc_18006D109
0x18006d0d6  lea     rdx, aAllowinprivate; "AllowInPrivate"
0x18006d0dd  mov     rcx, r14; this
0x18006d0e0  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006d0e5  mov     edi, eax
0x18006d0e7  test    eax, eax
0x18006d0e9  jz      short loc_18006D109
0x18006d0eb  mov     rcx, [rsp+0C8h+var_88]
0x18006d0f0  test    rcx, rcx
0x18006d0f3  jz      short loc_18006D104
0x18006d0f5  mov     rax, [rcx]
0x18006d0f8  mov     edx, r15d
0x18006d0fb  mov     rax, [rax]
0x18006d0fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d103  nop
0x18006d104  jmp     loc_18006DE0A
0x18006d109  lea     r8, [rsi+0B8h]; void *
0x18006d110  cmp     [r8+4], r15b
0x18006d114  jnz     short loc_18006D149
0x18006d116  lea     rdx, aAllowmicrosoft_2; "AllowMicrosoftCompatibilityList"
0x18006d11d  mov     rcx, r14; this
0x18006d120  call    ?InsertDataForNode@WmiRequestHandlerAdd@@QEAA?AW4_MI_Result@@PEBGPEAX@Z; WmiRequestHandlerAdd::InsertDataForNode(ushort const *,void *)
0x18006d125  mov     edi, eax
0x18006d127  test    eax, eax
0x18006d129  jz      short loc_18006D149
0x18006d12b  mov     rcx, [rsp+0C8h+var_88]
0x18006d130  test    rcx, rcx
0x18006d133  jz      short loc_18006D144
0x18006d135  mov     rax, [rcx]
0x18006d138  mov     edx, r15d
0x18006d13b  mov     rax, [rax]
0x18006d13e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d143  nop
0x18006d144  jmp     loc_18006DE0A
  ... truncated ...
```
