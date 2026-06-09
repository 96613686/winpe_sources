# CBackgroundUrlLauncher::HrLaunchUrl(URLObjectStruct *)

- ea: `0x140ec4af0`
- end: `0x140ec6188`
- name: `?HrLaunchUrl@CBackgroundUrlLauncher@@AEAAJPEAVURLObjectStruct@@@Z`
- size: `5784`
- prototype: `__int64 __fastcall(CBackgroundUrlLauncher *__hidden this, struct URLObjectStruct *)`
- caller_count: `2`
- callee_count: `54`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1418576e0`
- `0x141858ed0`

## callees

- `0x14001dd7c`
- `0x1400211a0`
- `0x1400255e8`
- `0x14002ba90`
- `0x14007131c`
- `0x14007efec`
- `0x1400a6c5c`
- `0x1400bb408`
- `0x1400fcac0`
- `0x140103fac`
- `0x14010aa08`
- `0x14010abac`
- `0x14010afb4`
- `0x1401aedac`
- `0x1405049f0`
- `0x140504c08`
- `0x140504c74`
- `0x140505260`
- `0x14050a2e0`
- `0x1406708f0`
- `0x1407e9990`
- `0x1407eafb0`
- `0x1407eceb0`
- `0x1409bd854`
- `0x1409bd920`
- `0x140adcb34`
- `0x140b57b60`
- `0x140c3513c`
- `0x140d1d10c`
- `0x140d21cb8`
- `0x140d57be0`
- `0x140de8534`
- `0x140dfda04`
- `0x140e11758`
- `0x140e19920`
- `0x140e6c0dc`
- `0x140e80b6c`
- `0x140e96b98`
- `0x140e9fbb0`
- `0x140eabe80`
- `0x140ebad08`
- `0x140ec4af0`
- `0x140ef1a7c`
- `0x140f2b380`
- `0x14164bfc4`
- `0x1417ac5cc`
- `0x14183fea0`
- `0x1418558a0`
- `0x141855c80`
- `0x141855ca8`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x140ec4e4c`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x140ec4e4c`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x140ec4ea9`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x140ec4ea9`
- `KERNEL32!GetFileAttributesW` at `0x140ec5e6d`
- `KERNEL32!GetFileAttributesW` at `0x140ec5e6d`
- `KERNEL32!CloseHandle` at `0x140ec60f9`
- `KERNEL32!CloseHandle` at `0x140ec60f9`
- `KERNEL32!GetCurrentThreadId` at `0x140ec4bae`
- `KERNEL32!GetCurrentThreadId` at `0x140ec4bae`
- `OLMAPI32!FIsFeatureEnabled` at `0x140ec4f2c`
- `OLMAPI32!FIsFeatureEnabled` at `0x140ec4f2c`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec4e36`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec509a`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec5161`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec5255`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec5326`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec54de`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec5905`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec5a78`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec4e36`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec509a`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec5161`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec5255`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec5326`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec54de`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec5905`
- `OLMAPI32!EtwTraceErrorTag` at `0x140ec5a78`
- `SHLWAPI!StrStrIW` at `0x140ec4e85`
- `SHLWAPI!StrStrIW` at `0x140ec4e85`
- `SHLWAPI!PathCreateFromUrlW` at `0x140ec5e58`
- `SHLWAPI!PathCreateFromUrlW` at `0x140ec5e58`
- `MSO!__imp_?MsoHrHlinkNavigateWithSrcInfoAndMsgCtx@@YAJPEAUIHlink@@PEAUIHlinkFrame@@KPEAUIBindCtx@@PEAUIBindStatusCallback@@PEAUIHlinkBrowseContext@@PEB_W5PEAUIOfficeIdentity@Authentication@Mso@@PEAUM365BrowserParams@m365_browser@@I@Z` at `0x140ec5ba8`
- `MSO!__imp_?MsoHrHlinkNavigateWithSrcInfoAndMsgCtx@@YAJPEAUIHlink@@PEAUIHlinkFrame@@KPEAUIBindCtx@@PEAUIBindStatusCallback@@PEAUIHlinkBrowseContext@@PEB_W5PEAUIOfficeIdentity@Authentication@Mso@@PEAUM365BrowserParams@m365_browser@@I@Z` at `0x140ec5ba8`
- `MSO!__imp_?GetReputationForIdentity@Safelinks@Mso@@YAJPEB_WAEAUIOfficeIdentity@Authentication@2@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAW4UrlVerdict@UrlReputation@2@W4RequestType@82@00@Z` at `0x140ec4fbb`
- `MSO!__imp_?GetReputationForIdentity@Safelinks@Mso@@YAJPEB_WAEAUIOfficeIdentity@Authentication@2@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAW4UrlVerdict@UrlReputation@2@W4RequestType@82@00@Z` at `0x140ec4fbb`
- `MSO!__imp_?MsoFConvertHttpToProtocolHandler@@YA_NPEB_WPEA_WH@Z` at `0x140ec4db8`
- `MSO!__imp_?MsoFConvertHttpToProtocolHandler@@YA_NPEB_WPEA_WH@Z` at `0x140ec4db8`
- `MSO!__imp_?MsoHrHlinkNavigateWithSourceInfo@@YAJPEAUIHlink@@PEAUIHlinkFrame@@KPEAUIBindCtx@@PEAUIBindStatusCallback@@PEAUIHlinkBrowseContext@@PEB_W5PEAUIOfficeIdentity@Authentication@Mso@@I@Z` at `0x140ec5c24`
- `MSO!__imp_?MsoHrHlinkNavigateWithSourceInfo@@YAJPEAUIHlink@@PEAUIHlinkFrame@@KPEAUIBindCtx@@PEAUIBindStatusCallback@@PEAUIHlinkBrowseContext@@PEB_W5PEAUIOfficeIdentity@Authentication@Mso@@I@Z` at `0x140ec5c24`
- `Mso98Win32Client!__imp_?AddAppDetailsAndBase64Encode@UrlReputation@Mso@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z` at `0x140ec5010`
- `Mso98Win32Client!__imp_?AddAppDetailsAndBase64Encode@UrlReputation@Mso@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z` at `0x140ec5010`
- `Mso98Win32Client!__imp_?IsSafeLinksUrl@UrlReputation@Mso@@YA_NPEB_W@Z` at `0x140ec4e6a`
- `Mso98Win32Client!__imp_?IsSafeLinksUrl@UrlReputation@Mso@@YA_NPEB_W@Z` at `0x140ec4e6a`
- `mso40uiWin32Client!__imp_?AddLinksOpenRightActivityAndReturnCommandParams@ProtocolHandlers@Mso@@YA?AV?$TCntPtr@UCommandParams@ProtocolHandlers@Mso@@@2@AEBUIMsoUrl@@PEBDPEB_W22@Z` at `0x140ec56ec`
- `mso40uiWin32Client!__imp_?AddLinksOpenRightActivityAndReturnCommandParams@ProtocolHandlers@Mso@@YA?AV?$TCntPtr@UCommandParams@ProtocolHandlers@Mso@@@2@AEBUIMsoUrl@@PEBDPEB_W22@Z` at `0x140ec56ec`
- `mso40uiWin32Client!mso40uiWin32Client_8443` at `0x140ec57a2`
- `mso40uiWin32Client!mso40uiWin32Client_8443` at `0x140ec57a2`
- `mso40uiWin32Client!mso40uiWin32Client_32195` at `0x140ec5750`
- `mso40uiWin32Client!mso40uiWin32Client_32195` at `0x140ec5750`
- `mso40uiWin32Client!__imp_?AppendLORQueryParamToUrl@ProtocolHandlers@Mso@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$TCntPtr@UCommandParams@ProtocolHandlers@Mso@@@2@@Z` at `0x140ec5cf8`
- `mso40uiWin32Client!__imp_?AppendLORQueryParamToUrl@ProtocolHandlers@Mso@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$TCntPtr@UCommandParams@ProtocolHandlers@Mso@@@2@@Z` at `0x140ec5cf8`
- `mso40uiWin32Client!__imp_?IsFlightToUpdateUrlWithCGuidEnabled@ProtocolHandlers@Mso@@YA_NXZ` at `0x140ec55c3`
- `mso40uiWin32Client!__imp_?IsFlightToUpdateUrlWithCGuidEnabled@ProtocolHandlers@Mso@@YA_NXZ` at `0x140ec55c3`
- `mso40uiWin32Client!__imp_?IsOpeningOfficeLinksFromSupportedAppsEnabled@ProtocolHandlers@Mso@@YA_NXZ` at `0x140ec5586`
- `mso40uiWin32Client!__imp_?IsOpeningOfficeLinksFromSupportedAppsEnabled@ProtocolHandlers@Mso@@YA_NXZ` at `0x140ec5586`
- `Mso30Win32Client!__imp_?EnableM365ProtocolByDefault@Hyperlink@Mso@@YA_NW4TeamEnum@AB@2@@Z` at `0x140ec5b02`
- `Mso30Win32Client!__imp_?EnableM365ProtocolByDefault@Hyperlink@Mso@@YA_NW4TeamEnum@AB@2@@Z` at `0x140ec5f6f`
- `Mso30Win32Client!__imp_?EnableM365ProtocolByDefault@Hyperlink@Mso@@YA_NW4TeamEnum@AB@2@@Z` at `0x140ec5b02`
- `Mso30Win32Client!__imp_?EnableM365ProtocolByDefault@Hyperlink@Mso@@YA_NW4TeamEnum@AB@2@@Z` at `0x140ec5f6f`
- `Mso30Win32Client!__imp_?MsoHrSafeToNavigateEx@@YAJPEB_WPEAUIHlinkSite@@KKPEAUHWND__@@@Z` at `0x140ec5197`
- `Mso30Win32Client!__imp_?MsoHrSafeToNavigateEx@@YAJPEB_WPEAUIHlinkSite@@KKPEAUHWND__@@@Z` at `0x140ec5197`
- `Mso30Win32Client!__imp_?IsM365BrowserLinkOpeningEnabled@Hyperlink@Mso@@YA_NW4TeamEnum@AB@2@@Z` at `0x140ec5aac`
- `Mso30Win32Client!__imp_?IsM365BrowserLinkOpeningEnabled@Hyperlink@Mso@@YA_NW4TeamEnum@AB@2@@Z` at `0x140ec5ebe`
- `Mso30Win32Client!__imp_?IsM365BrowserLinkOpeningEnabled@Hyperlink@Mso@@YA_NW4TeamEnum@AB@2@@Z` at `0x140ec5aac`
- `Mso30Win32Client!__imp_?IsM365BrowserLinkOpeningEnabled@Hyperlink@Mso@@YA_NW4TeamEnum@AB@2@@Z` at `0x140ec5ebe`
- `Mso30Win32Client!__imp_?OpenUrlInBrowser@Hyperlink@Mso@@YA?AV?$Future@W4LaunchBrowserResult@Hyperlink@Mso@@@2@AEBUIMsoUrl@@PEB_WW4Enum@IdP@Authentication@2@PEAUM365BrowserParams@m365_browser@@_N@Z` at `0x140ec5fd7`
- `Mso30Win32Client!__imp_?OpenUrlInBrowser@Hyperlink@Mso@@YA?AV?$Future@W4LaunchBrowserResult@Hyperlink@Mso@@@2@AEBUIMsoUrl@@PEB_WW4Enum@IdP@Authentication@2@PEAUM365BrowserParams@m365_browser@@_N@Z` at `0x140ec5fd7`
- `Mso30Win32Client!__imp_?MsoHrHlinkCreateFromString@@YAJPEB_W00PEAUIHlinkSite@@KPEAUIUnknown@@AEBU_GUID@@PEAPEAXI@Z` at `0x140ec5a63`
- `Mso30Win32Client!__imp_?MsoHrHlinkCreateFromString@@YAJPEB_W00PEAUIHlinkSite@@KPEAUIUnknown@@AEBU_GUID@@PEAPEAXI@Z` at `0x140ec5a63`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x140ec6107`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x140ec6107`
- `Mso20Win32Client!__imp_?MsoSHGetFileInfoW@@YA_KPEB_WKPEAU_SHFILEINFOW@@II@Z` at `0x140ec5399`
- `Mso20Win32Client!__imp_?MsoSHGetFileInfoW@@YA_KPEB_WKPEAU_SHFILEINFOW@@II@Z` at `0x140ec5452`
- `Mso20Win32Client!__imp_?MsoSHGetFileInfoW@@YA_KPEB_WKPEAU_SHFILEINFOW@@II@Z` at `0x140ec5399`
- `Mso20Win32Client!__imp_?MsoSHGetFileInfoW@@YA_KPEB_WKPEAU_SHFILEINFOW@@II@Z` at `0x140ec5452`
- `Mso20Win32Client!__imp_?Result@Activity@Telemetry@Mso@@QEAAAEAV?$optional@VResult@System@Office@@@std@@XZ` at `0x140ec60d7`
- `Mso20Win32Client!__imp_?Result@Activity@Telemetry@Mso@@QEAAAEAV?$optional@VResult@System@Office@@@std@@XZ` at `0x140ec60d7`
- `Mso20Win32Client!__imp_?MsoFRegSetDw@@YAHPEBU_msoreg@@K@Z` at `0x140ec554f`
- `Mso20Win32Client!__imp_?MsoFRegSetDw@@YAHPEBU_msoreg@@K@Z` at `0x140ec554f`
- `Mso20Win32Client!__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z` at `0x140ec553d`
- `Mso20Win32Client!__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z` at `0x140ec553d`
- `Mso20Win32Client!__imp_?Create@OGuid@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@Z` at `0x140ec56ae`
- `Mso20Win32Client!__imp_?Create@OGuid@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@Z` at `0x140ec56ae`
- `Mso20Win32Client!__imp_?MsoHrCreateUrlSimpleFromUser@@YAJPEAPEAUIMsoUrl@@PEB_WKPEBU1@W4MsoUrlCreateFlags@@PEAUIMsoMemHeap@@@Z` at `0x140ec5647`
- `Mso20Win32Client!__imp_?MsoHrCreateUrlSimpleFromUser@@YAJPEAPEAUIMsoUrl@@PEB_WKPEBU1@W4MsoUrlCreateFlags@@PEAUIMsoMemHeap@@@Z` at `0x140ec5647`
- `Mso20Win32Client!__imp_?MsoHrCreateUrlSimple@@YAJPEAPEAUIMsoUrl@@PEAUIMsoMemHeap@@@Z` at `0x140ec5299`
- `Mso20Win32Client!__imp_?MsoHrCreateUrlSimple@@YAJPEAPEAUIMsoUrl@@PEAUIMsoMemHeap@@@Z` at `0x140ec5299`

