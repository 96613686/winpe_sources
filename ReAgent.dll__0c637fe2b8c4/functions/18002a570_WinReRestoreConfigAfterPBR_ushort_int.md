# WinReRestoreConfigAfterPBR(ushort *,int)

- ea: `0x18002a570`
- end: `0x18002b350`
- name: `?WinReRestoreConfigAfterPBR@@YAHPEAGH@Z`
- size: `3552`
- prototype: `__int64 __fastcall(unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `32`
- tags: `file_ops, registry_config, service_task, installer_update`

## callees

- `0x180001f54`
- `0x180002786`
- `0x1800055c8`
- `0x180005694`
- `0x1800059fc`
- `0x180006ed8`
- `0x18000c6f0`
- `0x18000edec`
- `0x18000fe58`
- `0x18000ffcc`
- `0x1800109d0`
- `0x180011974`
- `0x1800145f4`
- `0x180014754`
- `0x18001835c`
- `0x1800187e0`
- `0x180018838`
- `0x18001c598`
- `0x18001df60`
- `0x18002a570`
- `0x18002bec4`
- `0x18002bfac`
- `0x180030fcc`
- `0x1800310a0`
- `0x1800322a8`
- `0x18003add0`
- `0x18003f2c0`
- `0x18004d3a0`
- `0x18004d52c`
- `0x18005cee2`
- `0x18005cf30`
- `0x18005f010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002b2eb`
- `KERNEL32!SetLastError` at `0x18002b2eb`
- `KERNEL32!DeleteFileW` at `0x18002abed`
- `KERNEL32!DeleteFileW` at `0x18002abed`
- `ole32!CoTaskMemFree` at `0x18002aa5c`
- `ole32!CoTaskMemFree` at `0x18002ad12`
- `ole32!CoTaskMemFree` at `0x18002adbf`
- `ole32!CoTaskMemFree` at `0x18002b2a1`
- `ole32!CoTaskMemFree` at `0x18002b2af`
- `ole32!CoTaskMemFree` at `0x18002b2bd`
- `ole32!CoTaskMemFree` at `0x18002aa5c`
- `ole32!CoTaskMemFree` at `0x18002ad12`
- `ole32!CoTaskMemFree` at `0x18002adbf`
- `ole32!CoTaskMemFree` at `0x18002b2a1`
- `ole32!CoTaskMemFree` at `0x18002b2af`
- `ole32!CoTaskMemFree` at `0x18002b2bd`

## string_xrefs

- `0x18002a7d9`: `DisableUpdateEnhancedConfigInfo`
- `0x18002a76e`: `failed to allocate path`
- `0x18002ad4c`: `failed to allocate path`
- `0x18002ad7d`: `%s\system32\%s`
- `0x18002b0db`: `failed to add file to directory path`
- `0x18002aaa5`: `failed to add winre.wim to directory path`
- `0x18002b1b7`: `failed to copy string`
- `0x18002a6f0`: `base\diagnosis\srt\reagent2\reagent\logfile.cpp`
- `0x18002a775`: `base\diagnosis\srt\reagent2\reagent\logfile.cpp`
- `0x18002a8e7`: `base\diagnosis\srt\reagent2\reagent\logfile.cpp`
- `0x18002a995`: `base\diagnosis\srt\reagent2\reagent\logfile.cpp`
- `0x18002aaac`: `base\diagnosis\srt\reagent2\reagent\logfile.cpp`
- `0x18002ad3d`: `base\diagnosis\srt\reagent2\reagent\logfile.cpp`
- `0x18002b1a8`: `base\diagnosis\srt\reagent2\reagent\logfile.cpp`
- `0x18002b262`: `base\diagnosis\srt\reagent2\reagent\logfile.cpp`
- `0x18002a7bd`: `failed to add reload file to directory path`
- `0x18002a693`: `Enter WinReRestoreConfigAfterPBR`
- `0x18002a6b5`: `Parameters: szNewOsConfigPath: %s, bUseDownlevelWinReLocation: %d`
- `0x18002a6c3`: `WinReRestoreConfigAfterPBR Searching for reload.xml`
- `0x18002a6e9`: `Failed to get log directory`
- `0x18002a6ff`: `WinReRestoreConfigAfterPBR %s (0x%x) in file %S line %d`
- `0x18002a784`: `WinReRestoreConfigAfterPBR %s (0x%x) in file %S line %d`
- `0x18002a8fd`: `WinReRestoreConfigAfterPBR %s (0x%x) in file %S line %d`
- `0x18002a9ab`: `WinReRestoreConfigAfterPBR %s (0x%x) in file %S line %d`
- `0x18002aabb`: `WinReRestoreConfigAfterPBR %s (0x%x) in file %S line %d`
- `0x18002ad53`: `WinReRestoreConfigAfterPBR %s (0x%x) in file %S line %d`
- `0x18002b1be`: `WinReRestoreConfigAfterPBR %s (0x%x) in file %S line %d`
- `0x18002b278`: `WinReRestoreConfigAfterPBR %s (0x%x) in file %S line %d`
- `0x18002a71b`: `WinReRestoreConfigAfterPBR Logs location is %s`
- `0x18002a73f`: `Failed to open log directory`
- `0x18002a7cb`: `WinReRestoreConfigAfterPBR Processing %s and disable update enhanced config info`
- `0x18002a812`: `Failed to parse reload.xml`
- `0x18002a83f`: `WinReRestoreConfigAfterPBR reload.xml WinreLocation: %s`
- `0x18002a85c`: `WinReRestoreConfigAfterPBR reload.xml ImageLocation: %s`
- `0x18002a871`: `WinReRestoreConfigAfterPBR reload.xml DownlevelWinreLocation: %s`
- `0x18002a886`: `WinReRestoreConfigAfterPBR reload.xml InstallState: %d`
- `0x18002a8f6`: `Failed to get ReAgent.xml path`
- `0x18002a9a4`: `Failed to parse ReAgent.xml`
- `0x18002a9d6`: `WinReRestoreConfigAfterPBR reagent.xml WinreLocation: %s`
- `0x18002a9eb`: `WinReRestoreConfigAfterPBR reagent.xml ImageLocation: %s`
- `0x18002aa00`: `WinReRestoreConfigAfterPBR reagent.xml DownlevelWinreLocation: %s`
- `0x18002aa15`: `WinReRestoreConfigAfterPBR reagent.xml InstallState: %d`
- `0x18002aae9`: `WinReRestoreConfigAfterPBR Using WinRE from downlevel OS`
- `0x18002aca2`: `WinReRestoreConfigAfterPBR Using installed WinRE from old OS`
- `0x18002ae28`: `WinReRestoreConfigAfterPBR Using staged WinRE from old OS`
- `0x18002aebe`: `WinReRestoreConfigAfterPBR Using staged WinRE from new OS`
- `0x18002af59`: `WinReRestoreConfigAfterPBR Using default WinRE from new OS`
- `0x18002ab35`: `Failed to clear WinreLocationPath`
- `0x18002add4`: `WinReRestoreConfigAfterPBR Deleting staged WinRE from %s`
- `0x18002abba`: `failed to add boot.sdi directory path`
- `0x18002abd7`: `WinReRestoreConfigAfterPBR Deleting old boot.sdi`
- `0x18002afd6`: `Failed to clear ImageLocationPath`
- `0x18002abf8`: `WinReRestoreConfigAfterPBR Searching for a recovery image from the old OS`
- `0x18002b005`: `Failed to add file to directory path`
- `0x18002afea`: `WinReRestoreConfigAfterPBR Found recovery image from old OS at %s`
- `0x18002b011`: `WinReRestoreConfigAfterPBR Searching for a recovery image from the new OS`
- `0x18002b0c7`: `Failed to update OsInstallLocationPath`
- `0x18002b0e7`: `WinReRestoreConfigAfterPBR Failed to find a recovery image`
- `0x18002b149`: ` Final InstallState: %d`
- `0x18002b15e`: ` Final OsInstallLocation: %s`
- `0x18002b20c`: `Failed to update ReAgent.xml`
- `0x18002b2ff`: `Exit WinReRestoreConfigAfterPBR return value: %d, last error: 0x%x`
- `0x18002a7a0`: `Reload.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WinReRestoreConfigAfterPBR(unsigned __int16 *a1, unsigned int a2)
{
  void *v4; // r15
  const unsigned __int16 *v5; // r8
  DWORD LogDirPathInternal; // ebx
  const wchar_t *v7; // r8
  WCHAR *v8; // r13
  void **v9; // rsi
  unsigned int v10; // r12d
  const wchar_t *v11; // r8
  int v12; // r14d
  struct ReAgentConfigInfo *ConfigInfo; // rbx
  __int64 v14; // r8
  void **v15; // rax
  void *v16; // r13
  struct ReAgentConfigInfo *v17; // r13
  unsigned __int16 *v18; // rbx
  int v19; // eax
  const wchar_t *v20; // r8
  unsigned __int64 v21; // rdx
  unsigned __int16 *v22; // r11
  LPCWSTR v23; // rbx
  unsigned int i; // r12d
  int v25; // eax
  unsigned __int64 v26; // rdx
  unsigned __int64 v27; // rdx
  unsigned __int64 v28; // rdx
  unsigned __int16 *v29; // r11
  unsigned int j; // r12d
  struct ReAgentConfigInfo *v31; // rbx
  int v32; // r12d
  __int64 v34; // [rsp+28h] [rbp-830h]
  int v35; // [rsp+28h] [rbp-830h]
  int v36; // [rsp+28h] [rbp-830h]
  int v37; // [rsp+34h] [rbp-824h]
  LPCWSTR lpFileName; // [rsp+38h] [rbp-820h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-818h] BYREF
  unsigned __int16 *v40; // [rsp+48h] [rbp-810h] BYREF
  unsigned int v41; // [rsp+50h] [rbp-808h]
  int v42; // [rsp+54h] [rbp-804h]
  unsigned __int16 *v43; // [rsp+58h] [rbp-800h]
  unsigned __int16 *v44; // [rsp+60h] [rbp-7F8h]
  unsigned __int16 *v45; // [rsp+68h] [rbp-7F0h]
  struct _GUID v46; // [rsp+70h] [rbp-7E8h] BYREF
  __int64 v47; // [rsp+80h] [rbp-7D8h]
  LPVOID v48[2]; // [rsp+90h] [rbp-7C8h] BYREF
  _QWORD v49[3]; // [rsp+A0h] [rbp-7B8h] BYREF
  int v50; // [rsp+B8h] [rbp-7A0h]
  int v51; // [rsp+BCh] [rbp-79Ch]
  __int128 v52; // [rsp+C0h] [rbp-798h]
  __int128 v53; // [rsp+D0h] [rbp-788h]
  __int64 v54; // [rsp+E0h] [rbp-778h]
  int v55; // [rsp+E8h] [rbp-770h]
  __int64 v56; // [rsp+F0h] [rbp-768h]
  unsigned __int16 v57; // [rsp+100h] [rbp-758h] BYREF
  _BYTE v58[606]; // [rsp+102h] [rbp-756h] BYREF
  unsigned __int16 v59; // [rsp+360h] [rbp-4F8h] BYREF
  _BYTE v60[6]; // [rsp+362h] [rbp-4F6h] BYREF
  WCHAR FileName; // [rsp+5C0h] [rbp-298h] BYREF
  _BYTE v62[606]; // [rsp+5C2h] [rbp-296h] BYREF

  v47 = -2;
  v41 = a2;
  v44 = a1;
  lpFileName = 0;
  v40 = 0;
  v48[0] = 0;
  v4 = 0;
  pv = 0;
  v49[1] = 0;
  v49[2] = 0;
  v50 = 0;
  v51 = 2;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v49[0] = &ReAgentReload::`vftable';
  v56 = 0;
  v59 = 0;
  memset_0(v60, 0, 0x25Au);
  v57 = 0;
  memset_0(v58, 0, 0x25Au);
  FileName = 0;
  memset_0(v62, 0, 0x25Au);
  v46 = GUID_NULL;
  UnattendInitializeLogEx2(0);
  UnattendLogW(0, L"Enter WinReRestoreConfigAfterPBR");
  v5 = a1;
  if ( !a1 )
    v5 = L"NULL";
  UnattendLogW(0, L"Parameters: szNewOsConfigPath: %s, bUseDownlevelWinReLocation: %d", v5, a2);
  UnattendLogW(0, L"WinReRestoreConfigAfterPBR Searching for reload.xml");
  LogDirPathInternal = WinReGetLogDirPathInternal(&lpFileName);
  if ( LogDirPathInternal )
  {
    v35 = 941;
    v7 = L"Failed to get log directory";
LABEL_5:
    UnattendLogW(
      2,
      L"WinReRestoreConfigAfterPBR %s (0x%x) in file %S line %d",
      v7,
      LogDirPathInternal,
      "base\\diagnosis\\srt\\reagent2\\reagent\\logfile.cpp",
      v35);
LABEL_120:
    SetLastError(LogDirPathInternal);
    v10 = 0;
    goto LABEL_121;
  }
  v8 = (WCHAR *)lpFileName;
  UnattendLogW(0, L"WinReRestoreConfigAfterPBR Logs location is %s", lpFileName);
  LogDirPathInternal = winreOpenOrCreateDir(v8);
  if ( LogDirPathInternal )
  {
    v35 = 945;
    v7 = L"Failed to open log directory";
    goto LABEL_5;
  }
  v9 = 0;
  v10 = 1;
  LogDirPathInternal = winreAllocPath(&v40);
  if ( !LogDirPathInternal )
  {
    LogDirPathInternal = winreAddFileToDirPath(v8, L"Reload.xml", v40);
    if ( LogDirPathInternal )
    {
      v36 = 955;
      v11 = L"failed to add reload file to directory path";
      goto LABEL_10;
    }
    UnattendLogW(0, L"WinReRestoreConfigAfterPBR Processing %s and disable update enhanced config info", v40);
    UnattendLogW(0, L"DisableUpdateEnhancedConfigInfo");
    v55 = 1;
    LogDirPathInternal = ReAgentReload::Init((ReAgentReload *)v49, v40, 1);
    if ( LogDirPathInternal )
    {
      v36 = 961;
      v11 = L"Failed to parse reload.xml";
      goto LABEL_10;
    }
    ConfigInfo = ReAgentXMLParser::GetConfigInfo((ReAgentXMLParser *)v49);
    lpFileName = (LPCWSTR)ConfigInfo;
    v43 = (unsigned __int16 *)((char *)ConfigInfo + 16);
    UnattendLogW(0, L"WinReRestoreConfigAfterPBR reload.xml WinreLocation: %s", (char *)ConfigInfo + 16);
    v45 = (unsigned __int16 *)((char *)ConfigInfo + 1256);
    UnattendLogW(0, L"WinReRestoreConfigAfterPBR reload.xml ImageLocation: %s", (char *)ConfigInfo + 1256);
    UnattendLogW(0, L"WinReRestoreConfigAfterPBR reload.xml DownlevelWinreLocation: %s", (char *)ConfigInfo + 6232);
    UnattendLogW(0, L"WinReRestoreConfigAfterPBR reload.xml InstallState: %d", *((unsigned int *)ConfigInfo + 1397));
    PrivateFreePartitionList(0);
    LogDirPathInternal = SetWinReOperationSyncKey();
    if ( LogDirPathInternal )
    {
      v36 = 985;
      v11 = L"Failed to set the operation key";
      goto LABEL_10;
    }
    v37 = 1;
    v42 = 1;
    LogDirPathInternal = winreGetConfigFilePathFromWinDir(v44, 1, v14, v48);
    if ( LogDirPathInternal )
    {
      UnattendLogW(
        2,
        L"WinReRestoreConfigAfterPBR %s (0x%x) in file %S line %d",
        L"Failed to get ReAgent.xml path",
        LogDirPathInternal,
        "base\\diagnosis\\srt\\reagent2\\reagent\\logfile.cpp",
        997);
LABEL_19:
      v12 = 1;
      goto LABEL_108;
    }
    try
    {
      v15 = (void **)operator new(0x50u);
      v9 = v15;
      if ( v15 )
      {
        v15[1] = 0;
        v15[2] = 0;
        *((_DWORD *)v15 + 6) = 0;
        *((_DWORD *)v15 + 7) = 2;
        v15[4] = 0;
        v15[5] = 0;
        v15[6] = 0;
        v15[7] = 0;
        v15[8] = 0;
        *v15 = &ReAgentConfig::`vftable';
        *((_DWORD *)v15 + 18) = 0;
      }
      else
      {
        v9 = 0;
      }
    }
    catch ( std::bad_alloc )
    {
      v4 = pv;
      v9 = 0;
      v37 = v42;
      v10 = v42;
      goto LABEL_107;
    }
    if ( !v9 )
    {
      v10 = 1;
LABEL_107:
      LogDirPathInternal = 8;
      UnattendLogW(
        2,
        L"WinReRestoreConfigAfterPBR %s (0x%x) in file %S line %d",
        L"failed to allocate memory",
        8,
        "base\\diagnosis\\srt\\reagent2\\reagent\\logfile.cpp",
        999);
      v12 = v37;
      goto LABEL_108;
    }
    v16 = v48[0];
    LogDirPathInternal = (*((__int64 (__fastcall **)(void **, LPVOID, __int64))*v9 + 1))(v9, v48[0], 1);
    if ( LogDirPathInternal )
    {
      UnattendLogW(
        2,
        L"WinReRestoreConfigAfterPBR %s (0x%x) in file %S line %d",
        L"Failed to parse ReAgent.xml",
        LogDirPathInternal,
        "base\\diagnosis\\srt\\reagent2\\reagent\\logfile.cpp",
        1001);
      v10 = 1;
      v12 = 1;
      goto LABEL_109;
    }
    v17 = ReAgentXMLParser::GetConfigInfo((ReAgentXMLParser *)v9);
    UnattendLogW(0, L"WinReRestoreConfigAfterPBR reagent.xml WinreLocation: %s", (char *)v17 + 16);
    UnattendLogW(0, L"WinReRestoreConfigAfterPBR reagent.xml ImageLocation: %s", (char *)v17 + 1256);
    UnattendLogW(0, L"WinReRestoreConfigAfterPBR reagent.xml DownlevelWinreLocation: %s", (char *)v17 + 6232);
    UnattendLogW(0, L"WinReRestoreConfigAfterPBR reagent.xml InstallState: %d", *((unsigned int *)v17 + 1397));
    v18 = v45;
    if ( *v45 )
    {
      v19 = winreAllocPath(&pv);
      v4 = pv;
      if ( !v19 && StringCchCopyW((unsigned __int16 *)pv, 0x12Eu, v18) < 0 && v4 )
      {
        CoTaskMemFree(v4);
        v4 = 0;
        pv = 0;
      }
    }
    if ( v41 )
    {
      LogDirPathInternal = winreAddFileToDirPath((unsigned __int16 *)lpFileName + 3116, L"Winre.wim", &v57);
      if ( LogDirPathInternal )
      {
        LODWORD(v34) = 1044;
LABEL_35:
        v20 = L"failed to add winre.wim to directory path";
LABEL_36:
        UnattendLogW(
          2,
          L"WinReRestoreConfigAfterPBR %s (0x%x) in file %S line %d",
          v20,
          LogDirPathInternal,
          "base\\diagnosis\\srt\\reagent2\\reagent\\logfile.cpp",
          v34);
LABEL_37:
        v10 = 1;
        goto LABEL_19;
      }
      if ( !Utils::DoesPathExist(&v57) )
      {
        UnattendLogW(0, L"WinReRestoreConfigAfterPBR Using WinRE from downlevel OS");
        ReAgentConfig::SetInstallState((ReAgentConfig *)v49, 0);
        LogDirPathInternal = ReAgentConfig::SetWinreLocationPath(
                               (ReAgentConfig *)v49,
                               v21,
                               &v46,
                               0,
                               (unsigned __int16 *)&cchOriginalDestLength);
        if ( LogDirPathInternal )
        {
          LODWORD(v34) = 1206;
LABEL_41:
          v20 = L"Failed to clear WinreLocationPath";
          goto LABEL_36;
        }
        LogDirPathInternal = ReAgentConfig::SetImageLocationPath(
                               (ReAgentConfig *)v49,
                               *((_QWORD *)lpFileName + 933),
                               (struct _GUID *)(lpFileName + 3722),
                               *((_DWORD *)lpFileName + 1860),
                               (unsigned __int16 *)lpFileName + 3418);
        if ( LogDirPathInternal )
        {
          LODWORD(v34) = 1213;
          v20 = L"Failed to stage WinRE to the downlevel WinRE location";
          goto LABEL_36;
        }
        LogDirPathInternal = winreAddFileToDirPath(v22, L"boot.sdi", &FileName);
        if ( LogDirPathInternal )
        {
          LODWORD(v34) = 1220;
          v20 = L"failed to add boot.sdi directory path";
          goto LABEL_36;
        }
        if ( !Utils::DoesPathExist(&FileName) )
        {
          UnattendLogW(0, L"WinReRestoreConfigAfterPBR Deleting old boot.sdi");
          DeleteFileW(&FileName);
        }
        goto LABEL_48;
      }
      goto LABEL_80;
    }
    LogDirPathInternal = winreAddFileToDirPath(v43, L"Winre.wim", &v57);
    if ( LogDirPathInternal )
    {
      LODWORD(v34) = 1056;
      goto LABEL_35;
    }
    if ( Utils::DoesPathExist(&v57) || (v23 = lpFileName, *((_DWORD *)lpFileName + 1397) != 1) )
    {
      LogDirPathInternal = winreAddFileToDirPath(v45, L"Winre.wim", &v57);
      if ( LogDirPathInternal )
      {
        LODWORD(v34) = 1068;
        goto LABEL_35;
      }
      if ( !Utils::DoesPathExist(&v57) )
      {
        UnattendLogW(0, L"WinReRestoreConfigAfterPBR Using staged WinRE from old OS");
        ReAgentConfig::SetInstallState((ReAgentConfig *)v49, 0);
        LogDirPathInternal = ReAgentConfig::SetWinreLocationPath(
                               (ReAgentConfig *)v49,
                               v26,
                               &v46,
                               0,
                               (unsigned __int16 *)&cchOriginalDestLength);
        if ( LogDirPathInternal )
        {
          LODWORD(v34) = 1137;
          goto LABEL_41;
        }
        goto LABEL_48;
      }
LABEL_80:
      LogDirPathInternal = winreAddFileToDirPath((unsigned __int16 *)v17 + 628, L"Winre.wim", &v57);
      if ( LogDirPathInternal )
      {
        LODWORD(v34) = 1082;
        goto LABEL_35;
      }
      if ( Utils::DoesPathExist(&v57) )
      {
        UnattendLogW(0, L"WinReRestoreConfigAfterPBR Using default WinRE from new OS");
        ReAgentConfig::SetInstallState((ReAgentConfig *)v49, 0);
        LogDirPathInternal = ReAgentConfig::SetWinreLocationPath(
                               (ReAgentConfig *)v49,
                               v28,
                               &v46,
                               0,
                               (unsigned __int16 *)&cchOriginalDestLength);
        if ( LogDirPathInternal )
        {
          LODWORD(v34) = 1242;
          goto LABEL_41;
        }
        LogDirPathInternal = ReAgentConfig::SetImageLocationPath((ReAgentConfig *)v49, 0, &v46, 0, v29);
        if ( LogDirPathInternal )
        {
          LODWORD(v34) = 1249;
          v20 = L"Failed to clear ImageLocationPath";
          goto LABEL_36;
        }
      }
      else
      {
        UnattendLogW(0, L"WinReRestoreConfigAfterPBR Using staged WinRE from new OS");
        ReAgentConfig::SetInstallState((ReAgentConfig *)v49, 0);
        LogDirPathInternal = ReAgentConfig::SetWinreLocationPath(
                               (ReAgentConfig *)v49,
                               v27,
                               &v46,
                               0,
                               (unsigned __int16 *)&cchOriginalDestLength);
        if ( LogDirPathInternal )
        {
          LODWORD(v34) = 1112;
          goto LABEL_41;
        }
        LogDirPathInternal = ReAgentConfig::SetImageLocationPath(
                               (ReAgentConfig *)v49,
                               *((_QWORD *)v17 + 311),
                               (struct _GUID *)((char *)v17 + 2468),
                               *((_DWORD *)v17 + 616),
                               (unsigned __int16 *)v17 + 930);
        if ( LogDirPathInternal )
        {
          LODWORD(v34) = 1122;
          v20 = L"Failed to stage WinRE to the new OS image location";
          goto LABEL_36;
        }
      }
      goto LABEL_48;
    }
    UnattendLogW(0, L"WinReRestoreConfigAfterPBR Using installed WinRE from old OS");
    if ( ReAgentXMLParser::IsOemDir((ReAgentXMLParser *)v9) )
    {
LABEL_49:
      UnattendLogW(0, L"WinReRestoreConfigAfterPBR Searching for a recovery image from the old OS");
      for ( i = 0; ; ++i )
      {
        if ( i >= 3 )
        {
          UnattendLogW(0, L"WinReRestoreConfigAfterPBR Searching for a recovery image from the new OS");
          for ( j = 0; ; ++j )
          {
            if ( j >= 3 )
            {
              UnattendLogW(2, L"WinReRestoreConfigAfterPBR Failed to find a recovery image");
              goto LABEL_102;
            }
            LogDirPathInternal = winreAddFileToDirPath((unsigned __int16 *)v17 + 1248, off_180061610[j], &v59);
            if ( LogDirPathInternal )
            {
              LODWORD(v34) = 1279;
              v20 = L"failed to add file to directory path";
              goto LABEL_36;
            }
            if ( !Utils::DoesPathExist(&v59) )
              break;
          }
          UnattendLogW(0, L"Found recovery image from new OS at %s", &v59);
          LogDirPathInternal = ReAgentConfig::SetOsInstallLocationPath(
                                 (ReAgentConfig *)v49,
                                 *((_QWORD *)v17 + 466),
                                 (struct _GUID *)((char *)v17 + 3708),
                                 *((_DWORD *)v17 + 926),
                                 (unsigned __int16 *)v17 + 1550,
                                 *((_DWORD *)v17 + 1395));
          if ( !LogDirPathInternal )
            goto LABEL_102;
          LODWORD(v34) = 1291;
          v20 = L"Failed to update OsInstallLocationPath";
          goto LABEL_36;
        }
        LogDirPathInternal = winreAddFileToDirPath((unsigned __int16 *)v23 + 1248, off_180061610[i], &v59);
        if ( LogDirPathInternal )
        {
          LODWORD(v34) = 1262;
          v20 = L"Failed to add file to directory path";
          goto LABEL_36;
        }
        if ( !Utils::DoesPathExist(&v59) )
          break;
        v23 = lpFileName;
      }
      UnattendLogW(0, L"WinReRestoreConfigAfterPBR Found recovery image from old OS at %s", &v59);
LABEL_102:
      v31 = ReAgentXMLParser::GetConfigInfo((ReAgentXMLParser *)v49);
      UnattendLogW(0, L" Final WinreLocation: %s", (char *)v31 + 16);
      UnattendLogW(0, L" Final ImageLocation: %s", (char *)v31 + 1256);
      UnattendLogW(0, L" Final DownlevelWinreLocation: %s", (char *)v31 + 6232);
      UnattendLogW(0, L" Final InstallState: %d", *((unsigned int *)v31 + 1397));
      UnattendLogW(0, L" Final OsInstallLocation: %s", (char *)v31 + 2496);
      UnattendLogW(0, L" Final OsImageIndex: %d", *((unsigned int *)v31 + 1395));
      v32 = StringCchCopyW((unsigned __int16 *)v31 + 2488, 0x12Eu, (const unsigned __int16 *)v17 + 2488);
      if ( v32 < 0 )
      {
        LODWORD(v34) = 1322;
        UnattendLogW(
          2,
          L"WinReRestoreConfigAfterPBR %s (0x%x) in file %S line %d",
          L"failed to copy string",
          (unsigned int)v32,
          "base\\diagnosis\\srt\\reagent2\\reagent\\logfile.cpp",
          v34);
        LogDirPathInternal = (unsigned __int16)v32;
        goto LABEL_37;
      }
      memcpy_0(v9[8], v31, 0x1D38u);
      *((_DWORD *)v9[8] + 1403) = 4;
      LogDirPathInternal = ReAgentXMLParser::Update((ReAgentXMLParser *)v9);
      if ( LogDirPathInternal )
      {
        LODWORD(v34) = 1326;
        v20 = L"Failed to update ReAgent.xml";
        goto LABEL_36;
      }
      (*(void (__fastcall **)(void **, __int64))*v9)(v9, 1);
      v9 = 0;
      RemoveWinReOperationSyncKey();
      v12 = 0;
      v10 = 1;
      goto LABEL_108;
    }
    if ( !*((_WORD *)v17 + 628) || Utils::DoesFileExist((const unsigned __int16 *)v17 + 628, L"Winre.wim") )
    {
      LogDirPathInternal = winreAllocPath(&pv);
      if ( LogDirPathInternal )
      {
        UnattendLogW(
          2,
          L"WinReRestoreConfigAfterPBR %s (0x%x) in file %S line %d",
          L"failed to allocate path",
          LogDirPathInternal,
          "base\\diagnosis\\srt\\reagent2\\reagent\\logfile.cpp",
          1171);
        v4 = pv;
        goto LABEL_37;
      }
      v4 = pv;
      if ( StringCchPrintfW((unsigned __int16 *)pv, 0x12Eu, L"%s\\system32\\%s", v44, L"Recovery") < 0 )
      {
        LogDirPathInternal = -1073741811;
        goto LABEL_37;
      }
      if ( Utils::DoesFileExist((const unsigned __int16 *)v4, L"Winre.wim") )
      {
        if ( !v4 )
        {
LABEL_48:
          v23 = lpFileName;
          goto LABEL_49;
        }
        CoTaskMemFree(v4);
        v4 = 0;
      }
    }
    else
    {
      v25 = winreAllocPath(&pv);
      v4 = pv;
      if ( !v25 && StringCchCopyW((unsigned __int16 *)pv, 0x12Eu, (const unsigned __int16 *)v17 + 628) < 0 )
      {
        if ( v4 )
        {
          CoTaskMemFree(v4);
          v4 = 0;
        }
        LogDirPathInternal = 266;
        goto LABEL_37;
      }
    }
    if ( v4 )
    {
      UnattendLogW(0, L"WinReRestoreConfigAfterPBR Deleting staged WinRE from %s", v4);
      winreDeleteStagedFiles((unsigned __int16 *)v4);
    }
    goto LABEL_48;
  }
  v36 = 951;
  v11 = L"failed to allocate path";
