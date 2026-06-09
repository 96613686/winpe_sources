# winreReconstructConfigXML

- ea: `0x18003bfbc`
- end: `0x18003cbe0`
- name: `winreReconstructConfigXML`
- size: `3108`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x180024ff0`

## callees

- `0x180002ba8`
- `0x1800059fc`
- `0x180006ed8`
- `0x18000c6c0`
- `0x18000c6f0`
- `0x180010010`
- `0x18001051c`
- `0x180010e78`
- `0x180014754`
- `0x1800187e0`
- `0x18001df60`
- `0x180039014`
- `0x1800393e4`
- `0x18003b988`
- `0x18003bfbc`
- `0x18004f8d0`
- `0x18005ced6`
- `0x18005cee2`
- `0x18005cf30`
- `0x18005cff0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003c23b`
- `msvcrt!_wcsicmp` at `0x18003c23b`
- `KERNEL32!GetLastError` at `0x18003c19b`
- `KERNEL32!GetLastError` at `0x18003c874`
- `KERNEL32!GetLastError` at `0x18003c19b`
- `KERNEL32!GetLastError` at `0x18003c874`
- `KERNEL32!RemoveDirectoryW` at `0x18003ca67`
- `KERNEL32!RemoveDirectoryW` at `0x18003ca67`
- `KERNEL32!MoveFileExW` at `0x18003c86a`
- `KERNEL32!MoveFileExW` at `0x18003c86a`
- `KERNEL32!CreateFileW` at `0x18003c27f`
- `KERNEL32!CreateFileW` at `0x18003c27f`
- `KERNEL32!CloseHandle` at `0x18003c1c0`
- `KERNEL32!CloseHandle` at `0x18003cb8f`
- `KERNEL32!CloseHandle` at `0x18003c1c0`
- `KERNEL32!CloseHandle` at `0x18003cb8f`
- `KERNEL32!DeviceIoControl` at `0x18003c2c5`
- `KERNEL32!DeviceIoControl` at `0x18003c306`
- `KERNEL32!DeviceIoControl` at `0x18003c2c5`
- `KERNEL32!DeviceIoControl` at `0x18003c306`
- `KERNEL32!DeleteFileW` at `0x18003c972`
- `KERNEL32!DeleteFileW` at `0x18003ca5a`
- `KERNEL32!DeleteFileW` at `0x18003c972`
- `KERNEL32!DeleteFileW` at `0x18003ca5a`
- `KERNEL32!GetDriveTypeW` at `0x18003c1d0`
- `KERNEL32!GetDriveTypeW` at `0x18003c1d0`
- `KERNEL32!FindFirstVolumeW` at `0x18003c18c`
- `KERNEL32!FindFirstVolumeW` at `0x18003c18c`
- `KERNEL32!FindNextVolumeW` at `0x18003c48b`
- `KERNEL32!FindNextVolumeW` at `0x18003c48b`
- `KERNEL32!FindVolumeClose` at `0x18003cb7c`
- `KERNEL32!FindVolumeClose` at `0x18003cb7c`
- `ole32!CoTaskMemFree` at `0x18003cb9d`
- `ole32!CoTaskMemFree` at `0x18003cb9d`

## string_xrefs

- `0x18003c508`: `failed to convert directory name to offset`
- `0x18003cabe`: `install.wim`
- `0x18003c774`: `failed to append path`
- `0x18003c53c`: `failed to copy string`
- `0x18003c882`: `failed to move file`
- `0x18003c13c`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x18003c50f`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x18003c5a1`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x18003c639`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x18003cb28`: `Updating config xml`
- `0x18003c9e1`: `reagent.xml`
- `0x18003cbaa`: `winreRestoreBackupXML failed: 0x%x`
- `0x18003c15a`: `winreReconstructConfigXML %s (0x%x) in file %S line %d`
- `0x18003c519`: `winreReconstructConfigXML %s (0x%x) in file %S line %d`
- `0x18003c5ab`: `winreReconstructConfigXML %s (0x%x) in file %S line %d`
- `0x18003c657`: `winreReconstructConfigXML %s (0x%x) in file %S line %d`
- `0x18003c545`: `Multiple winre.wims found. Cannot repair`
- `0x18003c415`: `Multiple install.wims found. Not setting install.wim path`
- `0x18003c618`: `failed to image location path`
- `0x18003c650`: `failed to find main OS config directory`

## pseudocode

```c
__int64 __fastcall winreReconstructConfigXML(ReAgentConfig *a1)
{
  int v1; // r15d
  unsigned __int16 *v2; // r14
  int WindowsVolume; // ebx
  HANDLE FirstVolumeW; // r13
  __int64 v5; // rdi
  int v6; // esi
  int v7; // r12d
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // r8
  unsigned __int64 v10; // r8
  const wchar_t *v11; // r8
  const wchar_t *v12; // r8
  ReAgentConfig *v13; // rsi
  const unsigned __int16 *v14; // rsi
  _QWORD *v15; // r11
  __int64 v16; // rdx
  const unsigned __int16 *v17; // r8
  __int64 v18; // r11
  __int64 v19; // rcx
  __int64 v20; // rdx
  const unsigned __int16 *v21; // r8
  DWORD LastError; // eax
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  const unsigned __int16 *v25; // r8
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  int v28; // ebx
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v31; // [rsp+40h] [rbp-C0h] BYREF
  int v32; // [rsp+48h] [rbp-B8h] BYREF
  int v33; // [rsp+4Ch] [rbp-B4h] BYREF
  int v34; // [rsp+50h] [rbp-B0h]
  unsigned __int16 *v35; // [rsp+58h] [rbp-A8h]
  ReAgentConfig *v36; // [rsp+60h] [rbp-A0h]
  __int64 v37; // [rsp+70h] [rbp-90h]
  _BYTE v38[24]; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v39; // [rsp+90h] [rbp-70h]
  struct _GUID v40; // [rsp+94h] [rbp-6Ch] BYREF
  unsigned __int64 v41; // [rsp+560h] [rbp+460h]
  DWORD BytesReturned[4]; // [rsp+5A0h] [rbp+4A0h] BYREF
  _DWORD v43[8]; // [rsp+5B0h] [rbp+4B0h] BYREF
  _BYTE Buf1[112]; // [rsp+5D0h] [rbp+4D0h] BYREF
  int OutBuffer; // [rsp+640h] [rbp+540h] BYREF
  _BYTE v46[92]; // [rsp+644h] [rbp+544h] BYREF
  WCHAR PathName; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE v48[606]; // [rsp+6A2h] [rbp+5A2h] BYREF
  WCHAR szVolumeName; // [rsp+900h] [rbp+800h] BYREF
  _BYTE v50[606]; // [rsp+902h] [rbp+802h] BYREF
  WCHAR ExistingFileName; // [rsp+B60h] [rbp+A60h] BYREF
  _BYTE v52[606]; // [rsp+B62h] [rbp+A62h] BYREF
  WCHAR szFileName; // [rsp+DC0h] [rbp+CC0h] BYREF
  _BYTE v54[606]; // [rsp+DC2h] [rbp+CC2h] BYREF
  unsigned __int16 v55; // [rsp+1020h] [rbp+F20h] BYREF
  _BYTE v56[606]; // [rsp+1022h] [rbp+F22h] BYREF
  unsigned __int16 v57; // [rsp+1280h] [rbp+1180h] BYREF
  _BYTE v58[606]; // [rsp+1282h] [rbp+1182h] BYREF
  wchar_t String1; // [rsp+14E0h] [rbp+13E0h] BYREF
  _BYTE v60[606]; // [rsp+14E2h] [rbp+13E2h] BYREF
  WCHAR NewFileName; // [rsp+1740h] [rbp+1640h] BYREF
  _BYTE v62[606]; // [rsp+1742h] [rbp+1642h] BYREF

  v36 = a1;
  v1 = 0;
  szVolumeName = 0;
  memset_0(v50, 0, 0x25Au);
  v31 = 0;
  BytesReturned[0] = 0;
  v33 = 0;
  v34 = 0;
  String1 = 0;
  memset_0(v60, 0, 0x25Au);
  v55 = 0;
  memset_0(v56, 0, 0x25Au);
  PathName = 0;
  memset_0(v48, 0, 0x25Au);
  szFileName = 0;
  memset_0(v54, 0, 0x25Au);
  v57 = 0;
  memset_0(v58, 0, 0x25Au);
  ExistingFileName = 0;
  memset_0(v52, 0, 0x25Au);
  NewFileName = 0;
  memset_0(v62, 0, 0x25Au);
  v35 = 0;
  v37 = 0;
  v2 = 0;
  memset_0(v38, 0, 0x528u);
  OutBuffer = 0;
  memset_0(v46, 0, sizeof(v46));
  memset_0(v43, 0, 0x90u);
  WindowsVolume = winreGetWindowsVolume(0, &String1);
  if ( WindowsVolume )
  {
    UnattendLogW(
      2,
      L"winreReconstructConfigXML %s (0x%x) in file %S line %d",
      L"failed to get Windows volume",
      (unsigned int)WindowsVolume,
      "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
      3304);
    goto LABEL_132;
  }
  memset_0(v43, 0, 0x90u);
  FirstVolumeW = FindFirstVolumeW(&szVolumeName, 0x12Eu);
  if ( FirstVolumeW == (HANDLE)-1LL )
  {
    WindowsVolume = GetLastError();
    goto LABEL_131;
  }
  v5 = -1;
  v6 = 0;
  v7 = 0;
  do
  {
    if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle((HANDLE)v5);
      v5 = 0;
    }
    if ( GetDriveTypeW(&szVolumeName) == 3 )
    {
      WindowsVolume = StringCchLengthW(&szVolumeName, 0x12Eu, &v31);
      if ( WindowsVolume < 0 )
      {
        LODWORD(dwFlagsAndAttributes) = 3329;
        v12 = L"failed to get the length of volume root";
        goto LABEL_48;
      }
      if ( !v31 )
        continue;
      v8 = 2 * v31 - 2;
      if ( v8 >= 0x25C )
        _report_rangecheckfailure();
      *(_WORD *)&v50[v8 - 2] = 0;
      if ( !_wcsicmp(&String1, &szVolumeName) )
      {
        UnattendLogW(0, L"Skipping OS volume");
        continue;
      }
      v5 = (__int64)CreateFileW(&szVolumeName, 1u, 7u, 0, 3u, 0x2000000u, 0);
      if ( v5 != -1 )
      {
        if ( DeviceIoControl((HANDLE)v5, 0x90064u, 0, 0, &OutBuffer, 0x60u, BytesReturned, 0) )
        {
          if ( DeviceIoControl((HANDLE)v5, 0x70048u, 0, 0, v43, 0x90u, BytesReturned, 0) )
          {
            if ( v43[0] )
            {
              if ( v43[0] != 1 )
                continue;
              if ( memcmp_0(Buf1, &PARTITION_MSFT_RECOVERY_GUID, 0x10u) )
                goto LABEL_20;
            }
            else if ( Buf1[0] != 39 && !Buf1[1] )
            {
LABEL_20:
              UnattendLogW(0, L"Skipping volume %s", &szVolumeName);
              continue;
            }
            UnattendLogW(0, L"Valid MBR parition found");
          }
          UnattendLogW(0, L" Scanning volume %s", &szVolumeName);
          v32 = 0;
          winreScanForWinReWim(&szVolumeName, &v55, v9, &v32, &v33);
          if ( v32 )
          {
            if ( v6 )
            {
              UnattendLogW(1, L"Multiple winre.wims found. Cannot repair");
              WindowsVolume = StringCchCopyW(&PathName, 0x12Eu, &cchOriginalDestLength);
              if ( WindowsVolume >= 0 )
              {
LABEL_124:
                WindowsVolume = 2;
                goto LABEL_125;
              }
              LODWORD(dwFlagsAndAttributes) = 3423;
              goto LABEL_42;
            }
            WindowsVolume = StringCchCopyW(&PathName, 0x12Eu, &v55);
            if ( WindowsVolume < 0 )
            {
              LODWORD(dwFlagsAndAttributes) = 3429;
              goto LABEL_42;
            }
            v1 = v33;
            v6 = 1;
          }
          v32 = 0;
          winreScanForInstallWim(&szVolumeName, &v55, v10, &v32);
          if ( v32 )
          {
            if ( v7 )
            {
              UnattendLogW(1, L"Multiple install.wims found. Not setting install.wim path");
              WindowsVolume = StringCchCopyW(&szFileName, 0x12Eu, &cchOriginalDestLength);
              if ( WindowsVolume < 0 )
              {
                LODWORD(dwFlagsAndAttributes) = 3442;
LABEL_42:
                v12 = L"failed to copy string";
LABEL_48:
                UnattendLogW(
                  2,
                  L"winreReconstructConfigXML %s (0x%x) in file %S line %d",
                  v12,
                  (unsigned int)WindowsVolume,
                  "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
                  dwFlagsAndAttributes);
                WindowsVolume = (unsigned __int16)WindowsVolume;
                goto LABEL_125;
              }
            }
            else
            {
              WindowsVolume = StringCchCopyW(&szFileName, 0x12Eu, &v55);
              if ( WindowsVolume < 0 )
              {
                LODWORD(dwFlagsAndAttributes) = 3446;
                goto LABEL_42;
              }
              v7 = 1;
            }
          }
        }
      }
    }
  }
  while ( FindNextVolumeW(FirstVolumeW, &szVolumeName, 0x12Eu) );
  if ( !v6 || !PathName )
  {
    UnattendLogW(1, L"Winre not found");
    goto LABEL_124;
  }
  UnattendLogW(0, L"Found winre at location %s", &PathName);
  if ( !v1 )
  {
    WindowsVolume = winreFindMainOsConfigDir(0);
    if ( WindowsVolume )
    {
      LODWORD(dwFlagsAndAttributes) = 3471;
      UnattendLogW(
        2,
        L"winreReconstructConfigXML %s (0x%x) in file %S line %d",
        L"failed to find main OS config directory",
        (unsigned int)WindowsVolume,
        "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
        dwFlagsAndAttributes);
      v2 = v35;
      goto LABEL_125;
    }
    v2 = v35;
    UnattendLogW(0, L"Moving winre form %s to %S", &PathName, v35);
    v31 = 0;
    WindowsVolume = StringCchLengthW(&PathName, 0x7FFFFFFFu, &v31);
    v14 = L"%s\\%s";
    if ( WindowsVolume >= 0 )
    {
      if ( !v31 || (v17 = L"%s\\%s", *(_WORD *)&v46[2 * v31 + 90] == 92) )
        v17 = L"%s%s";
      WindowsVolume = StringCchPrintfW(&ExistingFileName, 0x12Eu, v17, &PathName, L"Winre.wim");
      if ( WindowsVolume >= 0 )
        goto LABEL_68;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v16 = 15;
        goto LABEL_64;
      }
    }
    else
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v16 = 14;
LABEL_64:
        WPP_SF_d(v15[2], v16, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)WindowsVolume);
      }
    }
    WindowsVolume = (unsigned __int16)WindowsVolume;
    if ( (_WORD)WindowsVolume )
    {
      LODWORD(dwFlagsAndAttributes) = 3474;
LABEL_67:
      v11 = L"failed to append path";
      goto LABEL_40;
    }
