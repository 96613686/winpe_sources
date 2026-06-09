# WinReSetupBackupWinRE

- ea: `0x18002dd30`
- end: `0x18002eb2c`
- name: `WinReSetupBackupWinRE`
- size: `3580`
- prototype: ``
- caller_count: `0`
- callee_count: `34`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800055c8`
- `0x180005694`
- `0x1800059fc`
- `0x180006ed8`
- `0x180008b94`
- `0x18000c6c0`
- `0x18000c6f0`
- `0x1800103f4`
- `0x180011974`
- `0x1800121b0`
- `0x18001c2f4`
- `0x18001c324`
- `0x18001c354`
- `0x18001c448`
- `0x18001e4c8`
- `0x18001ee18`
- `0x18001f0c0`
- `0x18001f218`
- `0x18001f2bc`
- `0x18001f47c`
- `0x180028810`
- `0x180028aac`
- `0x18002d40c`
- `0x18002d88c`
- `0x18002dd30`
- `0x180030f18`
- `0x180031bb8`
- `0x180031e10`
- `0x180032c14`
- `0x18004df64`
- `0x18004f8d0`
- `0x180051dc8`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18002e60f`
- `ntdll!RtlNtStatusToDosError` at `0x18002e61e`
- `ntdll!RtlNtStatusToDosError` at `0x18002e60f`
- `ntdll!RtlNtStatusToDosError` at `0x18002e61e`
- `KERNEL32!CopyFileW` at `0x18002e59d`
- `KERNEL32!CopyFileW` at `0x18002e59d`
- `KERNEL32!GetLastError` at `0x18002df7f`
- `KERNEL32!GetLastError` at `0x18002e571`
- `KERNEL32!GetLastError` at `0x18002e5ad`
- `KERNEL32!GetLastError` at `0x18002e69f`
- `KERNEL32!GetLastError` at `0x18002e823`
- `KERNEL32!GetLastError` at `0x18002e90f`
- `KERNEL32!GetLastError` at `0x18002e948`
- `KERNEL32!GetLastError` at `0x18002e99e`
- `KERNEL32!GetLastError` at `0x18002e9d3`
- `KERNEL32!GetLastError` at `0x18002ea6d`
- `KERNEL32!GetLastError` at `0x18002df7f`
- `KERNEL32!GetLastError` at `0x18002e571`
- `KERNEL32!GetLastError` at `0x18002e5ad`
- `KERNEL32!GetLastError` at `0x18002e69f`
- `KERNEL32!GetLastError` at `0x18002e823`
- `KERNEL32!GetLastError` at `0x18002e90f`
- `KERNEL32!GetLastError` at `0x18002e948`
- `KERNEL32!GetLastError` at `0x18002e99e`
- `KERNEL32!GetLastError` at `0x18002e9d3`
- `KERNEL32!GetLastError` at `0x18002ea6d`
- `KERNEL32!WritePrivateProfileStringW` at `0x18002e905`
- `KERNEL32!WritePrivateProfileStringW` at `0x18002e93e`
- `KERNEL32!WritePrivateProfileStringW` at `0x18002e994`
- `KERNEL32!WritePrivateProfileStringW` at `0x18002e905`
- `KERNEL32!WritePrivateProfileStringW` at `0x18002e93e`
- `KERNEL32!WritePrivateProfileStringW` at `0x18002e994`
- `KERNEL32!WriteFile` at `0x18002e4fd`
- `KERNEL32!WriteFile` at `0x18002e4fd`
- `KERNEL32!SetLastError` at `0x18002e63b`
- `KERNEL32!SetLastError` at `0x18002e63b`
- `KERNEL32!CreateFileW` at `0x18002e4c9`
- `KERNEL32!CreateFileW` at `0x18002ea39`
- `KERNEL32!CreateFileW` at `0x18002e4c9`
- `KERNEL32!CreateFileW` at `0x18002ea39`
- `KERNEL32!CloseHandle` at `0x18002e506`
- `KERNEL32!CloseHandle` at `0x18002ea65`
- `KERNEL32!CloseHandle` at `0x18002e506`
- `KERNEL32!CloseHandle` at `0x18002ea65`
- `KERNEL32!DeleteFileW` at `0x18002df75`
- `KERNEL32!DeleteFileW` at `0x18002df75`
- `KERNEL32!CreateDirectoryW` at `0x18002e567`
- `KERNEL32!CreateDirectoryW` at `0x18002e567`
- `KERNEL32!GetVolumePathNameW` at `0x18002e9c9`
- `KERNEL32!GetVolumePathNameW` at `0x18002e9c9`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x18002e674`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x18002e7f8`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x18002e674`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x18002e7f8`
- `ADVAPI32!RegGetValueW` at `0x18002dfe7`
- `ADVAPI32!RegGetValueW` at `0x18002dfe7`
- `ole32!StringFromCLSID` at `0x18002e963`
- `ole32!StringFromCLSID` at `0x18002e963`
- `ole32!CoTaskMemFree` at `0x18002ea9b`
- `ole32!CoTaskMemFree` at `0x18002ea9b`

## string_xrefs

- `0x18002e0ac`: `DisableUpdateEnhancedConfigInfo`
- `0x18002e25c`: `failed to append path`
- `0x18002e250`: `base\diagnosis\srt\reagent2\reagent\setup.cpp`
- `0x18002de8f`: `backup directory: %s`
- `0x18002defa`: `Find existing PBR_IN_PROGRESS_MARKER, will delete it.`
- `0x18002df94`: ` Could not delete %s. Error: 0X%X`
- `0x18002e00c`: `BackupDirectory is NULL, will not create marker.`
- `0x18002e025`: `Failed to create marker in BackupDirectory`
- `0x18002e0e1`: `AgentConfig.Init failed. Error: 0X%X`
- `0x18002e54d`: `failed to get downlevel config file path by guid: 0x%x`
- `0x18002e57e`: `failed to create downlevel winre config directory with error 0x%x`
- `0x18002e5bd`: `copy downlevel ReAgent.xml failed:  0x%x`
- `0x18002e5c9`: `Try to use backup function to backup downlevel ReAgent.xml.`
- `0x18002e5f8`: `backup downlevel ReAgent.xml failed:  0x%x`
- `0x18002e6e4`: `Failed to copy winre location to caller's buffer. Error: 0X%X`
- `0x18002e74d`: `move directoy from %s to %s failed`
- `0x18002e915`: `WritePrivateProfileString partition offset string failed. Error: 0X%X`
- `0x18002e937`: `Relative path`
- `0x18002e94e`: `WritePrivateProfileString winre location failed. Error: 0X%X`
- `0x18002e96d`: `StringFromCLSID failed. hr = 0x%08X`
- `0x18002e9a4`: `WritePrivateProfileString OS GUID failed. Error: 0X%X`
- `0x18002e9d9`: `GetVolumePathName failed. Error: 0X%X`
- `0x18002ea54`: `Marker file %s created`
- `0x18002ea82`: `Unable to create the marker file %s. Error: 0X%X`