## string_xrefs

- `0x140ec4ea2`: `https://teams.microsoft.com/l/meetup-join/`
- `0x140ec4e7e`: `/?url=https%3A%2F%2Fteams.microsoft.com%2Fl%2Fmeetup-join%2F`
- `0x140ec4ed3`: `OpenJoinTeamsMeetingUrl`

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
  __int64 v25; // r8
  __int64 v26; // r9
  Mso::UrlReputation *v27; // rcx
  bool IsSafeLinksUrl; // al
  const WCHAR *v29; // rcx
  bool v30; // al
  __int64 v31; // rax
  int v32; // ecx
  _QWORD *v33; // rax
  const wchar_t *v34; // rcx
  __int128 *v35; // rdx
  _QWORD *v36; // rax
  int v37; // eax
  CBackgroundUrlLauncher *v38; // rdi
  const wchar_t *v39; // rdx
  const wchar_t *v40; // r9
  int v41; // eax
  __int64 v42; // rdx
  const wchar_t *v43; // rcx
  unsigned int v44; // edi
  int v45; // eax
  const wchar_t *v46; // rdi
  const wchar_t *v47; // rdx
  int v48; // eax
  __int64 v49; // rcx
  const wchar_t *v50; // rdx
  __int64 v51; // rax
  const wchar_t *v52; // rdx
  const wchar_t *v53; // rdx
  __int64 v54; // rcx
  wchar_t *v55; // rbx
  wchar_t *v56; // rcx
  wchar_t *v57; // rdi
  const wchar_t *v58; // r9
  int v59; // eax
  __int64 v60; // rdx
  wchar_t *v61; // rdx
  const wchar_t *v62; // rdx
  __int64 *ThreadLocalStoragePointer; // rax
  __int64 v64; // rbx
  Mso::ProtocolHandlers *v65; // rcx
  Mso::ProtocolHandlers *v66; // rcx
  const wchar_t *v67; // rax
  const wchar_t *v68; // rcx
  const wchar_t *v69; // rdx
  __int64 v70; // rax
  __int64 v71; // rdx
  __int128 *p_Src; // rax
  __int64 *v73; // rax
  __int64 v74; // rdx
  __int64 v75; // rcx
  HWND v76; // rcx
  __int64 v77; // rax
  int v78; // r13d
  int v79; // esi
  int v80; // edi
  int v81; // ebx
  __int64 v82; // rax
  int v83; // ecx
  __int128 *v84; // rax
  int Param; // eax
  __int64 v86; // rdx
  __int64 v87; // rcx
  _QWORD *v88; // r8
  const wchar_t *v89; // rcx
  int v90; // eax
  __int64 v91; // rcx
  struct IHlink *v92; // rcx
  _QWORD *v93; // rax
  __int64 v94; // rcx
  __int64 v95; // rax
  const wchar_t *v96; // rcx
  const wchar_t *v97; // rax
  const wchar_t *v98; // rcx
  const wchar_t *v99; // rax
  __int64 v100; // rax
  struct IHlink *v101; // rcx
  __int64 v102; // rax
  int v103; // eax
  const char *v104; // rdx
  const char *v105; // r8
  struct IHlink *v106; // rcx
  const WCHAR *v107; // rax
  const wchar_t *v108; // rcx
  DWORD FileAttributesW; // eax
  const WCHAR *v110; // rbx
  unsigned int v111; // edi
  __int64 v112; // rcx
  __int64 v113; // rax
  __int64 v114; // rax
  __int64 v115; // r8
  const char *v116; // rdx
  const char *v117; // r8
  int v118; // r8d
  unsigned int v119; // ebx
  __int64 v120; // rcx
  bool *v122; // [rsp+20h] [rbp-E0h]
  bool v123; // [rsp+28h] [rbp-D8h]
  char *v124; // [rsp+38h] [rbp-C8h]
  unsigned int v125; // [rsp+60h] [rbp-A0h] BYREF
  char v126; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v127; // [rsp+68h] [rbp-98h] BYREF
  char v128; // [rsp+70h] [rbp-90h] BYREF
  DWORD pcchPath[2]; // [rsp+78h] [rbp-88h] BYREF
  int v130[2]; // [rsp+80h] [rbp-80h] BYREF
  struct IHlink *v131; // [rsp+88h] [rbp-78h] BYREF
  PCWSTR pszFirst[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v133; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v134; // [rsp+B0h] [rbp-50h]
  int v135; // [rsp+B4h] [rbp-4Ch]
  __int64 v136; // [rsp+B8h] [rbp-48h] BYREF
  HWND v137; // [rsp+C0h] [rbp-40h] BYREF
  BOOL v138; // [rsp+C8h] [rbp-38h]
  char *v139; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t *String1; // [rsp+D8h] [rbp-28h] BYREF
  wchar_t *v141; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v142; // [rsp+E8h] [rbp-18h]
  int v143; // [rsp+F0h] [rbp-10h] BYREF
  struct IHlink **v144; // [rsp+F8h] [rbp-8h] BYREF
  bool v145[8]; // [rsp+100h] [rbp+0h] BYREF
  const wchar_t *v146; // [rsp+108h] [rbp+8h]
  __int64 v147; // [rsp+110h] [rbp+10h]
  char v148; // [rsp+118h] [rbp+18h]
  int v149; // [rsp+119h] [rbp+19h]
  __int16 v150; // [rsp+11Dh] [rbp+1Dh]
  char v151; // [rsp+11Fh] [rbp+1Fh]
  __int64 v152; // [rsp+120h] [rbp+20h]
  _BYTE v153[16]; // [rsp+128h] [rbp+28h] BYREF
  struct IOlkAccount *v154; // [rsp+138h] [rbp+38h] BYREF
  CBackgroundUrlLauncher *v155; // [rsp+140h] [rbp+40h]
  HWND v156; // [rsp+148h] [rbp+48h]
  _QWORD v157[2]; // [rsp+150h] [rbp+50h] BYREF
  _QWORD v158[4]; // [rsp+160h] [rbp+60h] BYREF
  char v159; // [rsp+180h] [rbp+80h]
  char v160[8]; // [rsp+188h] [rbp+88h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+190h] [rbp+90h] BYREF
  unsigned int *v162; // [rsp+200h] [rbp+100h] BYREF
  _BYTE *v163; // [rsp+208h] [rbp+108h]
  char v164; // [rsp+210h] [rbp+110h]
  struct _GUID v165; // [rsp+220h] [rbp+120h] BYREF
  _QWORD v166[2]; // [rsp+230h] [rbp+130h] BYREF
  __int64 v167; // [rsp+240h] [rbp+140h]
  unsigned __int64 v168; // [rsp+248h] [rbp+148h]
  __int128 Src; // [rsp+250h] [rbp+150h] BYREF
  __m128i v170; // [rsp+260h] [rbp+160h]
  __int128 v171; // [rsp+270h] [rbp+170h] BYREF
  __m128i si128; // [rsp+280h] [rbp+180h]
  _SHFILEINFOW v173; // [rsp+290h] [rbp+190h] BYREF
  WCHAR pszPath[2088]; // [rsp+550h] [rbp+450h] BYREF

  v155 = this;
  v3 = *((_QWORD *)a2 + 29);
  *((_QWORD *)a2 + 29) = 0;
  v136 = v3;
  if ( v3 )
    CheckpointStopwatch::Checkpoint(v3, UrlLaunchCheckpoints::URLLaunch);
  v4 = *((_QWORD *)a2 + 1);
  v5 = *(HWND *)a2;
  v156 = *(HWND *)a2;
  v6 = 1;
  v130[0] = 1;
  v7 = (char *)a2 + 32;
  v139 = (char *)a2 + 32;
  if ( *((_QWORD *)a2 + 7) > 7u )
  {
    v7 = *(char **)v7;
    v139 = v7;
  }
  v8 = (wchar_t *)((char *)a2 + 64);
  if ( *((_QWORD *)a2 + 11) > 7u )
    v8 = *(wchar_t **)v8;
  String1 = v8;
  v126 = *((_BYTE *)a2 + 96);
  v9 = (struct Mso::Authentication::IOfficeIdentity *)*((_QWORD *)a2 + 13);
  v144 = (struct IHlink **)v9;
  v154 = (struct IOlkAccount *)*((_QWORD *)a2 + 15);
  v138 = GetCurrentThreadId() != g_dwMainThreadId;
  v10 = 0;
  if ( !v138 )
    v10 = v5;
  v137 = v10;
  v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 152LL))(v4);
  v134 = v11;
  v135 = v11 <= 1;
  pszFirst[0] = 0;
  pszFirst[1] = 0;
  v141 = 0;
  v142 = 0;
  v171 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v171) = 0;
  memset_0(&v173, 0, sizeof(v173));
  LODWORD(v131) = 0;
  v143 = 0;
  v127 = 0;
  v158[0] = &v127;
  v158[1] = &String1;
  v158[2] = &v154;
  v158[3] = &v136;
  v159 = 1;
  v12 = (const struct Mso::Telemetry::EventFlags *)Mso::Telemetry::EventFlags::EventFlags(v160, 2);
  v157[0] = &off_14217AA60;
  v157[1] = "LaunchUrlResult";
  Mso::Telemetry::Activity::Activity(
    (Mso::Telemetry::Activity *)v153,
    (const struct Mso::Telemetry::EventName *)v157,
    v12);
  memset_0(&pExecInfo, 0, sizeof(pExecInfo));
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 64LL))(v4);
  pcchPath[0] = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 128LL))(v4);
  v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 136LL))(v4);
  v125 = StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrDup(pszFirst, v13);
  v14 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
  if ( (v125 & 0x80000000) != 0 )
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
      v19 = StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrDup(&v141, v20);
    }
    else
    {
      v18 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
      if ( v17 )
        v18 = v17;
      v19 = HrReportErrorTag(-2147467259, 1900695, v18, 0x1E50D60Du);
    }
    v125 = v19;
    v6 = v130[0];
    goto LABEL_26;
  }
  if ( !v135 )
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
    Mso::Url::CreateFromUser(v130, pszPath);
    v22 = Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(v130);
    v135 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 592LL))(v22);
    v6 = 0;
    v125 = StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrDup(pszFirst, pszPath);
    Mso::TCntPtr<CAttachmentHandlerActivationHost>::~TCntPtr<CAttachmentHandlerActivationHost>(v130);
    goto LABEL_25;
  }