LABEL_68:
    v31 = 0;
    if ( !v2 )
    {
      WindowsVolume = 87;
      goto LABEL_122;
    }
    WindowsVolume = StringCchLengthW(v2, 0x7FFFFFFFu, &v31);
    if ( WindowsVolume >= 0 )
    {
      if ( !v31 || (v21 = L"%s\\%s", v2[v31 - 1] == 92) )
        v21 = L"%s%s";
      WindowsVolume = StringCchPrintfW(&NewFileName, 0x12Eu, v21, v2, L"Winre.wim");
      if ( WindowsVolume >= 0 )
      {
LABEL_82:
        if ( !MoveFileExW(&ExistingFileName, &NewFileName, 3u) )
        {
          LastError = GetLastError();
          LODWORD(dwFlagsAndAttributes) = 3478;
          v11 = L"failed to move file";
          WindowsVolume = LastError;
          goto LABEL_40;
        }
        v31 = 0;
        WindowsVolume = StringCchLengthW(&PathName, 0x7FFFFFFFu, &v31);
        if ( WindowsVolume >= 0 )
        {
          if ( !v31 || (v25 = L"%s\\%s", *(_WORD *)&v46[2 * v31 + 90] == 92) )
            v25 = L"%s%s";
          WindowsVolume = StringCchPrintfW(&ExistingFileName, 0x12Eu, v25, &PathName, L"boot.sdi");
          if ( WindowsVolume >= 0 )
            goto LABEL_98;
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v24 = 15;
            goto LABEL_95;
          }
        }
        else
        {
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v24 = 14;
LABEL_95:
            WPP_SF_d(v23[2], v24, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)WindowsVolume);
          }
        }
        WindowsVolume = (unsigned __int16)WindowsVolume;
        if ( (_WORD)WindowsVolume )
        {
          LODWORD(dwFlagsAndAttributes) = 3480;
          goto LABEL_67;
        }