## pseudocode

```c
__int64 __fastcall WinReSetupBackupWinRE(__int64 a1, unsigned __int16 *a2, int a3, _WORD *a4, unsigned int a5)
{
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rdx
  const unsigned __int16 *v12; // rax
  __int64 v13; // rdx
  _QWORD *v14; // rax
  const WCHAR *v15; // r9
  unsigned __int64 v16; // rax
  __int64 v17; // r9
  unsigned __int64 v18; // rax
  const WCHAR *v19; // rax
  __int64 v20; // rdx
  _QWORD *v21; // rax
  unsigned int v22; // edi
  const wchar_t *v23; // rdx
  unsigned __int16 *v24; // rax
  unsigned int DownlevelConfigFilePathByGuid; // eax
  const wchar_t *v26; // rdx
  __int64 v27; // rcx
  struct ReAgentConfigInfo *ConfigInfo; // r13
  int IsWimBootEnabledInternal; // r14d
  const unsigned __int16 *v30; // r12
  int v31; // r14d
  const unsigned __int16 *v32; // r8
  const unsigned __int16 *v33; // rax
  __int64 v34; // r11
  int v35; // r14d
  _QWORD *v36; // rcx
  __int64 v37; // rdx
  _QWORD *v38; // rax
  const WCHAR *v39; // rcx
  unsigned __int64 v40; // rax
  __int64 v41; // rcx
  unsigned __int64 v42; // rax
  __int64 v43; // rcx
  const WCHAR *v44; // rax
  __int64 v45; // rdx
  HANDLE FileW; // rdi
  _QWORD *v47; // rax
  DWORD v48; // r8d
  const WCHAR *v49; // rax
  DWORD LastError; // eax
  const WCHAR *v51; // rax
  unsigned int (*v52)(union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, unsigned int, void *, void *, void *); // r8
  void *v53; // r9
  int v54; // eax
  ULONG v55; // edi
  int v56; // r11d
  const WCHAR *v57; // rax
  _QWORD *v58; // rax
  DWORD v59; // eax
  const unsigned __int16 *v60; // rax
  unsigned __int16 *v61; // r9
  int v62; // eax
  _QWORD *v63; // rax
  unsigned int v64; // eax
  _QWORD *v65; // rax
  _QWORD *v66; // rax
  __int64 v67; // rdx
  char *v68; // r10
  char *i; // r9
  __int64 v70; // r9
  const WCHAR *v71; // rax
  _QWORD *v72; // rax
  __int64 v73; // rdx
  DWORD v74; // eax
  _QWORD *v75; // rax
  const WCHAR *v76; // rcx
  unsigned __int64 v77; // rax
  __int64 v78; // rcx
  unsigned __int64 v79; // rax
  __int64 v80; // rcx
  int v81; // eax
  const WCHAR *v82; // rax
  DWORD v83; // eax
  const WCHAR *v84; // rax
  DWORD v85; // eax
  HRESULT v86; // eax
  const WCHAR *v87; // rax
  DWORD v88; // eax
  const WCHAR *v89; // rax
  DWORD v90; // eax
  unsigned __int64 v91; // rax
  __int64 v92; // rcx
  const WCHAR *v93; // rax
  HANDLE v94; // rbx
  _QWORD *v95; // rax
  _QWORD *v96; // rax
  const wchar_t *v97; // r8
  __int64 v98; // rdx
  __int64 v99; // rdx
  __int64 v100; // rdx
  __int64 v101; // rdx
  LPDWORD pdwType; // [rsp+20h] [rbp-E0h]
  int pvData; // [rsp+28h] [rbp-D8h]
  int pcbData; // [rsp+30h] [rbp-D0h]
  LPCWSTR lpFileName; // [rsp+40h] [rbp-C0h] BYREF
  _WORD *v107; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v108; // [rsp+50h] [rbp-B0h]
  LPOLESTR lpsz; // [rsp+58h] [rbp-A8h] BYREF
  int v110; // [rsp+60h] [rbp-A0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+68h] [rbp-98h] BYREF
  union _ULARGE_INTEGER FreeBytesAvailableToCaller; // [rsp+70h] [rbp-90h] BYREF
  int v113; // [rsp+78h] [rbp-88h] BYREF
  __int128 v114; // [rsp+80h] [rbp-80h] BYREF
  __int64 v115; // [rsp+90h] [rbp-70h]
  _QWORD v116[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v117; // [rsp+B0h] [rbp-50h]
  DWORD v118; // [rsp+C0h] [rbp-40h] BYREF
  DWORD v119; // [rsp+C8h] [rbp-38h] BYREF
  IID rclsid; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v121[4]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v122[4]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v123[4]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v124[4]; // [rsp+140h] [rbp+40h] BYREF
  _QWORD v125[3]; // [rsp+160h] [rbp+60h] BYREF
  int v126; // [rsp+178h] [rbp+78h]
  int v127; // [rsp+17Ch] [rbp+7Ch]
  __int128 v128; // [rsp+180h] [rbp+80h]
  __int128 v129; // [rsp+190h] [rbp+90h]
  __int64 v130; // [rsp+1A0h] [rbp+A0h]
  int v131; // [rsp+1A8h] [rbp+A8h]
  unsigned __int16 v132; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v133[606]; // [rsp+1B2h] [rbp+B2h] BYREF
  WCHAR NewFileName; // [rsp+410h] [rbp+310h] BYREF
  _BYTE v135[606]; // [rsp+412h] [rbp+312h] BYREF
  WCHAR szVolumePathName; // [rsp+670h] [rbp+570h] BYREF
  _BYTE v137[526]; // [rsp+672h] [rbp+572h] BYREF
  WCHAR PathName; // [rsp+880h] [rbp+780h] BYREF
  _BYTE v139[606]; // [rsp+882h] [rbp+782h] BYREF
  WCHAR String[304]; // [rsp+AE0h] [rbp+9E0h] BYREF

  v110 = a3;
  v107 = a4;
  PathName = 0;
  memset_0(v139, 0, 0x25Au);
  NewFileName = 0;
  memset_0(v135, 0, 0x25Au);
  std::wstring::wstring(v124, v8);
  std::wstring::wstring(v116, v9);
  std::wstring::wstring(v122, v10);
  NumberOfBytesWritten = 0;
  FreeBytesAvailableToCaller.QuadPart = 0;
  szVolumePathName = 0;
  rclsid = GUID_NULL;
  memset_0(v137, 0, 0x206u);
  std::wstring::wstring(v123, v11);
  lpFileName = 0;
  v113 = 0;
  v118 = 4;
  lpsz = 0;
  memset_0(String, 0, 0x25Cu);
  v125[1] = 0;
  v128 = 0;
  v129 = 0;
  v125[0] = &ReAgentConfig::`vftable';
  v125[2] = 0;
  v126 = 0;
  v127 = 2;
  v130 = 0;
  v131 = 0;
  UnattendInitializeLogEx2(0);
  UnattendLogW(0, L"Enter WinReSetupBackupWinRE");
  v12 = a2;
  if ( !a2 )
    v12 = L"NULL";
  v108 = v12;
  UnattendLogW(0, L"backup directory: %s", v12);
  LogGuid(L"targetOsGuid: ", a1);
  if ( a4 && a5 )
    *a4 = 0;
  if ( a2 && (unsigned int)winreDoesFileExist(a2, L"$PBR_IN_PROGRESS_BACKUP.MARKER") )
  {
    UnattendLogW(0, L"Find existing PBR_IN_PROGRESS_MARKER, will delete it.");
    std::wstring::wstring(&v114, v13);
    std::wstring::assign(&v114, a2);
    v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v114);
    v15 = &cchOriginalDestLength;
    if ( *((_WORD *)v14 + v115 - 1) != 92 )
      v15 = L"\\";
    v16 = std::char_traits<unsigned short>::length(v15);
    std::wstring::append(&v114, v17, v16);
    v18 = std::char_traits<unsigned short>::length(L"$PBR_IN_PROGRESS_BACKUP.MARKER");
    std::wstring::append(&v114, (__int64)L"$PBR_IN_PROGRESS_BACKUP.MARKER", v18);
    v19 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v114);
    if ( !DeleteFileW(v19) )
    {
      GetLastError();
      v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v114);
      UnattendLogW(2, L" Could not delete %s. Error: 0X%X", v21);
    }
    std::wstring::~wstring((__int64)&v114, v20);
  }
  v119 = 16;
  RegGetValueW(
    HKEY_LOCAL_MACHINE,
    L"SOFTWARE\\Microsoft\\RecoveryEnvironment",
    L"PbrInProgress",
    0x10u,
    &v119,
    &v113,
    &v118);
  if ( !v113 )
  {
    v22 = 0;
    if ( !(unsigned int)winreGetOSGuidOrDefault(a1, &rclsid) )
    {
      v23 = L"failed to get os guid or default";
      goto LABEL_18;
    }
    if ( !(unsigned int)pGetExistingWinREPath(&rclsid, v124, v116, &NumberOfBytesWritten) )
    {
      v22 = 1;
      UnattendLogW(0, L"WinRE not enabled. There is nothing to backup");
      goto LABEL_142;
    }
    if ( CBootCfg::GetOsInfoForBootEntry((CBootCfg *)CBootCfg::m_instance, &rclsid, (struct _SRT_OS_INFO **)&lpFileName) )
    {
      UnattendLogW(1, L"failed to get os info for boot entry");
      goto LABEL_142;
    }
    UnattendLogW(0, L"DisableUpdateEnhancedConfigInfo");
    v131 = 1;
    v24 = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v124);
    DownlevelConfigFilePathByGuid = ReAgentConfig::Init((ReAgentConfig *)v125, v24, 1);
    if ( DownlevelConfigFilePathByGuid )
    {
      v26 = L"AgentConfig.Init failed. Error: 0X%X";
      v27 = 1;
LABEL_27:
      UnattendLogW(v27, v26, DownlevelConfigFilePathByGuid);
      goto LABEL_142;
    }
    ConfigInfo = ReAgentXMLParser::GetConfigInfo((ReAgentXMLParser *)v125);
    IsWimBootEnabledInternal = WinReIsWimBootEnabledInternal(lpFileName);
    if ( IsWimBootEnabledInternal )
      UnattendLogW(0, L"WimBoot is enabled");
    v30 = L"%s\\%s";
    if ( !ConfigInfo || !*((_WORD *)ConfigInfo + 3116) )
    {
      if ( IsWimBootEnabledInternal )
        goto LABEL_78;
LABEL_52:
      if ( !v117 )
        goto LABEL_78;
      v132 = 0;
      v114 = 0;
      memset_0(v133, 0, 0x25Au);
      v33 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v116);
      lpFileName = 0;
      if ( !v33 )
        goto LABEL_46;
      v35 = StringCchLengthW(v33, 0x7FFFFFFFu, (unsigned __int64 *)&lpFileName);
      if ( v35 >= 0 )
      {
        if ( !lpFileName || *(_WORD *)(v34 + 2LL * (_QWORD)lpFileName - 2) == 92 )
          v30 = L"%s%s";
        v35 = StringCchPrintfW(&v132, 0x12Eu, v30, v34, L"Winre.wim");
        if ( v35 >= 0 )
        {
LABEL_67:
          if ( !(unsigned int)Utils::GetWimImageInfo(&v132, 1u, (struct _WIM_IMAGE_INFO *)&v114) )
          {
            UnattendLogW(0, L"WinRE image version: %d.%d", (unsigned int)v114, DWORD1(v114));
            if ( (unsigned int)v114 <= 6 && DWORD1(v114) < 4 )
            {
              UnattendLogW(0, L"The current WinRE will be preserved.");
              if ( a2 )
              {
                std::wstring::wstring(v121, a2);
                v38 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v121);
                v39 = &cchOriginalDestLength;
                if ( *((_WORD *)v38 + v121[2] - 1) != 92 )
                  v39 = L"\\";
                v40 = std::char_traits<unsigned short>::length(v39);
                std::wstring::append(v121, v41, v40);
                v42 = std::char_traits<unsigned short>::length(L"WinReLocation.txt");
                std::wstring::append(v121, v43, v42);
                v44 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v121);
                FileW = CreateFileW(v44, 0x40000000u, 0, 0, 2u, 0x80u, 0);
                if ( FileW != (HANDLE)-1LL )
                {
                  NumberOfBytesWritten = 0;
                  v47 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v116);
                  WriteFile(FileW, v47, v48, &NumberOfBytesWritten, 0);
                  CloseHandle(FileW);
                }
                std::wstring::~wstring((__int64)v121, v45);
              }
              v22 = 1;
              goto LABEL_142;
            }
          }
