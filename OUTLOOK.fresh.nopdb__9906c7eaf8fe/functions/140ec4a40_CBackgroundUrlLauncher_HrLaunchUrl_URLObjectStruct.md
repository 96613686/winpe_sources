# CBackgroundUrlLauncher::HrLaunchUrl(URLObjectStruct *)

- ea: `0x140ec4a40`
- end: `0x140ec60d8`
- name: `?HrLaunchUrl@CBackgroundUrlLauncher@@AEAAJPEAVURLObjectStruct@@@Z`
- size: `5784`
- prototype: `__int64 __fastcall(CBackgroundUrlLauncher *__hidden this, struct URLObjectStruct *)`
- caller_count: `2`
- callee_count: `54`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x141857620`
- `0x141858e10`

## callees

- `0x14001dd7c`
- `0x1400211a0`
- `0x1400255e8`
- `0x14002ba90`
- `0x1400712cc`
- `0x14007efec`
- `0x1400a6c6c`
- `0x1400bb418`
- `0x140103f1c`
- `0x14010a978`
- `0x14010ab1c`
- `0x14010af24`
- `0x1401aed8c`
- `0x140503f00`
- `0x140504118`
- `0x140504184`
- `0x140504770`
- `0x140509800`
- `0x14067af14`
- `0x1407e8900`
- `0x1407e99f0`
- `0x1407eb010`
- `0x1407ecf10`
- `0x1409bd704`
- `0x1409bd7d0`
- `0x140adca14`
- `0x140b57ab0`
- `0x140c3508c`
- `0x140d1d05c`
- `0x140d21c08`
- `0x140d57b30`
- `0x140de8484`
- `0x140dfd954`
- `0x140e116a8`
- `0x140e19870`
- `0x140e6c02c`
- `0x140e80abc`
- `0x140e96ae8`
- `0x140e9fb00`
- `0x140eabdd0`
- `0x140ebac58`
- `0x140ec4a40`
- `0x140ef19bc`
- `0x140f2b2c0`
- `0x14164bf04`
- `0x1417ac50c`
- `0x14183fde0`
- `0x1418557e0`
- `0x141855bc0`
- `0x141855be8`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x140ec4d9c`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x140ec4d9c`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x140ec4df9`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x140ec4df9`
- `KERNEL32!GetFileAttributesW` at `0x140ec5dbd`
- `KERNEL32!GetFileAttributesW` at `0x140ec5dbd`
- `KERNEL32!CloseHandle` at `0x140ec6049`
- `KERNEL32!CloseHandle` at `0x140ec6049`
- `KERNEL32!GetCurrentThreadId` at `0x140ec4afe`
- `KERNEL32!GetCurrentThreadId` at `0x140ec4afe`
- `OLMAPI32!FIsFeatureEnabled` at `0x140ec4e7c`
- `OLMAPI32!FIsFeatureEnabled` at `0x140ec4e7c`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec4d86`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec4fea`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec50b1`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec51a5`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec5276`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec542e`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec5855`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec59c8`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec4d86`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec4fea`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec50b1`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec51a5`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec5276`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec542e`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec5855`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec59c8`
- `SHLWAPI!StrStrIW` at `0x140ec4dd5`
- `SHLWAPI!StrStrIW` at `0x140ec4dd5`
- `SHLWAPI!PathCreateFromUrlW` at `0x140ec5da8`
- `SHLWAPI!PathCreateFromUrlW` at `0x140ec5da8`
- `MSO!__imp_?MsoHrHlinkNavigateWithSrcInfoAndMsgCtx@@YAJPEAUIHlink@@PEAUIHlinkFrame@@KPEAUIBindCtx@@PEAUIBindStatusCallback@@PEAUIHlinkBrowseContext@@PEB_W5PEAUIOfficeIdentity@Authentication@Mso@@PEAUM365BrowserParams@m365_browser@@I@Z` at `0x140ec5af8`
- `MSO!__imp_?MsoHrHlinkNavigateWithSrcInfoAndMsgCtx@@YAJPEAUIHlink@@PEAUIHlinkFrame@@KPEAUIBindCtx@@PEAUIBindStatusCallback@@PEAUIHlinkBrowseContext@@PEB_W5PEAUIOfficeIdentity@Authentication@Mso@@PEAUM365BrowserParams@m365_browser@@I@Z` at `0x140ec5af8`
- `MSO!__imp_?GetReputationForIdentity@Safelinks@Mso@@YAJPEB_WAEAUIOfficeIdentity@Authentication@2@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAW4UrlVerdict@UrlReputation@2@W4RequestType@82@00@Z` at `0x140ec4f0b`
- `MSO!__imp_?GetReputationForIdentity@Safelinks@Mso@@YAJPEB_WAEAUIOfficeIdentity@Authentication@2@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAW4UrlVerdict@UrlReputation@2@W4RequestType@82@00@Z` at `0x140ec4f0b`
- `MSO!__imp_?MsoFConvertHttpToProtocolHandler@@YA_NPEB_WPEA_WH@Z` at `0x140ec4d08`
- `MSO!__imp_?MsoFConvertHttpToProtocolHandler@@YA_NPEB_WPEA_WH@Z` at `0x140ec4d08`
- `MSO!__imp_?MsoHrHlinkNavigateWithSourceInfo@@YAJPEAUIHlink@@PEAUIHlinkFrame@@KPEAUIBindCtx@@PEAUIBindStatusCallback@@PEAUIHlinkBrowseContext@@PEB_W5PEAUIOfficeIdentity@Authentication@Mso@@I@Z` at `0x140ec5b74`
- `MSO!__imp_?MsoHrHlinkNavigateWithSourceInfo@@YAJPEAUIHlink@@PEAUIHlinkFrame@@KPEAUIBindCtx@@PEAUIBindStatusCallback@@PEAUIHlinkBrowseContext@@PEB_W5PEAUIOfficeIdentity@Authentication@Mso@@I@Z` at `0x140ec5b74`
- `Mso98Win32Client!__imp_?AddAppDetailsAndBase64Encode@UrlReputation@Mso@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z` at `0x140ec4f60`
- `Mso98Win32Client!__imp_?AddAppDetailsAndBase64Encode@UrlReputation@Mso@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z` at `0x140ec4f60`
- `Mso98Win32Client!__imp_?IsSafeLinksUrl@UrlReputation@Mso@@YA_NPEB_W@Z` at `0x140ec4dba`
- `Mso98Win32Client!__imp_?IsSafeLinksUrl@UrlReputation@Mso@@YA_NPEB_W@Z` at `0x140ec4dba`
- `mso40uiWin32Client!__imp_?AddLinksOpenRightActivityAndReturnCommandParams@ProtocolHandlers@Mso@@YA?AV?$TCntPtr@UCommandParams@ProtocolHandlers@Mso@@@2@AEBUIMsoUrl@@PEBDPEB_W22@Z` at `0x140ec563c`
- `mso40uiWin32Client!__imp_?AddLinksOpenRightActivityAndReturnCommandParams@ProtocolHandlers@Mso@@YA?AV?$TCntPtr@UCommandParams@ProtocolHandlers@Mso@@@2@AEBUIMsoUrl@@PEBDPEB_W22@Z` at `0x140ec563c`
- `mso40uiWin32Client!mso40uiWin32Client_8443` at `0x140ec56f2`
- `mso40uiWin32Client!mso40uiWin32Client_8443` at `0x140ec56f2`
- `mso40uiWin32Client!mso40uiWin32Client_32195` at `0x140ec56a0`
- `mso40uiWin32Client!mso40uiWin32Client_32195` at `0x140ec56a0`
- `mso40uiWin32Client!__imp_?AppendLORQueryParamToUrl@ProtocolHandlers@Mso@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$TCntPtr@UCommandParams@ProtocolHandlers@Mso@@@2@@Z` at `0x140ec5c48`
- `mso40uiWin32Client!__imp_?AppendLORQueryParamToUrl@ProtocolHandlers@Mso@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$TCntPtr@UCommandParams@ProtocolHandlers@Mso@@@2@@Z` at `0x140ec5c48`
- `mso40uiWin32Client!__imp_?IsFlightToUpdateUrlWithCGuidEnabled@ProtocolHandlers@Mso@@YA_NXZ` at `0x140ec5513`
- `mso40uiWin32Client!__imp_?IsFlightToUpdateUrlWithCGuidEnabled@ProtocolHandlers@Mso@@YA_NXZ` at `0x140ec5513`
- `mso40uiWin32Client!__imp_?IsOpeningOfficeLinksFromSupportedAppsEnabled@ProtocolHandlers@Mso@@YA_NXZ` at `0x140ec54d6`
- `mso40uiWin32Client!__imp_?IsOpeningOfficeLinksFromSupportedAppsEnabled@ProtocolHandlers@Mso@@YA_NXZ` at `0x140ec54d6`
- `Mso30Win32Client!__imp_?EnableM365ProtocolByDefault@Hyperlink@Mso@@YA_NW4TeamEnum@AB@2@@Z` at `0x140ec5a52`
- `Mso30Win32Client!__imp_?EnableM365ProtocolByDefault@Hyperlink@Mso@@YA_NW4TeamEnum@AB@2@@Z` at `0x140ec5ebf`
- `Mso30Win32Client!__imp_?EnableM365ProtocolByDefault@Hyperlink@Mso@@YA_NW4TeamEnum@AB@2@@Z` at `0x140ec5a52`
- `Mso30Win32Client!__imp_?EnableM365ProtocolByDefault@Hyperlink@Mso@@YA_NW4TeamEnum@AB@2@@Z` at `0x140ec5ebf`
- `Mso30Win32Client!__imp_?MsoHrSafeToNavigateEx@@YAJPEB_WPEAUIHlinkSite@@KKPEAUHWND__@@@Z` at `0x140ec50e7`
- `Mso30Win32Client!__imp_?MsoHrSafeToNavigateEx@@YAJPEB_WPEAUIHlinkSite@@KKPEAUHWND__@@@Z` at `0x140ec50e7`
- `Mso30Win32Client!__imp_?IsM365BrowserLinkOpeningEnabled@Hyperlink@Mso@@YA_NW4TeamEnum@AB@2@@Z` at `0x140ec59fc`
- `Mso30Win32Client!__imp_?IsM365BrowserLinkOpeningEnabled@Hyperlink@Mso@@YA_NW4TeamEnum@AB@2@@Z` at `0x140ec5e0e`
- `Mso30Win32Client!__imp_?IsM365BrowserLinkOpeningEnabled@Hyperlink@Mso@@YA_NW4TeamEnum@AB@2@@Z` at `0x140ec59fc`
- `Mso30Win32Client!__imp_?IsM365BrowserLinkOpeningEnabled@Hyperlink@Mso@@YA_NW4TeamEnum@AB@2@@Z` at `0x140ec5e0e`
- `Mso30Win32Client!__imp_?OpenUrlInBrowser@Hyperlink@Mso@@YA?AV?$Future@W4LaunchBrowserResult@Hyperlink@Mso@@@2@AEBUIMsoUrl@@PEB_WW4Enum@IdP@Authentication@2@PEAUM365BrowserParams@m365_browser@@_N@Z` at `0x140ec5f27`
- `Mso30Win32Client!__imp_?OpenUrlInBrowser@Hyperlink@Mso@@YA?AV?$Future@W4LaunchBrowserResult@Hyperlink@Mso@@@2@AEBUIMsoUrl@@PEB_WW4Enum@IdP@Authentication@2@PEAUM365BrowserParams@m365_browser@@_N@Z` at `0x140ec5f27`
- `Mso30Win32Client!__imp_?MsoHrHlinkCreateFromString@@YAJPEB_W00PEAUIHlinkSite@@KPEAUIUnknown@@AEBU_GUID@@PEAPEAXI@Z` at `0x140ec59b3`
- `Mso30Win32Client!__imp_?MsoHrHlinkCreateFromString@@YAJPEB_W00PEAUIHlinkSite@@KPEAUIUnknown@@AEBU_GUID@@PEAPEAXI@Z` at `0x140ec59b3`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x140ec6057`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x140ec6057`
- `Mso20Win32Client!__imp_?MsoSHGetFileInfoW@@YA_KPEB_WKPEAU_SHFILEINFOW@@II@Z` at `0x140ec52e9`
- `Mso20Win32Client!__imp_?MsoSHGetFileInfoW@@YA_KPEB_WKPEAU_SHFILEINFOW@@II@Z` at `0x140ec53a2`
- `Mso20Win32Client!__imp_?MsoSHGetFileInfoW@@YA_KPEB_WKPEAU_SHFILEINFOW@@II@Z` at `0x140ec52e9`
- `Mso20Win32Client!__imp_?MsoSHGetFileInfoW@@YA_KPEB_WKPEAU_SHFILEINFOW@@II@Z` at `0x140ec53a2`
- `Mso20Win32Client!__imp_?Result@Activity@Telemetry@Mso@@QEAAAEAV?$optional@VResult@System@Office@@@std@@XZ` at `0x140ec6027`
- `Mso20Win32Client!__imp_?Result@Activity@Telemetry@Mso@@QEAAAEAV?$optional@VResult@System@Office@@@std@@XZ` at `0x140ec6027`
- `Mso20Win32Client!__imp_?MsoFRegSetDw@@YAHPEBU_msoreg@@K@Z` at `0x140ec549f`
- `Mso20Win32Client!__imp_?MsoFRegSetDw@@YAHPEBU_msoreg@@K@Z` at `0x140ec549f`
- `Mso20Win32Client!__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z` at `0x140ec548d`
- `Mso20Win32Client!__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z` at `0x140ec548d`
- `Mso20Win32Client!__imp_?Create@OGuid@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@Z` at `0x140ec55fe`
- `Mso20Win32Client!__imp_?Create@OGuid@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@Z` at `0x140ec55fe`
- `Mso20Win32Client!__imp_?MsoHrCreateUrlSimpleFromUser@@YAJPEAPEAUIMsoUrl@@PEB_WKPEBU1@W4MsoUrlCreateFlags@@PEAUIMsoMemHeap@@@Z` at `0x140ec5597`
- `Mso20Win32Client!__imp_?MsoHrCreateUrlSimpleFromUser@@YAJPEAPEAUIMsoUrl@@PEB_WKPEBU1@W4MsoUrlCreateFlags@@PEAUIMsoMemHeap@@@Z` at `0x140ec5597`
- `Mso20Win32Client!__imp_?MsoHrCreateUrlSimple@@YAJPEAPEAUIMsoUrl@@PEAUIMsoMemHeap@@@Z` at `0x140ec51e9`
- `Mso20Win32Client!__imp_?MsoHrCreateUrlSimple@@YAJPEAPEAUIMsoUrl@@PEAUIMsoMemHeap@@@Z` at `0x140ec51e9`

## string_xrefs

- `0x140ec4df2`: `https://teams.microsoft.com/l/meetup-join/`
- `0x140ec4dce`: `/?url=https%3A%2F%2Fteams.microsoft.com%2Fl%2Fmeetup-join%2F`
- `0x140ec4e23`: `OpenJoinTeamsMeetingUrl`