LABEL_98:
        DeleteFileW(&ExistingFileName);
        v31 = 0;
        WindowsVolume = StringCchLengthW(&PathName, 0x7FFFFFFFu, &v31);
        if ( WindowsVolume >= 0 )
        {
          if ( !v31 || *(_WORD *)&v46[2 * v31 + 90] == 92 )
            v14 = L"%s%s";
          WindowsVolume = StringCchPrintfW(&ExistingFileName, 0x12Eu, v14, &PathName, L"reagent.xml");
          if ( WindowsVolume >= 0 )
            goto LABEL_112;
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v27 = 15;
            goto LABEL_109;
          }
        }
        else
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v27 = 14;
LABEL_109:
            WPP_SF_d(v26[2], v27, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)WindowsVolume);
          }
        }
        WindowsVolume = (unsigned __int16)WindowsVolume;
        if ( (_WORD)WindowsVolume )
        {
          LODWORD(dwFlagsAndAttributes) = 3482;
          goto LABEL_67;
        }
LABEL_112:
        DeleteFileW(&ExistingFileName);
        RemoveDirectoryW(&PathName);
        v13 = v36;
        goto LABEL_113;
      }
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_81;
      v19 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v20 = 15;
    }
    else
    {
      if ( (_UNKNOWN **)v18 == &WPP_GLOBAL_Control || (*(_BYTE *)(v18 + 28) & 2) == 0 )
      {
LABEL_81:
        WindowsVolume = (unsigned __int16)WindowsVolume;
        if ( !(_WORD)WindowsVolume )
          goto LABEL_82;
LABEL_122:
        LODWORD(dwFlagsAndAttributes) = 3475;
        goto LABEL_67;
      }
      v19 = *(_QWORD *)(v18 + 16);
      v20 = 14;
    }
    WPP_SF_d(v19, v20, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)WindowsVolume);
    goto LABEL_81;
  }
  WindowsVolume = winreConvertDirNameToOffset(&PathName, (__int64)&v57);
  if ( WindowsVolume )
  {
    LODWORD(dwFlagsAndAttributes) = 3465;
    v11 = L"failed to convert directory name to offset";
LABEL_40:
    UnattendLogW(
      2,
      L"winreReconstructConfigXML %s (0x%x) in file %S line %d",
      v11,
      (unsigned int)WindowsVolume,
      "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
      dwFlagsAndAttributes);
    goto LABEL_125;
  }
  UnattendLogW(0, L"Setting staging location to %s", &PathName);
  v13 = v36;
  WindowsVolume = ReAgentConfig::SetImageLocationPath(v36, v41, &v40, v39, &v57);
  if ( WindowsVolume )
  {
    LODWORD(dwFlagsAndAttributes) = 3467;
    v11 = L"failed to image location path";
    goto LABEL_40;
  }