LABEL_78:
          DownlevelConfigFilePathByGuid = winreGetDownlevelConfigFilePathByGuid(&rclsid, &PathName, &NewFileName);
          if ( DownlevelConfigFilePathByGuid )
          {
            v26 = L"failed to get downlevel config file path by guid: 0x%x";
LABEL_80:
            v27 = 2;
            goto LABEL_27;
          }
          if ( !CreateDirectoryW(&PathName, 0) )
          {
            DownlevelConfigFilePathByGuid = GetLastError();
            if ( DownlevelConfigFilePathByGuid != 183 )
            {
              v26 = L"failed to create downlevel winre config directory with error 0x%x";
              goto LABEL_80;
            }
          }
          v49 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v124);
          v22 = CopyFileW(v49, &NewFileName, 0);
          if ( !v22 )
          {
            LastError = GetLastError();
            UnattendLogW(2, L"copy downlevel ReAgent.xml failed:  0x%x", LastError);
            UnattendLogW(0, L"Try to use backup function to backup downlevel ReAgent.xml.");
            v51 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v124);
            v54 = pCopyFile(v51, &NewFileName, v52, v53, pdwType, pvData, pcbData);
            v55 = v54;
            if ( v54 < 0 )
            {
              UnattendLogW(2, L"backup downlevel ReAgent.xml failed:  0x%x", (unsigned int)v54);
              if ( (v55 & 0x10000000) != 0 )
              {
                if ( RtlNtStatusToDosError(v55) != 317 )
                  v55 = RtlNtStatusToDosError(v55);
              }
              else if ( (v55 & 0x1FFF0000) == 0x70000 )
              {
                v55 = (unsigned __int16)v55;
              }
              SetLastError(v55);
              goto LABEL_92;
            }
            v22 = 1;
          }
          v56 = v110;
          if ( v110 )
          {
            v57 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v116);
            if ( GetDiskFreeSpaceExW(v57, &FreeBytesAvailableToCaller, 0, 0) )
            {
              v58 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v116);
              UnattendLogW(0, L"Free space on %s before moving %I64u", v58, FreeBytesAvailableToCaller.QuadPart);
            }
            else
            {
              v59 = GetLastError();
              UnattendLogW(2, L"failed to get disk free space with error 0x%x", v59);
            }
            v56 = v110;
          }
          if ( v107 )
          {
            v60 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v116);
            v62 = StringCchCopyW(v61, a5, v60);
            if ( v62 < 0 )
            {
              UnattendLogW(1, L"Failed to copy winre location to caller's buffer. Error: 0X%X", (unsigned int)v62);
LABEL_92:
              v22 = 0;
              goto LABEL_142;
            }
          }
          if ( v56 )
          {
            v63 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v116);
            v64 = winREMoveDirectory(v63, a2, 0);
          }
          else
          {
            if ( !a2 )
              goto LABEL_107;
            v65 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v116);
            v64 = winRECopyDirectory(v65, a2, 0);
          }
          v56 = v110;
          v22 = v64;
