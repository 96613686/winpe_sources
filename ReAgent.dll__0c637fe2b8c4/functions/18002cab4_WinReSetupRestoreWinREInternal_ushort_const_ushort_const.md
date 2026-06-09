# WinReSetupRestoreWinREInternal(ushort const *,ushort const *)

- ea: `0x18002cab4`
- end: `0x18002d404`
- name: `?WinReSetupRestoreWinREInternal@@YAHPEBG0@Z`
- size: `2384`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002f860`

## callees

- `0x1800059fc`
- `0x180008b94`
- `0x18000c6f0`
- `0x180011974`
- `0x1800121b0`
- `0x1800145f4`
- `0x180014754`
- `0x18001c324`
- `0x18001c448`
- `0x18001ee18`
- `0x18001f0c0`
- `0x18001f47c`
- `0x1800289d8`
- `0x180028aac`
- `0x180028e30`
- `0x18002cab4`
- `0x18002f6a0`
- `0x180030f18`
- `0x180031814`
- `0x180031a00`
- `0x180034aa4`
- `0x1800356d4`
- `0x18003591c`
- `0x180035e88`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `msvcrt!_wtoi64` at `0x18002cc93`
- `msvcrt!_wtoi64` at `0x18002ce97`
- `msvcrt!_wtoi64` at `0x18002cf1b`
- `msvcrt!_wtoi64` at `0x18002cc93`
- `msvcrt!_wtoi64` at `0x18002ce97`
- `msvcrt!_wtoi64` at `0x18002cf1b`
- `KERNEL32!GetLastError` at `0x18002cc1d`
- `KERNEL32!GetLastError` at `0x18002cc71`
- `KERNEL32!GetLastError` at `0x18002ccda`
- `KERNEL32!GetLastError` at `0x18002cd81`
- `KERNEL32!GetLastError` at `0x18002d010`
- `KERNEL32!GetLastError` at `0x18002d054`
- `KERNEL32!GetLastError` at `0x18002d17e`
- `KERNEL32!GetLastError` at `0x18002d1b0`
- `KERNEL32!GetLastError` at `0x18002cc1d`
- `KERNEL32!GetLastError` at `0x18002cc71`
- `KERNEL32!GetLastError` at `0x18002ccda`
- `KERNEL32!GetLastError` at `0x18002cd81`
- `KERNEL32!GetLastError` at `0x18002d010`
- `KERNEL32!GetLastError` at `0x18002d054`
- `KERNEL32!GetLastError` at `0x18002d17e`
- `KERNEL32!GetLastError` at `0x18002d1b0`
- `KERNEL32!HeapFree` at `0x18002cf8d`
- `KERNEL32!HeapFree` at `0x18002cf8d`
- `KERNEL32!HeapAlloc` at `0x18002cc0f`
- `KERNEL32!HeapAlloc` at `0x18002cc0f`
- `KERNEL32!GetProcessHeap` at `0x18002cbff`
- `KERNEL32!GetProcessHeap` at `0x18002cf7f`
- `KERNEL32!GetProcessHeap` at `0x18002cbff`
- `KERNEL32!GetProcessHeap` at `0x18002cf7f`
- `KERNEL32!GetPrivateProfileStringW` at `0x18002cc67`
- `KERNEL32!GetPrivateProfileStringW` at `0x18002ccd0`
- `KERNEL32!GetPrivateProfileStringW` at `0x18002cd0f`
- `KERNEL32!GetPrivateProfileStringW` at `0x18002ce87`
- `KERNEL32!GetPrivateProfileStringW` at `0x18002cf0e`
- `KERNEL32!GetPrivateProfileStringW` at `0x18002cc67`
- `KERNEL32!GetPrivateProfileStringW` at `0x18002ccd0`
- `KERNEL32!GetPrivateProfileStringW` at `0x18002cd0f`
- `KERNEL32!GetPrivateProfileStringW` at `0x18002ce87`
- `KERNEL32!GetPrivateProfileStringW` at `0x18002cf0e`
- `KERNEL32!GetFileAttributesW` at `0x18002cbc7`
- `KERNEL32!GetFileAttributesW` at `0x18002cdac`
- `KERNEL32!GetFileAttributesW` at `0x18002ce32`
- `KERNEL32!GetFileAttributesW` at `0x18002d15c`
- `KERNEL32!GetFileAttributesW` at `0x18002cbc7`
- `KERNEL32!GetFileAttributesW` at `0x18002cdac`
- `KERNEL32!GetFileAttributesW` at `0x18002ce32`
- `KERNEL32!GetFileAttributesW` at `0x18002d15c`
- `KERNEL32!DeleteFileW` at `0x18002cf56`
- `KERNEL32!DeleteFileW` at `0x18002cff9`
- `KERNEL32!DeleteFileW` at `0x18002d174`
- `KERNEL32!DeleteFileW` at `0x18002cf56`
- `KERNEL32!DeleteFileW` at `0x18002cff9`
- `KERNEL32!DeleteFileW` at `0x18002d174`
- `KERNEL32!GetVolumePathNameW` at `0x18002d113`
- `KERNEL32!GetVolumePathNameW` at `0x18002d113`
- `ole32!CoTaskMemFree` at `0x18002d3f8`
- `ole32!CoTaskMemFree` at `0x18002d3f8`
- `ole32!CLSIDFromString` at `0x18002cd21`
- `ole32!CLSIDFromString` at `0x18002cd21`

## string_xrefs

- `0x18002d246`: `DisableUpdateEnhancedConfigInfo`
- `0x18002d272`: `failed to init agent config`
- `0x18002d394`: `ReAgent.xml`
- `0x18002d3b3`: `failed to back up config file`
- `0x18002d235`: `Failed to get WinRE config file path`
- `0x18002d3bc`: `base\diagnosis\srt\reagent2\reagent\setup.cpp`
- `0x18002d194`: ` Could not delete %s. Error: 0X%X`
- `0x18002ccc6`: `Relative path`
- `0x18002cce0`: `GetPrivateProfileString relative path failed. Error: 0X%X`
- `0x18002ce4e`: `Check undo-Installtion info from %s`
- `0x18002ceb6`: `Find new WinRE partition offset %I64u while original offset during backup is %I64u`
- `0x18002cfd4`: `No %s file under Undo directory %s`
- `0x18002d098`: `Failed to create relative dir %s on target partition`
- `0x18002d1b9`: `failed to get volume path name. Error: 0X%X`
- `0x18002d1d1`: `Partition has been resized, recreate WinRE BCD entry`
- `0x18002d2a4`: `failed to remove current WinRE bcd entry: 0x%x`
- `0x18002d2c7`: `failed to update device path in WinRE BCD: 0x%x`
- `0x18002d345`: `Partition offset is changed, update it in config`
- `0x18002d37b`: `failed to update offset to config file: 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WinReSetupRestoreWinREInternal(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  _QWORD *v4; // rax
  const WCHAR *v5; // r9
  unsigned __int64 v6; // r8
  __int64 v7; // r9
  unsigned __int64 v8; // rax
  const WCHAR *v9; // rax
  _QWORD *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r15
  HANDLE ProcessHeap; // rax
  void *v14; // rdi
  DWORD LastError; // eax
  const WCHAR *v16; // rax
  DWORD v17; // eax
  unsigned __int64 v18; // rsi
  const WCHAR *v19; // rax
  DWORD v20; // eax
  const WCHAR *v21; // rax
  HRESULT v22; // eax
  int v23; // r12d
  int v24; // r13d
  DWORD v25; // eax
  _QWORD *v26; // rax
  const WCHAR *v27; // rcx
  unsigned __int64 v28; // rax
  __int64 v29; // rcx
  unsigned __int64 v30; // rax
  const WCHAR *v31; // rax
  _QWORD *v32; // rax
  const WCHAR *v33; // rax
  unsigned __int64 v34; // r14
  const WCHAR *v35; // rax
  const WCHAR *v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rdx
  HANDLE v39; // rax
  const WCHAR *v41; // rax
  DWORD v42; // eax
  DWORD v43; // eax
  struct PartitionNode *v44; // rsi
  int v45; // eax
  __int64 v46; // r8
  unsigned __int64 v47; // rax
  __int64 v48; // rcx
  const WCHAR *v49; // rax
  __int64 v50; // rdx
  const WCHAR *v51; // rax
  _QWORD *v52; // rax
  DWORD v53; // eax
  unsigned int ConfigFilePathFromOsGuid; // eax
  unsigned __int16 *v55; // r14
  const wchar_t *v56; // r8
  struct ReAgentConfigInfo *ConfigInfo; // rax
  unsigned int v58; // eax
  unsigned int RecoveryEntryInBCD; // eax
  struct ReAgentConfigInfo *v60; // rax
  unsigned int v61; // eax
  unsigned int v62; // eax
  unsigned int v63; // eax
  LPCWSTR lpFileName; // [rsp+30h] [rbp-D8h]
  int v65; // [rsp+3Ch] [rbp-CCh]
  struct PartitionNode *v66[2]; // [rsp+40h] [rbp-C8h] BYREF
  unsigned __int16 *pclsid; // [rsp+50h] [rbp-B8h]
  GUID pclsid_8; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v69[4]; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v70; // [rsp+88h] [rbp-80h] BYREF
  _QWORD v71[4]; // [rsp+98h] [rbp-70h] BYREF
  _QWORD v72[3]; // [rsp+B8h] [rbp-50h] BYREF
  int v73; // [rsp+D0h] [rbp-38h]
  int v74; // [rsp+D4h] [rbp-34h]
  __int128 v75; // [rsp+D8h] [rbp-30h]
  __int128 v76; // [rsp+E8h] [rbp-20h]
  _OWORD *v77; // [rsp+F8h] [rbp-10h]
  int v78; // [rsp+100h] [rbp-8h]
  WCHAR ReturnedString[304]; // [rsp+108h] [rbp+0h] BYREF
  WCHAR szVolumePathName; // [rsp+368h] [rbp+260h] BYREF
  _BYTE v81[526]; // [rsp+36Ah] [rbp+262h] BYREF
  WCHAR szFileName[304]; // [rsp+578h] [rbp+470h] BYREF

  v66[1] = (struct PartitionNode *)-2LL;
  *(_QWORD *)&v70 = a1;
  v66[0] = 0;
  memset_0(ReturnedString, 0, 0x25Cu);
  memset_0(szFileName, 0, 0x25Cu);
  szVolumePathName = 0;
  memset_0(v81, 0, 0x206u);
  pclsid_8 = 0;
  pclsid = 0;
  std::wstring::wstring(v71, a1);
  v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v71);
  v5 = &cchOriginalDestLength;
  if ( *((_WORD *)v4 + v71[2] - 1) != 92 )
    v5 = L"\\";
  v6 = std::char_traits<unsigned short>::length(v5);
  std::wstring::append(v71, v7, v6);
  v8 = std::char_traits<unsigned short>::length(L"location.txt");
  std::wstring::append(v71, (__int64)L"location.txt", v8);
  v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v71);
  if ( GetFileAttributesW(v9) != -1 )
  {
    v12 = 0;
    ProcessHeap = GetProcessHeap();
    v14 = HeapAlloc(ProcessHeap, 8u, 0x25Cu);
    if ( !v14 )
    {
      LastError = GetLastError();
      UnattendLogW(1, L"HeapAlloc failed. Error: 0X%X", LastError);
      goto LABEL_31;
    }
    v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v71);
    if ( !GetPrivateProfileStringW(L"WinRE Location", L"Partition offset", 0, (LPWSTR)v14, 0x12Eu, v16) )
    {
      v17 = GetLastError();
      UnattendLogW(1, L"GetPrivateProfileString partition offset failed. Error: 0X%X", v17);
LABEL_30:
      v39 = GetProcessHeap();
      HeapFree(v39, 0, v14);
      goto LABEL_31;
    }
    v18 = _wtoi64((const wchar_t *)v14);
    memset_0(v14, 0, 0x25Cu);
    v19 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v71);
    if ( !GetPrivateProfileStringW(L"WinRE Location", L"Relative path", 0, ReturnedString, 0x12Eu, v19)
      || (v21 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v71),
          !GetPrivateProfileStringW(L"WinRE Location", L"OS Guid", 0, (LPWSTR)v14, 0x12Eu, v21)) )
    {
      v20 = GetLastError();
      UnattendLogW(1, L"GetPrivateProfileString relative path failed. Error: 0X%X", v20);
      goto LABEL_30;
    }
    v22 = CLSIDFromString((LPCOLESTR)v14, &pclsid_8);
    if ( v22 < 0 )
    {
      UnattendLogW(1, L"Failed to convert String {%s} to GUID. Error: 0X%X", v14, (unsigned int)v22);
      goto LABEL_30;
    }
    v23 = 0;
    v24 = 0;
    v65 = 0;
    memset_0(v14, 0, 0x25Cu);
    LogGuid(L"OS Guid:", &pclsid_8);
    if ( !(unsigned int)WinReSetupRemoveWinRE(&pclsid_8) )
    {
      v25 = GetLastError();
      UnattendLogW(2, L"failed to cleanup existing WinRE with error 0x%x", v25);
    }
    if ( a2 && GetFileAttributesW(a2) != -1 )
    {
      std::wstring::wstring(v69, a2);
      v26 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v69);
      v27 = &cchOriginalDestLength;
      if ( *((_WORD *)v26 + v69[2] - 1) != 92 )
        v27 = L"\\";
      v28 = std::char_traits<unsigned short>::length(v27);
      std::wstring::append(v69, v29, v28);
      v30 = std::char_traits<unsigned short>::length(L"location.txt");
      std::wstring::append(v69, (__int64)L"location.txt", v30);
      v31 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v69);
      if ( GetFileAttributesW(v31) == -1 )
      {
        UnattendLogW(0, L"No %s file under Undo directory %s", L"location.txt", a2);
      }
      else
      {
        v32 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v69);
        UnattendLogW(0, L"Check undo-Installtion info from %s", v32);
        v33 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v69);
        if ( GetPrivateProfileStringW(L"WinRE Location", L"New Partition offset", 0, (LPWSTR)v14, 0x12Eu, v33) )
        {
          v23 = 1;
          v34 = _wtoi64((const wchar_t *)v14);
          memset_0(v14, 0, 0x25Cu);
          UnattendLogW(
            0,
            L"Find new WinRE partition offset %I64u while original offset during backup is %I64u",
            v34,
            v18);
          if ( v34 != v18 )
          {
            if ( v34 >= v18 )
            {
              UnattendLogW(1, L"WinRE partition is resized, cannot restore WinRE");
              std::wstring::~wstring((__int64)v69, v38);
              goto LABEL_29;
            }
            v24 = 1;
            UnattendLogW(0, L"WinRE partition is extended, restore WinRE to extended partyition");
            v18 = v34;
          }
        }
        v35 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v69);
        if ( GetPrivateProfileStringW(L"WinRE Location", L"Current WinRE partition offset", 0, (LPWSTR)v14, 0x12Eu, v35) )
        {
          v12 = _wtoi64((const wchar_t *)v14);
          memset_0(v14, 0, 0x25Cu);
          UnattendLogW(0, L"Current partition offset of new OS is %I64u", v12);
          v65 = 1;
        }
        v36 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v69);
        DeleteFileW(v36);
      }
      std::wstring::~wstring((__int64)v69, v37);
    }
    v41 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v71);
    DeleteFileW(v41);
    if ( (unsigned int)winreFindPartitionByOffset(v18, v66) )
      goto LABEL_39;
    v42 = GetLastError();
    UnattendLogW(1, L"failed to find partition by offset %I64u. Error: 0X%X", v18, v42);
    if ( v65 )
    {
      UnattendLogW(0, L"Try to find current WinRE partition used by new OS");
      if ( !(unsigned int)winreFindPartitionByOffset(v12, v66) )
      {
        v43 = GetLastError();
        UnattendLogW(1, L"failed to find partition by offset %I64u. Error: 0X%X", v18, v43);
        goto LABEL_29;
      }
      v23 = 1;
      v24 = 1;
LABEL_39:
      v44 = v66[0];
      if ( !(unsigned int)winRECreateDirectoryInPartition(v66[0], ReturnedString) )
        UnattendLogW(2, L"Failed to create relative dir %s on target partition", ReturnedString);
      v45 = StringCchPrintfW(szFileName, 0x12Eu, L"%s%s", (char *)v44 + 656, ReturnedString);
      if ( v45 < 0 )
      {
        UnattendLogW(1, L"StringCchPrintf failed. Error: 0X%X", (unsigned int)v45);
        goto LABEL_29;
      }
      LOBYTE(v46) = 1;
      LODWORD(v12) = winREMoveDirectory(v70, szFileName, v46);
      if ( GetVolumePathNameW(szFileName, &szVolumePathName, 0x104u) )
      {
        std::wstring::wstring(v69, &szVolumePathName);
        v47 = std::char_traits<unsigned short>::length(L"$WINRE_BACKUP_PARTITION.MARKER");
        std::wstring::append(v69, v48, v47);
        v49 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v69);
        if ( GetFileAttributesW(v49) != -1 )
        {
          v51 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v69);
          if ( !DeleteFileW(v51) )
          {
            GetLastError();
            v52 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v69);
            UnattendLogW(2, L" Could not delete %s. Error: 0X%X", v52);
          }
        }
        std::wstring::~wstring((__int64)v69, v50);
      }
      else
      {
        v53 = GetLastError();
        UnattendLogW(2, L"failed to get volume path name. Error: 0X%X", v53);
      }
      if ( !v23 )
        goto LABEL_30;
      UnattendLogW(0, L"Partition has been resized, recreate WinRE BCD entry");
      v72[1] = 0;
      v72[2] = 0;
      v73 = 0;
      v74 = 2;
      v75 = 0;
      v76 = 0;
      v77 = 0;
      v72[0] = &ReAgentConfig::`vftable';
      v78 = 0;
      ConfigFilePathFromOsGuid = winreGetConfigFilePathFromOsGuid(&pclsid_8);
      v55 = pclsid;
      if ( ConfigFilePathFromOsGuid )
      {
        LODWORD(lpFileName) = 1836;
        v56 = L"Failed to get WinRE config file path";
      }
      else
      {
        UnattendLogW(0, L"DisableUpdateEnhancedConfigInfo");
        v78 = 1;
        ConfigFilePathFromOsGuid = ReAgentConfig::Init((ReAgentConfig *)v72, v55, 1);
        if ( ConfigFilePathFromOsGuid )
        {
          LODWORD(lpFileName) = 1844;
          v56 = L"failed to init agent config";
        }
        else
        {
          v70 = 0;
          ConfigInfo = ReAgentXMLParser::GetConfigInfo((ReAgentXMLParser *)v72);
          v58 = winreRemoveRecoverySequenceEx(&pclsid_8, ConfigInfo);
          if ( v58 )
            UnattendLogW(2, L"failed to remove current WinRE bcd entry: 0x%x", v58);
          RecoveryEntryInBCD = winreCreateRecoveryEntryInBCD(v44);
          if ( RecoveryEntryInBCD )
          {
            UnattendLogW(2, L"failed to update device path in WinRE BCD: 0x%x", RecoveryEntryInBCD);
          }
          else
          {
            LogGuid(L"New WinRE BCD Guid: ", &v70);
            *v77 = v70;
            v60 = ReAgentXMLParser::GetConfigInfo((ReAgentXMLParser *)v72);
            v61 = winreSetRecoverySequence(&v70, *((unsigned int *)v60 + 1556), &pclsid_8);
            if ( v61 )
              UnattendLogW(2, L"failed to set Recovery Sequence: 0x%x", v61);
            v62 = winreRegisterInRecoveryBCD(v44, &pclsid_8);
            if ( v62 )
              UnattendLogW(
                2,
                L"Failed to register WinRE in recovery BCD, recovery button may be unavailable: 0x%x",
                v62);
          }
          if ( v24 )
          {
            UnattendLogW(0, L"Partition offset is changed, update it in config");
            v63 = ReAgentConfig::SetWinreLocationPath(
                    (ReAgentConfig *)v72,
                    *((_QWORD *)v44 + 158),
                    (struct _GUID *)((char *)v44 + 36),
                    *((_DWORD *)v44 + 8),
                    ReturnedString);
            if ( v63 )
              UnattendLogW(2, L"failed to update offset to config file: 0x%x", v63);
            else
              ReAgentXMLParser::Update((ReAgentXMLParser *)v72);
          }
          ConfigFilePathFromOsGuid = winreBackupRecoveryFile(v55, (ReAgentXMLParser *)v72, L"ReAgent.xml");
          if ( !ConfigFilePathFromOsGuid )
            goto LABEL_69;
          LODWORD(lpFileName) = 1902;
          v56 = L"failed to back up config file";
        }
      }
      UnattendLogW(
        2,
        L"WinReSetupRestoreWinREInternal %s (0x%x) in file %S line %d",
        v56,
        ConfigFilePathFromOsGuid,
        "base\\diagnosis\\srt\\reagent2\\reagent\\setup.cpp",
        lpFileName);
LABEL_69:
      v72[0] = &ReAgentConfig::`vftable';
      ReAgentXMLParser::~ReAgentXMLParser((ReAgentXMLParser *)v72);
      if ( v55 )
        CoTaskMemFree(v55);
      goto LABEL_30;
    }