LABEL_10:
  UnattendLogW(
    2,
    L"WinReRestoreConfigAfterPBR %s (0x%x) in file %S line %d",
    v11,
    LogDirPathInternal,
    "base\\diagnosis\\srt\\reagent2\\reagent\\logfile.cpp",
    v36);
  v12 = 0;
LABEL_108:
  v16 = v48[0];
LABEL_109:
  if ( v40 )
    CoTaskMemFree(v40);
  if ( v16 )
    CoTaskMemFree(v16);
  if ( v4 )
    CoTaskMemFree(v4);
  if ( v9 )
    (*(void (__fastcall **)(void **, __int64))*v9)(v9, 1);
  if ( v12 )
    RemoveWinReOperationSyncKey();
  if ( LogDirPathInternal )
    goto LABEL_120;
LABEL_121:
  WinReDeleteLogFilesInternal();
  UnattendLogW(0, L"Exit WinReRestoreConfigAfterPBR return value: %d, last error: 0x%x", v10, LogDirPathInternal);
  UnattendFinalizeLog();
  ReAgentReload::~ReAgentReload((ReAgentReload *)v49);
  return v10;
}

```

## disassembly

```asm
0x18002a570  mov     r11, rsp
0x18002a573  push    rdi
0x18002a574  push    r12
0x18002a576  push    r13
0x18002a578  push    r14
0x18002a57a  push    r15
0x18002a57c  sub     rsp, 830h
0x18002a583  mov     qword ptr [r11-7D8h], 0FFFFFFFFFFFFFFFEh
0x18002a58e  mov     [r11+18h], rbx
0x18002a592  mov     [r11+20h], rsi
0x18002a596  mov     rax, cs:__security_cookie
0x18002a59d  xor     rax, rsp
0x18002a5a0  mov     [rsp+858h+var_38], rax
0x18002a5a8  mov     esi, edx
0x18002a5aa  mov     [rsp+858h+var_808], edx
0x18002a5ae  mov     rbx, rcx
0x18002a5b1  mov     [rsp+858h+var_7F8], rcx
0x18002a5b6  xor     edi, edi
0x18002a5b8  mov     [rsp+858h+lpFileName], rdi
0x18002a5bd  mov     [rsp+858h+var_810], rdi
0x18002a5c2  mov     [r11-7C8h], rdi
0x18002a5c9  mov     r15d, edi
0x18002a5cc  mov     [rsp+858h+pv], rdi
0x18002a5d1  mov     [r11-7B0h], rdi
0x18002a5d8  mov     [r11-7A8h], rdi
0x18002a5df  mov     [rsp+858h+var_7A0], edi
0x18002a5e6  lea     r14d, [rdi+2]
0x18002a5ea  mov     [r11-79Ch], r14d
0x18002a5f1  xorps   xmm0, xmm0
0x18002a5f4  movdqa  [rsp+858h+var_798], xmm0
0x18002a5fd  xorps   xmm1, xmm1
0x18002a600  movdqa  [rsp+858h+var_788], xmm1
0x18002a609  mov     [r11-778h], rdi
0x18002a610  mov     [rsp+858h+var_770], edi
0x18002a617  lea     rax, ??_7ReAgentReload@@6B@; const ReAgentReload::`vftable'
0x18002a61e  mov     [r11-7B8h], rax
0x18002a625  mov     [r11-768h], rdi
0x18002a62c  mov     [rsp+858h+var_4F8], di
0x18002a634  mov     r12d, 25Ah
0x18002a63a  mov     r8d, r12d; Size
0x18002a63d  xor     edx, edx; Val
0x18002a63f  lea     rcx, [r11-4F6h]; void *
0x18002a646  call    memset_0
0x18002a64b  mov     [rsp+858h+var_758], di
0x18002a653  mov     r8d, r12d; Size
0x18002a656  xor     edx, edx; Val
0x18002a658  lea     rcx, [rsp+858h+var_756]; void *
0x18002a660  call    memset_0
0x18002a665  mov     [rsp+858h+FileName], di
0x18002a66d  mov     r8d, r12d; Size
0x18002a670  xor     edx, edx; Val
0x18002a672  lea     rcx, [rsp+858h+var_296]; void *
0x18002a67a  call    memset_0
0x18002a67f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002a686  movdqu  xmmword ptr [rsp+858h+var_7E8.Data1], xmm0
0x18002a68c  xor     ecx, ecx
0x18002a68e  call    UnattendInitializeLogEx2
0x18002a693  lea     rdx, aEnterWinrerest_0; "Enter WinReRestoreConfigAfterPBR"
0x18002a69a  xor     ecx, ecx
0x18002a69c  call    UnattendLogW
0x18002a6a1  lea     rax, aNull_0; "NULL"
0x18002a6a8  mov     r8, rbx
0x18002a6ab  test    rbx, rbx
0x18002a6ae  cmovz   r8, rax
0x18002a6b2  mov     r9d, esi
0x18002a6b5  lea     rdx, aParametersSzne; "Parameters: szNewOsConfigPath: %s, bUse"...
0x18002a6bc  xor     ecx, ecx
0x18002a6be  call    UnattendLogW
0x18002a6c3  lea     rdx, aWinrerestoreco_19; "WinReRestoreConfigAfterPBR Searching fo"...
0x18002a6ca  xor     ecx, ecx
0x18002a6cc  call    UnattendLogW
0x18002a6d1  lea     rcx, [rsp+858h+lpFileName]
0x18002a6d6  call    WinReGetLogDirPathInternal
0x18002a6db  mov     ebx, eax
0x18002a6dd  test    eax, eax
0x18002a6df  jz      short loc_18002A713
0x18002a6e1  mov     dword ptr [rsp+858h+var_830], 3ADh
0x18002a6e9  lea     r8, aFailedToGetLog; "Failed to get log directory"
0x18002a6f0  lea     rax, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002a6f7  mov     r9d, ebx
0x18002a6fa  mov     [rsp+858h+var_838], rax
0x18002a6ff  lea     rdx, aWinrerestoreco_8; "WinReRestoreConfigAfterPBR %s (0x%x) in"...
0x18002a706  mov     ecx, r14d
0x18002a709  call    UnattendLogW
0x18002a70e  jmp     loc_18002B2E9
0x18002a713  mov     r13, [rsp+858h+lpFileName]
0x18002a718  mov     r8, r13
0x18002a71b  lea     rdx, aWinrerestoreco_9; "WinReRestoreConfigAfterPBR Logs locatio"...
0x18002a722  xor     ecx, ecx
0x18002a724  call    UnattendLogW
0x18002a729  mov     rcx, r13; lpFileName
0x18002a72c  call    winreOpenOrCreateDir
0x18002a731  mov     ebx, eax
0x18002a733  test    eax, eax
0x18002a735  jz      short loc_18002A748
0x18002a737  mov     dword ptr [rsp+858h+var_830], 3B1h
0x18002a73f  lea     r8, aFailedToOpenLo_2; "Failed to open log directory"
0x18002a746  jmp     short loc_18002A6F0
0x18002a748  mov     rsi, rdi
0x18002a74b  mov     r12d, 1
0x18002a751  mov     [rsp+858h+var_828], r12d
0x18002a756  lea     rcx, [rsp+858h+var_810]
0x18002a75b  call    winreAllocPath
0x18002a760  mov     ebx, eax
0x18002a762  test    eax, eax
0x18002a764  jz      short loc_18002A79B
0x18002a766  mov     dword ptr [rsp+858h+var_830], 3B7h
0x18002a76e  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x18002a775  lea     rax, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002a77c  mov     r9d, ebx
0x18002a77f  mov     [rsp+858h+var_838], rax
0x18002a784  lea     rdx, aWinrerestoreco_8; "WinReRestoreConfigAfterPBR %s (0x%x) in"...
0x18002a78b  mov     ecx, r14d
0x18002a78e  call    UnattendLogW
0x18002a793  mov     r14d, esi
0x18002a796  jmp     loc_18002B28C
0x18002a79b  mov     r8, [rsp+858h+var_810]; unsigned __int16 *
0x18002a7a0  lea     rdx, aReloadXml; "Reload.xml"
0x18002a7a7  mov     rcx, r13; unsigned __int16 *
0x18002a7aa  call    winreAddFileToDirPath
0x18002a7af  mov     ebx, eax
0x18002a7b1  test    eax, eax
0x18002a7b3  jz      short loc_18002A7C6
0x18002a7b5  mov     dword ptr [rsp+858h+var_830], 3BBh
0x18002a7bd  lea     r8, aFailedToAddRel; "failed to add reload file to directory "...
0x18002a7c4  jmp     short loc_18002A775
0x18002a7c6  mov     r8, [rsp+858h+var_810]
0x18002a7cb  lea     rdx, aWinrerestoreco_3; "WinReRestoreConfigAfterPBR Processing %"...
0x18002a7d2  xor     ecx, ecx
0x18002a7d4  call    UnattendLogW
0x18002a7d9  lea     rdx, aDisableupdatee; "DisableUpdateEnhancedConfigInfo"
0x18002a7e0  xor     ecx, ecx
0x18002a7e2  call    UnattendLogW
0x18002a7e7  mov     [rsp+858h+var_770], r12d
0x18002a7ef  mov     r8d, r12d; int
0x18002a7f2  mov     rdx, [rsp+858h+var_810]; unsigned __int16 *
0x18002a7f7  lea     rcx, [rsp+858h+var_7B8]; this
0x18002a7ff  call    ?Init@ReAgentReload@@UEAAKPEAGH@Z; ReAgentReload::Init(ushort *,int)
0x18002a804  mov     ebx, eax
0x18002a806  test    eax, eax
0x18002a808  jz      short loc_18002A81E
0x18002a80a  mov     dword ptr [rsp+858h+var_830], 3C1h
0x18002a812  lea     r8, aFailedToParseR; "Failed to parse reload.xml"
0x18002a819  jmp     loc_18002A775
0x18002a81e  lea     rcx, [rsp+858h+var_7B8]; this
0x18002a826  call    ?GetConfigInfo@ReAgentXMLParser@@QEAAPEAUReAgentConfigInfo@@XZ; ReAgentXMLParser::GetConfigInfo(void)
0x18002a82b  mov     rbx, rax
0x18002a82e  mov     [rsp+858h+lpFileName], rax
0x18002a833  add     rax, 10h
0x18002a837  mov     [rsp+858h+var_800], rax
0x18002a83c  mov     r8, rax
0x18002a83f  lea     rdx, aWinrerestoreco_18; "WinReRestoreConfigAfterPBR reload.xml W"...
0x18002a846  xor     ecx, ecx
0x18002a848  call    UnattendLogW
0x18002a84d  lea     rax, [rbx+4E8h]
0x18002a854  mov     [rsp+858h+var_7F0], rax
0x18002a859  mov     r8, rax
0x18002a85c  lea     rdx, aWinrerestoreco_10; "WinReRestoreConfigAfterPBR reload.xml I"...
0x18002a863  xor     ecx, ecx
0x18002a865  call    UnattendLogW
0x18002a86a  lea     r8, [rbx+1858h]
0x18002a871  lea     rdx, aWinrerestoreco_14; "WinReRestoreConfigAfterPBR reload.xml D"...
0x18002a878  xor     ecx, ecx
0x18002a87a  call    UnattendLogW
0x18002a87f  mov     r8d, [rbx+15D4h]
0x18002a886  lea     rdx, aWinrerestoreco_13; "WinReRestoreConfigAfterPBR reload.xml I"...
0x18002a88d  xor     ecx, ecx
0x18002a88f  call    UnattendLogW
0x18002a894  xor     ecx, ecx; pv
0x18002a896  call    PrivateFreePartitionList
0x18002a89b  call    SetWinReOperationSyncKey
0x18002a8a0  mov     ebx, eax
0x18002a8a2  test    eax, eax
0x18002a8a4  jz      short loc_18002A8BA
0x18002a8a6  mov     dword ptr [rsp+858h+var_830], 3D9h
0x18002a8ae  lea     r8, aFailedToSetThe; "Failed to set the operation key"
0x18002a8b5  jmp     loc_18002A775
0x18002a8ba  mov     [rsp+858h+var_824], r12d
0x18002a8bf  mov     [rsp+858h+var_804], r12d
0x18002a8c4  lea     r9, [rsp+858h+var_7C8]
0x18002a8cc  mov     edx, r12d
0x18002a8cf  mov     rcx, [rsp+858h+var_7F8]
0x18002a8d4  call    winreGetConfigFilePathFromWinDir
0x18002a8d9  mov     ebx, eax
0x18002a8db  test    eax, eax
0x18002a8dd  jz      short loc_18002A914
0x18002a8df  mov     dword ptr [rsp+858h+var_830], 3E5h
0x18002a8e7  lea     rax, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002a8ee  mov     [rsp+858h+var_838], rax
0x18002a8f3  mov     r9d, ebx
0x18002a8f6  lea     r8, aFailedToGetRea; "Failed to get ReAgent.xml path"
0x18002a8fd  lea     rdx, aWinrerestoreco_8; "WinReRestoreConfigAfterPBR %s (0x%x) in"...
0x18002a904  mov     ecx, r14d
0x18002a907  call    UnattendLogW
0x18002a90c  mov     r14d, r12d
0x18002a90f  jmp     loc_18002B28C
0x18002a914  mov     ecx, 50h ; 'P'; Size
0x18002a919  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a91e  mov     rsi, rax
0x18002a921  test    rax, rax
0x18002a924  jz      short loc_18002A958
0x18002a926  mov     [rax+8], rdi
0x18002a92a  mov     [rax+10h], rdi
0x18002a92e  mov     [rax+18h], edi
0x18002a931  mov     [rax+1Ch], r14d
0x18002a935  mov     [rax+20h], rdi
0x18002a939  mov     [rax+28h], rdi
0x18002a93d  mov     [rax+30h], rdi
0x18002a941  mov     [rax+38h], rdi
0x18002a945  mov     [rax+40h], rdi
0x18002a949  lea     rax, ??_7ReAgentConfig@@6B@; const ReAgentConfig::`vftable'
0x18002a950  mov     [rsi], rax
0x18002a953  mov     [rsi+48h], edi
0x18002a956  jmp     short loc_18002A95B
0x18002a958  mov     rsi, rdi
0x18002a95b  test    rsi, rsi
0x18002a95e  jnz     short loc_18002A96A
0x18002a960  mov     r12d, [rsp+858h+var_828]
0x18002a965  jmp     loc_18002B255
0x18002a96a  mov     rax, [rsi]
0x18002a96d  mov     r8d, r12d
0x18002a970  mov     r13, [rsp+858h+var_7C8]
0x18002a978  mov     rdx, r13
0x18002a97b  mov     rcx, rsi
0x18002a97e  mov     rax, [rax+8]
0x18002a982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a987  mov     ebx, eax
0x18002a989  test    eax, eax
0x18002a98b  jz      short loc_18002A9C7
0x18002a98d  mov     dword ptr [rsp+858h+var_830], 3E9h
0x18002a995  lea     rax, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002a99c  mov     [rsp+858h+var_838], rax
0x18002a9a1  mov     r9d, ebx
0x18002a9a4  lea     r8, aFailedToParseR_0; "Failed to parse ReAgent.xml"
0x18002a9ab  lea     rdx, aWinrerestoreco_8; "WinReRestoreConfigAfterPBR %s (0x%x) in"...
0x18002a9b2  mov     ecx, r14d
0x18002a9b5  call    UnattendLogW
0x18002a9ba  mov     r12d, [rsp+858h+var_828]
0x18002a9bf  mov     r14d, r12d
0x18002a9c2  jmp     loc_18002B294
0x18002a9c7  mov     rcx, rsi; this
0x18002a9ca  call    ?GetConfigInfo@ReAgentXMLParser@@QEAAPEAUReAgentConfigInfo@@XZ; ReAgentXMLParser::GetConfigInfo(void)
0x18002a9cf  mov     r13, rax
0x18002a9d2  lea     r8, [rax+10h]
0x18002a9d6  lea     rdx, aWinrerestoreco_0; "WinReRestoreConfigAfterPBR reagent.xml "...
0x18002a9dd  xor     ecx, ecx
0x18002a9df  call    UnattendLogW
0x18002a9e4  lea     r8, [r13+4E8h]
0x18002a9eb  lea     rdx, aWinrerestoreco_4; "WinReRestoreConfigAfterPBR reagent.xml "...
0x18002a9f2  xor     ecx, ecx
0x18002a9f4  call    UnattendLogW
0x18002a9f9  lea     r8, [r13+1858h]
0x18002aa00  lea     rdx, aWinrerestoreco_1; "WinReRestoreConfigAfterPBR reagent.xml "...
0x18002aa07  xor     ecx, ecx
0x18002aa09  call    UnattendLogW
0x18002aa0e  mov     r8d, [r13+15D4h]
0x18002aa15  lea     rdx, aWinrerestoreco_6; "WinReRestoreConfigAfterPBR reagent.xml "...
0x18002aa1c  xor     ecx, ecx
0x18002aa1e  call    UnattendLogW
0x18002aa23  mov     rbx, [rsp+858h+var_7F0]
0x18002aa28  cmp     di, [rbx]
0x18002aa2b  jz      short loc_18002AA6A
0x18002aa2d  lea     rcx, [rsp+858h+pv]
0x18002aa32  call    winreAllocPath
0x18002aa37  mov     r15, [rsp+858h+pv]
0x18002aa3c  test    eax, eax
0x18002aa3e  jnz     short loc_18002AA6A
0x18002aa40  mov     r8, rbx; unsigned __int16 *
0x18002aa43  mov     edx, 12Eh; unsigned __int64
0x18002aa48  mov     rcx, r15; unsigned __int16 *
0x18002aa4b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002aa50  test    eax, eax
0x18002aa52  jns     short loc_18002AA6A
0x18002aa54  test    r15, r15
0x18002aa57  jz      short loc_18002AA6A
0x18002aa59  mov     rcx, r15; pv
0x18002aa5c  call    cs:__imp_CoTaskMemFree
0x18002aa62  mov     r15, rdi
0x18002aa65  mov     [rsp+858h+pv], rdi
0x18002aa6a  lea     r8, [rsp+858h+var_758]; unsigned __int16 *
0x18002aa72  lea     r12, aWinreWim; "Winre.wim"
0x18002aa79  mov     rdx, r12; unsigned __int16 *
0x18002aa7c  cmp     [rsp+858h+var_808], edi
0x18002aa80  jz      loc_18002AC5E
0x18002aa86  mov     rcx, [rsp+858h+lpFileName]
0x18002aa8b  add     rcx, 1858h; unsigned __int16 *
0x18002aa92  call    winreAddFileToDirPath
0x18002aa97  mov     ebx, eax
0x18002aa99  test    eax, eax
0x18002aa9b  jz      short loc_18002AAD4
0x18002aa9d  mov     dword ptr [rsp+858h+var_830], 414h
0x18002aaa5  lea     r8, aFailedToAddWin_0; "failed to add winre.wim to directory pa"...
0x18002aaac  lea     rax, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002aab3  mov     r9d, ebx
0x18002aab6  mov     [rsp+858h+var_838], rax
0x18002aabb  lea     rdx, aWinrerestoreco_8; "WinReRestoreConfigAfterPBR %s (0x%x) in"...
0x18002aac2  mov     ecx, r14d
0x18002aac5  call    UnattendLogW
0x18002aaca  mov     r12d, [rsp+858h+var_828]
0x18002aacf  jmp     loc_18002A90C
  ... truncated ...
```