LABEL_113:
  if ( v7 )
  {
    if ( szFileName )
    {
      if ( !(unsigned int)winreGetPBRImageIndex(&szFileName) )
      {
        v28 = v34;
        if ( v34 )
        {
          if ( !(unsigned int)winreConvertDirNameToOffset(&szFileName, (__int64)&v57) )
          {
            UnattendLogW(0, L"Setting PBR image location to %s", &PathName);
            ReAgentConfig::SetOsInstallLocationPath(v13, v41, &v40, v39, &v57, v28);
          }
        }
      }
    }
  }
  else
  {
    UnattendLogW(1, L"PBRImage was not set");
  }
  *(_DWORD *)(*((_QWORD *)v13 + 8) + 5612LL) = 4;
  UnattendLogW(0, L"Updating config xml");
  WindowsVolume = ReAgentXMLParser::Update(v13);
LABEL_125:
  if ( FirstVolumeW )
    FindVolumeClose(FirstVolumeW);
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v5);
  if ( v2 )
    CoTaskMemFree(v2);
LABEL_131:
  if ( WindowsVolume )
LABEL_132:
    UnattendLogW(1, L"winreRestoreBackupXML failed: 0x%x", (unsigned int)WindowsVolume);
  return (unsigned int)WindowsVolume;
}