LABEL_107:
          if ( !v22 )
          {
            v66 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v116);
            UnattendLogW(2, L"move directoy from %s to %s failed", v66, v108);
            goto LABEL_142;
          }
          if ( v56 )
          {
            FreeBytesAvailableToCaller.QuadPart = 0;
            LOWORD(v110) = 92;
            if ( v117 )
            {
              v68 = (char *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v116);
              for ( i = &v68[2 * v67 - 2];
                    *(_WORD *)i != 92 || (unsigned int)std::char_traits<unsigned short>::compare(i, &v110, 1);
                    i -= 2 )
              {
                if ( i == v68 )
                  goto LABEL_117;
              }
              v70 = (i - v68) >> 1;
            }
            else
            {
LABEL_117:
              v70 = -1;
            }
            if ( v70 != -1 )
            {
              std::wstring::wstring(v121, v116, 0);
              v71 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v121);
              if ( GetDiskFreeSpaceExW(v71, &FreeBytesAvailableToCaller, 0, 0) )
              {
                v72 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v121);
                UnattendLogW(0, L"Free space on %s after moving %I64u", v72, FreeBytesAvailableToCaller.QuadPart);
              }
              else
              {
                v74 = GetLastError();
                UnattendLogW(2, L"failed to get free disk space with error: 0x%x", v74);
              }
              std::wstring::~wstring((__int64)v121, v73);
            }
          }
          if ( a2 )
          {
            std::wstring::assign(v122, a2);
            v75 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v122);
            v76 = &cchOriginalDestLength;
            if ( *((_WORD *)v75 + v122[2] - 1) != 92 )
              v76 = L"\\";
            v77 = std::char_traits<unsigned short>::length(v76);
            std::wstring::append(v122, v78, v77);
            v79 = std::char_traits<unsigned short>::length(L"location.txt");
            std::wstring::append(v122, v80, v79);
            if ( ConfigInfo )
            {
              v81 = StringCchPrintfW(String, 0x12Eu, L"%I64u", *((_QWORD *)ConfigInfo + 156));
              if ( v81 < 0 )
              {
                UnattendLogW(1, L"StringCchPrintf winre location offset failed. Error: 0X%X", (unsigned int)v81);
                goto LABEL_92;
              }
            }
            v82 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v122);
            if ( !WritePrivateProfileStringW(L"WinRE Location", L"Partition offset", String, v82) )
            {
              v83 = GetLastError();
              UnattendLogW(1, L"WritePrivateProfileString partition offset string failed. Error: 0X%X", v83);
              goto LABEL_92;
            }
            v84 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v122);
            if ( !WritePrivateProfileStringW(L"WinRE Location", L"Relative path", (LPCWSTR)ConfigInfo + 310, v84) )
            {
              v85 = GetLastError();
              UnattendLogW(1, L"WritePrivateProfileString winre location failed. Error: 0X%X", v85);
              goto LABEL_92;
            }
            v86 = StringFromCLSID(&rclsid, &lpsz);
            if ( v86 < 0 )
            {
              UnattendLogW(1, L"StringFromCLSID failed. hr = 0x%08X", (unsigned int)v86);
              goto LABEL_92;
            }
            v87 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v122);
            if ( !WritePrivateProfileStringW(L"WinRE Location", L"OS Guid", lpsz, v87) )
            {
              v88 = GetLastError();
              UnattendLogW(1, L"WritePrivateProfileString OS GUID failed. Error: 0X%X", v88);
              goto LABEL_92;
            }
          }
          v89 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v116);
          if ( GetVolumePathNameW(v89, &szVolumePathName, 0x104u) )
          {
            std::wstring::assign(v123, &szVolumePathName);
            v91 = std::char_traits<unsigned short>::length(L"$WINRE_BACKUP_PARTITION.MARKER");
            std::wstring::append(v123, v92, v91);
            v93 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v123);
            v94 = CreateFileW(v93, 0x40000000u, 0, 0, 2u, 2u, 0);
            if ( v94 == (HANDLE)-1LL )
            {
              GetLastError();
              v96 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v123);
              UnattendLogW(2, L"Unable to create the marker file %s. Error: 0X%X", v96);
            }
            else
            {
              v95 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v123);
              UnattendLogW(0, L"Marker file %s created", v95);
              CloseHandle(v94);
            }
          }
          else
          {
            v90 = GetLastError();
            UnattendLogW(2, L"GetVolumePathName failed. Error: 0X%X", v90);
          }
          goto LABEL_142;
        }
        v36 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v37 = 15;
          goto LABEL_65;
        }
      }
      else
      {
        v36 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v37 = 14;
LABEL_65:
          WPP_SF_d(v36[2], v37, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)v35);
        }
      }
      if ( (_WORD)v35 )
        goto LABEL_46;
      goto LABEL_67;
    }
    if ( IsWimBootEnabledInternal )
      goto LABEL_78;
    v132 = 0;
    v114 = 0;
    memset_0(v133, 0, 0x25Au);
    lpFileName = 0;
    v31 = StringCchLengthW((const unsigned __int16 *)ConfigInfo + 3116, 0x7FFFFFFFu, (unsigned __int64 *)&lpFileName);
    if ( v31 >= 0 )
    {
      if ( !lpFileName || (v32 = L"%s\\%s", *((_WORD *)ConfigInfo + (_QWORD)lpFileName + 3115) == 92) )
        v32 = L"%s%s";
      v31 = StringCchPrintfW(&v132, 0x12Eu, v32, (char *)ConfigInfo + 6232, L"Winre.wim");
      if ( v31 >= 0 )
        goto LABEL_47;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids,
          (unsigned int)v31);
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids,
        (unsigned int)v31);
    }
    if ( (_WORD)v31 )
    {
LABEL_46:
      UnattendLogW(2, L"WinReSetupBackupWinRE %s (0x%x) in file %S line %d", L"failed to append path");
      goto LABEL_142;
    }