LABEL_29:
    LODWORD(v12) = 0;
    goto LABEL_30;
  }
  v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v71);
  UnattendLogW(0, L"%s file does not exist.", v10);
  LODWORD(v12) = 1;
LABEL_31:
  std::wstring::~wstring((__int64)v71, v11);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18002cab4  mov     rax, rsp
0x18002cab7  push    rbp
0x18002cab8  push    rsi
0x18002cab9  push    rdi
0x18002caba  push    r12
0x18002cabc  push    r13
0x18002cabe  push    r14
0x18002cac0  push    r15
0x18002cac2  lea     rbp, [rax-718h]
0x18002cac9  sub     rsp, 7E0h
0x18002cad0  mov     [rsp+810h+var_7D0], 0FFFFFFFFFFFFFFFEh
0x18002cad9  mov     [rax+18h], rbx
0x18002cadd  mov     rax, cs:__security_cookie
0x18002cae4  xor     rax, rsp
0x18002cae7  mov     [rbp+710h+var_40], rax
0x18002caee  mov     r14, rdx
0x18002caf1  mov     rbx, rcx
0x18002caf4  mov     qword ptr [rbp+710h+var_790], rcx
0x18002caf8  mov     [rsp+810h+var_7D8], 0
0x18002cb01  mov     r12d, 25Ch
0x18002cb07  mov     r8d, r12d; Size
0x18002cb0a  xor     edx, edx; Val
0x18002cb0c  lea     rcx, [rbp+710h+ReturnedString]; void *
0x18002cb10  call    memset_0
0x18002cb15  mov     r8d, r12d; Size
0x18002cb18  xor     edx, edx; Val
0x18002cb1a  lea     rcx, [rbp+710h+szFileName]; void *
0x18002cb21  call    memset_0
0x18002cb26  xor     eax, eax
0x18002cb28  mov     [rbp+710h+szVolumePathName], ax
0x18002cb2f  xor     edx, edx; Val
0x18002cb31  lea     r8d, [r12-56h]; Size
0x18002cb36  lea     rcx, [rbp+710h+var_4AE]; void *
0x18002cb3d  call    memset_0
0x18002cb42  xorps   xmm0, xmm0
0x18002cb45  movups  xmmword ptr [rsp+810h+pclsid.Data4], xmm0
0x18002cb4a  mov     qword ptr [rsp+810h+pclsid.Data1], 0
0x18002cb53  mov     rdx, rbx
0x18002cb56  lea     rcx, [rbp+710h+var_780]
0x18002cb5a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18002cb5f  nop
0x18002cb60  lea     rcx, [rbp+710h+var_780]
0x18002cb64  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002cb69  mov     rcx, [rbp+710h+var_770]
0x18002cb6d  lea     rdx, pszSrc; "\\"
0x18002cb74  lea     r9, cchOriginalDestLength
0x18002cb7b  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x18002cb81  cmovnz  r9, rdx
0x18002cb85  mov     rcx, r9
0x18002cb88  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18002cb8d  mov     r8, rax
0x18002cb90  mov     rdx, r9
0x18002cb93  lea     rcx, [rbp+710h+var_780]
0x18002cb97  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18002cb9c  lea     rcx, aLocationTxt; "location.txt"
0x18002cba3  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18002cba8  mov     r8, rax
0x18002cbab  lea     rdx, aLocationTxt; "location.txt"
0x18002cbb2  lea     rcx, [rbp+710h+var_780]
0x18002cbb6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18002cbbb  lea     rcx, [rbp+710h+var_780]
0x18002cbbf  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002cbc4  mov     rcx, rax; lpFileName
0x18002cbc7  call    cs:__imp_GetFileAttributesW
0x18002cbcd  cmp     eax, 0FFFFFFFFh
0x18002cbd0  jnz     short loc_18002CBF7
0x18002cbd2  lea     rcx, [rbp+710h+var_780]
0x18002cbd6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002cbdb  mov     r8, rax
0x18002cbde  lea     rdx, aSFileDoesNotEx; "%s file does not exist."
0x18002cbe5  xor     ecx, ecx
0x18002cbe7  call    UnattendLogW
0x18002cbec  mov     r15d, 1
0x18002cbf2  jmp     loc_18002CF94
0x18002cbf7  xor     r15d, r15d
0x18002cbfa  mov     dword ptr [rsp+810h+var_7E0], r15d
0x18002cbff  call    cs:__imp_GetProcessHeap
0x18002cc05  mov     rcx, rax; hHeap
0x18002cc08  mov     r8, r12; dwBytes
0x18002cc0b  lea     edx, [r15+8]; dwFlags
0x18002cc0f  call    cs:__imp_HeapAlloc
0x18002cc15  mov     rdi, rax
0x18002cc18  test    rax, rax
0x18002cc1b  jnz     short loc_18002CC3A
0x18002cc1d  call    cs:__imp_GetLastError
0x18002cc23  mov     r8d, eax
0x18002cc26  lea     rdx, aHeapallocFaile; "HeapAlloc failed. Error: 0X%X"
0x18002cc2d  lea     ecx, [rdi+1]
0x18002cc30  call    UnattendLogW
0x18002cc35  jmp     loc_18002CF94
0x18002cc3a  lea     rcx, [rbp+710h+var_780]
0x18002cc3e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002cc43  mov     [rsp+810h+lpFileName], rax; lpFileName
0x18002cc48  mov     [rsp+810h+nSize], 12Eh; nSize
0x18002cc50  mov     r9, rdi; lpReturnedString
0x18002cc53  xor     r8d, r8d; lpDefault
0x18002cc56  lea     rdx, aPartitionOffse; "Partition offset"
0x18002cc5d  lea     rbx, aWinreLocation; "WinRE Location"
0x18002cc64  mov     rcx, rbx; lpAppName
0x18002cc67  call    cs:__imp_GetPrivateProfileStringW
0x18002cc6d  test    eax, eax
0x18002cc6f  jnz     short loc_18002CC90
0x18002cc71  call    cs:__imp_GetLastError
0x18002cc77  lea     rdx, aGetprivateprof_0; "GetPrivateProfileString partition offse"...
0x18002cc7e  mov     r8d, eax
0x18002cc81  mov     ecx, 1
0x18002cc86  call    UnattendLogW
0x18002cc8b  jmp     loc_18002CF7F
0x18002cc90  mov     rcx, rdi; String
0x18002cc93  call    cs:__imp__wtoi64
0x18002cc99  mov     rsi, rax
0x18002cc9c  mov     r8, r12; Size
0x18002cc9f  xor     edx, edx; Val
0x18002cca1  mov     rcx, rdi; void *
0x18002cca4  call    memset_0
0x18002cca9  lea     rcx, [rbp+710h+var_780]
0x18002ccad  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ccb2  mov     [rsp+810h+lpFileName], rax; lpFileName
0x18002ccb7  mov     [rsp+810h+nSize], 12Eh; nSize
0x18002ccbf  lea     r9, [rbp+710h+ReturnedString]; lpReturnedString
0x18002ccc3  xor     r8d, r8d; lpDefault
0x18002ccc6  lea     rdx, aRelativePath; "Relative path"
0x18002cccd  mov     rcx, rbx; lpAppName
0x18002ccd0  call    cs:__imp_GetPrivateProfileStringW
0x18002ccd6  test    eax, eax
0x18002ccd8  jnz     short loc_18002CCE9
0x18002ccda  call    cs:__imp_GetLastError
0x18002cce0  lea     rdx, aGetprivateprof; "GetPrivateProfileString relative path f"...
0x18002cce7  jmp     short loc_18002CC7E
0x18002cce9  lea     rcx, [rbp+710h+var_780]
0x18002cced  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ccf2  mov     [rsp+810h+lpFileName], rax; lpFileName
0x18002ccf7  mov     [rsp+810h+nSize], 12Eh; nSize
0x18002ccff  mov     r9, rdi; lpReturnedString
0x18002cd02  xor     r8d, r8d; lpDefault
0x18002cd05  lea     rdx, aOsGuid; "OS Guid"
0x18002cd0c  mov     rcx, rbx; lpAppName
0x18002cd0f  call    cs:__imp_GetPrivateProfileStringW
0x18002cd15  test    eax, eax
0x18002cd17  jz      short loc_18002CCDA
0x18002cd19  lea     rdx, [rsp+810h+pclsid.Data4]; pclsid
0x18002cd1e  mov     rcx, rdi; lpsz
0x18002cd21  call    cs:__imp_CLSIDFromString
0x18002cd27  test    eax, eax
0x18002cd29  jns     short loc_18002CD47
0x18002cd2b  mov     r9d, eax
0x18002cd2e  mov     r8, rdi
0x18002cd31  lea     rdx, aFailedToConver_2; "Failed to convert String {%s} to GUID. "...
0x18002cd38  mov     ecx, 1
0x18002cd3d  call    UnattendLogW
0x18002cd42  jmp     loc_18002CF7F
0x18002cd47  xor     r12d, r12d
0x18002cd4a  xor     r13d, r13d
0x18002cd4d  mov     dword ptr [rsp+810h+var_7E0+4], r12d
0x18002cd52  xor     edx, edx; Val
0x18002cd54  mov     r8d, 25Ch; Size
0x18002cd5a  mov     rcx, rdi; void *
0x18002cd5d  call    memset_0
0x18002cd62  lea     rdx, [rsp+810h+pclsid.Data4]
0x18002cd67  lea     rcx, aOsGuid_0; "OS Guid:"
0x18002cd6e  call    LogGuid
0x18002cd73  lea     rcx, [rsp+810h+pclsid.Data4]
0x18002cd78  call    WinReSetupRemoveWinRE
0x18002cd7d  test    eax, eax
0x18002cd7f  jnz     short loc_18002CD9B
0x18002cd81  call    cs:__imp_GetLastError
0x18002cd87  mov     r8d, eax
0x18002cd8a  lea     rdx, aFailedToCleanu; "failed to cleanup existing WinRE with e"...
0x18002cd91  lea     ecx, [r12+2]
0x18002cd96  call    UnattendLogW
0x18002cd9b  mov     ebx, 1
0x18002cda0  test    r14, r14
0x18002cda3  jz      loc_18002CFED
0x18002cda9  mov     rcx, r14; lpFileName
0x18002cdac  call    cs:__imp_GetFileAttributesW
0x18002cdb2  cmp     eax, 0FFFFFFFFh
0x18002cdb5  jz      loc_18002CFED
0x18002cdbb  mov     rdx, r14
0x18002cdbe  lea     rcx, [rsp+60h]
0x18002cdc3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18002cdc8  nop
0x18002cdc9  lea     rcx, [rsp+60h]
0x18002cdce  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002cdd3  mov     rcx, [rsp+70h]
0x18002cdd8  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x18002cdde  lea     rcx, cchOriginalDestLength
0x18002cde5  lea     rax, pszSrc; "\\"
0x18002cdec  cmovnz  rcx, rax
0x18002cdf0  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18002cdf5  mov     r8, rax
0x18002cdf8  mov     rdx, rcx
0x18002cdfb  lea     rcx, [rsp+60h]
0x18002ce00  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18002ce05  lea     rcx, aLocationTxt; "location.txt"
0x18002ce0c  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18002ce11  mov     r8, rax
0x18002ce14  lea     rdx, aLocationTxt; "location.txt"
0x18002ce1b  lea     rcx, [rsp+60h]
0x18002ce20  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18002ce25  lea     rcx, [rsp+60h]
0x18002ce2a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ce2f  mov     rcx, rax; lpFileName
0x18002ce32  call    cs:__imp_GetFileAttributesW
0x18002ce38  cmp     eax, 0FFFFFFFFh
0x18002ce3b  jz      loc_18002CFCA
0x18002ce41  lea     rcx, [rsp+60h]
0x18002ce46  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ce4b  mov     r8, rax
0x18002ce4e  lea     rdx, aCheckUndoInsta; "Check undo-Installtion info from %s"
0x18002ce55  xor     ecx, ecx
0x18002ce57  call    UnattendLogW
0x18002ce5c  lea     rcx, [rsp+60h]
0x18002ce61  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ce66  mov     [rsp+810h+lpFileName], rax; lpFileName
0x18002ce6b  mov     [rsp+810h+nSize], 12Eh; nSize
0x18002ce73  mov     r9, rdi; lpReturnedString
0x18002ce76  xor     r8d, r8d; lpDefault
0x18002ce79  lea     rdx, aNewPartitionOf; "New Partition offset"
0x18002ce80  lea     rcx, aWinreLocation; "WinRE Location"
0x18002ce87  call    cs:__imp_GetPrivateProfileStringW
0x18002ce8d  test    eax, eax
0x18002ce8f  jz      short loc_18002CEE3
0x18002ce91  mov     r12d, ebx
0x18002ce94  mov     rcx, rdi; String
0x18002ce97  call    cs:__imp__wtoi64
0x18002ce9d  mov     r14, rax
0x18002cea0  xor     edx, edx; Val
0x18002cea2  mov     r8d, 25Ch; Size
0x18002cea8  mov     rcx, rdi; void *
0x18002ceab  call    memset_0
0x18002ceb0  mov     r9, rsi
0x18002ceb3  mov     r8, r14
0x18002ceb6  lea     rdx, aFindNewWinrePa; "Find new WinRE partition offset %I64u w"...
0x18002cebd  xor     ecx, ecx
0x18002cebf  call    UnattendLogW
0x18002cec4  cmp     r14, rsi
0x18002cec7  jz      short loc_18002CEE3
0x18002cec9  jnb     loc_18002CF61
0x18002cecf  mov     r13d, ebx
0x18002ced2  lea     rdx, aWinrePartition_1; "WinRE partition is extended, restore Wi"...
0x18002ced9  xor     ecx, ecx
0x18002cedb  call    UnattendLogW
0x18002cee0  mov     rsi, r14
0x18002cee3  lea     rcx, [rsp+60h]
0x18002cee8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ceed  mov     [rsp+810h+lpFileName], rax; lpFileName
0x18002cef2  mov     [rsp+810h+nSize], 12Eh; nSize
0x18002cefa  mov     r9, rdi; lpReturnedString
0x18002cefd  xor     r8d, r8d; lpDefault
0x18002cf00  lea     rdx, aCurrentWinrePa_0; "Current WinRE partition offset"
0x18002cf07  lea     rcx, aWinreLocation; "WinRE Location"
0x18002cf0e  call    cs:__imp_GetPrivateProfileStringW
0x18002cf14  test    eax, eax
0x18002cf16  jz      short loc_18002CF49
0x18002cf18  mov     rcx, rdi; String
0x18002cf1b  call    cs:__imp__wtoi64
0x18002cf21  mov     r15, rax
0x18002cf24  xor     edx, edx; Val
0x18002cf26  mov     r8d, 25Ch; Size
0x18002cf2c  mov     rcx, rdi; void *
0x18002cf2f  call    memset_0
0x18002cf34  mov     r8, r15
0x18002cf37  lea     rdx, aCurrentPartiti; "Current partition offset of new OS is %"...
0x18002cf3e  xor     ecx, ecx
0x18002cf40  call    UnattendLogW
0x18002cf45  mov     dword ptr [rsp+810h+var_7E0+4], ebx
0x18002cf49  lea     rcx, [rsp+60h]
0x18002cf4e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002cf53  mov     rcx, rax; lpFileName
0x18002cf56  call    cs:__imp_DeleteFileW
0x18002cf5c  jmp     loc_18002CFE3
0x18002cf61  lea     rdx, aWinrePartition; "WinRE partition is resized, cannot rest"...
0x18002cf68  mov     ecx, ebx
0x18002cf6a  call    UnattendLogW
0x18002cf6f  nop
0x18002cf70  lea     rcx, [rsp+60h]
0x18002cf75  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002cf7a  mov     r15d, dword ptr [rsp+810h+var_7E0]
0x18002cf7f  call    cs:__imp_GetProcessHeap
0x18002cf85  mov     rcx, rax; hHeap
0x18002cf88  mov     r8, rdi; lpMem
0x18002cf8b  xor     edx, edx; dwFlags
0x18002cf8d  call    cs:__imp_HeapFree
0x18002cf93  nop
0x18002cf94  lea     rcx, [rbp+710h+var_780]
0x18002cf98  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002cf9d  mov     eax, r15d
0x18002cfa0  mov     rcx, [rbp+710h+var_40]
0x18002cfa7  xor     rcx, rsp; StackCookie
0x18002cfaa  call    __security_check_cookie
0x18002cfaf  mov     rbx, [rsp+810h+arg_10]
0x18002cfb7  add     rsp, 7E0h
0x18002cfbe  pop     r15
0x18002cfc0  pop     r14
0x18002cfc2  pop     r13
0x18002cfc4  pop     r12
0x18002cfc6  pop     rdi
0x18002cfc7  pop     rsi
0x18002cfc8  pop     rbp
0x18002cfc9  retn
  ... truncated ...
```