## pseudocode

```c
__int64 __fastcall CBackgroundUrlLauncher::HrLaunchUrl(CBackgroundUrlLauncher *this, struct URLObjectStruct *a2)
{
  __int64 v3; // rcx
  __int64 v4; // rbx
  HWND v5; // r14
  int v6; // edi
  char *v7; // r13
  wchar_t *v8; // rax
  struct Mso::Authentication::IOfficeIdentity *v9; // rsi
  HWND v10; // rax
  unsigned int v11; // r14d
  const struct Mso::Telemetry::EventFlags *v12; // rax
  __int64 v13; // rax
  const wchar_t *v14; // r15
  PCWSTR v15; // r14
  const wchar_t *v16; // rcx
  PCWSTR v17; // rdi
  const wchar_t *v18; // r8
  int v19; // eax
  __int64 v20; // rax
  const wchar_t *v21; // rcx
  __int64 v22; // rax
  const wchar_t *v23; // rbx
  const wchar_t *v24; // rdx
  Mso::UrlReputation *v25; // rcx
  bool IsSafeLinksUrl; // al
  const WCHAR *v27; // rcx
  bool v28; // al
  __int64 v29; // rax
  int v30; // ecx
  _QWORD *v31; // rax
  const wchar_t *v32; // rcx
  __int128 *v33; // rdx
  _QWORD *v34; // rax
  int v35; // eax
  CBackgroundUrlLauncher *v36; // rdi
  const wchar_t *v37; // rdx
  const wchar_t *v38; // r9
  int v39; // eax
  __int64 v40; // rdx
  const wchar_t *v41; // rcx
  unsigned int v42; // edi
  int v43; // eax
  const wchar_t *v44; // rdi
  const wchar_t *v45; // rdx
  int v46; // eax
  __int64 v47; // rcx
  const wchar_t *v48; // rdx
  __int64 v49; // rax
  const wchar_t *v50; // rdx
  const wchar_t *v51; // rdx
  __int64 v52; // rcx
  wchar_t *v53; // rbx
  wchar_t *v54; // rcx
  wchar_t *v55; // rdi
  const wchar_t *v56; // r9
  int v57; // eax
  __int64 v58; // rdx
  wchar_t *v59; // rdx
  const wchar_t *v60; // rdx
  __int64 *ThreadLocalStoragePointer; // rax
  __int64 v62; // rbx
  Mso::ProtocolHandlers *v63; // rcx
  Mso::ProtocolHandlers *v64; // rcx
  const wchar_t *v65; // rax
  const wchar_t *v66; // rcx
  const wchar_t *v67; // rdx
  __int64 v68; // rax
  __int64 v69; // rdx
  __int128 *p_Src; // rax
  __int64 *v71; // rax
  __int64 v72; // rdx
  __int64 v73; // rcx
  HWND v74; // rcx
  __int64 v75; // rax
  int v76; // r13d
  int v77; // esi
  int v78; // edi
  int v79; // ebx
  __int64 v80; // rax
  int v81; // ecx
  __int128 *v82; // rax
  int Param; // eax
  __int64 v84; // rdx
  __int64 v85; // rcx
  _QWORD *v86; // r8
  const wchar_t *v87; // rcx
  int v88; // eax
  __int64 v89; // rcx
  struct IHlink *v90; // rcx
  _QWORD *v91; // rax
  __int64 v92; // rcx
  __int64 v93; // rax
  const wchar_t *v94; // rcx
  const wchar_t *v95; // rax
  const wchar_t *v96; // rcx
  const wchar_t *v97; // rax
  __int64 v98; // rax
  struct IHlink *v99; // rcx
  const wchar_t *v100; // rdx
  __int64 v101; // rax
  int v102; // eax
  const char *v103; // rdx
  const char *v104; // r8
  struct IHlink *v105; // rcx
  const WCHAR *v106; // rax
  const wchar_t *v107; // rcx
  DWORD FileAttributesW; // eax
  const WCHAR *v109; // rbx
  unsigned int v110; // edi
  __int64 v111; // rcx
  __int64 v112; // rax
  __int64 v113; // rax
  __int64 v114; // r8
  const char *v115; // rdx
  const char *v116; // r8
  int v117; // r8d
  unsigned int v118; // ebx
  __int64 v119; // rcx
  bool *v121; // [rsp+20h] [rbp-E0h]
  bool v122; // [rsp+28h] [rbp-D8h]
  char *v123; // [rsp+38h] [rbp-C8h]
  unsigned int v124; // [rsp+60h] [rbp-A0h] BYREF
  char v125; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v126; // [rsp+68h] [rbp-98h] BYREF
  char v127; // [rsp+70h] [rbp-90h] BYREF
  DWORD pcchPath[2]; // [rsp+78h] [rbp-88h] BYREF
  int v129[2]; // [rsp+80h] [rbp-80h] BYREF
  struct IHlink *v130; // [rsp+88h] [rbp-78h] BYREF
  PCWSTR pszFirst[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v132; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v133; // [rsp+B0h] [rbp-50h]
  int v134; // [rsp+B4h] [rbp-4Ch]
  __int64 v135; // [rsp+B8h] [rbp-48h] BYREF
  HWND v136; // [rsp+C0h] [rbp-40h] BYREF
  BOOL v137; // [rsp+C8h] [rbp-38h]
  char *v138; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t *String1; // [rsp+D8h] [rbp-28h] BYREF
  wchar_t *v140; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v141; // [rsp+E8h] [rbp-18h]
  int v142; // [rsp+F0h] [rbp-10h] BYREF
  struct IHlink **v143; // [rsp+F8h] [rbp-8h] BYREF
  bool v144[8]; // [rsp+100h] [rbp+0h] BYREF
  const wchar_t *v145; // [rsp+108h] [rbp+8h]
  __int64 v146; // [rsp+110h] [rbp+10h]
  char v147; // [rsp+118h] [rbp+18h]
  int v148; // [rsp+119h] [rbp+19h]
  __int16 v149; // [rsp+11Dh] [rbp+1Dh]
  char v150; // [rsp+11Fh] [rbp+1Fh]
  __int64 v151; // [rsp+120h] [rbp+20h]
  _BYTE v152[16]; // [rsp+128h] [rbp+28h] BYREF
  struct IOlkAccount *v153; // [rsp+138h] [rbp+38h] BYREF
  CBackgroundUrlLauncher *v154; // [rsp+140h] [rbp+40h]
  HWND v155; // [rsp+148h] [rbp+48h]
  _QWORD v156[2]; // [rsp+150h] [rbp+50h] BYREF
  _QWORD v157[4]; // [rsp+160h] [rbp+60h] BYREF
  char v158; // [rsp+180h] [rbp+80h]
  char v159[8]; // [rsp+188h] [rbp+88h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+190h] [rbp+90h] BYREF
  unsigned int *v161; // [rsp+200h] [rbp+100h] BYREF
  _BYTE *v162; // [rsp+208h] [rbp+108h]
  char v163; // [rsp+210h] [rbp+110h]
  struct _GUID v164; // [rsp+220h] [rbp+120h] BYREF
  _QWORD v165[2]; // [rsp+230h] [rbp+130h] BYREF
  __int64 v166; // [rsp+240h] [rbp+140h]
  unsigned __int64 v167; // [rsp+248h] [rbp+148h]
  __int128 Src; // [rsp+250h] [rbp+150h] BYREF
  __m128i v169; // [rsp+260h] [rbp+160h]
  __int128 v170; // [rsp+270h] [rbp+170h] BYREF
  __m128i si128; // [rsp+280h] [rbp+180h]
  _SHFILEINFOW v172; // [rsp+290h] [rbp+190h] BYREF
  WCHAR pszPath[2088]; // [rsp+550h] [rbp+450h] BYREF

  v154 = this;
  v3 = *((_QWORD *)a2 + 29);
  *((_QWORD *)a2 + 29) = 0;
  v135 = v3;
  if ( v3 )
    CheckpointStopwatch::Checkpoint(v3, UrlLaunchCheckpoints::URLLaunch);
  v4 = *((_QWORD *)a2 + 1);
  v5 = *(HWND *)a2;
  v155 = *(HWND *)a2;
  v6 = 1;
  v129[0] = 1;
  v7 = (char *)a2 + 32;
  v138 = (char *)a2 + 32;
  if ( *((_QWORD *)a2 + 7) > 7u )
  {
    v7 = *(char **)v7;
    v138 = v7;
  }
  v8 = (wchar_t *)((char *)a2 + 64);
  if ( *((_QWORD *)a2 + 11) > 7u )
    v8 = *(wchar_t **)v8;
  String1 = v8;
  v125 = *((_BYTE *)a2 + 96);
  v9 = (struct Mso::Authentication::IOfficeIdentity *)*((_QWORD *)a2 + 13);
  v143 = (struct IHlink **)v9;
  v153 = (struct IOlkAccount *)*((_QWORD *)a2 + 15);
  v137 = GetCurrentThreadId() != g_dwMainThreadId;
  v10 = 0;
  if ( !v137 )
    v10 = v5;
  v136 = v10;
  v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 152LL))(v4);
  v133 = v11;
  v134 = v11 <= 1;
  pszFirst[0] = 0;
  pszFirst[1] = 0;
  v140 = 0;
  v141 = 0;
  v170 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v170) = 0;
  memset_0(&v172, 0, sizeof(v172));
  LODWORD(v130) = 0;
  v142 = 0;
  v126 = 0;
  v157[0] = &v126;
  v157[1] = &String1;
  v157[2] = &v153;
  v157[3] = &v135;
  v158 = 1;
  v12 = (const struct Mso::Telemetry::EventFlags *)Mso::Telemetry::EventFlags::EventFlags(v159, 2);
  v156[0] = &off_14217AAC0;
  v156[1] = "LaunchUrlResult";
  Mso::Telemetry::Activity::Activity(
    (Mso::Telemetry::Activity *)v152,
    (const struct Mso::Telemetry::EventName *)v156,
    v12);
  memset_0(&pExecInfo, 0, sizeof(pExecInfo));
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 64LL))(v4);
  pcchPath[0] = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 128LL))(v4);
  v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 136LL))(v4);
  v124 = StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrDup(pszFirst, v13);
  v14 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
  if ( (v124 & 0x80000000) != 0 )
    goto LABEL_25;
  memset_0(pszPath, 0, 0x1048u);
  if ( v11 == 3 )
  {
    v15 = pszFirst[0];
    if ( pszFirst[0] )
    {
      v16 = pszFirst[0];
      v17 = pszFirst[0];
    }
    else
    {
      v16 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
      v17 = 0;
    }
    if ( IsFileZoneLocalIntranetOrTrusted(v16) )
    {
      v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 648LL))(v4);
      v19 = StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrDup(&v140, v20);
    }
    else
    {
      v18 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
      if ( v17 )
        v18 = v17;
      v19 = HrReportErrorTag(-2147467259, 1900695, v18, 0x1E50D60Du);
    }
    v124 = v19;
    v6 = v129[0];
    goto LABEL_26;
  }
  if ( !v134 )
  {
LABEL_25:
    v15 = pszFirst[0];
    goto LABEL_26;
  }
  v21 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
  v15 = pszFirst[0];
  if ( pszFirst[0] )
    v21 = pszFirst[0];
  if ( MsoFConvertHttpToProtocolHandler(v21, pszPath, 2084) )
  {
    Mso::Url::CreateFromUser(v129, pszPath);
    v22 = Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(v129);
    v134 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 592LL))(v22);
    v6 = 0;
    v124 = StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrDup(pszFirst, pszPath);
    Mso::TCntPtr<CAttachmentHandlerActivationHost>::~TCntPtr<CAttachmentHandlerActivationHost>(v129);
    goto LABEL_25;
  }
LABEL_26:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 72LL))(v4);
  v23 = 0;
  if ( (v124 & 0x80000000) != 0 )
  {
    EtwTraceErrorTag(v124, 842431081);
    goto LABEL_267;
  }
  if ( !_wcsicmp(String1, L"Outlook-Body") )
  {
    if ( v15 )
    {
      v25 = (Mso::UrlReputation *)v15;
      v23 = v15;
    }
    else
    {
      v25 = (Mso::UrlReputation *)&VariableLengthBuffer<wchar_t>::s_szEmpty;
    }
    IsSafeLinksUrl = Mso::UrlReputation::IsSafeLinksUrl(v25, v24);
    v27 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
    if ( IsSafeLinksUrl )
    {
      if ( v23 )
        v27 = v23;
      v23 = 0;
      v28 = StrStrIW(v27, L"/?url=https%3A%2F%2Fteams.microsoft.com%2Fl%2Fmeetup-join%2F") != 0;
    }
    else
    {
      if ( v23 )
        v27 = v23;
      v23 = 0;
      v28 = _wcsnicmp(v27, L"https://teams.microsoft.com/l/meetup-join/", 0x2Au) == 0;
    }
    if ( v28 )
    {
      v29 = Mso::Telemetry::EventFlags::EventFlags(v129, 2);
      *(_QWORD *)&v132 = &off_14217AAC0;
      *((_QWORD *)&v132 + 1) = "OpenJoinTeamsMeetingUrl";
      Mso::Telemetry::SendTelemetryEvent<>(&v132, v29);
      v164 = 0;
      HrGetAccountUID(v153, &v164);
      EventWriteCalendar_JoinOnline(v124, 1u, 5u, &v164);
    }
  }
  if ( v125 && (unsigned __int8)FIsFeatureEnabled(536870919) )
  {
    v129[0] = 0;
    v127 = 1;
    v125 = 0;
    CBackgroundUrlLauncher::ForceCheckReputation(
      v30,
      (_DWORD)a2,
      (unsigned int)pszFirst,
      (unsigned int)&v127,
      (__int64)&v125);
    if ( v127 )
    {
      v31 = (_QWORD *)((char *)a2 + 136);
      if ( *((_QWORD *)a2 + 20) > 7u )
        v31 = (_QWORD *)*v31;
      v32 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
      v15 = pszFirst[0];
      if ( pszFirst[0] )
        v32 = pszFirst[0];
      v122 = (char)v31;
      LOBYTE(v121) = 0;
      if ( (int)Mso::Safelinks::GetReputationForIdentity(v32, *((_QWORD *)a2 + 13), &v170, v129) >= 0 && v129[0] == -1 )
      {
        v33 = &v170;
        if ( si128.m128i_i64[1] > 7uLL )
          v33 = (__int128 *)v170;
        StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrDup(pszFirst, v33);
        v15 = pszFirst[0];
      }
      EventWriteOutllib_GetReputationForIdentity(v129[0]);
    }
    else
    {
      v15 = pszFirst[0];
    }
    if ( v125 )
    {
      Mso::UrlReputation::AddAppDetailsAndBase64Encode(v165, 0);
      if ( v166 )
      {
        std::wstring::wstring(&Src, L"clickparams=");
        v34 = (_QWORD *)StringUtil::UrlEncode(&v161, v165);
        if ( v34[3] > 7u )
          v34 = (_QWORD *)*v34;
        std::wstring::append(&Src, v34);
        std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(&v161);
        v35 = AddQueryParam(pszFirst, &Src);
        v124 = v35;
        if ( v35 < 0 )
        {
          EtwTraceErrorTag((unsigned int)v35, 506843299);
          std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(&Src);
          std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v165);
          goto LABEL_267;
        }
        std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(&Src);
        v15 = pszFirst[0];
      }
      std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v165);
    }
  }
  if ( v6 )
  {
    v161 = &v124;
    v162 = v152;
    v163 = 1;
    if ( v137 )
    {
      v36 = v154;
      if ( v15 )
      {
        v37 = v15;
        v23 = v15;
      }
      else
      {
        v37 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
      }
      (*(void (__fastcall **)(_QWORD, const wchar_t *, int *, _QWORD))(**((_QWORD **)v154 + 55) + 40LL))(
        *((_QWORD *)v154 + 55),
        v37,
        &v142,
        0);
      v38 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
      if ( v23 )
        v38 = v23;
      v23 = 0;
      v39 = CBackgroundUrlLauncher::HrMakeFgCall(v36, 0, v155, v38, 0);
      v124 = v39;
      if ( v39 < 0 )
      {
        v40 = 1651926838;
LABEL_72:
        EtwTraceErrorTag((unsigned int)v39, v40);
        sub_141855BC0(&v161);
        goto LABEL_267;
      }
    }
    else
    {
      v41 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
      if ( v15 )
        v41 = v15;
      v39 = MsoHrSafeToNavigateEx(v41, 0, 0, 2u, v136);
      v124 = v39;
      if ( v39 < 0 )
      {
        v40 = 1651926839;
        goto LABEL_72;
      }
    }
    sub_141855BC0(&v161);
  }
  v42 = v133;
  if ( v133 == 3 )
  {
    VariableLengthBuffer<wchar_t>::EnsureLength(&v140);
    if ( HIDWORD(v141) )
    {
      v161 = &v124;
      v162 = v152;
      v163 = 1;
      v43 = StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::Find(pszFirst, L"#");
      v15 = pszFirst[0];
      if ( v43 > 0 )
      {
        *(_QWORD *)v129 = 0;
        *(_QWORD *)&v164.Data1 = 0;
        *(_QWORD *)v164.Data4 = 0;
        v132 = 0u;
        v44 = 0;
        v45 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
        if ( pszFirst[0] )
          v45 = pszFirst[0];
        v46 = StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrDup(&v164, v45);
        v124 = v46;
        if ( v46 < 0 )
        {
          EtwTraceErrorTag((unsigned int)v46, 1594576);
          VariableLengthBuffer<wchar_t>::Free(&v132);
          VariableLengthBuffer<wchar_t>::Free(&v164);
          v47 = *(_QWORD *)v129;
          goto LABEL_91;
        }
        StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrReplaceAll(&v164, L"#", L"%23");
        MsoHrCreateUrlSimple((struct IMsoUrl **)v129, 0);
        v48 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
        if ( v15 )
          v48 = v15;
        if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, _QWORD, _QWORD, __int64))(**(_QWORD **)v129 + 40LL))(
               *(_QWORD *)v129,
               v48,
               pcchPath[0],
               0,
               1) >= 0 )
        {
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v129 + 64LL))(*(_QWORD *)v129);
          v49 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v129 + 648LL))(*(_QWORD *)v129);
          v124 = StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrDup(&v132, v49);
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v129 + 72LL))(*(_QWORD *)v129);
          v23 = (const wchar_t *)v132;
        }
        if ( (v124 & 0x80000000) != 0 )
        {
          EtwTraceErrorTag(v124, 1594577);
          VariableLengthBuffer<wchar_t>::Free(&v132);
          VariableLengthBuffer<wchar_t>::Free(&v164);
          v47 = *(_QWORD *)v129;
          *(_QWORD *)v129 = 0;
LABEL_91:
          if ( v47 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
          goto LABEL_93;
        }
        if ( v23 )
          v44 = v23;
        else
          v23 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
        if ( MsoSHGetFileInfoW(v23, 0x10u, &v172, 0x2B8u, 0x800u) )
        {
          LODWORD(v130) = 1;
          v50 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
          if ( *(_QWORD *)&v164.Data1 )
            v50 = *(const wchar_t **)&v164.Data1;
          StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrDup(pszFirst, v50);
          v51 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
          if ( v44 )
            v51 = v44;
          StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrDup(&v140, v51);
          v15 = pszFirst[0];
        }
        VariableLengthBuffer<wchar_t>::Free(&v132);
        VariableLengthBuffer<wchar_t>::Free(&v164);
        v52 = *(_QWORD *)v129;
        *(_QWORD *)v129 = 0;
        if ( v52 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      }
      if ( v137 )
      {
        v53 = v140;
        if ( !(_DWORD)v130 )
        {
          if ( v140 )
          {
            v54 = v140;
            v55 = v140;
          }
          else
          {
            v54 = (wchar_t *)&VariableLengthBuffer<wchar_t>::s_szEmpty;
            v55 = 0;
          }
          if ( !MsoSHGetFileInfoW(v54, 0x10u, &v172, 0x2B8u, 0x800u) )
          {
            if ( v55 )
              v14 = v55;
            v124 = HrReportErrorTag(-2147467259, 1966714, v14, 0x32373369u);
            DelayDisplayErrorContext(v124, 2);
            v124 = 1;
            goto LABEL_93;
          }
        }
        v56 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
        if ( v53 )
          v56 = v53;
        v57 = CBackgroundUrlLauncher::HrMakeFgCall(v154, 1u, v155, v56, &v172);
        v124 = v57;
        if ( v57 < 0 )
        {
          v58 = 842478442;
LABEL_119:
          EtwTraceErrorTag((unsigned int)v57, v58);
LABEL_93:
          sub_141855BE8(&v161);
          goto LABEL_267;
        }
      }
      else
      {
        v59 = (wchar_t *)&VariableLengthBuffer<wchar_t>::s_szEmpty;
        if ( v140 )
          v59 = v140;
        v57 = HrAskUserOpenSave(v136, v59, 0);
        v124 = v57;
        if ( v57 < 0 )
        {
          v58 = 842478443;
          goto LABEL_119;
        }
      }
      if ( (v57 & 0x800FFFFF) == 1 )
        goto LABEL_93;
      sub_141855BE8(&v161);
      v42 = v133;
    }
  }
  v60 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
  if ( v15 )
    v60 = v15;
  MsoFRegSetWz((const struct _msoreg *)&vmsoridUseRWHlinkNavigation, v60);
  MsoFRegSetDw((const struct _msoreg *)&vmsoridUseRWOSHlinkNavigation, 1u);
  ThreadLocalStoragePointer = (__int64 *)NtCurrentTeb()->ThreadLocalStoragePointer;
  v62 = *ThreadLocalStoragePointer;
  if ( dword_14274D3A8 > *(_DWORD *)(*ThreadLocalStoragePointer + 8) )
  {
    Init_thread_header(&dword_14274D3A8);
    if ( dword_14274D3A8 == -1 )
    {
      byte_14274D3AC = Mso::ProtocolHandlers::IsOpeningOfficeLinksFromSupportedAppsEnabled(v63);
      Init_thread_footer(&dword_14274D3A8);
    }
  }
  if ( dword_14274D3B0 > *(_DWORD *)(v62 + 8) )
  {
    Init_thread_header(&dword_14274D3B0);
    if ( dword_14274D3B0 == -1 )
    {
      byte_14274D3B4 = Mso::ProtocolHandlers::IsFlightToUpdateUrlWithCGuidEnabled(v64);
      Init_thread_footer(&dword_14274D3B0);
    }
  }
  *(_QWORD *)pcchPath = 0;
  if ( v42 == 1 && (byte_14274D3AC || byte_14274D3B4) )
  {
    if ( v15 )
    {
      v65 = v15;
      v66 = v15;
    }
    else
    {
      v65 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
      v66 = 0;
    }
    if ( v65 && *v65 )
    {
      v67 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
      if ( v66 )
        v67 = v66;
      if ( (int)MsoHrCreateUrlSimpleFromUser(pcchPath, v67, 0, 0, 1, 0) >= 0 )
      {
        v68 = Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(pcchPath);
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v68 + 152LL))(v68) == 1 )
        {
          v163 = 0;
          Src = 0;
          v169 = _mm_load_si128((const __m128i *)&_xmm);
          LOWORD(Src) = 0;
          LOBYTE(v69) = 1;
          OGuid::Create(&Src, v69);
          p_Src = &Src;
          if ( v169.m128i_i64[1] > 7uLL )
            LOBYTE(p_Src) = Src;
          v122 = (char)p_Src;
          LOBYTE(v121) = (_BYTE)String1;
          v71 = (__int64 *)Mso::ProtocolHandlers::AddLinksOpenRightActivityAndReturnCommandParams(
                             &v136,
                             *(_QWORD *)pcchPath,
                             "HrLaunchUrl",
                             v7);
          v72 = *v71;
          *v71 = 0;
          v73 = v126;
          v126 = v72;
          if ( v73 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
          v74 = v136;
          if ( v136 )
          {
            v136 = 0;
            (*(void (__fastcall **)(HWND))(*(_QWORD *)v74 + 16LL))(v74);
          }
          if ( v126 && *(_BYTE *)(Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(&v126) + 870) )
          {
            v75 = mso40uiWin32Client_32195(&v132, 1023639);
            if ( v163 )
            {
              *(_QWORD *)v161 = v162;
              v163 = 0;
            }
            v161 = *(unsigned int **)v75;
            v162 = *(_BYTE **)(v75 + 8);
            *(_QWORD *)v75 = v75 + 8;
            v163 = 1;
            *(_QWORD *)v132 = *((_QWORD *)&v132 + 1);
          }
          v76 = (unsigned __int8)mso40uiWin32Client_8443();
          EventWriteOutllib_LinksInformation(
            v126 != 0,
            (unsigned __int8)byte_14274D3AC,
            (unsigned __int8)byte_14274D3B4,
            v76);
          if ( v126 )
          {
            v77 = *(_DWORD *)(Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(&v126) + 876);
            v78 = *(unsigned __int8 *)(Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(&v126) + 868);
            v79 = *(unsigned __int8 *)(Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(&v126) + 864);
            v80 = Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(&v126);
            EventWriteOutllib_CommandInfoData(*(unsigned __int8 *)(v80 + 870), v79, v78, v77);
            v9 = (struct Mso::Authentication::IOfficeIdentity *)v143;
            v42 = v133;
          }
          if ( !(_BYTE)v76 )
            goto LABEL_232;
          if ( !(unsigned __int8)Outlook::Ripcord<3224568>::getValue() )
            goto LABEL_184;
          if ( !v126 )
          {
LABEL_232:
            std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(&Src);
            if ( v163 )
              *(_QWORD *)v161 = v162;
            goto LABEL_234;
          }
          if ( !*(_BYTE *)(Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(&v126) + 864)
            || !*(_DWORD *)(Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(&v126) + 876) )
          {
LABEL_184:
            if ( v126 )
            {
              if ( *(_BYTE *)(Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(&v126) + 864) && byte_14274D3AC )
              {
                v165[0] = &v124;
                v165[1] = v152;
                LOBYTE(v166) = 1;
                v130 = 0;
                v87 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
                if ( v15 )
                  v87 = v15;
                v88 = MsoHrHlinkCreateFromString(v87, 0, 0, 0, 0, 0, &IID_IHlink, (void **)&v130, 0x254E796u);
                v124 = v88;
                if ( v88 < 0 )
                {
                  EtwTraceErrorTag((unsigned int)v88, 38081558);
                  v90 = v130;
                  if ( v130 )
                  {
                    v130 = 0;
                    ((void (__fastcall *)(struct IHlink *))v90->lpVtbl->Release)(v90);
                  }
                  sub_141855C10(v165);
                  goto LABEL_171;
                }
                LOBYTE(v89) = 59;
                if ( (unsigned __int8)Mso::Hyperlink::IsM365BrowserLinkOpeningEnabled(v89) )
                {
                  v91 = (_QWORD *)((char *)a2 + 200);
                  if ( *((_QWORD *)a2 + 28) > 7u )
                    v91 = (_QWORD *)*v91;
                  *(_QWORD *)v144 = v91;
                  v145 = L"outlook";
                  v146 = sub_140E116A8();
                  v147 = 59;
                  v148 = 0;
                  v149 = 0;
                  v150 = 0;
                  v151 = 0;
                  v132 = 0;
                  LOBYTE(v92) = 59;
                  if ( (unsigned __int8)Mso::Hyperlink::EnableM365ProtocolByDefault(v92) )
                  {
                    v93 = std::make_shared<m365_browser::phase_1::M365BrowserDelegateImpl,>(&v164);
                    std::shared_ptr<MeetingAttendeeGridDpiDetails>::operator=(&v132, v93);
                    std::shared_ptr<Outlook::Search::IFindPaneAccessorWeakRef>::~shared_ptr<Outlook::Search::IFindPaneAccessorWeakRef>(&v164);
                    v151 = v132;
                  }
                  if ( v135 )
                    CheckpointStopwatch::Checkpoint(v135, UrlLaunchCheckpoints::HyperlinkNavigate_WithContext);
                  v94 = (const wchar_t *)((char *)a2 + 168);
                  if ( *((_QWORD *)a2 + 24) > 7u )
                    v94 = *(const wchar_t **)v94;
                  v95 = (const wchar_t *)((char *)a2 + 136);
                  if ( *((_QWORD *)a2 + 20) > 7u )
                    v95 = *(const wchar_t **)v95;
                  v124 = MsoHrHlinkNavigateWithSrcInfoAndMsgCtx(
                           v130,
                           0,
                           2u,
                           0,
                           0,
                           0,
                           v95,
                           v94,
                           v9,
                           (struct m365_browser::M365BrowserParams *)v144,
                           0x1E8998C7u);
                  std::shared_ptr<Outlook::Search::IFindPaneAccessorWeakRef>::~shared_ptr<Outlook::Search::IFindPaneAccessorWeakRef>(&v132);
                }
                else
                {
                  if ( v135 )
                    CheckpointStopwatch::Checkpoint(v135, UrlLaunchCheckpoints::HyperlinkNavigate_WithSource);
                  v96 = (const wchar_t *)((char *)a2 + 168);
                  if ( *((_QWORD *)a2 + 24) > 7u )
                    v96 = *(const wchar_t **)v96;
                  v97 = (const wchar_t *)((char *)a2 + 136);
                  if ( *((_QWORD *)a2 + 20) > 7u )
                    v97 = *(const wchar_t **)v97;
                  v124 = MsoHrHlinkNavigateWithSourceInfo(v130, 0, 2u, 0, 0, 0, v97, v96, v9, 0x1F0C43DAu);
                }
                v98 = Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(&v126);
                EventWriteOutllib_CallMsoHrHlinkNavigateWithAccount(v124, *(unsigned __int8 *)(v98 + 868));
                if ( !*(_BYTE *)(Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(&v126) + 868)
                  || v124 != -2147467259 )
                {
                  v105 = v130;
                  if ( v130 )
                  {
                    v130 = 0;
                    ((void (__fastcall *)(struct IHlink *))v105->lpVtbl->Release)(v105);
                  }
                  sub_141855C10(v165);
                  goto LABEL_228;
                }
                v99 = v130;
                if ( v130 )
                {
                  v130 = 0;
                  ((void (__fastcall *)(struct IHlink *))v99->lpVtbl->Release)(v99);
                }
                sub_141855C10(v165);
              }
              if ( v126
                && *(_BYTE *)(Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(&v126) + 864)
                && !*(_BYTE *)(Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(&v126) + 868)
                && byte_14274D3B4 )
              {
                v100 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
                if ( v15 )
                  v100 = v15;
                std::wstring::wstring(v165, v100);
                Mso::ProtocolHandlers::AppendLORQueryParamToUrl(v165, &v126);
                v101 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v165);
                v102 = StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrDup(pszFirst, v101);
                v124 = v102;
                if ( v102 < 0 )
                {
                  HandleCORgError_Impl(0, v103, v104, 0, (bool)v121, v122, 0, v123, 0x26548DAu, v102, (int *)&v124);
                  std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v165);
LABEL_228:
                  std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(&Src);
                  if ( v163 )
                  {
                    *(_QWORD *)v161 = v162;
                    v163 = 0;
                  }
                  goto LABEL_230;
                }
                std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v165);
                v15 = pszFirst[0];
              }
            }
            goto LABEL_232;
          }
          v82 = &Src;
          if ( v169.m128i_i64[1] > 7uLL )
            v82 = (__int128 *)Src;
          CBackgroundUrlLauncher::GetODSPLinkTelemetryQueryParamsString(
            v81,
            (unsigned int)v165,
            v126,
            (_DWORD)v138,
            (__int64)String1,
            (__int64)v82);
          if ( *(_BYTE *)(Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(&v126) + 868) )
          {
            if ( (int)StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::Find(pszFirst, L"&reserved=0") > 0 )
            {
              v86 = v165;
              if ( v167 > 7 )
                v86 = (_QWORD *)v165[0];
              Param = StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrReplaceAll(pszFirst, L"reserved=0", v86);
              v124 = Param;
              if ( Param < 0 )
              {
                v84 = 506843297;
                goto LABEL_170;
              }
            }
            else
            {
              Param = AddQueryParam(pszFirst, v165);
              v124 = Param;
              if ( Param < 0 )
              {
                v84 = 506843298;
LABEL_170:
                EtwTraceErrorTag((unsigned int)Param, v84);
                std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v165);
LABEL_171:
                std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(&Src);
                if ( v163 )
                {
                  *(_QWORD *)v161 = v162;
                  v163 = 0;
                }
                v85 = *(_QWORD *)pcchPath;
                if ( *(_QWORD *)pcchPath )
                {
                  *(_QWORD *)pcchPath = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
                }
                goto LABEL_267;
              }
            }
          }
          else
          {
            if ( !v166 )
            {
LABEL_183:
              std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v165);
              goto LABEL_184;
            }
            Param = AddQueryParam(pszFirst, v165);
            v124 = Param;
            if ( Param < 0 )
            {
              v84 = 506843296;
              goto LABEL_170;
            }
          }
          v15 = pszFirst[0];
          goto LABEL_183;
        }
      }
    }
  }
LABEL_234:
  Mso::TCntPtr<CAttachmentHandlerActivationHost>::~TCntPtr<CAttachmentHandlerActivationHost>(pcchPath);
  pExecInfo.cbSize = 112;
  pExecInfo.nShow = 1;
  if ( v15 )
  {
    v106 = v15;
    v107 = v15;
  }
  else
  {
    v106 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
    v107 = 0;
  }
  pExecInfo.lpFile = v106;
  pExecInfo.fMask = 1280;
  if ( v42 == 3 )
  {
    pcchPath[0] = 260;
    if ( v107 )
      v14 = v107;
    if ( PathCreateFromUrlW(v14, pszPath, pcchPath, 0) >= 0 )
    {
      FileAttributesW = GetFileAttributesW(pszPath);
      if ( FileAttributesW != -1 && (FileAttributesW & 0x10) != 0 )
      {
        pExecInfo.lpParameters = &FullPath;
        pExecInfo.lpVerb = L"explore";
        pExecInfo.fMask |= 1u;
        pExecInfo.lpClass = L"Folder";
      }
    }
  }
  else
  {
    LOBYTE(v107) = 59;
    if ( (unsigned __int8)Mso::Hyperlink::IsM365BrowserLinkOpeningEnabled(v107) && v134 )
    {
      LODWORD(v130) = 0;
      if ( v9 )
        v109 = (const WCHAR *)(*(__int64 (__fastcall **)(struct Mso::Authentication::IOfficeIdentity *))(*(_QWORD *)v9 + 16LL))(v9);
      else
        v109 = &FullPath;
      if ( v9 )
        v110 = (*(__int64 (__fastcall **)(struct Mso::Authentication::IOfficeIdentity *))(*(_QWORD *)v9 + 40LL))(v9);
      else
        v110 = 0;
      if ( v15 )
        v14 = v15;
      Mso::Url::CreateFromUser(pcchPath, v14);
      *(_QWORD *)v144 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)a2 + 200);
      v145 = L"outlook";
      v146 = sub_140E116A8();
      v147 = 59;
      v148 = 0;
      v149 = 0;
      v150 = 0;
      v151 = 0;
      v132 = 0;
      LOBYTE(v111) = 59;
      if ( (unsigned __int8)Mso::Hyperlink::EnableM365ProtocolByDefault(v111) )
      {
        v112 = std::make_shared<m365_browser::phase_1::M365BrowserDelegateImpl,>(&v164);
        std::shared_ptr<MeetingAttendeeGridDpiDetails>::operator=(&v132, v112);
        std::shared_ptr<Outlook::Search::IFindPaneAccessorWeakRef>::~shared_ptr<Outlook::Search::IFindPaneAccessorWeakRef>(&v164);
        v151 = v132;
      }
      if ( v135 )
        CheckpointStopwatch::Checkpoint(v135, UrlLaunchCheckpoints::OpenInBrowser);
      v122 = 0;
      v121 = v144;
      v113 = Mso::Hyperlink::OpenUrlInBrowser(&v136, *(_QWORD *)pcchPath, v109, v110);
      v143 = &v130;
      sub_1418557E0(v113, &v138, v114, &v143);
      Mso::TCntPtr<CAttachmentHandlerActivationHost>::~TCntPtr<CAttachmentHandlerActivationHost>(&v138);
      Mso::TCntPtr<CAttachmentHandlerActivationHost>::~TCntPtr<CAttachmentHandlerActivationHost>(&v136);
      EventWriteOutllib_CallOpenUrlInBrowser();
      if ( (int)v130 >= 0 )
      {
        std::shared_ptr<Outlook::Search::IFindPaneAccessorWeakRef>::~shared_ptr<Outlook::Search::IFindPaneAccessorWeakRef>(&v132);
LABEL_230:
        Mso::TCntPtr<CAttachmentHandlerActivationHost>::~TCntPtr<CAttachmentHandlerActivationHost>(pcchPath);
        goto LABEL_267;
      }
      std::shared_ptr<Outlook::Search::IFindPaneAccessorWeakRef>::~shared_ptr<Outlook::Search::IFindPaneAccessorWeakRef>(&v132);
      Mso::TCntPtr<CAttachmentHandlerActivationHost>::~TCntPtr<CAttachmentHandlerActivationHost>(pcchPath);
    }
  }
  if ( v135 )
    CheckpointStopwatch::Checkpoint(v135, UrlLaunchCheckpoints::__use_OlkShellExecute__);
  v124 = OlkShellExecuteExW(&pExecInfo, 1);
  EventWriteOutllib_CallOlkShellExecute(v124);
  if ( (v124 & 0x80000000) == 0 )
  {
    if ( (unsigned __int64)pExecInfo.hInstApp - 1 <= 0x1F )
    {
      v124 = -2147467259;
      HandleCORgError_Impl(0, v115, v116, 0, (bool)v121, v122, 0, v123, 0x38786E70u, -2147467259, (int *)&v124);
    }
  }
  else
  {
    HandleCORgError_Impl(0, v115, v116, 0, (bool)v121, v122, 0, v123, 0x1F20C183u, v124, (int *)&v124);
  }
LABEL_267:
  if ( v135 )
    CheckpointStopwatch::Checkpoint(v135, UrlLaunchCheckpoints::URLLaunch_Complete);
  if ( !*(_BYTE *)(Mso::Telemetry::Activity::Result(v152) + 432) )
    Mso::Telemetry::SetActivityResultHr((Mso::Telemetry *)v152, (struct Mso::Telemetry::Activity *)v124, v117);
  CloseHandle(pExecInfo.hProcess);
  v118 = v124;
  Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)v152);
  sub_140E19870(v157);
  v119 = v126;
  if ( v126 )
  {
    v126 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v119 + 16LL))(v119);
  }
  std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(&v170);
  VariableLengthBuffer<wchar_t>::Free(&v140);
  VariableLengthBuffer<wchar_t>::Free(pszFirst);
  std::unique_ptr<OfficeExtension::ServerRuntime::IRichApiMessageEntry>::~unique_ptr<OfficeExtension::ServerRuntime::IRichApiMessageEntry>(&v135);
  return v118;
}

```