LABEL_47:
    if ( !(unsigned int)Utils::GetWimImageInfo(&v132, 1u, (struct _WIM_IMAGE_INFO *)&v114) )
    {
      UnattendLogW(0, L"Downlevel WinRE image version: %d.%d", (unsigned int)v114, DWORD1(v114));
      if ( (unsigned int)v114 <= 6 && DWORD1(v114) < 3 )
      {
        UnattendLogW(0, L"The downlevel WinRE image will be preserved.");
        goto LABEL_78;
      }
    }
    goto LABEL_52;
  }
  v22 = 1;
  UnattendLogW(0, L"PBR in progress.");
  if ( !a2 )
  {
    UnattendLogW(0, L"BackupDirectory is NULL, will not create marker.");
    goto LABEL_142;
  }
  if ( !(unsigned int)winreSetPBRMarkerForBackup(a2) )
  {
    v23 = L"Failed to create marker in BackupDirectory";
LABEL_18:
    UnattendLogW(2, v23);
  }
LABEL_142:
  if ( lpsz )
    CoTaskMemFree(lpsz);
  v97 = L"TRUE";
  if ( !v22 )
    v97 = L"FALSE";
  UnattendLogW(0, L" (WinRE)WinReSetupBackupWinRE() returning %s", v97);
  UnattendFinalizeLog();
  v125[0] = &ReAgentConfig::`vftable';
  ReAgentXMLParser::~ReAgentXMLParser((ReAgentXMLParser *)v125);
  std::wstring::~wstring((__int64)v123, v98);
  std::wstring::~wstring((__int64)v122, v99);
  std::wstring::~wstring((__int64)v116, v100);
  std::wstring::~wstring((__int64)v124, v101);
  return v22;
}

```