LABEL_26:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 72LL))(v4);
  v23 = 0;
  if ( (v125 & 0x80000000) != 0 )
  {
    EtwTraceErrorTag(v125, 842431081);
    goto LABEL_265;
  }
  if ( !_wcsicmp(String1, L"Outlook-Body") )
  {
    if ( v15 )
    {
      v27 = (Mso::UrlReputation *)v15;
      v23 = v15;
    }
    else
    {
      v27 = (Mso::UrlReputation *)&VariableLengthBuffer<wchar_t>::s_szEmpty;
    }
    IsSafeLinksUrl = Mso::UrlReputation::IsSafeLinksUrl(v27, v24);
    v29 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
    if ( IsSafeLinksUrl )
    {
      if ( v23 )
        v29 = v23;
      v23 = 0;
      v30 = StrStrIW(v29, L"/?url=https%3A%2F%2Fteams.microsoft.com%2Fl%2Fmeetup-join%2F") != 0;
    }
    else
    {
      if ( v23 )
        v29 = v23;
      v23 = 0;
      v30 = _wcsnicmp(v29, L"https://teams.microsoft.com/l/meetup-join/", 0x2Au) == 0;
    }
    if ( v30 )
    {
      v31 = Mso::Telemetry::EventFlags::EventFlags(v130, 2);
      *(_QWORD *)&v133 = &off_14217AA60;
      *((_QWORD *)&v133 + 1) = "OpenJoinTeamsMeetingUrl";
      Mso::Telemetry::SendTelemetryEvent<>(&v133, v31);
      v165 = 0;
      HrGetAccountUID(v154, &v165);
      EventWriteCalendar_JoinOnline(v125, 1u, 5u, &v165);
    }
  }
  if ( v126 && (unsigned __int8)FIsFeatureEnabled(536870919, v24, v25, v26) )
  {
    v130[0] = 0;
    v128 = 1;
    v126 = 0;
    CBackgroundUrlLauncher::ForceCheckReputation(
      v32,
      (_DWORD)a2,
      (unsigned int)pszFirst,
      (unsigned int)&v128,
      (__int64)&v126);
    if ( v128 )
    {
      v33 = (_QWORD *)((char *)a2 + 136);
      if ( *((_QWORD *)a2 + 20) > 7u )
        v33 = (_QWORD *)*v33;
      v34 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
      v15 = pszFirst[0];
      if ( pszFirst[0] )
        v34 = pszFirst[0];
      v123 = (char)v33;
      LOBYTE(v122) = 0;
      if ( (int)Mso::Safelinks::GetReputationForIdentity(v34, *((_QWORD *)a2 + 13), &v171, v130) >= 0 && v130[0] == -1 )
      {
        v35 = &v171;
        if ( si128.m128i_i64[1] > 7uLL )
          v35 = (__int128 *)v171;
        StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrDup(pszFirst, v35);
        v15 = pszFirst[0];
      }
      EventWriteOutllib_GetReputationForIdentity(v130[0]);
    }
    else
    {
      v15 = pszFirst[0];
    }
    if ( v126 )
    {
      Mso::UrlReputation::AddAppDetailsAndBase64Encode(v166, 0);
      if ( v167 )
      {
        std::wstring::wstring(&Src);
        v36 = (_QWORD *)StringUtil::UrlEncode(&v162, v166);
        if ( v36[3] > 7u )
          v36 = (_QWORD *)*v36;
        std::wstring::append(&Src, v36);
        std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(&v162);
        v37 = AddQueryParam(pszFirst, &Src);
        v125 = v37;
        if ( v37 < 0 )
        {
          EtwTraceErrorTag((unsigned int)v37, 506843299);
          std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(&Src);
          std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v166);
          goto LABEL_265;
        }
        std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(&Src);
        v15 = pszFirst[0];
      }
      std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v166);
    }
  }
  if ( v6 )
  {
    v162 = &v125;
    v163 = v153;
    v164 = 1;
    if ( v138 )
    {
      v38 = v155;
      if ( v15 )
      {
        v39 = v15;
        v23 = v15;
      }
      else
      {
        v39 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
      }
      (*(void (__fastcall **)(_QWORD, const wchar_t *, int *, _QWORD))(**((_QWORD **)v155 + 55) + 40LL))(
        *((_QWORD *)v155 + 55),
        v39,
        &v143,
        0);
      v40 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
      if ( v23 )
        v40 = v23;
      v23 = 0;
      v41 = CBackgroundUrlLauncher::HrMakeFgCall(v38, 0, v156, v40, 0);
      v125 = v41;
      if ( v41 < 0 )
      {
        v42 = 1651926838;
LABEL_72:
        EtwTraceErrorTag((unsigned int)v41, v42);
        sub_141855C80(&v162);
        goto LABEL_265;
      }
    }
    else
    {
      v43 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
      if ( v15 )
        v43 = v15;
      v41 = MsoHrSafeToNavigateEx(v43, 0, 0, 2u, v137);
      v125 = v41;
      if ( v41 < 0 )
      {
        v42 = 1651926839;
        goto LABEL_72;
      }
    }
    sub_141855C80(&v162);
  }
  v44 = v134;
  if ( v134 == 3 )
  {
    VariableLengthBuffer<wchar_t>::EnsureLength(&v141);
    if ( HIDWORD(v142) )
    {
      v162 = &v125;
      v163 = v153;
      v164 = 1;
      v45 = StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::Find(pszFirst, L"#");
      v15 = pszFirst[0];
      if ( v45 > 0 )
      {
        *(_QWORD *)v130 = 0;
        *(_QWORD *)&v165.Data1 = 0;
        *(_QWORD *)v165.Data4 = 0;
        v133 = 0u;
        v46 = 0;
        v47 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
        if ( pszFirst[0] )
          v47 = pszFirst[0];
        v48 = StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrDup(&v165, v47);
        v125 = v48;
        if ( v48 < 0 )
        {
          EtwTraceErrorTag((unsigned int)v48, 1594576);
          VariableLengthBuffer<wchar_t>::Free(&v133);
          VariableLengthBuffer<wchar_t>::Free(&v165);
          v49 = *(_QWORD *)v130;
          goto LABEL_91;
        }
        StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrReplaceAll(&v165, L"#", L"%23");
        MsoHrCreateUrlSimple((struct IMsoUrl **)v130, 0);
        v50 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
        if ( v15 )
          v50 = v15;
        if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, _QWORD, _QWORD, __int64))(**(_QWORD **)v130 + 40LL))(
               *(_QWORD *)v130,
               v50,
               pcchPath[0],
               0,
               1) >= 0 )
        {
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v130 + 64LL))(*(_QWORD *)v130);
          v51 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v130 + 648LL))(*(_QWORD *)v130);
          v125 = StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrDup(&v133, v51);
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v130 + 72LL))(*(_QWORD *)v130);
          v23 = (const wchar_t *)v133;
        }
        if ( (v125 & 0x80000000) != 0 )
        {
          EtwTraceErrorTag(v125, 1594577);
          VariableLengthBuffer<wchar_t>::Free(&v133);
          VariableLengthBuffer<wchar_t>::Free(&v165);
          v49 = *(_QWORD *)v130;
          *(_QWORD *)v130 = 0;
LABEL_91:
          if ( v49 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
          goto LABEL_93;
        }
        if ( v23 )
          v46 = v23;
        else
          v23 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
        if ( MsoSHGetFileInfoW(v23, 0x10u, &v173, 0x2B8u, 0x800u) )
        {
          LODWORD(v131) = 1;
          v52 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
          if ( *(_QWORD *)&v165.Data1 )
            v52 = *(const wchar_t **)&v165.Data1;
          StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrDup(pszFirst, v52);
          v53 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
          if ( v46 )
            v53 = v46;
          StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrDup(&v141, v53);
          v15 = pszFirst[0];
        }
        VariableLengthBuffer<wchar_t>::Free(&v133);
        VariableLengthBuffer<wchar_t>::Free(&v165);
        v54 = *(_QWORD *)v130;
        *(_QWORD *)v130 = 0;
        if ( v54 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
      }
      if ( v138 )
      {
        v55 = v141;
        if ( !(_DWORD)v131 )
        {
          if ( v141 )
          {
            v56 = v141;
            v57 = v141;
          }
          else
          {
            v56 = (wchar_t *)&VariableLengthBuffer<wchar_t>::s_szEmpty;
            v57 = 0;
          }
          if ( !MsoSHGetFileInfoW(v56, 0x10u, &v173, 0x2B8u, 0x800u) )
          {
            if ( v57 )
              v14 = v57;
            v125 = HrReportErrorTag(-2147467259, 1966714, v14, 0x32373369u);
            DelayDisplayErrorContext(v125, 2);
            v125 = 1;
            goto LABEL_93;
          }
        }
        v58 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
        if ( v55 )
          v58 = v55;
        v59 = CBackgroundUrlLauncher::HrMakeFgCall(v155, 1u, v156, v58, &v173);
        v125 = v59;
        if ( v59 < 0 )
        {
          v60 = 842478442;
LABEL_119:
          EtwTraceErrorTag((unsigned int)v59, v60);
LABEL_93:
          sub_141855CA8(&v162);
          goto LABEL_265;
        }
      }
      else
      {
        v61 = (wchar_t *)&VariableLengthBuffer<wchar_t>::s_szEmpty;
        if ( v141 )
          v61 = v141;
        v59 = HrAskUserOpenSave(v137, v61, 0);
        v125 = v59;
        if ( v59 < 0 )
        {
          v60 = 842478443;
          goto LABEL_119;
        }
      }
      if ( (v59 & 0x800FFFFF) == 1 )
        goto LABEL_93;
      sub_141855CA8(&v162);
      v44 = v134;
    }
  }
  v62 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
  if ( v15 )
    v62 = v15;
  MsoFRegSetWz((const struct _msoreg *)&vmsoridUseRWHlinkNavigation, v62);
  MsoFRegSetDw((const struct _msoreg *)&vmsoridUseRWOSHlinkNavigation, 1u);
  ThreadLocalStoragePointer = (__int64 *)NtCurrentTeb()->ThreadLocalStoragePointer;
  v64 = *ThreadLocalStoragePointer;
  if ( dword_14274D378 > *(_DWORD *)(*ThreadLocalStoragePointer + 8) )
  {
    Init_thread_header(&dword_14274D378);
    if ( dword_14274D378 == -1 )
    {
      byte_14274D37C = Mso::ProtocolHandlers::IsOpeningOfficeLinksFromSupportedAppsEnabled(v65);
      Init_thread_footer(&dword_14274D378);
    }
  }
  if ( dword_14274D380 > *(_DWORD *)(v64 + 8) )
  {
    Init_thread_header(&dword_14274D380);
    if ( dword_14274D380 == -1 )
    {
      byte_14274D384 = Mso::ProtocolHandlers::IsFlightToUpdateUrlWithCGuidEnabled(v66);
      Init_thread_footer(&dword_14274D380);
    }
  }
  *(_QWORD *)pcchPath = 0;
  if ( v44 == 1 && (byte_14274D37C || byte_14274D384) )
  {
    if ( v15 )
    {
      v67 = v15;
      v68 = v15;
    }
    else
    {
      v67 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
      v68 = 0;
    }
    if ( v67 && *v67 )
    {
      v69 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
      if ( v68 )
        v69 = v68;
      v123 = 0;
      LOBYTE(v122) = 1;
      if ( (int)MsoHrCreateUrlSimpleFromUser(pcchPath, v69, 0, 0) >= 0 )
      {
        v70 = Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(pcchPath);
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v70 + 152LL))(v70) == 1 )
        {
          v164 = 0;
          Src = 0;
          v170 = _mm_load_si128((const __m128i *)&_xmm);
          LOWORD(Src) = 0;
          LOBYTE(v71) = 1;
          OGuid::Create(&Src, v71);
          p_Src = &Src;
          if ( v170.m128i_i64[1] > 7uLL )
            LOBYTE(p_Src) = Src;
          v123 = (char)p_Src;
          LOBYTE(v122) = (_BYTE)String1;
          v73 = (__int64 *)Mso::ProtocolHandlers::AddLinksOpenRightActivityAndReturnCommandParams(
                             &v137,
                             *(_QWORD *)pcchPath,
                             "HrLaunchUrl",
                             v7);
          v74 = *v73;
          *v73 = 0;
          v75 = v127;
          v127 = v74;
          if ( v75 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
          v76 = v137;
          if ( v137 )
          {
            v137 = 0;
            (*(void (__fastcall **)(HWND))(*(_QWORD *)v76 + 16LL))(v76);
          }
          if ( v127 && *(_BYTE *)(Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(&v127) + 870) )
          {
            v77 = mso40uiWin32Client_32195(&v133, 1023639);
            if ( v164 )
            {
              *(_QWORD *)v162 = v163;
              v164 = 0;
            }
            v162 = *(unsigned int **)v77;
            v163 = *(_BYTE **)(v77 + 8);
            *(_QWORD *)v77 = v77 + 8;
            v164 = 1;
            *(_QWORD *)v133 = *((_QWORD *)&v133 + 1);
          }
          v78 = (unsigned __int8)mso40uiWin32Client_8443();
          EventWriteOutllib_LinksInformation(
            v127 != 0,
            (unsigned __int8)byte_14274D37C,
            (unsigned __int8)byte_14274D384,
            v78);
          if ( v127 )
          {
            v79 = *(_DWORD *)(Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(&v127) + 876);
            v80 = *(unsigned __int8 *)(Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(&v127) + 868);
            v81 = *(unsigned __int8 *)(Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(&v127) + 864);
            v82 = Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(&v127);
            EventWriteOutllib_CommandInfoData(*(unsigned __int8 *)(v82 + 870), v81, v80, v79);
            v9 = (struct Mso::Authentication::IOfficeIdentity *)v144;
            v44 = v134;
          }
          if ( !(_BYTE)v78 )
            goto LABEL_230;
          if ( !(unsigned __int8)Outlook::Ripcord<3224568>::getValue() )
            goto LABEL_184;
          if ( !v127 )
          {
LABEL_230:
            std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(&Src);
            if ( v164 )
              *(_QWORD *)v162 = v163;
            goto LABEL_232;
          }
          if ( !*(_BYTE *)(Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(&v127) + 864)
            || !*(_DWORD *)(Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(&v127) + 876) )
          {
LABEL_184:
            if ( v127 )
            {
              if ( *(_BYTE *)(Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(&v127) + 864) && byte_14274D37C )
              {
                v166[0] = &v125;
                v166[1] = v153;
                LOBYTE(v167) = 1;
                v131 = 0;
                v89 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
                if ( v15 )
                  v89 = v15;
                v90 = MsoHrHlinkCreateFromString(v89, 0, 0, 0, 0, 0, &IID_IHlink, (void **)&v131, 0x254E796u);
                v125 = v90;
                if ( v90 < 0 )
                {
                  EtwTraceErrorTag((unsigned int)v90, 38081558);
                  v92 = v131;
                  if ( v131 )
                  {
                    v131 = 0;
                    ((void (__fastcall *)(struct IHlink *))v92->lpVtbl->Release)(v92);
                  }
                  sub_141855CD0(v166);
                  goto LABEL_171;
                }
                LOBYTE(v91) = 59;
                if ( (unsigned __int8)Mso::Hyperlink::IsM365BrowserLinkOpeningEnabled(v91) )
                {
                  v93 = (_QWORD *)((char *)a2 + 200);
                  if ( *((_QWORD *)a2 + 28) > 7u )
                    v93 = (_QWORD *)*v93;
                  *(_QWORD *)v145 = v93;
                  v146 = L"outlook";
                  v147 = sub_140E11758();
                  v148 = 59;
                  v149 = 0;
                  v150 = 0;
                  v151 = 0;
                  v152 = 0;
                  v133 = 0;
                  LOBYTE(v94) = 59;
                  if ( (unsigned __int8)Mso::Hyperlink::EnableM365ProtocolByDefault(v94) )
                  {
                    v95 = std::make_shared<m365_browser::phase_1::M365BrowserDelegateImpl,>(&v165);
                    std::shared_ptr<MeetingAttendeeGridDpiDetails>::operator=(&v133, v95);
                    std::shared_ptr<Outlook::Search::IFindPaneAccessorWeakRef>::~shared_ptr<Outlook::Search::IFindPaneAccessorWeakRef>(&v165);
                    v152 = v133;
                  }
                  if ( v136 )
                    CheckpointStopwatch::Checkpoint(v136, UrlLaunchCheckpoints::HyperlinkNavigate_WithContext);
                  v96 = (const wchar_t *)((char *)a2 + 168);
                  if ( *((_QWORD *)a2 + 24) > 7u )
                    v96 = *(const wchar_t **)v96;
                  v97 = (const wchar_t *)((char *)a2 + 136);
                  if ( *((_QWORD *)a2 + 20) > 7u )
                    v97 = *(const wchar_t **)v97;
                  v125 = MsoHrHlinkNavigateWithSrcInfoAndMsgCtx(
                           v131,
                           0,
                           2u,
                           0,
                           0,
                           0,
                           v97,
                           v96,
                           v9,
                           (struct m365_browser::M365BrowserParams *)v145,
                           0x1E8998C7u);
                  std::shared_ptr<Outlook::Search::IFindPaneAccessorWeakRef>::~shared_ptr<Outlook::Search::IFindPaneAccessorWeakRef>(&v133);
                }
                else
                {
                  if ( v136 )
                    CheckpointStopwatch::Checkpoint(v136, UrlLaunchCheckpoints::HyperlinkNavigate_WithSource);
                  v98 = (const wchar_t *)((char *)a2 + 168);
                  if ( *((_QWORD *)a2 + 24) > 7u )
                    v98 = *(const wchar_t **)v98;
                  v99 = (const wchar_t *)((char *)a2 + 136);
                  if ( *((_QWORD *)a2 + 20) > 7u )
                    v99 = *(const wchar_t **)v99;
                  v125 = MsoHrHlinkNavigateWithSourceInfo(v131, 0, 2u, 0, 0, 0, v99, v98, v9, 0x1F0C43DAu);
                }
                v100 = Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(&v127);
                EventWriteOutllib_CallMsoHrHlinkNavigateWithAccount(v125, *(unsigned __int8 *)(v100 + 868));
                if ( !*(_BYTE *)(Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(&v127) + 868)
                  || v125 != -2147467259 )
                {
                  v106 = v131;
                  if ( v131 )
                  {
                    v131 = 0;
                    ((void (__fastcall *)(struct IHlink *))v106->lpVtbl->Release)(v106);
                  }
                  sub_141855CD0(v166);
                  goto LABEL_226;
                }
                v101 = v131;
                if ( v131 )
                {
                  v131 = 0;
                  ((void (__fastcall *)(struct IHlink *))v101->lpVtbl->Release)(v101);
                }
                sub_141855CD0(v166);
              }
              if ( v127
                && *(_BYTE *)(Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(&v127) + 864)
                && !*(_BYTE *)(Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(&v127) + 868)
                && byte_14274D384 )
              {
                std::wstring::wstring(v166);
                Mso::ProtocolHandlers::AppendLORQueryParamToUrl(v166, &v127);
                v102 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v166);
                v103 = StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrDup(pszFirst, v102);
                v125 = v103;
                if ( v103 < 0 )
                {
                  HandleCORgError_Impl(0, v104, v105, 0, (bool)v122, v123, 0, v124, 0x26548DAu, v103, (int *)&v125);
                  std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v166);
LABEL_226:
                  std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(&Src);
                  if ( v164 )
                  {
                    *(_QWORD *)v162 = v163;
                    v164 = 0;
                  }
                  goto LABEL_228;
                }
                std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v166);
                v15 = pszFirst[0];
              }
            }
            goto LABEL_230;
          }
          v84 = &Src;
          if ( v170.m128i_i64[1] > 7uLL )
            v84 = (__int128 *)Src;
          CBackgroundUrlLauncher::GetODSPLinkTelemetryQueryParamsString(
            v83,
            (unsigned int)v166,
            v127,
            (_DWORD)v139,
            (__int64)String1,
            (__int64)v84);
          if ( *(_BYTE *)(Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(&v127) + 868) )
          {
            if ( (int)StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::Find(pszFirst, L"&reserved=0") > 0 )
            {
              v88 = v166;
              if ( v168 > 7 )
                v88 = (_QWORD *)v166[0];
              Param = StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrReplaceAll(pszFirst, L"reserved=0", v88);
              v125 = Param;
              if ( Param < 0 )
              {
                v86 = 506843297;
                goto LABEL_170;
              }
            }
            else
            {
              Param = AddQueryParam(pszFirst, v166);
              v125 = Param;
              if ( Param < 0 )
              {
                v86 = 506843298;
LABEL_170:
                EtwTraceErrorTag((unsigned int)Param, v86);
                std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v166);
LABEL_171:
                std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(&Src);
                if ( v164 )
                {
                  *(_QWORD *)v162 = v163;
                  v164 = 0;
                }
                v87 = *(_QWORD *)pcchPath;
                if ( *(_QWORD *)pcchPath )
                {
                  *(_QWORD *)pcchPath = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
                }
                goto LABEL_265;
              }
            }
          }
          else
          {
            if ( !v167 )
            {
LABEL_183:
              std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(v166);
              goto LABEL_184;
            }
            Param = AddQueryParam(pszFirst, v166);
            v125 = Param;
            if ( Param < 0 )
            {
              v86 = 506843296;
              goto LABEL_170;
            }
          }
          v15 = pszFirst[0];
          goto LABEL_183;
        }
      }
    }
  }