## disassembly

```asm
0x140ec4a40  mov     [rsp-8+arg_10], rbx
0x140ec4a45  push    rbp
0x140ec4a46  push    rsi
0x140ec4a47  push    rdi
0x140ec4a48  push    r12
0x140ec4a4a  push    r13
0x140ec4a4c  push    r14
0x140ec4a4e  push    r15
0x140ec4a50  lea     rbp, [rsp-14B0h]
0x140ec4a58  mov     eax, 15B0h
0x140ec4a5d  call    _alloca_probe
0x140ec4a62  sub     rsp, rax
0x140ec4a65  mov     rax, cs:__security_cookie
0x140ec4a6c  xor     rax, rsp
0x140ec4a6f  mov     [rbp+14E0h+var_40], rax
0x140ec4a76  mov     r12, rdx
0x140ec4a79  mov     [rbp+14E0h+var_14A0], rcx
0x140ec4a7d  mov     rcx, [rdx+0E8h]
0x140ec4a84  xor     r15d, r15d
0x140ec4a87  mov     [rdx+0E8h], r15
0x140ec4a8e  mov     [rbp+14E0h+var_1528], rcx
0x140ec4a92  test    rcx, rcx
0x140ec4a95  jz      short loc_140EC4AA3
0x140ec4a97  mov     rdx, cs:?URLLaunch@UrlLaunchCheckpoints@@2V?$StringLiteral@D@StringLiterals@Mso@@B; Mso::StringLiterals::StringLiteral<char> const UrlLaunchCheckpoints::URLLaunch
0x140ec4a9e  call    ?Checkpoint@CheckpointStopwatch@@QEAAXV?$StringLiteral@D@StringLiterals@Mso@@@Z; CheckpointStopwatch::Checkpoint(Mso::StringLiterals::StringLiteral<char>)
0x140ec4aa3  mov     rbx, [r12+8]
0x140ec4aa8  mov     r14, [r12]
0x140ec4aac  mov     [rbp+14E0h+var_1498], r14
0x140ec4ab0  mov     edi, 1
0x140ec4ab5  mov     [rbp+14E0h+var_1560], edi
0x140ec4ab8  lea     r13, [r12+20h]
0x140ec4abd  mov     [rbp+14E0h+var_1510], r13
0x140ec4ac1  cmp     qword ptr [r13+18h], 7
0x140ec4ac6  jbe     short loc_140EC4AD0
0x140ec4ac8  mov     r13, [r13+0]
0x140ec4acc  mov     [rbp+14E0h+var_1510], r13
0x140ec4ad0  lea     rax, [r12+40h]
0x140ec4ad5  cmp     qword ptr [rax+18h], 7
0x140ec4ada  jbe     short loc_140EC4ADF
0x140ec4adc  mov     rax, [rax]
0x140ec4adf  mov     [rbp+14E0h+String1], rax
0x140ec4ae3  mov     al, [r12+60h]
0x140ec4ae8  mov     byte ptr [rsp+15E0h+var_1580+4], al
0x140ec4aec  mov     rsi, [r12+68h]
0x140ec4af1  mov     [rbp+14E0h+var_14E8], rsi
0x140ec4af5  mov     rax, [r12+78h]
0x140ec4afa  mov     [rbp+14E0h+var_14A8], rax
0x140ec4afe  call    cs:__imp_GetCurrentThreadId
0x140ec4b04  mov     ecx, r15d
0x140ec4b07  cmp     eax, cs:?g_dwMainThreadId@@3KA; ulong g_dwMainThreadId
0x140ec4b0d  setnz   cl
0x140ec4b10  mov     [rbp+14E0h+var_1518], ecx
0x140ec4b13  mov     rax, r15
0x140ec4b16  test    ecx, ecx
0x140ec4b18  cmovz   rax, r14
0x140ec4b1c  mov     [rbp+14E0h+var_1520], rax
0x140ec4b20  mov     rax, [rbx]
0x140ec4b23  mov     rcx, rbx
0x140ec4b26  mov     rax, [rax+98h]
0x140ec4b2d  call    cs:__guard_dispatch_icall_fptr
0x140ec4b33  mov     r14d, eax
0x140ec4b36  mov     [rbp+14E0h+var_1530], eax
0x140ec4b39  mov     eax, r15d
0x140ec4b3c  cmp     r14d, edi
0x140ec4b3f  setbe   al
0x140ec4b42  mov     [rbp+14E0h+var_152C], eax
0x140ec4b45  mov     [rbp+14E0h+pszFirst], r15
0x140ec4b49  mov     [rbp+14E0h+var_1548], r15
0x140ec4b4d  mov     [rbp+14E0h+var_1500], r15
0x140ec4b51  mov     [rbp+14E0h+var_14F8], r15
0x140ec4b55  xorps   xmm0, xmm0
0x140ec4b58  movups  [rbp+14E0h+var_1370], xmm0
0x140ec4b5f  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140ec4b67  movdqu  [rbp+14E0h+var_1360], xmm1
0x140ec4b6f  mov     word ptr [rbp+14E0h+var_1370], r15w
0x140ec4b77  xor     edx, edx; Val
0x140ec4b79  mov     r8d, 2B8h; Size
0x140ec4b7f  lea     rcx, [rbp+14E0h+var_1350]; void *
0x140ec4b86  call    memset_0
0x140ec4b8b  mov     dword ptr [rbp+14E0h+var_1558], r15d
0x140ec4b8f  mov     [rbp+14E0h+var_14F0], r15d
0x140ec4b93  mov     [rsp+15E0h+var_1578], r15
0x140ec4b98  lea     rax, [rsp+15E0h+var_1578]
0x140ec4b9d  mov     [rbp+14E0h+var_1480], rax
0x140ec4ba1  lea     rax, [rbp+14E0h+String1]
0x140ec4ba5  mov     [rbp+14E0h+var_1478], rax
0x140ec4ba9  lea     rax, [rbp+14E0h+var_14A8]
0x140ec4bad  mov     [rbp+14E0h+var_1470], rax
0x140ec4bb1  lea     rax, [rbp+14E0h+var_1528]
0x140ec4bb5  mov     [rbp+14E0h+var_1468], rax
0x140ec4bb9  mov     [rbp+14E0h+var_1460], 1
0x140ec4bc0  mov     edx, 2
0x140ec4bc5  lea     rcx, [rbp+14E0h+var_1458]
0x140ec4bcc  call    ??0EventFlags@Telemetry@Mso@@QEAA@W4DataCategories@12@@Z; Mso::Telemetry::EventFlags::EventFlags(Mso::Telemetry::DataCategories)
0x140ec4bd1  lea     rcx, off_14217AAC0
0x140ec4bd8  mov     [rbp+14E0h+var_1490], rcx
0x140ec4bdc  lea     rcx, aLaunchurlresul; "LaunchUrlResult"
0x140ec4be3  mov     [rbp+14E0h+var_1488], rcx
0x140ec4be7  mov     r8, rax; struct Mso::Telemetry::EventFlags *
0x140ec4bea  lea     rdx, [rbp+14E0h+var_1490]; struct Mso::Telemetry::EventName *
0x140ec4bee  lea     rcx, [rbp+14E0h+var_14B8]; this
0x140ec4bf2  call    ??0Activity@Telemetry@Mso@@QEAA@AEBUEventName@12@AEBUEventFlags@12@@Z; Mso::Telemetry::Activity::Activity(Mso::Telemetry::EventName const &,Mso::Telemetry::EventFlags const &)
0x140ec4bf7  xor     edx, edx; Val
0x140ec4bf9  lea     r8d, [rdx+70h]; Size
0x140ec4bfd  lea     rcx, [rbp+14E0h+pExecInfo]; void *
0x140ec4c04  call    memset_0
0x140ec4c09  mov     rax, [rbx]
0x140ec4c0c  mov     rcx, rbx
0x140ec4c0f  mov     rax, [rax+40h]
0x140ec4c13  call    cs:__guard_dispatch_icall_fptr
0x140ec4c19  mov     rax, [rbx]
0x140ec4c1c  mov     rcx, rbx
0x140ec4c1f  mov     rax, [rax+80h]
0x140ec4c26  call    cs:__guard_dispatch_icall_fptr
0x140ec4c2c  mov     [rsp+15E0h+pcchPath], eax
0x140ec4c30  mov     rcx, [rbx]
0x140ec4c33  mov     rax, [rcx+88h]
0x140ec4c3a  mov     rcx, rbx
0x140ec4c3d  call    cs:__guard_dispatch_icall_fptr
0x140ec4c43  mov     rdx, rax
0x140ec4c46  lea     rcx, [rbp+14E0h+pszFirst]
0x140ec4c4a  call    ?HrDup@?$StringTemplate@_WV?$VariableLengthBuffer@_W@@@@QEAAJPEB_W@Z; StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrDup(wchar_t const *)
0x140ec4c4f  mov     dword ptr [rsp+15E0h+var_1580], eax
0x140ec4c53  lea     r15, ?s_szEmpty@?$VariableLengthBuffer@_W@@2QB_WB; wchar_t const near * const VariableLengthBuffer<wchar_t>::s_szEmpty
0x140ec4c5a  test    eax, eax
0x140ec4c5c  js      loc_140EC4D63
0x140ec4c62  xor     edx, edx; Val
0x140ec4c64  mov     r8d, 1048h; Size
0x140ec4c6a  lea     rcx, [rbp+14E0h+pszPath]; void *
0x140ec4c71  call    memset_0
0x140ec4c76  cmp     r14d, 3
0x140ec4c7a  jnz     short loc_140EC4CE7
0x140ec4c7c  mov     r14, [rbp+14E0h+pszFirst]
0x140ec4c80  test    r14, r14
0x140ec4c83  jz      short loc_140EC4C8D
0x140ec4c85  mov     rcx, r14
0x140ec4c88  mov     rdi, r14
0x140ec4c8b  jmp     short loc_140EC4C92
0x140ec4c8d  mov     rcx, r15; wchar_t *
0x140ec4c90  xor     edi, edi
0x140ec4c92  call    ?IsFileZoneLocalIntranetOrTrusted@@YA_NPEB_W@Z; IsFileZoneLocalIntranetOrTrusted(wchar_t const *)
0x140ec4c97  test    al, al
0x140ec4c99  jnz     short loc_140EC4CBC
0x140ec4c9b  mov     r8, r15
0x140ec4c9e  test    rdi, rdi
0x140ec4ca1  cmovnz  r8, rdi; wchar_t *
0x140ec4ca5  mov     edx, 1D0097h; int
0x140ec4caa  mov     ecx, 80004005h; int
0x140ec4caf  mov     r9d, 1E50D60Dh; unsigned int
0x140ec4cb5  call    ?HrReportErrorTag@@YAJJHPEB_WK@Z; HrReportErrorTag(long,int,wchar_t const *,ulong)
0x140ec4cba  jmp     short loc_140EC4CDB
0x140ec4cbc  mov     rax, [rbx]
0x140ec4cbf  mov     rcx, rbx
0x140ec4cc2  mov     rax, [rax+288h]
0x140ec4cc9  call    cs:__guard_dispatch_icall_fptr
0x140ec4ccf  mov     rdx, rax
0x140ec4cd2  lea     rcx, [rbp+14E0h+var_1500]
0x140ec4cd6  call    ?HrDup@?$StringTemplate@_WV?$VariableLengthBuffer@_W@@@@QEAAJPEB_W@Z; StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrDup(wchar_t const *)
0x140ec4cdb  mov     dword ptr [rsp+15E0h+var_1580], eax
0x140ec4cdf  mov     edi, [rbp+14E0h+var_1560]
0x140ec4ce2  jmp     loc_140EC4D67
0x140ec4ce7  cmp     [rbp+14E0h+var_152C], 0
0x140ec4ceb  jz      short loc_140EC4D63
0x140ec4ced  mov     rcx, r15
0x140ec4cf0  mov     r14, [rbp+14E0h+pszFirst]
0x140ec4cf4  test    r14, r14
0x140ec4cf7  cmovnz  rcx, r14
0x140ec4cfb  mov     r8d, 824h
0x140ec4d01  lea     rdx, [rbp+14E0h+pszPath]
0x140ec4d08  call    cs:__imp_?MsoFConvertHttpToProtocolHandler@@YA_NPEB_WPEA_WH@Z; MsoFConvertHttpToProtocolHandler(wchar_t const *,wchar_t *,int)
0x140ec4d0e  test    al, al
0x140ec4d10  jz      short loc_140EC4D67
0x140ec4d12  lea     rdx, [rbp+14E0h+pszPath]
0x140ec4d19  lea     rcx, [rbp+14E0h+var_1560]
0x140ec4d1d  call    ?CreateFromUser@Url@Mso@@YA?AV?$TCntPtr@UIMsoUrl@@@2@PEB_W@Z; Mso::Url::CreateFromUser(wchar_t const *)
0x140ec4d22  lea     rcx, [rbp+14E0h+var_1560]
0x140ec4d26  call    ??C?$TCntPtr@UISelectionProvider@VirtualList@@@Mso@@QEBAPEAUISelectionProvider@VirtualList@@XZ; Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(void)
0x140ec4d2b  mov     rdx, rax
0x140ec4d2e  mov     rcx, [rax]
0x140ec4d31  mov     rax, [rcx+250h]
0x140ec4d38  mov     rcx, rdx
0x140ec4d3b  call    cs:__guard_dispatch_icall_fptr
0x140ec4d41  mov     [rbp+14E0h+var_152C], eax
0x140ec4d44  xor     edi, edi
0x140ec4d46  lea     rdx, [rbp+14E0h+pszPath]
0x140ec4d4d  lea     rcx, [rbp+14E0h+pszFirst]
0x140ec4d51  call    ?HrDup@?$StringTemplate@_WV?$VariableLengthBuffer@_W@@@@QEAAJPEB_W@Z; StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrDup(wchar_t const *)
0x140ec4d56  mov     dword ptr [rsp+15E0h+var_1580], eax
0x140ec4d5a  lea     rcx, [rbp+14E0h+var_1560]; void *
0x140ec4d5e  call    ??1?$TCntPtr@VCAttachmentHandlerActivationHost@@@Mso@@QEAA@XZ; Mso::TCntPtr<CAttachmentHandlerActivationHost>::~TCntPtr<CAttachmentHandlerActivationHost>(void)
0x140ec4d63  mov     r14, [rbp+14E0h+pszFirst]
0x140ec4d67  mov     rax, [rbx]
0x140ec4d6a  mov     rcx, rbx
0x140ec4d6d  mov     rax, [rax+48h]
0x140ec4d71  call    cs:__guard_dispatch_icall_fptr
0x140ec4d77  mov     ecx, dword ptr [rsp+15E0h+var_1580]
0x140ec4d7b  xor     ebx, ebx
0x140ec4d7d  test    ecx, ecx
0x140ec4d7f  jns     short loc_140EC4D91
0x140ec4d81  mov     edx, 32367A69h
0x140ec4d86  call    cs:__imp_EtwTraceErrorTag
0x140ec4d8c  jmp     loc_140EC600E
0x140ec4d91  lea     rdx, ?g_wszOutlookBody@@3QB_WB; "Outlook-Body"
0x140ec4d98  mov     rcx, [rbp+14E0h+String1]; String1
0x140ec4d9c  call    cs:__imp__wcsicmp
0x140ec4da2  test    eax, eax
0x140ec4da4  jnz     loc_140EC4E6D
0x140ec4daa  test    r14, r14
0x140ec4dad  jz      short loc_140EC4DB7
0x140ec4daf  mov     rcx, r14
0x140ec4db2  mov     rbx, r14
0x140ec4db5  jmp     short loc_140EC4DBA
0x140ec4db7  mov     rcx, r15
0x140ec4dba  call    cs:__imp_?IsSafeLinksUrl@UrlReputation@Mso@@YA_NPEB_W@Z; Mso::UrlReputation::IsSafeLinksUrl(wchar_t const *)
0x140ec4dc0  mov     rcx, r15
0x140ec4dc3  test    al, al
0x140ec4dc5  jz      short loc_140EC4DE5
0x140ec4dc7  test    rbx, rbx
0x140ec4dca  cmovnz  rcx, rbx; pszFirst
0x140ec4dce  lea     rdx, aUrlHttps3a2f2f; "/?url=https%3A%2F%2Fteams.microsoft.com"...
0x140ec4dd5  call    cs:__imp_StrStrIW
0x140ec4ddb  xor     ebx, ebx
0x140ec4ddd  test    rax, rax
0x140ec4de0  setnz   al
0x140ec4de3  jmp     short loc_140EC4E06
0x140ec4de5  test    rbx, rbx
0x140ec4de8  cmovnz  rcx, rbx; String1
0x140ec4dec  mov     r8d, 2Ah ; '*'; MaxCount
0x140ec4df2  lea     rdx, aHttpsTeamsMicr_1; "https://teams.microsoft.com/l/meetup-jo"...
0x140ec4df9  call    cs:__imp__wcsnicmp
0x140ec4dff  xor     ebx, ebx
0x140ec4e01  test    eax, eax
0x140ec4e03  setz    al
0x140ec4e06  test    al, al
0x140ec4e08  jz      short loc_140EC4E6D
0x140ec4e0a  mov     edx, 2
0x140ec4e0f  lea     rcx, [rbp+14E0h+var_1560]
0x140ec4e13  call    ??0EventFlags@Telemetry@Mso@@QEAA@W4DataCategories@12@@Z; Mso::Telemetry::EventFlags::EventFlags(Mso::Telemetry::DataCategories)
0x140ec4e18  lea     rcx, off_14217AAC0
0x140ec4e1f  mov     qword ptr [rbp+14E0h+var_1540], rcx
0x140ec4e23  lea     rcx, aOpenjointeamsm; "OpenJoinTeamsMeetingUrl"
0x140ec4e2a  mov     qword ptr [rbp+14E0h+var_1540+8], rcx
0x140ec4e2e  mov     rdx, rax
0x140ec4e31  lea     rcx, [rbp+14E0h+var_1540]
0x140ec4e35  call    ??$SendTelemetryEvent@$$V@Telemetry@Mso@@YAXAEBUEventName@01@AEBUEventFlags@01@@Z; Mso::Telemetry::SendTelemetryEvent<>(Mso::Telemetry::EventName const &,Mso::Telemetry::EventFlags const &)
0x140ec4e3a  xorps   xmm0, xmm0
0x140ec4e3d  movups  xmmword ptr [rbp+14E0h+var_13C0.Data1], xmm0
0x140ec4e44  lea     rdx, [rbp+14E0h+var_13C0]; struct _GUID *
0x140ec4e4b  mov     rcx, [rbp+14E0h+var_14A8]; struct IOlkAccount *
0x140ec4e4f  call    ?HrGetAccountUID@@YAJPEAUIOlkAccount@@AEAU_GUID@@@Z; HrGetAccountUID(IOlkAccount *,_GUID &)
0x140ec4e54  lea     r9, [rbp+14E0h+var_13C0]; struct _GUID *
0x140ec4e5b  mov     edx, 1; unsigned int
0x140ec4e60  lea     r8d, [rdx+4]; unsigned int
0x140ec4e64  mov     ecx, dword ptr [rsp+15E0h+var_1580]; unsigned int
0x140ec4e68  call    ?EventWriteCalendar_JoinOnline@@YAKIIIPEBU_GUID@@@Z; EventWriteCalendar_JoinOnline(uint,uint,uint,_GUID const *)
0x140ec4e6d  cmp     byte ptr [rsp+15E0h+var_1580+4], bl
0x140ec4e71  jz      loc_140EC5029
0x140ec4e77  mov     ecx, 20000007h
0x140ec4e7c  call    cs:__imp_FIsFeatureEnabled
0x140ec4e82  test    al, al
0x140ec4e84  jz      loc_140EC5029
0x140ec4e8a  mov     [rbp+14E0h+var_1560], ebx
0x140ec4e8d  mov     [rsp+15E0h+var_1570], 1
0x140ec4e92  mov     byte ptr [rsp+15E0h+var_1580+4], bl
0x140ec4e96  lea     rax, [rsp+15E0h+var_1580+4]
0x140ec4e9b  mov     [rsp+15E0h+var_15C0], rax
0x140ec4ea0  lea     r9, [rsp+15E0h+var_1570]
0x140ec4ea5  lea     r8, [rbp+14E0h+pszFirst]
0x140ec4ea9  mov     rdx, r12
0x140ec4eac  call    ?ForceCheckReputation@CBackgroundUrlLauncher@@AEAAXPEAVURLObjectStruct@@AEAV?$VariableLengthString@_W@@AEA_N2@Z; CBackgroundUrlLauncher::ForceCheckReputation(URLObjectStruct *,VariableLengthString<wchar_t> &,bool &,bool &)
0x140ec4eb1  cmp     [rsp+15E0h+var_1570], bl
0x140ec4eb5  jz      loc_140EC4F49
0x140ec4ebb  lea     rdx, [r12+0A8h]
0x140ec4ec3  cmp     qword ptr [rdx+18h], 7
0x140ec4ec8  jbe     short loc_140EC4ECD
0x140ec4eca  mov     rdx, [rdx]
0x140ec4ecd  lea     rax, [r12+88h]
0x140ec4ed5  cmp     qword ptr [rax+18h], 7
0x140ec4eda  jbe     short loc_140EC4EDF
0x140ec4edc  mov     rax, [rax]
0x140ec4edf  mov     rcx, r15
0x140ec4ee2  mov     r14, [rbp+14E0h+pszFirst]
0x140ec4ee6  test    r14, r14
0x140ec4ee9  cmovnz  rcx, r14
0x140ec4eed  mov     qword ptr [rsp+15E0h+var_15B0], rdx
0x140ec4ef2  mov     qword ptr [rsp+15E0h+var_15B8], rax
0x140ec4ef7  mov     dword ptr [rsp+15E0h+var_15C0], ebx
0x140ec4efb  lea     r9, [rbp+14E0h+var_1560]
0x140ec4eff  lea     r8, [rbp+14E0h+var_1370]
0x140ec4f06  mov     rdx, [r12+68h]
0x140ec4f0b  call    cs:__imp_?GetReputationForIdentity@Safelinks@Mso@@YAJPEB_WAEAUIOfficeIdentity@Authentication@2@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAW4UrlVerdict@UrlReputation@2@W4RequestType@82@00@Z; Mso::Safelinks::GetReputationForIdentity(wchar_t const *,Mso::Authentication::IOfficeIdentity &,std::wstring &,Mso::UrlReputation::UrlVerdict &,Mso::UrlReputation::RequestType,wchar_t const *,wchar_t const *)
0x140ec4f11  test    eax, eax
0x140ec4f13  js      short loc_140EC4F3F
0x140ec4f15  cmp     [rbp+14E0h+var_1560], 0FFFFFFFFh
0x140ec4f19  jnz     short loc_140EC4F3F
0x140ec4f1b  lea     rdx, [rbp+14E0h+var_1370]
0x140ec4f22  cmp     qword ptr [rbp+14E0h+var_1360+8], 7
0x140ec4f2a  cmova   rdx, qword ptr [rbp+14E0h+var_1370]
0x140ec4f32  lea     rcx, [rbp+14E0h+pszFirst]
0x140ec4f36  call    ?HrDup@?$StringTemplate@_WV?$VariableLengthBuffer@_W@@@@QEAAJPEB_W@Z; StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrDup(wchar_t const *)
  ... truncated ...
```