## disassembly

```asm
0x18002dd30  mov     [rsp-8+arg_10], rbx
0x18002dd35  push    rbp
0x18002dd36  push    rsi
0x18002dd37  push    rdi
0x18002dd38  push    r12
0x18002dd3a  push    r13
0x18002dd3c  push    r14
0x18002dd3e  push    r15
0x18002dd40  lea     rbp, [rsp-0C50h]
0x18002dd48  sub     rsp, 0D50h
0x18002dd4f  mov     rax, cs:__security_cookie
0x18002dd56  xor     rax, rsp
0x18002dd59  mov     [rbp+0C80h+var_40], rax
0x18002dd60  mov     [rsp+0D80h+var_D20], r8d
0x18002dd65  mov     rsi, rdx
0x18002dd68  mov     rbx, rcx
0x18002dd6b  mov     [rsp+0D80h+var_D38], r9
0x18002dd70  mov     r14d, 25Ah
0x18002dd76  lea     rcx, [rbp+0C80h+var_4FE]; void *
0x18002dd7d  xor     r15d, r15d
0x18002dd80  mov     r8d, r14d; Size
0x18002dd83  xor     edx, edx; Val
0x18002dd85  mov     [rbp+0C80h+PathName], r15w
0x18002dd8d  mov     rdi, r9
0x18002dd90  call    memset_0
0x18002dd95  mov     r8d, r14d; Size
0x18002dd98  mov     [rbp+0C80h+NewFileName], r15w
0x18002dda0  xor     edx, edx; Val
0x18002dda2  lea     rcx, [rbp+0C80h+var_96E]; void *
0x18002dda9  call    memset_0
0x18002ddae  lea     rcx, [rbp+0C80h+var_C40]
0x18002ddb2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002ddb7  lea     rcx, [rbp+0C80h+var_CE0]
0x18002ddbb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002ddc0  lea     rcx, [rbp+0C80h+var_C80]
0x18002ddc4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002ddc9  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002ddd0  xor     edx, edx; Val
0x18002ddd2  mov     [rsp+0D80h+NumberOfBytesWritten], r15d
0x18002ddd7  lea     r8d, [r14-54h]; Size
0x18002dddb  mov     qword ptr [rsp+0D80h+FreeBytesAvailableToCaller], r15
0x18002dde0  lea     rcx, [rbp+0C80h+var_70E]; void *
0x18002dde7  mov     [rbp+0C80h+szVolumePathName], r15w
0x18002ddef  movdqu  xmmword ptr [rbp+0C80h+rclsid.Data1], xmm0
0x18002ddf4  call    memset_0
0x18002ddf9  lea     rcx, [rbp+0C80h+var_C60]
0x18002ddfd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002de02  xor     edx, edx; Val
0x18002de04  mov     [rsp+0D80h+lpFileName], r15
0x18002de09  lea     r8d, [r14+2]; Size
0x18002de0d  mov     [rsp+0D80h+var_D08], r15d
0x18002de12  lea     rcx, [rbp+0C80h+String]; void *
0x18002de19  mov     [rbp+0C80h+var_CC0], 4
0x18002de20  mov     [rsp+0D80h+lpsz], r15
0x18002de25  call    memset_0
0x18002de2a  xorps   xmm0, xmm0
0x18002de2d  mov     [rbp+0C80h+var_C18], r15
0x18002de31  xorps   xmm1, xmm1
0x18002de34  movdqa  [rbp+0C80h+var_C00], xmm0
0x18002de3c  lea     rax, ??_7ReAgentConfig@@6B@; const ReAgentConfig::`vftable'
0x18002de43  movdqa  [rbp+0C80h+var_BF0], xmm1
0x18002de4b  lea     r14d, [r15+2]
0x18002de4f  mov     [rbp+0C80h+var_C20], rax
0x18002de53  xor     ecx, ecx
0x18002de55  mov     [rbp+0C80h+var_C10], r15
0x18002de59  mov     [rbp+0C80h+var_C08], r15d
0x18002de5d  mov     [rbp+0C80h+var_C04], r14d
0x18002de61  mov     [rbp+0C80h+var_BE0], r15
0x18002de68  mov     [rbp+0C80h+var_BD8], r15d
0x18002de6f  call    UnattendInitializeLogEx2
0x18002de74  lea     rdx, aEnterWinresetu; "Enter WinReSetupBackupWinRE"
0x18002de7b  xor     ecx, ecx
0x18002de7d  call    UnattendLogW
0x18002de82  lea     rcx, aNull_0; "NULL"
0x18002de89  test    rsi, rsi
0x18002de8c  mov     rax, rsi
0x18002de8f  lea     rdx, aBackupDirector; "backup directory: %s"
0x18002de96  cmovz   rax, rcx
0x18002de9a  xor     ecx, ecx
0x18002de9c  mov     r8, rax
0x18002de9f  mov     [rsp+0D80h+var_D30], rax
0x18002dea4  call    UnattendLogW
0x18002dea9  mov     rdx, rbx
0x18002deac  lea     rcx, aTargetosguid; "targetOsGuid: "
0x18002deb3  call    LogGuid
0x18002deb8  test    rdi, rdi
0x18002debb  jz      short loc_18002DECA
0x18002debd  cmp     dword ptr [rbp+0C80h+arg_20], r15d
0x18002dec4  jbe     short loc_18002DECA
0x18002dec6  mov     [rdi], r15w
0x18002deca  lea     r13, pszSrc; "\\"
0x18002ded1  mov     r12d, 5Ch ; '\'
0x18002ded7  test    rsi, rsi
0x18002deda  jz      loc_18002DFAC
0x18002dee0  lea     rdi, aPbrInProgressB; "$PBR_IN_PROGRESS_BACKUP.MARKER"
0x18002dee7  mov     rcx, rsi; unsigned __int16 *
0x18002deea  mov     rdx, rdi; unsigned __int16 *
0x18002deed  call    winreDoesFileExist
0x18002def2  test    eax, eax
0x18002def4  jz      loc_18002DFAC
0x18002defa  lea     rdx, aFindExistingPb; "Find existing PBR_IN_PROGRESS_MARKER, w"...
0x18002df01  xor     ecx, ecx
0x18002df03  call    UnattendLogW
0x18002df08  lea     rcx, [rbp+0C80h+var_D00]
0x18002df0c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002df11  mov     rdx, rsi
0x18002df14  lea     rcx, [rbp+0C80h+var_D00]
0x18002df18  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18002df1d  lea     rcx, [rbp+0C80h+var_D00]
0x18002df21  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002df26  mov     rcx, [rbp+0C80h+var_CF0]
0x18002df2a  lea     r9, cchOriginalDestLength
0x18002df31  cmp     [rax+rcx*2-2], r12w
0x18002df37  cmovnz  r9, r13
0x18002df3b  mov     rcx, r9
0x18002df3e  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18002df43  mov     r8, rax
0x18002df46  lea     rcx, [rbp+0C80h+var_D00]
0x18002df4a  mov     rdx, r9
0x18002df4d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18002df52  mov     rcx, rdi
0x18002df55  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18002df5a  mov     r8, rax
0x18002df5d  lea     rcx, [rbp+0C80h+var_D00]
0x18002df61  mov     rdx, rdi
0x18002df64  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18002df69  lea     rcx, [rbp+0C80h+var_D00]
0x18002df6d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002df72  mov     rcx, rax; lpFileName
0x18002df75  call    cs:__imp_DeleteFileW
0x18002df7b  test    eax, eax
0x18002df7d  jnz     short loc_18002DFA3
0x18002df7f  call    cs:__imp_GetLastError
0x18002df85  lea     rcx, [rbp+0C80h+var_D00]
0x18002df89  mov     r9d, eax
0x18002df8c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002df91  mov     r8, rax
0x18002df94  lea     rdx, aCouldNotDelete_0; " Could not delete %s. Error: 0X%X"
0x18002df9b  mov     ecx, r14d
0x18002df9e  call    UnattendLogW
0x18002dfa3  lea     rcx, [rbp+0C80h+var_D00]
0x18002dfa7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002dfac  lea     rax, [rbp+0C80h+var_CC0]
0x18002dfb0  mov     r9d, 10h; dwFlags
0x18002dfb6  mov     qword ptr [rsp+0D80h+pcbData], rax; int
0x18002dfbb  lea     r8, aPbrinprogress; "PbrInProgress"
0x18002dfc2  lea     rax, [rsp+0D80h+var_D08]
0x18002dfc7  mov     [rbp+0C80h+var_CB8], r9d
0x18002dfcb  mov     [rsp+0D80h+pvData], rax; int
0x18002dfd0  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\RecoveryEnvironmen"...
0x18002dfd7  lea     rax, [rbp+0C80h+var_CB8]
0x18002dfdb  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002dfe2  mov     [rsp+0D80h+pdwType], rax; void *
0x18002dfe7  call    cs:__imp_RegGetValueW
0x18002dfed  cmp     [rsp+0D80h+var_D08], r15d
0x18002dff2  jz      short loc_18002E039
0x18002dff4  lea     rdx, aPbrInProgress; "PBR in progress."
0x18002dffb  xor     ecx, ecx
0x18002dffd  mov     edi, 1
0x18002e002  call    UnattendLogW
0x18002e007  test    rsi, rsi
0x18002e00a  jnz     short loc_18002E015
0x18002e00c  lea     rdx, aBackupdirector; "BackupDirectory is NULL, will not creat"...
0x18002e013  jmp     short loc_18002E079
0x18002e015  mov     rcx, rsi; unsigned __int16 *
0x18002e018  call    winreSetPBRMarkerForBackup
0x18002e01d  test    eax, eax
0x18002e01f  jnz     loc_18002EA91
0x18002e025  lea     rdx, aFailedToCreate_13; "Failed to create marker in BackupDirect"...
0x18002e02c  mov     ecx, r14d
0x18002e02f  call    UnattendLogW
0x18002e034  jmp     loc_18002EA91
0x18002e039  lea     rdx, [rbp+0C80h+rclsid]
0x18002e03d  mov     rcx, rbx
0x18002e040  mov     edi, r15d
0x18002e043  call    winreGetOSGuidOrDefault
0x18002e048  test    eax, eax
0x18002e04a  jnz     short loc_18002E055
0x18002e04c  lea     rdx, aFailedToGetOsG_0; "failed to get os guid or default"
0x18002e053  jmp     short loc_18002E02C
0x18002e055  lea     r9, [rsp+0D80h+NumberOfBytesWritten]
0x18002e05a  lea     r8, [rbp+0C80h+var_CE0]
0x18002e05e  lea     rdx, [rbp+0C80h+var_C40]
0x18002e062  lea     rcx, [rbp+0C80h+rclsid]
0x18002e066  call    ?pGetExistingWinREPath@@YAHPEAU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1AEAH@Z; pGetExistingWinREPath(_GUID *,std::wstring &,std::wstring &,int &)
0x18002e06b  test    eax, eax
0x18002e06d  jnz     short loc_18002E085
0x18002e06f  lea     edi, [rax+1]
0x18002e072  lea     rdx, aWinreNotEnable; "WinRE not enabled. There is nothing to "...
0x18002e079  xor     ecx, ecx
0x18002e07b  call    UnattendLogW
0x18002e080  jmp     loc_18002EA91
0x18002e085  lea     r8, [rsp+0D80h+lpFileName]; struct _SRT_OS_INFO **
0x18002e08a  lea     rdx, [rbp+0C80h+rclsid]; struct _GUID *
0x18002e08e  lea     rcx, ?m_instance@CBootCfg@@0V1@A; this
0x18002e095  call    ?GetOsInfoForBootEntry@CBootCfg@@QEAAKPEBU_GUID@@PEAPEAU_SRT_OS_INFO@@@Z; CBootCfg::GetOsInfoForBootEntry(_GUID const *,_SRT_OS_INFO * *)
0x18002e09a  test    eax, eax
0x18002e09c  jz      short loc_18002E0AC
0x18002e09e  lea     rdx, aFailedToGetOsI_0; "failed to get os info for boot entry"
0x18002e0a5  mov     ecx, 1
0x18002e0aa  jmp     short loc_18002E02F
0x18002e0ac  lea     rdx, aDisableupdatee; "DisableUpdateEnhancedConfigInfo"
0x18002e0b3  xor     ecx, ecx
0x18002e0b5  call    UnattendLogW
0x18002e0ba  mov     ebx, 1
0x18002e0bf  lea     rcx, [rbp+0C80h+var_C40]
0x18002e0c3  mov     [rbp+0C80h+var_BD8], ebx
0x18002e0c9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002e0ce  mov     rdx, rax; unsigned __int16 *
0x18002e0d1  lea     rcx, [rbp+0C80h+var_C20]; this
0x18002e0d5  mov     r8d, ebx; int
0x18002e0d8  call    ?Init@ReAgentConfig@@UEAAKPEAGH@Z; ReAgentConfig::Init(ushort *,int)
0x18002e0dd  test    eax, eax
0x18002e0df  jz      short loc_18002E0F7
0x18002e0e1  lea     rdx, aAgentconfigIni_0; "AgentConfig.Init failed. Error: 0X%X"
0x18002e0e8  mov     ecx, ebx
0x18002e0ea  mov     r8d, eax
0x18002e0ed  call    UnattendLogW
0x18002e0f2  jmp     loc_18002EA91
0x18002e0f7  lea     rcx, [rbp+0C80h+var_C20]; this
0x18002e0fb  call    ?GetConfigInfo@ReAgentXMLParser@@QEAAPEAUReAgentConfigInfo@@XZ; ReAgentXMLParser::GetConfigInfo(void)
0x18002e100  mov     rcx, [rsp+0D80h+lpFileName]; lpFileName
0x18002e105  mov     r13, rax
0x18002e108  call    ?WinReIsWimBootEnabledInternal@@YAHPEAG@Z; WinReIsWimBootEnabledInternal(ushort *)
0x18002e10d  mov     r14d, eax
0x18002e110  test    eax, eax
0x18002e112  jz      short loc_18002E122
0x18002e114  lea     rdx, aWimbootIsEnabl; "WimBoot is enabled"
0x18002e11b  xor     ecx, ecx
0x18002e11d  call    UnattendLogW
0x18002e122  lea     r12, aSS_1; "%s\\%s"
0x18002e129  test    r13, r13
0x18002e12c  jz      loc_18002E2C7
0x18002e132  lea     r15, [r13+1858h]
0x18002e139  xor     eax, eax
0x18002e13b  cmp     ax, [r15]
0x18002e13f  jz      loc_18002E2C4
0x18002e145  test    r14d, r14d
0x18002e148  jnz     loc_18002E52F
0x18002e14e  xorps   xmm0, xmm0
0x18002e151  mov     [rbp+0C80h+var_BD0], ax
0x18002e158  xor     edx, edx; Val
0x18002e15a  lea     rcx, [rbp+0C80h+var_BCE]; void *
0x18002e161  mov     r8d, 25Ah; Size
0x18002e167  movups  [rbp+0C80h+var_D00], xmm0
0x18002e16b  call    memset_0
0x18002e170  lea     r8, [rsp+0D80h+lpFileName]; unsigned __int64 *
0x18002e175  mov     [rsp+0D80h+lpFileName], rdi
0x18002e17a  mov     edx, 7FFFFFFFh; unsigned __int64
0x18002e17f  mov     rcx, r15; unsigned __int16 *
0x18002e182  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002e187  mov     r14d, eax
0x18002e18a  test    eax, eax
0x18002e18c  jns     short loc_18002E1C4
0x18002e18e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e195  lea     rax, WPP_GLOBAL_Control
0x18002e19c  cmp     rcx, rax
0x18002e19f  jz      short loc_18002E1BF
0x18002e1a1  test    byte ptr [rcx+1Ch], 2
0x18002e1a5  jz      short loc_18002E1BF
0x18002e1a7  mov     rcx, [rcx+10h]
0x18002e1ab  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18002e1b2  mov     edx, 0Eh
0x18002e1b7  mov     r9d, r14d
0x18002e1ba  call    WPP_SF_d
0x18002e1bf  xor     r15d, r15d
0x18002e1c2  jmp     short loc_18002E23F
0x18002e1c4  mov     rax, [rsp+0D80h+lpFileName]
0x18002e1c9  test    rax, rax
0x18002e1cc  jz      short loc_18002E1DE
0x18002e1ce  mov     ecx, 5Ch ; '\'
0x18002e1d3  mov     r8, r12
0x18002e1d6  cmp     [r15+rax*2-2], cx
0x18002e1dc  jnz     short loc_18002E1E5
0x18002e1de  lea     r8, aSS_2; "%s%s"
0x18002e1e5  lea     rax, aWinreWim; "Winre.wim"
0x18002e1ec  mov     r9, r15
0x18002e1ef  mov     edx, 12Eh; unsigned __int64
0x18002e1f4  mov     [rsp+0D80h+pdwType], rax
0x18002e1f9  lea     rcx, [rbp+0C80h+var_BD0]; unsigned __int16 *
0x18002e200  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e205  xor     r15d, r15d
0x18002e208  mov     r14d, eax
0x18002e20b  test    eax, eax
0x18002e20d  jns     short loc_18002E279
0x18002e20f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e216  lea     rax, WPP_GLOBAL_Control
0x18002e21d  cmp     rcx, rax
0x18002e220  jz      short loc_18002E23F
0x18002e222  test    byte ptr [rcx+1Ch], 2
0x18002e226  jz      short loc_18002E23F
0x18002e228  mov     rcx, [rcx+10h]
0x18002e22c  lea     edx, [r15+0Fh]
0x18002e230  mov     r9d, r14d
0x18002e233  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18002e23a  call    WPP_SF_d
0x18002e23f  movzx   r9d, r14w
0x18002e243  test    r9d, r9d
0x18002e246  jz      short loc_18002E279
0x18002e248  mov     dword ptr [rsp+0D80h+pvData], 2EDh
  ... truncated ...
```