LABEL_232:
  Mso::TCntPtr<CAttachmentHandlerActivationHost>::~TCntPtr<CAttachmentHandlerActivationHost>(pcchPath);
  pExecInfo.cbSize = 112;
  pExecInfo.nShow = 1;
  if ( v15 )
  {
    v107 = v15;
    v108 = v15;
  }
  else
  {
    v107 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
    v108 = 0;
  }
  pExecInfo.lpFile = v107;
  pExecInfo.fMask = 1280;
  if ( v44 == 3 )
  {
    pcchPath[0] = 260;
    if ( v108 )
      v14 = v108;
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
    LOBYTE(v108) = 59;
    if ( (unsigned __int8)Mso::Hyperlink::IsM365BrowserLinkOpeningEnabled(v108) && v135 )
    {
      LODWORD(v131) = 0;
      if ( v9 )
        v110 = (const WCHAR *)(*(__int64 (__fastcall **)(struct Mso::Authentication::IOfficeIdentity *))(*(_QWORD *)v9 + 16LL))(v9);
      else
        v110 = &FullPath;
      if ( v9 )
        v111 = (*(__int64 (__fastcall **)(struct Mso::Authentication::IOfficeIdentity *))(*(_QWORD *)v9 + 40LL))(v9);
      else
        v111 = 0;
      if ( v15 )
        v14 = v15;
      Mso::Url::CreateFromUser(pcchPath, v14);
      *(_QWORD *)v145 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)a2 + 200);
      v146 = L"outlook";
      v147 = sub_140E11758();
      v148 = 59;
      v149 = 0;
      v150 = 0;
      v151 = 0;
      v152 = 0;
      v133 = 0;
      LOBYTE(v112) = 59;
      if ( (unsigned __int8)Mso::Hyperlink::EnableM365ProtocolByDefault(v112) )
      {
        v113 = std::make_shared<m365_browser::phase_1::M365BrowserDelegateImpl,>(&v165);
        std::shared_ptr<MeetingAttendeeGridDpiDetails>::operator=(&v133, v113);
        std::shared_ptr<Outlook::Search::IFindPaneAccessorWeakRef>::~shared_ptr<Outlook::Search::IFindPaneAccessorWeakRef>(&v165);
        v152 = v133;
      }
      if ( v136 )
        CheckpointStopwatch::Checkpoint(v136, UrlLaunchCheckpoints::OpenInBrowser);
      v123 = 0;
      v122 = v145;
      v114 = Mso::Hyperlink::OpenUrlInBrowser(&v137, *(_QWORD *)pcchPath, v110, v111);
      v144 = &v131;
      sub_1418558A0(v114, &v139, v115, &v144);
      Mso::TCntPtr<CAttachmentHandlerActivationHost>::~TCntPtr<CAttachmentHandlerActivationHost>(&v139);
      Mso::TCntPtr<CAttachmentHandlerActivationHost>::~TCntPtr<CAttachmentHandlerActivationHost>(&v137);
      EventWriteOutllib_CallOpenUrlInBrowser();
      if ( (int)v131 >= 0 )
      {
        std::shared_ptr<Outlook::Search::IFindPaneAccessorWeakRef>::~shared_ptr<Outlook::Search::IFindPaneAccessorWeakRef>(&v133);
LABEL_228:
        Mso::TCntPtr<CAttachmentHandlerActivationHost>::~TCntPtr<CAttachmentHandlerActivationHost>(pcchPath);
        goto LABEL_265;
      }
      std::shared_ptr<Outlook::Search::IFindPaneAccessorWeakRef>::~shared_ptr<Outlook::Search::IFindPaneAccessorWeakRef>(&v133);
      Mso::TCntPtr<CAttachmentHandlerActivationHost>::~TCntPtr<CAttachmentHandlerActivationHost>(pcchPath);
    }
  }
  if ( v136 )
    CheckpointStopwatch::Checkpoint(v136, UrlLaunchCheckpoints::__use_OlkShellExecute__);
  v125 = OlkShellExecuteExW(&pExecInfo, 1);
  EventWriteOutllib_CallOlkShellExecute(v125);
  if ( (v125 & 0x80000000) == 0 )
  {
    if ( (unsigned __int64)pExecInfo.hInstApp - 1 <= 0x1F )
    {
      v125 = -2147467259;
      HandleCORgError_Impl(0, v116, v117, 0, (bool)v122, v123, 0, v124, 0x38786E70u, -2147467259, (int *)&v125);
    }
  }
  else
  {
    HandleCORgError_Impl(0, v116, v117, 0, (bool)v122, v123, 0, v124, 0x1F20C183u, v125, (int *)&v125);
  }