```

## disassembly

```asm
0x18003bfbc  push    rbp
0x18003bfbe  push    rbx
0x18003bfbf  push    rsi
0x18003bfc0  push    rdi
0x18003bfc1  push    r12
0x18003bfc3  push    r13
0x18003bfc5  push    r14
0x18003bfc7  push    r15
0x18003bfc9  lea     rbp, [rsp-18B8h]
0x18003bfd1  mov     eax, 19B8h
0x18003bfd6  call    _alloca_probe
0x18003bfdb  sub     rsp, rax
0x18003bfde  mov     rax, cs:__security_cookie
0x18003bfe5  xor     rax, rsp
0x18003bfe8  mov     [rbp+18F0h+var_50], rax
0x18003bfef  mov     [rsp+19F0h+var_1990], rcx
0x18003bff4  mov     ebx, 25Ah
0x18003bff9  xor     r15d, r15d
0x18003bffc  lea     rcx, [rbp+18F0h+var_10EE]; void *
0x18003c003  mov     r8d, ebx; Size
0x18003c006  mov     [rbp+18F0h+szVolumeName], r15w
0x18003c00e  xor     edx, edx; Val
0x18003c010  call    memset_0
0x18003c015  mov     r8d, ebx; Size
0x18003c018  mov     [rsp+19F0h+var_19B0], r15
0x18003c01d  xor     edx, edx; Val
0x18003c01f  mov     [rbp+18F0h+BytesReturned], r15d
0x18003c026  lea     rcx, [rbp+18F0h+var_50E]; void *
0x18003c02d  mov     [rsp+19F0h+var_19A4], r15d
0x18003c032  mov     [rsp+19F0h+var_19A0], r15d
0x18003c037  mov     [rbp+18F0h+String1], r15w
0x18003c03f  call    memset_0
0x18003c044  mov     r8d, ebx; Size
0x18003c047  mov     [rbp+18F0h+var_9D0], r15w
0x18003c04f  xor     edx, edx; Val
0x18003c051  lea     rcx, [rbp+18F0h+var_9CE]; void *
0x18003c058  call    memset_0
0x18003c05d  mov     r8d, ebx; Size
0x18003c060  mov     [rbp+18F0h+PathName], r15w
0x18003c068  xor     edx, edx; Val
0x18003c06a  lea     rcx, [rbp+18F0h+var_134E]; void *
0x18003c071  call    memset_0
0x18003c076  mov     r8d, ebx; Size
0x18003c079  mov     [rbp+18F0h+szFileName], r15w
0x18003c081  xor     edx, edx; Val
0x18003c083  lea     rcx, [rbp+18F0h+var_C2E]; void *
0x18003c08a  call    memset_0
0x18003c08f  mov     r8d, ebx; Size
0x18003c092  mov     [rbp+18F0h+var_770], r15w
0x18003c09a  xor     edx, edx; Val
0x18003c09c  lea     rcx, [rbp+18F0h+var_76E]; void *
0x18003c0a3  call    memset_0
0x18003c0a8  mov     r8d, ebx; Size
0x18003c0ab  mov     [rbp+18F0h+ExistingFileName], r15w
0x18003c0b3  xor     edx, edx; Val
0x18003c0b5  lea     rcx, [rbp+18F0h+var_E8E]; void *
0x18003c0bc  call    memset_0
0x18003c0c1  mov     r8d, ebx; Size
0x18003c0c4  mov     [rbp+18F0h+NewFileName], r15w
0x18003c0cc  xor     edx, edx; Val
0x18003c0ce  lea     rcx, [rbp+18F0h+var_2AE]; void *
0x18003c0d5  call    memset_0
0x18003c0da  xor     edx, edx; Val
0x18003c0dc  mov     [rsp+19F0h+var_1998], r15
0x18003c0e1  mov     r8d, 528h; Size
0x18003c0e7  mov     [rsp+19F0h+var_1980], r15
0x18003c0ec  lea     rcx, [rsp+19F0h+var_1978]; void *
0x18003c0f1  mov     r14d, r15d
0x18003c0f4  call    memset_0
0x18003c0f9  xor     edx, edx; Val
0x18003c0fb  mov     [rbp+18F0h+OutBuffer], r15d
0x18003c102  lea     r8d, [r15+5Ch]; Size
0x18003c106  lea     rcx, [rbp+18F0h+var_13AC]; void *
0x18003c10d  call    memset_0
0x18003c112  mov     edi, 90h
0x18003c117  lea     rcx, [rbp+18F0h+var_1440]; void *
0x18003c11e  mov     r8d, edi; Size
0x18003c121  xor     edx, edx; Val
0x18003c123  call    memset_0
0x18003c128  lea     rdx, [rbp+18F0h+String1]
0x18003c12f  xor     ecx, ecx
0x18003c131  call    winreGetWindowsVolume
0x18003c136  mov     ebx, eax
0x18003c138  test    eax, eax
0x18003c13a  jz      short loc_18003C16F
0x18003c13c  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18003c143  mov     dword ptr [rsp+19F0h+dwFlagsAndAttributes], 0CE8h
0x18003c14b  mov     r9d, ebx
0x18003c14e  mov     qword ptr [rsp+19F0h+dwCreationDisposition], rax
0x18003c153  lea     r8, aFailedToGetWin_14; "failed to get Windows volume"
0x18003c15a  lea     rdx, aWinrereconstru; "winreReconstructConfigXML %s (0x%x) in "...
0x18003c161  lea     ecx, [r15+2]
0x18003c165  call    UnattendLogW
0x18003c16a  jmp     loc_18003CBA7
0x18003c16f  mov     r8, rdi; Size
0x18003c172  lea     rcx, [rbp+18F0h+var_1440]; void *
0x18003c179  xor     edx, edx; Val
0x18003c17b  call    memset_0
0x18003c180  mov     edx, 12Eh; cchBufferLength
0x18003c185  lea     rcx, [rbp+18F0h+szVolumeName]; lpszVolumeName
0x18003c18c  call    cs:__imp_FindFirstVolumeW
0x18003c192  mov     r13, rax
0x18003c195  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003c199  jnz     short loc_18003C1A8
0x18003c19b  call    cs:__imp_GetLastError
0x18003c1a1  mov     ebx, eax
0x18003c1a3  jmp     loc_18003CBA3
0x18003c1a8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003c1ac  xor     ebx, ebx
0x18003c1ae  mov     esi, ebx
0x18003c1b0  mov     r12d, ebx
0x18003c1b3  lea     rax, [rdi-1]
0x18003c1b7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003c1bb  ja      short loc_18003C1C9
0x18003c1bd  mov     rcx, rdi; hObject
0x18003c1c0  call    cs:__imp_CloseHandle
0x18003c1c6  mov     rdi, rbx
0x18003c1c9  lea     rcx, [rbp+18F0h+szVolumeName]; lpRootPathName
0x18003c1d0  call    cs:__imp_GetDriveTypeW
0x18003c1d6  cmp     eax, 3
0x18003c1d9  jnz     loc_18003C47B
0x18003c1df  lea     r8, [rsp+19F0h+var_19B0]; unsigned __int64 *
0x18003c1e4  mov     edx, 12Eh; unsigned __int64
0x18003c1e9  lea     rcx, [rbp+18F0h+szVolumeName]; unsigned __int16 *
0x18003c1f0  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003c1f5  mov     ebx, eax
0x18003c1f7  test    eax, eax
0x18003c1f9  js      loc_18003C592
0x18003c1ff  mov     rax, [rsp+19F0h+var_19B0]
0x18003c204  cmp     rax, 1
0x18003c208  jb      loc_18003C479
0x18003c20e  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18003c216  cmp     rcx, 25Ch
0x18003c21d  jnb     loc_18003C58C
0x18003c223  xor     ebx, ebx
0x18003c225  lea     rdx, [rbp+18F0h+szVolumeName]; String2
0x18003c22c  mov     [rbp+rcx+18F0h+szVolumeName], bx
0x18003c234  lea     rcx, [rbp+18F0h+String1]; String1
0x18003c23b  call    cs:__imp__wcsicmp
0x18003c241  test    eax, eax
0x18003c243  jnz     short loc_18003C258
0x18003c245  lea     rdx, aSkippingOsVolu; "Skipping OS volume"
0x18003c24c  xor     ecx, ecx
0x18003c24e  call    UnattendLogW
0x18003c253  jmp     loc_18003C47B
0x18003c258  xor     r9d, r9d; lpSecurityAttributes
0x18003c25b  mov     [rsp+19F0h+hTemplateFile], rbx; hTemplateFile
0x18003c260  mov     dword ptr [rsp+19F0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18003c268  lea     rcx, [rbp+18F0h+szVolumeName]; lpFileName
0x18003c26f  mov     [rsp+19F0h+dwCreationDisposition], 3; dwCreationDisposition
0x18003c277  lea     edx, [r9+1]; dwDesiredAccess
0x18003c27b  lea     r8d, [r9+7]; dwShareMode
0x18003c27f  call    cs:__imp_CreateFileW
0x18003c285  mov     rdi, rax
0x18003c288  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003c28c  jz      loc_18003C47B
0x18003c292  mov     [rsp+19F0h+lpOverlapped], rbx; lpOverlapped
0x18003c297  lea     rax, [rbp+18F0h+BytesReturned]
0x18003c29e  mov     [rsp+19F0h+hTemplateFile], rax; lpBytesReturned
0x18003c2a3  xor     r9d, r9d; nInBufferSize
0x18003c2a6  lea     rax, [rbp+18F0h+OutBuffer]
0x18003c2ad  mov     dword ptr [rsp+19F0h+dwFlagsAndAttributes], 60h ; '`'; nOutBufferSize
0x18003c2b5  xor     r8d, r8d; lpInBuffer
0x18003c2b8  mov     qword ptr [rsp+19F0h+dwCreationDisposition], rax; lpOutBuffer
0x18003c2bd  mov     edx, 90064h; dwIoControlCode
0x18003c2c2  mov     rcx, rdi; hDevice
0x18003c2c5  call    cs:__imp_DeviceIoControl
0x18003c2cb  test    eax, eax
0x18003c2cd  jz      loc_18003C47B
0x18003c2d3  mov     [rsp+19F0h+lpOverlapped], rbx; lpOverlapped
0x18003c2d8  lea     rax, [rbp+18F0h+BytesReturned]
0x18003c2df  mov     [rsp+19F0h+hTemplateFile], rax; lpBytesReturned
0x18003c2e4  xor     r9d, r9d; nInBufferSize
0x18003c2e7  lea     rax, [rbp+18F0h+var_1440]
0x18003c2ee  mov     dword ptr [rsp+19F0h+dwFlagsAndAttributes], 90h; nOutBufferSize
0x18003c2f6  xor     r8d, r8d; lpInBuffer
0x18003c2f9  mov     qword ptr [rsp+19F0h+dwCreationDisposition], rax; lpOutBuffer
0x18003c2fe  mov     edx, 70048h; dwIoControlCode
0x18003c303  mov     rcx, rdi; hDevice
0x18003c306  call    cs:__imp_DeviceIoControl
0x18003c30c  test    eax, eax
0x18003c30e  jz      short loc_18003C377
0x18003c310  mov     eax, [rbp+18F0h+var_1440]
0x18003c316  test    eax, eax
0x18003c318  jnz     short loc_18003C345
0x18003c31a  cmp     [rbp+18F0h+Buf1], 27h ; '''
0x18003c321  jz      short loc_18003C369
0x18003c323  cmp     [rbp+18F0h+var_141F], bl
0x18003c329  jnz     short loc_18003C369
0x18003c32b  lea     r8, [rbp+18F0h+szVolumeName]
0x18003c332  xor     ecx, ecx
0x18003c334  lea     rdx, aSkippingVolume_0; "Skipping volume %s"
0x18003c33b  call    UnattendLogW
0x18003c340  jmp     loc_18003C47B
0x18003c345  cmp     eax, 1
0x18003c348  jnz     loc_18003C47B
0x18003c34e  lea     r8d, [rax+0Fh]; Size
0x18003c352  lea     rdx, PARTITION_MSFT_RECOVERY_GUID; Buf2
0x18003c359  lea     rcx, [rbp+18F0h+Buf1]; Buf1
0x18003c360  call    memcmp_0
0x18003c365  test    eax, eax
0x18003c367  jnz     short loc_18003C32B
0x18003c369  lea     rdx, aValidMbrPariti; "Valid MBR parition found"
0x18003c370  xor     ecx, ecx
0x18003c372  call    UnattendLogW
0x18003c377  lea     r8, [rbp+18F0h+szVolumeName]
0x18003c37e  xor     ecx, ecx
0x18003c380  lea     rdx, aScanningVolume; " Scanning volume %s"
0x18003c387  call    UnattendLogW
0x18003c38c  lea     rax, [rsp+19F0h+var_19A4]
0x18003c391  mov     [rsp+19F0h+var_19A8], ebx
0x18003c395  lea     r9, [rsp+19F0h+var_19A8]; int *
0x18003c39a  mov     qword ptr [rsp+19F0h+dwCreationDisposition], rax; int *
0x18003c39f  lea     rdx, [rbp+18F0h+var_9D0]; unsigned __int16 *
0x18003c3a6  lea     rcx, [rbp+18F0h+szVolumeName]; unsigned __int16 *
0x18003c3ad  call    ?winreScanForWinReWim@@YAKPEBGPEAG_KPEAH3@Z; winreScanForWinReWim(ushort const *,ushort *,unsigned __int64,int *,int *)
0x18003c3b2  cmp     [rsp+19F0h+var_19A8], ebx
0x18003c3b6  jz      short loc_18003C3EE
0x18003c3b8  test    esi, esi
0x18003c3ba  jnz     loc_18003C545
0x18003c3c0  lea     r8, [rbp+18F0h+var_9D0]; unsigned __int16 *
0x18003c3c7  mov     edx, 12Eh; unsigned __int64
0x18003c3cc  lea     rcx, [rbp+18F0h+PathName]; unsigned __int16 *
0x18003c3d3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003c3d8  mov     ebx, eax
0x18003c3da  test    eax, eax
0x18003c3dc  js      loc_18003C534
0x18003c3e2  mov     r15d, [rsp+19F0h+var_19A4]
0x18003c3e7  mov     esi, 1
0x18003c3ec  xor     ebx, ebx
0x18003c3ee  lea     r9, [rsp+19F0h+var_19A8]; int *
0x18003c3f3  mov     [rsp+19F0h+var_19A8], ebx
0x18003c3f7  lea     rdx, [rbp+18F0h+var_9D0]; unsigned __int16 *
0x18003c3fe  lea     rcx, [rbp+18F0h+szVolumeName]; unsigned __int16 *
0x18003c405  call    ?winreScanForInstallWim@@YAKPEBGPEAG_KPEAH@Z; winreScanForInstallWim(ushort const *,ushort *,unsigned __int64,int *)
0x18003c40a  cmp     [rsp+19F0h+var_19A8], ebx
0x18003c40e  jz      short loc_18003C47B
0x18003c410  test    r12d, r12d
0x18003c413  jz      short loc_18003C451
0x18003c415  lea     rdx, aMultipleInstal; "Multiple install.wims found. Not settin"...
0x18003c41c  mov     ecx, 1
0x18003c421  call    UnattendLogW
0x18003c426  lea     r8, cchOriginalDestLength; unsigned __int16 *
0x18003c42d  mov     edx, 12Eh; unsigned __int64
0x18003c432  lea     rcx, [rbp+18F0h+szFileName]; unsigned __int16 *
0x18003c439  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003c43e  mov     ebx, eax
0x18003c440  test    eax, eax
0x18003c442  jns     short loc_18003C479
0x18003c444  mov     dword ptr [rsp+19F0h+dwFlagsAndAttributes], 0D72h
0x18003c44c  jmp     loc_18003C53C
0x18003c451  lea     r8, [rbp+18F0h+var_9D0]; unsigned __int16 *
0x18003c458  mov     edx, 12Eh; unsigned __int64
0x18003c45d  lea     rcx, [rbp+18F0h+szFileName]; unsigned __int16 *
0x18003c464  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003c469  mov     ebx, eax
0x18003c46b  test    eax, eax
0x18003c46d  js      loc_18003C582
0x18003c473  mov     r12d, 1
0x18003c479  xor     ebx, ebx
0x18003c47b  mov     r8d, 12Eh; cchBufferLength
0x18003c481  lea     rdx, [rbp+18F0h+szVolumeName]; lpszVolumeName
0x18003c488  mov     rcx, r13; hFindVolume
0x18003c48b  call    cs:__imp_FindNextVolumeW
0x18003c491  test    eax, eax
0x18003c493  jnz     loc_18003C1B3
0x18003c499  test    esi, esi
0x18003c49b  jz      loc_18003CB5E
0x18003c4a1  cmp     [rbp+18F0h+PathName], bx
0x18003c4a8  jz      loc_18003CB5E
0x18003c4ae  lea     r8, [rbp+18F0h+PathName]
0x18003c4b5  xor     ecx, ecx
0x18003c4b7  lea     rdx, aFoundWinreAtLo; "Found winre at location %s"
0x18003c4be  call    UnattendLogW
0x18003c4c3  test    r15d, r15d
0x18003c4c6  jz      loc_18003C624
0x18003c4cc  lea     rax, [rbp+18F0h+var_770]
0x18003c4d3  xor     r9d, r9d
0x18003c4d6  lea     r8, [rsp+19F0h+var_1980]
0x18003c4db  mov     qword ptr [rsp+19F0h+dwCreationDisposition], rax; __int64
0x18003c4e0  lea     rdx, aWinreWim_1; "winre.wim"
0x18003c4e7  lea     rcx, [rbp+18F0h+PathName]; lpszFileName
0x18003c4ee  call    winreConvertDirNameToOffset
0x18003c4f3  xor     r15d, r15d
0x18003c4f6  mov     ebx, eax
0x18003c4f8  test    eax, eax
0x18003c4fa  jz      loc_18003C5C9
0x18003c500  mov     dword ptr [rsp+19F0h+dwFlagsAndAttributes], 0D89h
0x18003c508  lea     r8, aFailedToConver_0; "failed to convert directory name to off"...
0x18003c50f  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18003c516  mov     r9d, ebx
0x18003c519  lea     rdx, aWinrereconstru; "winreReconstructConfigXML %s (0x%x) in "...
0x18003c520  mov     qword ptr [rsp+19F0h+dwCreationDisposition], rax
0x18003c525  mov     ecx, 2
0x18003c52a  call    UnattendLogW
0x18003c52f  jmp     loc_18003CB74
0x18003c534  mov     dword ptr [rsp+19F0h+dwFlagsAndAttributes], 0D65h
0x18003c53c  lea     r8, aFailedToCopySt; "failed to copy string"
0x18003c543  jmp     short loc_18003C5A1
0x18003c545  lea     rdx, aMultipleWinreW; "Multiple winre.wims found. Cannot repai"...
  ... truncated ...
```