LABEL_265:
  if ( v136 )
    CheckpointStopwatch::Checkpoint(v136, UrlLaunchCheckpoints::URLLaunch_Complete);
  if ( !*(_BYTE *)(Mso::Telemetry::Activity::Result(v153) + 432) )
    Mso::Telemetry::SetActivityResultHr((Mso::Telemetry *)v153, (struct Mso::Telemetry::Activity *)v125, v118);
  CloseHandle(pExecInfo.hProcess);
  v119 = v125;
  Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)v153);
  sub_140E19920(v158);
  v120 = v127;
  if ( v127 )
  {
    v127 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v120 + 16LL))(v120);
  }
  std::basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>::~basic_string<wchar_t,case_insensitive_wchar_traits,std::allocator<wchar_t>>(&v171);
  VariableLengthBuffer<wchar_t>::Free(&v141);
  VariableLengthBuffer<wchar_t>::Free(pszFirst);
  std::unique_ptr<OfficeExtension::ServerRuntime::IRichApiMessageEntry>::~unique_ptr<OfficeExtension::ServerRuntime::IRichApiMessageEntry>(&v136);
  return v119;
}

```

## disassembly

```asm
0x140ec4af0  mov     [rsp-8+arg_10], rbx
0x140ec4af5  push    rbp
0x140ec4af6  push    rsi
0x140ec4af7  push    rdi
0x140ec4af8  push    r12
0x140ec4afa  push    r13
0x140ec4afc  push    r14
0x140ec4afe  push    r15
0x140ec4b00  lea     rbp, [rsp-14B0h]
0x140ec4b08  mov     eax, 15B0h
0x140ec4b0d  call    _alloca_probe
0x140ec4b12  sub     rsp, rax
0x140ec4b15  mov     rax, cs:__security_cookie
0x140ec4b1c  xor     rax, rsp
0x140ec4b1f  mov     [rbp+14E0h+var_40], rax
0x140ec4b26  mov     r12, rdx
0x140ec4b29  mov     [rbp+14E0h+var_14A0], rcx
0x140ec4b2d  mov     rcx, [rdx+0E8h]
0x140ec4b34  xor     r15d, r15d
0x140ec4b37  mov     [rdx+0E8h], r15
0x140ec4b3e  mov     [rbp+14E0h+var_1528], rcx
0x140ec4b42  test    rcx, rcx
0x140ec4b45  jz      short loc_140EC4B53
0x140ec4b47  mov     rdx, cs:?URLLaunch@UrlLaunchCheckpoints@@2V?$StringLiteral@D@StringLiterals@Mso@@B; Mso::StringLiterals::StringLiteral<char> const UrlLaunchCheckpoints::URLLaunch
0x140ec4b4e  call    ?Checkpoint@CheckpointStopwatch@@QEAAXV?$StringLiteral@D@StringLiterals@Mso@@@Z; CheckpointStopwatch::Checkpoint(Mso::StringLiterals::StringLiteral<char>)
0x140ec4b53  mov     rbx, [r12+8]
0x140ec4b58  mov     r14, [r12]
0x140ec4b5c  mov     [rbp+14E0h+var_1498], r14
0x140ec4b60  mov     edi, 1
0x140ec4b65  mov     [rbp+14E0h+var_1560], edi
0x140ec4b68  lea     r13, [r12+20h]
0x140ec4b6d  mov     [rbp+14E0h+var_1510], r13
0x140ec4b71  cmp     qword ptr [r13+18h], 7
0x140ec4b76  jbe     short loc_140EC4B80
0x140ec4b78  mov     r13, [r13+0]
0x140ec4b7c  mov     [rbp+14E0h+var_1510], r13
0x140ec4b80  lea     rax, [r12+40h]
0x140ec4b85  cmp     qword ptr [rax+18h], 7
0x140ec4b8a  jbe     short loc_140EC4B8F
0x140ec4b8c  mov     rax, [rax]
0x140ec4b8f  mov     [rbp+14E0h+String1], rax
0x140ec4b93  mov     al, [r12+60h]
0x140ec4b98  mov     byte ptr [rsp+15E0h+var_1580+4], al
0x140ec4b9c  mov     rsi, [r12+68h]
0x140ec4ba1  mov     [rbp+14E0h+var_14E8], rsi
0x140ec4ba5  mov     rax, [r12+78h]
0x140ec4baa  mov     [rbp+14E0h+var_14A8], rax
0x140ec4bae  call    cs:__imp_GetCurrentThreadId
0x140ec4bb4  mov     ecx, r15d
0x140ec4bb7  cmp     eax, cs:?g_dwMainThreadId@@3KA; ulong g_dwMainThreadId
0x140ec4bbd  setnz   cl
0x140ec4bc0  mov     [rbp+14E0h+var_1518], ecx
0x140ec4bc3  mov     rax, r15
0x140ec4bc6  test    ecx, ecx
0x140ec4bc8  cmovz   rax, r14
0x140ec4bcc  mov     [rbp+14E0h+var_1520], rax
0x140ec4bd0  mov     rax, [rbx]
0x140ec4bd3  mov     rcx, rbx
0x140ec4bd6  mov     rax, [rax+98h]
0x140ec4bdd  call    cs:__guard_dispatch_icall_fptr
0x140ec4be3  mov     r14d, eax
0x140ec4be6  mov     [rbp+14E0h+var_1530], eax
0x140ec4be9  mov     eax, r15d
0x140ec4bec  cmp     r14d, edi
0x140ec4bef  setbe   al
0x140ec4bf2  mov     [rbp+14E0h+var_152C], eax
0x140ec4bf5  mov     [rbp+14E0h+pszFirst], r15
0x140ec4bf9  mov     [rbp+14E0h+var_1548], r15
0x140ec4bfd  mov     [rbp+14E0h+var_1500], r15
0x140ec4c01  mov     [rbp+14E0h+var_14F8], r15
0x140ec4c05  xorps   xmm0, xmm0
0x140ec4c08  movups  [rbp+14E0h+var_1370], xmm0
0x140ec4c0f  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140ec4c17  movdqu  [rbp+14E0h+var_1360], xmm1
0x140ec4c1f  mov     word ptr [rbp+14E0h+var_1370], r15w
0x140ec4c27  xor     edx, edx; Val
0x140ec4c29  mov     r8d, 2B8h; Size
0x140ec4c2f  lea     rcx, [rbp+14E0h+var_1350]; void *
0x140ec4c36  call    memset_0
0x140ec4c3b  mov     dword ptr [rbp+14E0h+var_1558], r15d
0x140ec4c3f  mov     [rbp+14E0h+var_14F0], r15d
0x140ec4c43  mov     [rsp+15E0h+var_1578], r15
0x140ec4c48  lea     rax, [rsp+15E0h+var_1578]
0x140ec4c4d  mov     [rbp+14E0h+var_1480], rax
0x140ec4c51  lea     rax, [rbp+14E0h+String1]
0x140ec4c55  mov     [rbp+14E0h+var_1478], rax
0x140ec4c59  lea     rax, [rbp+14E0h+var_14A8]
0x140ec4c5d  mov     [rbp+14E0h+var_1470], rax
0x140ec4c61  lea     rax, [rbp+14E0h+var_1528]
0x140ec4c65  mov     [rbp+14E0h+var_1468], rax
0x140ec4c69  mov     [rbp+14E0h+var_1460], 1
0x140ec4c70  mov     edx, 2
0x140ec4c75  lea     rcx, [rbp+14E0h+var_1458]
0x140ec4c7c  call    ??0EventFlags@Telemetry@Mso@@QEAA@W4DataCategories@12@@Z; Mso::Telemetry::EventFlags::EventFlags(Mso::Telemetry::DataCategories)
0x140ec4c81  lea     rcx, off_14217AA60
0x140ec4c88  mov     [rbp+14E0h+var_1490], rcx
0x140ec4c8c  lea     rcx, aLaunchurlresul; "LaunchUrlResult"
0x140ec4c93  mov     [rbp+14E0h+var_1488], rcx
0x140ec4c97  mov     r8, rax; struct Mso::Telemetry::EventFlags *
0x140ec4c9a  lea     rdx, [rbp+14E0h+var_1490]; struct Mso::Telemetry::EventName *
0x140ec4c9e  lea     rcx, [rbp+14E0h+var_14B8]; this
0x140ec4ca2  call    ??0Activity@Telemetry@Mso@@QEAA@AEBUEventName@12@AEBUEventFlags@12@@Z; Mso::Telemetry::Activity::Activity(Mso::Telemetry::EventName const &,Mso::Telemetry::EventFlags const &)
0x140ec4ca7  xor     edx, edx; Val
0x140ec4ca9  lea     r8d, [rdx+70h]; Size
0x140ec4cad  lea     rcx, [rbp+14E0h+pExecInfo]; void *
0x140ec4cb4  call    memset_0
0x140ec4cb9  mov     rax, [rbx]
0x140ec4cbc  mov     rcx, rbx
0x140ec4cbf  mov     rax, [rax+40h]
0x140ec4cc3  call    cs:__guard_dispatch_icall_fptr
0x140ec4cc9  mov     rax, [rbx]
0x140ec4ccc  mov     rcx, rbx
0x140ec4ccf  mov     rax, [rax+80h]
0x140ec4cd6  call    cs:__guard_dispatch_icall_fptr
0x140ec4cdc  mov     [rsp+15E0h+pcchPath], eax
0x140ec4ce0  mov     rcx, [rbx]
0x140ec4ce3  mov     rax, [rcx+88h]
0x140ec4cea  mov     rcx, rbx
0x140ec4ced  call    cs:__guard_dispatch_icall_fptr
0x140ec4cf3  mov     rdx, rax
0x140ec4cf6  lea     rcx, [rbp+14E0h+pszFirst]
0x140ec4cfa  call    ?HrDup@?$StringTemplate@_WV?$VariableLengthBuffer@_W@@@@QEAAJPEB_W@Z; StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrDup(wchar_t const *)
0x140ec4cff  mov     dword ptr [rsp+15E0h+var_1580], eax
0x140ec4d03  lea     r15, ?s_szEmpty@?$VariableLengthBuffer@_W@@2QB_WB; wchar_t const near * const VariableLengthBuffer<wchar_t>::s_szEmpty
0x140ec4d0a  test    eax, eax
0x140ec4d0c  js      loc_140EC4E13
0x140ec4d12  xor     edx, edx; Val
0x140ec4d14  mov     r8d, 1048h; Size
0x140ec4d1a  lea     rcx, [rbp+14E0h+pszPath]; void *
0x140ec4d21  call    memset_0
0x140ec4d26  cmp     r14d, 3
0x140ec4d2a  jnz     short loc_140EC4D97
0x140ec4d2c  mov     r14, [rbp+14E0h+pszFirst]
0x140ec4d30  test    r14, r14
0x140ec4d33  jz      short loc_140EC4D3D
0x140ec4d35  mov     rcx, r14
0x140ec4d38  mov     rdi, r14
0x140ec4d3b  jmp     short loc_140EC4D42
0x140ec4d3d  mov     rcx, r15; wchar_t *
0x140ec4d40  xor     edi, edi
0x140ec4d42  call    ?IsFileZoneLocalIntranetOrTrusted@@YA_NPEB_W@Z; IsFileZoneLocalIntranetOrTrusted(wchar_t const *)
0x140ec4d47  test    al, al
0x140ec4d49  jnz     short loc_140EC4D6C
0x140ec4d4b  mov     r8, r15
0x140ec4d4e  test    rdi, rdi
0x140ec4d51  cmovnz  r8, rdi; wchar_t *
0x140ec4d55  mov     edx, 1D0097h; int
0x140ec4d5a  mov     ecx, 80004005h; int
0x140ec4d5f  mov     r9d, 1E50D60Dh; unsigned int
0x140ec4d65  call    ?HrReportErrorTag@@YAJJHPEB_WK@Z; HrReportErrorTag(long,int,wchar_t const *,ulong)
0x140ec4d6a  jmp     short loc_140EC4D8B
0x140ec4d6c  mov     rax, [rbx]
0x140ec4d6f  mov     rcx, rbx
0x140ec4d72  mov     rax, [rax+288h]
0x140ec4d79  call    cs:__guard_dispatch_icall_fptr
0x140ec4d7f  mov     rdx, rax
0x140ec4d82  lea     rcx, [rbp+14E0h+var_1500]
0x140ec4d86  call    ?HrDup@?$StringTemplate@_WV?$VariableLengthBuffer@_W@@@@QEAAJPEB_W@Z; StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrDup(wchar_t const *)
0x140ec4d8b  mov     dword ptr [rsp+15E0h+var_1580], eax
0x140ec4d8f  mov     edi, [rbp+14E0h+var_1560]
0x140ec4d92  jmp     loc_140EC4E17
0x140ec4d97  cmp     [rbp+14E0h+var_152C], 0
0x140ec4d9b  jz      short loc_140EC4E13
0x140ec4d9d  mov     rcx, r15
0x140ec4da0  mov     r14, [rbp+14E0h+pszFirst]
0x140ec4da4  test    r14, r14
0x140ec4da7  cmovnz  rcx, r14
0x140ec4dab  mov     r8d, 824h
0x140ec4db1  lea     rdx, [rbp+14E0h+pszPath]
0x140ec4db8  call    cs:__imp_?MsoFConvertHttpToProtocolHandler@@YA_NPEB_WPEA_WH@Z; MsoFConvertHttpToProtocolHandler(wchar_t const *,wchar_t *,int)
0x140ec4dbe  test    al, al
0x140ec4dc0  jz      short loc_140EC4E17
0x140ec4dc2  lea     rdx, [rbp+14E0h+pszPath]
0x140ec4dc9  lea     rcx, [rbp+14E0h+var_1560]
0x140ec4dcd  call    ?CreateFromUser@Url@Mso@@YA?AV?$TCntPtr@UIMsoUrl@@@2@PEB_W@Z; Mso::Url::CreateFromUser(wchar_t const *)
0x140ec4dd2  lea     rcx, [rbp+14E0h+var_1560]
0x140ec4dd6  call    ??C?$TCntPtr@UISelectionProvider@VirtualList@@@Mso@@QEBAPEAUISelectionProvider@VirtualList@@XZ; Mso::TCntPtr<VirtualList::ISelectionProvider>::operator->(void)
0x140ec4ddb  mov     rdx, rax
0x140ec4dde  mov     rcx, [rax]
0x140ec4de1  mov     rax, [rcx+250h]
0x140ec4de8  mov     rcx, rdx
0x140ec4deb  call    cs:__guard_dispatch_icall_fptr
0x140ec4df1  mov     [rbp+14E0h+var_152C], eax
0x140ec4df4  xor     edi, edi
0x140ec4df6  lea     rdx, [rbp+14E0h+pszPath]
0x140ec4dfd  lea     rcx, [rbp+14E0h+pszFirst]
0x140ec4e01  call    ?HrDup@?$StringTemplate@_WV?$VariableLengthBuffer@_W@@@@QEAAJPEB_W@Z; StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrDup(wchar_t const *)
0x140ec4e06  mov     dword ptr [rsp+15E0h+var_1580], eax
0x140ec4e0a  lea     rcx, [rbp+14E0h+var_1560]; void *
0x140ec4e0e  call    ??1?$TCntPtr@VCAttachmentHandlerActivationHost@@@Mso@@QEAA@XZ; Mso::TCntPtr<CAttachmentHandlerActivationHost>::~TCntPtr<CAttachmentHandlerActivationHost>(void)
0x140ec4e13  mov     r14, [rbp+14E0h+pszFirst]
0x140ec4e17  mov     rax, [rbx]
0x140ec4e1a  mov     rcx, rbx
0x140ec4e1d  mov     rax, [rax+48h]
0x140ec4e21  call    cs:__guard_dispatch_icall_fptr
0x140ec4e27  mov     ecx, dword ptr [rsp+15E0h+var_1580]
0x140ec4e2b  xor     ebx, ebx
0x140ec4e2d  test    ecx, ecx
0x140ec4e2f  jns     short loc_140EC4E41
0x140ec4e31  mov     edx, 32367A69h
0x140ec4e36  call    cs:__imp_EtwTraceErrorTag
0x140ec4e3c  jmp     loc_140EC60BE
0x140ec4e41  lea     rdx, ?g_wszOutlookBody@@3QB_WB; "Outlook-Body"
0x140ec4e48  mov     rcx, [rbp+14E0h+String1]; String1
0x140ec4e4c  call    cs:__imp__wcsicmp
0x140ec4e52  test    eax, eax
0x140ec4e54  jnz     loc_140EC4F1D
0x140ec4e5a  test    r14, r14
0x140ec4e5d  jz      short loc_140EC4E67
0x140ec4e5f  mov     rcx, r14
0x140ec4e62  mov     rbx, r14
0x140ec4e65  jmp     short loc_140EC4E6A
0x140ec4e67  mov     rcx, r15
0x140ec4e6a  call    cs:__imp_?IsSafeLinksUrl@UrlReputation@Mso@@YA_NPEB_W@Z; Mso::UrlReputation::IsSafeLinksUrl(wchar_t const *)
0x140ec4e70  mov     rcx, r15
0x140ec4e73  test    al, al
0x140ec4e75  jz      short loc_140EC4E95
0x140ec4e77  test    rbx, rbx
0x140ec4e7a  cmovnz  rcx, rbx; pszFirst
0x140ec4e7e  lea     rdx, aUrlHttps3a2f2f; "/?url=https%3A%2F%2Fteams.microsoft.com"...
0x140ec4e85  call    cs:__imp_StrStrIW
0x140ec4e8b  xor     ebx, ebx
0x140ec4e8d  test    rax, rax
0x140ec4e90  setnz   al
0x140ec4e93  jmp     short loc_140EC4EB6
0x140ec4e95  test    rbx, rbx
0x140ec4e98  cmovnz  rcx, rbx; String1
0x140ec4e9c  mov     r8d, 2Ah ; '*'; MaxCount
0x140ec4ea2  lea     rdx, aHttpsTeamsMicr_1; "https://teams.microsoft.com/l/meetup-jo"...
0x140ec4ea9  call    cs:__imp__wcsnicmp
0x140ec4eaf  xor     ebx, ebx
0x140ec4eb1  test    eax, eax
0x140ec4eb3  setz    al
0x140ec4eb6  test    al, al
0x140ec4eb8  jz      short loc_140EC4F1D
0x140ec4eba  mov     edx, 2
0x140ec4ebf  lea     rcx, [rbp+14E0h+var_1560]
0x140ec4ec3  call    ??0EventFlags@Telemetry@Mso@@QEAA@W4DataCategories@12@@Z; Mso::Telemetry::EventFlags::EventFlags(Mso::Telemetry::DataCategories)
0x140ec4ec8  lea     rcx, off_14217AA60
0x140ec4ecf  mov     qword ptr [rbp+14E0h+var_1540], rcx
0x140ec4ed3  lea     rcx, aOpenjointeamsm; "OpenJoinTeamsMeetingUrl"
0x140ec4eda  mov     qword ptr [rbp+14E0h+var_1540+8], rcx
0x140ec4ede  mov     rdx, rax
0x140ec4ee1  lea     rcx, [rbp+14E0h+var_1540]
0x140ec4ee5  call    ??$SendTelemetryEvent@$$V@Telemetry@Mso@@YAXAEBUEventName@01@AEBUEventFlags@01@@Z; Mso::Telemetry::SendTelemetryEvent<>(Mso::Telemetry::EventName const &,Mso::Telemetry::EventFlags const &)
0x140ec4eea  xorps   xmm0, xmm0
0x140ec4eed  movups  xmmword ptr [rbp+14E0h+var_13C0.Data1], xmm0
0x140ec4ef4  lea     rdx, [rbp+14E0h+var_13C0]; struct _GUID *
0x140ec4efb  mov     rcx, [rbp+14E0h+var_14A8]; struct IOlkAccount *
0x140ec4eff  call    ?HrGetAccountUID@@YAJPEAUIOlkAccount@@AEAU_GUID@@@Z; HrGetAccountUID(IOlkAccount *,_GUID &)
0x140ec4f04  lea     r9, [rbp+14E0h+var_13C0]; struct _GUID *
0x140ec4f0b  mov     edx, 1; unsigned int
0x140ec4f10  lea     r8d, [rdx+4]; unsigned int
0x140ec4f14  mov     ecx, dword ptr [rsp+15E0h+var_1580]; unsigned int
0x140ec4f18  call    ?EventWriteCalendar_JoinOnline@@YAKIIIPEBU_GUID@@@Z; EventWriteCalendar_JoinOnline(uint,uint,uint,_GUID const *)
0x140ec4f1d  cmp     byte ptr [rsp+15E0h+var_1580+4], bl
0x140ec4f21  jz      loc_140EC50D9
0x140ec4f27  mov     ecx, 20000007h
0x140ec4f2c  call    cs:__imp_FIsFeatureEnabled
0x140ec4f32  test    al, al
0x140ec4f34  jz      loc_140EC50D9
0x140ec4f3a  mov     [rbp+14E0h+var_1560], ebx
0x140ec4f3d  mov     [rsp+15E0h+var_1570], 1
0x140ec4f42  mov     byte ptr [rsp+15E0h+var_1580+4], bl
0x140ec4f46  lea     rax, [rsp+15E0h+var_1580+4]
0x140ec4f4b  mov     [rsp+15E0h+var_15C0], rax
0x140ec4f50  lea     r9, [rsp+15E0h+var_1570]
0x140ec4f55  lea     r8, [rbp+14E0h+pszFirst]
0x140ec4f59  mov     rdx, r12
0x140ec4f5c  call    ?ForceCheckReputation@CBackgroundUrlLauncher@@AEAAXPEAVURLObjectStruct@@AEAV?$VariableLengthString@_W@@AEA_N2@Z; CBackgroundUrlLauncher::ForceCheckReputation(URLObjectStruct *,VariableLengthString<wchar_t> &,bool &,bool &)
0x140ec4f61  cmp     [rsp+15E0h+var_1570], bl
0x140ec4f65  jz      loc_140EC4FF9
0x140ec4f6b  lea     rdx, [r12+0A8h]
0x140ec4f73  cmp     qword ptr [rdx+18h], 7
0x140ec4f78  jbe     short loc_140EC4F7D
0x140ec4f7a  mov     rdx, [rdx]
0x140ec4f7d  lea     rax, [r12+88h]
0x140ec4f85  cmp     qword ptr [rax+18h], 7
0x140ec4f8a  jbe     short loc_140EC4F8F
0x140ec4f8c  mov     rax, [rax]
0x140ec4f8f  mov     rcx, r15
0x140ec4f92  mov     r14, [rbp+14E0h+pszFirst]
0x140ec4f96  test    r14, r14
0x140ec4f99  cmovnz  rcx, r14
0x140ec4f9d  mov     qword ptr [rsp+15E0h+var_15B0], rdx
0x140ec4fa2  mov     qword ptr [rsp+15E0h+var_15B8], rax
0x140ec4fa7  mov     dword ptr [rsp+15E0h+var_15C0], ebx
0x140ec4fab  lea     r9, [rbp+14E0h+var_1560]
0x140ec4faf  lea     r8, [rbp+14E0h+var_1370]
0x140ec4fb6  mov     rdx, [r12+68h]
0x140ec4fbb  call    cs:__imp_?GetReputationForIdentity@Safelinks@Mso@@YAJPEB_WAEAUIOfficeIdentity@Authentication@2@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAW4UrlVerdict@UrlReputation@2@W4RequestType@82@00@Z; Mso::Safelinks::GetReputationForIdentity(wchar_t const *,Mso::Authentication::IOfficeIdentity &,std::wstring &,Mso::UrlReputation::UrlVerdict &,Mso::UrlReputation::RequestType,wchar_t const *,wchar_t const *)
0x140ec4fc1  test    eax, eax
0x140ec4fc3  js      short loc_140EC4FEF
0x140ec4fc5  cmp     [rbp+14E0h+var_1560], 0FFFFFFFFh
0x140ec4fc9  jnz     short loc_140EC4FEF
0x140ec4fcb  lea     rdx, [rbp+14E0h+var_1370]
0x140ec4fd2  cmp     qword ptr [rbp+14E0h+var_1360+8], 7
0x140ec4fda  cmova   rdx, qword ptr [rbp+14E0h+var_1370]
0x140ec4fe2  lea     rcx, [rbp+14E0h+pszFirst]
0x140ec4fe6  call    ?HrDup@?$StringTemplate@_WV?$VariableLengthBuffer@_W@@@@QEAAJPEB_W@Z; StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrDup(wchar_t const *)
  ... truncated ...
```
