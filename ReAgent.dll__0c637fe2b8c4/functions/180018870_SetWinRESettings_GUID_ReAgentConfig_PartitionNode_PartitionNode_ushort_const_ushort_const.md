# SetWinRESettings(_GUID *,ReAgentConfig *,PartitionNode *,PartitionNode *,ushort const *,ushort const *)

- ea: `0x180018870`
- end: `0x18001914d`
- name: `?SetWinRESettings@@YAKPEAU_GUID@@PEAVReAgentConfig@@PEAUPartitionNode@@2PEBG3@Z`
- size: `2269`
- prototype: `unsigned int __usercall@<eax>(struct _GUID *@<rcx>, struct ReAgentConfig *this@<rdx>, struct PartitionNode *@<r8>, struct PartitionNode *@<r9>, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800193e8`

## callees

- `0x1800059fc`
- `0x180006ed8`
- `0x18000c658`
- `0x18000fe58`
- `0x18001051c`
- `0x1800109d0`
- `0x1800109f8`
- `0x180011344`
- `0x180011974`
- `0x1800145f4`
- `0x180014754`
- `0x18001835c`
- `0x180018870`
- `0x18001e4c8`
- `0x18001fd7c`
- `0x180028e30`
- `0x1800295a0`
- `0x1800298cc`
- `0x180029f28`
- `0x180030f18`
- `0x180031a00`
- `0x18003211c`
- `0x180032564`
- `0x180034aa4`
- `0x1800356d4`
- `0x180035e88`
- `0x180039b38`
- `0x180039dd4`
- `0x18004d52c`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180018c6f`
- `KERNEL32!GetLastError` at `0x1800190fa`
- `KERNEL32!GetLastError` at `0x18001912a`
- `KERNEL32!GetLastError` at `0x180018c6f`
- `KERNEL32!GetLastError` at `0x1800190fa`
- `KERNEL32!GetLastError` at `0x18001912a`
- `KERNEL32!MoveFileExW` at `0x180018c61`
- `KERNEL32!MoveFileExW` at `0x180018c61`
- `KERNEL32!SetFileAttributesW` at `0x1800190f0`
- `KERNEL32!SetFileAttributesW` at `0x1800190f0`
- `KERNEL32!DeleteFileW` at `0x18001911c`
- `KERNEL32!DeleteFileW` at `0x18001911c`
- `ole32!CoTaskMemFree` at `0x180018a42`
- `ole32!CoTaskMemFree` at `0x180018a50`
- `ole32!CoTaskMemFree` at `0x180018a5e`
- `ole32!CoTaskMemFree` at `0x180018a6e`
- `ole32!CoTaskMemFree` at `0x180018a42`
- `ole32!CoTaskMemFree` at `0x180018a50`
- `ole32!CoTaskMemFree` at `0x180018a5e`
- `ole32!CoTaskMemFree` at `0x180018a6e`

## string_xrefs

- `0x180019050`: `failed to find main os config directory`
- `0x1800190a7`: `failed to add file to directory path`
- `0x18001894f`: `base\diagnosis\srt\reagent2\reagent\installex.cpp`
- `0x180018a10`: `base\diagnosis\srt\reagent2\reagent\installex.cpp`
- `0x180018ac8`: `base\diagnosis\srt\reagent2\reagent\installex.cpp`
- `0x180018f9b`: `base\diagnosis\srt\reagent2\reagent\installex.cpp`
- `0x180019039`: `base\diagnosis\srt\reagent2\reagent\installex.cpp`
- `0x180019090`: `base\diagnosis\srt\reagent2\reagent\installex.cpp`
- `0x18001899a`: `Failed to get config path`
- `0x180018e8e`: `Failed to update config file`
- `0x180018ef1`: `Failed to uninstall WinRE`
- `0x180018948`: `Failed to get config path from os guid`
- `0x1800189de`: `OEM partition, copying boot.sdi`
- `0x180018a09`: `winreCopyBootSdiOnly failed`
- `0x180018adf`: `failed to copy target dir string`
- `0x180018b12`: `Copying WinRE from %s to staging location on %s`
- `0x180018b56`: `winreCopyWIM failed`
- `0x180018b9b`: `Failed to create BCD recovery entry %d`
- `0x180018bce`: `BCD could not be set, Copying Winre.wim from %s to staging location`
- `0x180018ec6`: `BCD could not be set, Copying Winre.wim from %s to staging location`
- `0x180018bfc`: `Failed to copy string %s `
- `0x180018c7f`: `Failed to move winre.wim back %s %s error:%d`
- `0x180018c9b`: `WinRE created BCD entry: `
- `0x180018cda`: `winre RenameWimDir failed`
- `0x180018ce6`: `Moved Winre and boot.sdi from staging location to target`
- `0x180018cf9`: `Updating reagent.xml`
- `0x180018d10`: `Set WinRE location path to: %s`
- `0x180018d6b`: `Set scheduled operation: WinReNoOperation`
- `0x180018e43`: `Set install state to: enabled`
- `0x180018f20`: `Creating backup of reagent.xml`
- `0x180018f40`: `Created backup of reagent.xml`
- `0x180018f53`: `Configuring the WinRE validation task.`
- `0x180018f69`: `Completed the WinRE validation task.`
- `0x180018fb2`: `Failed to get customization file path`
- `0x180018ff9`: `Created backup of customization file`
- `0x18001910c`: `SetFileAttributes failed. Error: 0X%08X`
- `0x18001913c`: `Cannot delete %s. Error: 0X%08X`
- `0x180018f7e`: `ReCustomization.xml`
- `0x180018fe5`: `ReCustomization.xml`
- `0x180018f2e`: `ReAgent.xml`

## pseudocode

```c
__int64 __fastcall SetWinRESettings(
        struct _GUID *a1,
        struct ReAgentConfig *this,
        struct PartitionNode *a3,
        struct PartitionNode *a4,
        unsigned __int16 *a5,
        const unsigned __int16 *a6)
{
  unsigned __int16 *v9; // r12
  __int64 v10; // r8
  unsigned int ConfigFilePathFromOsGuid; // ebx
  const wchar_t *v12; // r8
  unsigned __int16 *v13; // r13
  unsigned __int16 *v14; // rsi
  const wchar_t *v15; // r8
  unsigned int RecoveryEntryInBCD; // eax
  unsigned __int64 v18; // r11
  ReAgentXMLParser *v19; // rcx
  int OsVersion; // eax
  unsigned __int16 *v21; // rbx
  ReAgentXMLParser *v22; // rcx
  int v23; // eax
  struct ReAgentConfigInfo *v24; // r15
  int v25; // ebx
  unsigned int v26; // eax
  ReAgentXMLParser *v27; // rdx
  DWORD LastError; // eax
  DWORD v29; // eax
  unsigned __int16 *v30; // [rsp+20h] [rbp-E0h]
  WCHAR *v31; // [rsp+28h] [rbp-D8h]
  int v32; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v33; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v34; // [rsp+48h] [rbp-B8h]
  unsigned __int16 *v35; // [rsp+50h] [rbp-B0h] BYREF
  struct ReAgentConfigInfo *ConfigInfo; // [rsp+58h] [rbp-A8h]
  LPVOID v37; // [rsp+60h] [rbp-A0h]
  struct PartitionNode *v38; // [rsp+68h] [rbp-98h]
  LPVOID pv; // [rsp+70h] [rbp-90h] BYREF
  __int128 v40; // [rsp+78h] [rbp-88h] BYREF
  WCHAR NewFileName[304]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR ExistingFileName[304]; // [rsp+2F0h] [rbp+1F0h] BYREF
  unsigned __int16 v43[304]; // [rsp+550h] [rbp+450h] BYREF

  v38 = a3;
  v40 = 0;
  memset_0(ExistingFileName, 0, 0x25Cu);
  memset_0(v43, 0, 0x25Cu);
  pv = 0;
  v33 = 0;
  v9 = 0;
  v37 = 0;
  v35 = 0;
  v34 = 0;
  UnattendLogW(0, L"Enter SetWinRESettings");
  ConfigInfo = ReAgentXMLParser::GetConfigInfo(this);
  if ( a1 )
  {
    ConfigFilePathFromOsGuid = winreGetConfigFilePathFromOsGuid(a1);
    if ( ConfigFilePathFromOsGuid )
    {
      v32 = 624;
      v12 = L"Failed to get config path from os guid";
LABEL_4:
      UnattendLogW(
        2,
        L"SetWinRESettings %s (0x%x) in file %S line %d",
        v12,
        ConfigFilePathFromOsGuid,
        "base\\diagnosis\\srt\\reagent2\\reagent\\installex.cpp",
        v32);
      v13 = (unsigned __int16 *)pv;
      v14 = 0;
      goto LABEL_14;
    }
  }
  else
  {
    ConfigFilePathFromOsGuid = winreGetConfigFilePathFromWinDir(0, 0, v10, &pv);
    if ( ConfigFilePathFromOsGuid )
    {
      v32 = 633;
      v12 = L"Failed to get config path";
      goto LABEL_4;
    }
  }
  v13 = (unsigned __int16 *)pv;
  LODWORD(pv) = WinReIsWimBootEnabledInternal((LPCWSTR)pv);
  if ( (unsigned int)winreIsSamePartition(v38, a4) && (LODWORD(v9) = ReAgentXMLParser::IsOemDir(this), (_DWORD)v9) )
  {
    UnattendLogW(0, L"OEM partition, copying boot.sdi");
    ConfigFilePathFromOsGuid = winreCopyBootSdiOnly(a1, a5);
    if ( ConfigFilePathFromOsGuid )
    {
      LODWORD(v31) = 654;
      v15 = L"winreCopyBootSdiOnly failed";
LABEL_11:
      UnattendLogW(
        2,
        L"SetWinRESettings %s (0x%x) in file %S line %d",
        v15,
        ConfigFilePathFromOsGuid,
        "base\\diagnosis\\srt\\reagent2\\reagent\\installex.cpp",
        v31);
LABEL_12:
      v14 = 0;
LABEL_13:
      v9 = 0;
      goto LABEL_14;
    }
    ConfigFilePathFromOsGuid = StringCchCopyW(v43, 0x12Eu, L"\\Recovery\\WindowsRE");
    if ( (ConfigFilePathFromOsGuid & 0x80000000) != 0 )
    {
      UnattendLogW(
        2,
        L"SetWinRESettings %s (0x%x) in file %S line %d",
        L"failed to copy target dir string",
        ConfigFilePathFromOsGuid,
        "base\\diagnosis\\srt\\reagent2\\reagent\\installex.cpp",
        657);
      ConfigFilePathFromOsGuid = (unsigned __int16)ConfigFilePathFromOsGuid;
      goto LABEL_12;
    }
    UnattendLogW(0, L"boot.sdi copied");
  }
  else
  {
    UnattendLogW(0, L"Copying WinRE from %s to staging location on %s", a5, (char *)a4 + 656);
    ConfigFilePathFromOsGuid = winreCopyWIM(a1, (__int64)a4, (__int64)a5, a6 == 0, ExistingFileName, v31);
    if ( ConfigFilePathFromOsGuid )
    {
      LODWORD(v31) = 669;
      v15 = L"winreCopyWIM failed";
      goto LABEL_11;
    }
    UnattendLogW(0, L"Copied WinRE to staging location");
  }
  UnattendLogW(0, L"Creating BCD entry");
  RecoveryEntryInBCD = winreCreateRecoveryEntryInBCD(a4);
  ConfigFilePathFromOsGuid = RecoveryEntryInBCD;
  if ( RecoveryEntryInBCD )
  {
    UnattendLogW(0, L"Failed to create BCD recovery entry %d", RecoveryEntryInBCD);
    if ( ExistingFileName[0] )
    {
      memset_0(NewFileName, 0, 0x25Cu);
      UnattendLogW(0, L"BCD could not be set, Copying Winre.wim from %s to staging location", (char *)ConfigInfo + 16);
      if ( StringCchCopyW(NewFileName, 0x12Eu, a5) >= 0 )
      {
        if ( StringCchCatW(NewFileName, v18, L"\\winre.wim") >= 0 )
        {
          UnattendLogW(0, L"Moving %s to %s", ExistingFileName, NewFileName);
          if ( !MoveFileExW(ExistingFileName, NewFileName, 2u) )
          {
            LODWORD(v30) = GetLastError();
            UnattendLogW(0, L"Failed to move winre.wim back %s %s error:%d", ExistingFileName, a5, v30);
          }
        }
        else
        {
          UnattendLogW(0, L"Failed to concatenate string");
        }
      }
      else
      {
        UnattendLogW(0, L"Failed to copy string %s ", a5);
      }
    }
    goto LABEL_12;
  }
  LogGuid(L"WinRE created BCD entry: ", &v40);
  if ( !(_DWORD)v9 )
  {
    UnattendLogW(0, L"Moving Winre and boot.sdi from staging location to target");
    ConfigFilePathFromOsGuid = winreRenameWIMDir(a4, v43);
    if ( ConfigFilePathFromOsGuid )
    {
      LODWORD(v31) = 723;
      v15 = L"winre RenameWimDir failed";
      goto LABEL_11;
    }
    UnattendLogW(0, L"Moved Winre and boot.sdi from staging location to target");
  }
  UnattendLogW(0, L"Updating reagent.xml");
  UnattendLogW(0, L"Set WinRE location path to: %s", v43);
  ConfigFilePathFromOsGuid = ReAgentConfig::SetWinreLocationPath(
                               this,
                               *((_QWORD *)a4 + 158),
                               (struct _GUID *)((char *)a4 + 36),
                               *((_DWORD *)a4 + 8),
                               v43);
  if ( ConfigFilePathFromOsGuid )
  {
    LODWORD(v31) = 738;
    v15 = L"Failed to set WinRE location";
    goto LABEL_11;
  }
  UnattendLogW(0, L"Set recovery guid");
  *(_OWORD *)*((_QWORD *)this + 8) = v40;
  UnattendLogW(0, L"Set scheduled operation: WinReNoOperation");
  *(_DWORD *)(*((_QWORD *)this + 8) + 5612LL) = 4;
  ConfigFilePathFromOsGuid = ReAgentXMLParser::CopyPathInfo(
                               v19,
                               (unsigned __int16 *)&qword_1800709D0,
                               (unsigned __int16 *)(*((_QWORD *)this + 8) + 5616LL));
  if ( ConfigFilePathFromOsGuid )
  {
    LODWORD(v31) = 746;
    v15 = L"Failed to set operation param";
    goto LABEL_11;
  }
  OsVersion = winreGetOsVersion(&v35);
  v21 = v35;
  v37 = v35;
  if ( !OsVersion )
  {
    UnattendLogW(0, L"Set OS build version: %s", v35);
    ReAgentXMLParser::CopyPathInfo(v22, v21, (unsigned __int16 *)(*((_QWORD *)this + 8) + 4976LL));
  }
  if ( (unsigned int)winreIsServerSku() )
  {
    UnattendLogW(0, L"Server SKU detected");
    v23 = 1;
  }
  else
  {
    v23 = 0;
  }
  v24 = ConfigInfo;
  *((_DWORD *)ConfigInfo + 1402) = v23;
  v25 = (int)pv;
  UnattendLogW(0, L"Set Wimboot state: %d", (unsigned int)pv);
  *(_DWORD *)(*((_QWORD *)this + 8) + 7472LL) = v25 != 0;
  UnattendLogW(0, L"Set install state to: enabled");
  *(_DWORD *)(*((_QWORD *)this + 8) + 5588LL) = 1;
  *(_DWORD *)(*((_QWORD *)this + 8) + 5604LL) = 0;
  ConfigFilePathFromOsGuid = ReAgentXMLParser::Update(this);
  if ( ConfigFilePathFromOsGuid )
  {
    LODWORD(v31) = 774;
    v15 = L"Failed to update config file";
    goto LABEL_11;
  }
  UnattendLogW(0, L"Setting the recovery sequence for the target OS.");
  if ( (unsigned int)winreSetRecoverySequence(&v40, *((unsigned int *)v24 + 1556), a1) )
  {
    UnattendLogW(0, L"BCD could not be set, Copying Winre.wim from %s to staging location", (char *)v24 + 16);
    ConfigFilePathFromOsGuid = winreUnInstallInternal(a1, 0, 0);
    if ( !ConfigFilePathFromOsGuid )
      goto LABEL_12;
    LODWORD(v31) = 792;
    v15 = L"Failed to uninstall WinRE";
    goto LABEL_11;
  }
  v26 = winreRegisterInRecoveryBCD(a4, a1);
  if ( v26 )
    UnattendLogW(2, L"Failed to register WinRE in recovery BCD, recovery button may be unavailable: 0x%x", v26);
  UnattendLogW(0, L"Creating backup of reagent.xml");
  winreBackupRecoveryFile(v13, this, L"ReAgent.xml");
  UnattendLogW(0, L"Created backup of reagent.xml");
  if ( !a1 )
  {
    UnattendLogW(0, L"Configuring the WinRE validation task.");
    winreConfigureValidationTask(1);
    UnattendLogW(0, L"Completed the WinRE validation task.");
  }
  ConfigFilePathFromOsGuid = winreGetRecoveryFilePath(0, 0, 1, L"ReCustomization.xml", &v33);
  if ( ConfigFilePathFromOsGuid )
  {
    LODWORD(v31) = 827;
    UnattendLogW(
      2,
      L"SetWinRESettings %s (0x%x) in file %S line %d",
      L"Failed to get customization file path",
      ConfigFilePathFromOsGuid,
      "base\\diagnosis\\srt\\reagent2\\reagent\\installex.cpp",
      v31);
    v14 = v33;
    goto LABEL_13;
  }
  UnattendLogW(0, L"Creating backup of customization file");
  v27 = this;
  v14 = v33;
  winreBackupRecoveryFile(v33, v27, L"ReCustomization.xml");
  UnattendLogW(0, L"Created backup of customization file");
  if ( !*((_WORD *)v24 + 628) )
    goto LABEL_13;
  memset_0(NewFileName, 0, 0x25Cu);
  ConfigFilePathFromOsGuid = winreFindMainOsConfigDir(a1);
  if ( ConfigFilePathFromOsGuid )
  {
    LODWORD(v31) = 844;
    UnattendLogW(
      2,
      L"SetWinRESettings %s (0x%x) in file %S line %d",
      L"failed to find main os config directory",
      ConfigFilePathFromOsGuid,
      "base\\diagnosis\\srt\\reagent2\\reagent\\installex.cpp",
      v31);
    v9 = v34;
  }
  else
  {
    v9 = v34;
    ConfigFilePathFromOsGuid = winreAddFileToDirPath(v34, L"Winre.wim", NewFileName);
    if ( ConfigFilePathFromOsGuid )
    {
      LODWORD(v31) = 848;
      UnattendLogW(
        2,
        L"SetWinRESettings %s (0x%x) in file %S line %d",
        L"failed to add file to directory path",
        ConfigFilePathFromOsGuid,
        "base\\diagnosis\\srt\\reagent2\\reagent\\installex.cpp",
        v31);
    }
    else if ( !Utils::DoesPathExist(NewFileName) )
    {
      UnattendLogW(0, L"Deleting file %s", NewFileName);
      if ( !SetFileAttributesW(NewFileName, 0x80u) )
      {
        LastError = GetLastError();
        UnattendLogW(2, L"SetFileAttributes failed. Error: 0X%08X", NewFileName, LastError);
      }
      if ( !DeleteFileW(NewFileName) )
      {
        v29 = GetLastError();
        UnattendLogW(2, L"Cannot delete %s. Error: 0X%08X", NewFileName, v29);
      }
    }
  }
LABEL_14:
  if ( v13 )
    CoTaskMemFree(v13);
  if ( v14 )
    CoTaskMemFree(v14);
  if ( v9 )
    CoTaskMemFree(v9);
  if ( v37 )
    CoTaskMemFree(v37);
  UnattendLogW(0, L"SetWinRESettings return with error code 0x%x", ConfigFilePathFromOsGuid);
  return ConfigFilePathFromOsGuid;
}

```

## disassembly

```asm
0x180018870  push    rbp
0x180018872  push    rbx
0x180018873  push    rsi
0x180018874  push    rdi
0x180018875  push    r12
0x180018877  push    r13
0x180018879  push    r14
0x18001887b  push    r15
0x18001887d  lea     rbp, [rsp-6C8h]
0x180018885  sub     rsp, 7C8h
0x18001888c  mov     rax, cs:__security_cookie
0x180018893  xor     rax, rsp
0x180018896  mov     [rbp+700h+var_50], rax
0x18001889d  mov     r15, [rbp+700h+arg_20]
0x1800188a4  mov     rsi, rdx
0x1800188a7  mov     [rsp+800h+var_798], r8
0x1800188ac  mov     rdi, rcx
0x1800188af  xorps   xmm0, xmm0
0x1800188b2  lea     rcx, [rbp+700h+ExistingFileName]; void *
0x1800188b9  mov     ebx, 25Ch
0x1800188be  xor     edx, edx; Val
0x1800188c0  mov     r8d, ebx; Size
0x1800188c3  mov     r14, r9
0x1800188c6  movups  [rsp+800h+var_788], xmm0
0x1800188cb  call    memset_0
0x1800188d0  mov     r8d, ebx; Size
0x1800188d3  lea     rcx, [rbp+700h+var_2B0]; void *
0x1800188da  xor     edx, edx; Val
0x1800188dc  call    memset_0
0x1800188e1  xor     r13d, r13d
0x1800188e4  lea     rdx, aEnterSetwinres; "Enter SetWinRESettings"
0x1800188eb  mov     eax, r13d
0x1800188ee  mov     [rsp+800h+pv], r13
0x1800188f3  xor     ecx, ecx
0x1800188f5  mov     [rsp+800h+var_7D0], rax
0x1800188fa  mov     [rsp+800h+var_7C0], rax
0x1800188ff  mov     r12d, r13d
0x180018902  mov     [rsp+800h+var_7A0], rax
0x180018907  mov     [rsp+800h+var_7B0], rax
0x18001890c  mov     [rsp+800h+var_7C8], r13
0x180018911  mov     [rsp+800h+var_7B8], r13
0x180018916  call    UnattendLogW
0x18001891b  mov     rcx, rsi; this
0x18001891e  call    ?GetConfigInfo@ReAgentXMLParser@@QEAAPEAUReAgentConfigInfo@@XZ; ReAgentXMLParser::GetConfigInfo(void)
0x180018923  mov     [rsp+800h+var_7A8], rax
0x180018928  test    rdi, rdi
0x18001892b  jz      short loc_18001897E
0x18001892d  lea     r8, [rsp+800h+pv]
0x180018932  mov     rcx, rdi
0x180018935  call    winreGetConfigFilePathFromOsGuid
0x18001893a  mov     ebx, eax
0x18001893c  test    eax, eax
0x18001893e  jz      short loc_1800189A3
0x180018940  mov     dword ptr [rsp+800h+var_7D8], 270h
0x180018948  lea     r8, aFailedToGetCon_2; "Failed to get config path from os guid"
0x18001894f  lea     rax, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180018956  mov     r9d, ebx
0x180018959  lea     rdx, aSetwinresettin_0; "SetWinRESettings %s (0x%x) in file %S l"...
0x180018960  mov     [rsp+800h+var_7E0], rax
0x180018965  mov     ecx, 2
0x18001896a  call    UnattendLogW
0x18001896f  mov     r13, [rsp+800h+pv]
0x180018974  mov     rsi, [rsp+800h+var_7D0]
0x180018979  jmp     loc_180018A3A
0x18001897e  lea     r9, [rsp+800h+pv]
0x180018983  xor     edx, edx
0x180018985  xor     ecx, ecx
0x180018987  call    winreGetConfigFilePathFromWinDir
0x18001898c  mov     ebx, eax
0x18001898e  test    eax, eax
0x180018990  jz      short loc_1800189A3
0x180018992  mov     dword ptr [rsp+800h+var_7D8], 279h
0x18001899a  lea     r8, aFailedToGetCon_1; "Failed to get config path"
0x1800189a1  jmp     short loc_18001894F
0x1800189a3  mov     r13, [rsp+800h+pv]
0x1800189a8  mov     rcx, r13; lpFileName
0x1800189ab  call    ?WinReIsWimBootEnabledInternal@@YAHPEAG@Z; WinReIsWimBootEnabledInternal(ushort *)
0x1800189b0  mov     rcx, [rsp+800h+var_798]
0x1800189b5  mov     rdx, r14
0x1800189b8  mov     dword ptr [rsp+800h+pv], eax
0x1800189bc  call    winreIsSamePartition
0x1800189c1  xor     ebx, ebx
0x1800189c3  test    eax, eax
0x1800189c5  jz      loc_180018B08
0x1800189cb  mov     rcx, rsi; this
0x1800189ce  call    ?IsOemDir@ReAgentXMLParser@@QEAAHXZ; ReAgentXMLParser::IsOemDir(void)
0x1800189d3  mov     r12d, eax
0x1800189d6  test    eax, eax
0x1800189d8  jz      loc_180018B08
0x1800189de  lea     rdx, aOemPartitionCo; "OEM partition, copying boot.sdi"
0x1800189e5  xor     ecx, ecx
0x1800189e7  call    UnattendLogW
0x1800189ec  mov     rdx, r15
0x1800189ef  mov     rcx, rdi
0x1800189f2  call    winreCopyBootSdiOnly
0x1800189f7  mov     ebx, eax
0x1800189f9  test    eax, eax
0x1800189fb  jz      loc_180018AAA
0x180018a01  mov     dword ptr [rsp+800h+var_7D8], 28Eh
0x180018a09  lea     r8, aWinrecopyboots_1; "winreCopyBootSdiOnly failed"
0x180018a10  lea     rax, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180018a17  mov     r9d, ebx
0x180018a1a  lea     rdx, aSetwinresettin_0; "SetWinRESettings %s (0x%x) in file %S l"...
0x180018a21  mov     [rsp+800h+var_7E0], rax
0x180018a26  mov     ecx, 2
0x180018a2b  call    UnattendLogW
0x180018a30  mov     rsi, [rsp+800h+var_7D0]
0x180018a35  mov     r12, [rsp+800h+var_7C8]
0x180018a3a  test    r13, r13
0x180018a3d  jz      short loc_180018A48
0x180018a3f  mov     rcx, r13; pv
0x180018a42  call    cs:__imp_CoTaskMemFree
0x180018a48  test    rsi, rsi
0x180018a4b  jz      short loc_180018A56
0x180018a4d  mov     rcx, rsi; pv
0x180018a50  call    cs:__imp_CoTaskMemFree
0x180018a56  test    r12, r12
0x180018a59  jz      short loc_180018A64
0x180018a5b  mov     rcx, r12; pv
0x180018a5e  call    cs:__imp_CoTaskMemFree
0x180018a64  mov     rcx, [rsp+800h+var_7A0]; pv
0x180018a69  test    rcx, rcx
0x180018a6c  jz      short loc_180018A74
0x180018a6e  call    cs:__imp_CoTaskMemFree
0x180018a74  mov     r8d, ebx
0x180018a77  lea     rdx, aSetwinresettin; "SetWinRESettings return with error code"...
0x180018a7e  xor     ecx, ecx
0x180018a80  call    UnattendLogW
0x180018a85  mov     eax, ebx
0x180018a87  mov     rcx, [rbp+700h+var_50]
0x180018a8e  xor     rcx, rsp; StackCookie
0x180018a91  call    __security_check_cookie
0x180018a96  add     rsp, 7C8h
0x180018a9d  pop     r15
0x180018a9f  pop     r14
0x180018aa1  pop     r13
0x180018aa3  pop     r12
0x180018aa5  pop     rdi
0x180018aa6  pop     rsi
0x180018aa7  pop     rbx
0x180018aa8  pop     rbp
0x180018aa9  retn
0x180018aaa  lea     r8, aRecoveryWindow; "\\Recovery\\WindowsRE"
0x180018ab1  mov     edx, 12Eh; unsigned __int64
0x180018ab6  lea     rcx, [rbp+700h+var_2B0]; unsigned __int16 *
0x180018abd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018ac2  mov     ebx, eax
0x180018ac4  test    eax, eax
0x180018ac6  jns     short loc_180018AFF
0x180018ac8  lea     rax, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180018acf  mov     dword ptr [rsp+800h+var_7D8], 291h
0x180018ad7  mov     r9d, ebx
0x180018ada  mov     [rsp+800h+var_7E0], rax
0x180018adf  lea     r8, aFailedToCopyTa; "failed to copy target dir string"
0x180018ae6  mov     ecx, 2
0x180018aeb  lea     rdx, aSetwinresettin_0; "SetWinRESettings %s (0x%x) in file %S l"...
0x180018af2  call    UnattendLogW
0x180018af7  movzx   ebx, bx
0x180018afa  jmp     loc_180018A30
0x180018aff  lea     rdx, aBootSdiCopied; "boot.sdi copied"
0x180018b06  jmp     short loc_180018B69
0x180018b08  lea     r9, [r14+290h]
0x180018b0f  mov     r8, r15
0x180018b12  lea     rdx, aCopyingWinreFr; "Copying WinRE from %s to staging locati"...
0x180018b19  xor     ecx, ecx
0x180018b1b  call    UnattendLogW
0x180018b20  cmp     [rbp+700h+arg_28], rbx
0x180018b27  lea     rax, [rbp+700h+ExistingFileName]
0x180018b2e  mov     r9d, ebx
0x180018b31  mov     [rsp+800h+var_7E0], rax; unsigned __int16 *
0x180018b36  setz    r9b; int
0x180018b3a  mov     r8, r15; int
0x180018b3d  mov     rdx, r14; int
0x180018b40  mov     rcx, rdi; int
0x180018b43  call    winreCopyWIM
0x180018b48  mov     ebx, eax
0x180018b4a  test    eax, eax
0x180018b4c  jz      short loc_180018B62
0x180018b4e  mov     dword ptr [rsp+800h+var_7D8], 29Dh
0x180018b56  lea     r8, aWinrecopywimFa; "winreCopyWIM failed"
0x180018b5d  jmp     loc_180018A10
0x180018b62  lea     rdx, aCopiedWinreToS; "Copied WinRE to staging location"
0x180018b69  xor     ecx, ecx
0x180018b6b  call    UnattendLogW
0x180018b70  lea     rdx, aCreatingBcdEnt; "Creating BCD entry"
0x180018b77  xor     ecx, ecx
0x180018b79  call    UnattendLogW
0x180018b7e  mov     r8, rdi
0x180018b81  lea     rdx, [rsp+800h+var_788]
0x180018b86  mov     rcx, r14; struct PartitionNode *
0x180018b89  call    winreCreateRecoveryEntryInBCD
0x180018b8e  mov     ebx, eax
0x180018b90  test    eax, eax
0x180018b92  jz      loc_180018C96
0x180018b98  mov     r8d, eax
0x180018b9b  lea     rdx, aFailedToCreate_22; "Failed to create BCD recovery entry %d"
0x180018ba2  xor     ecx, ecx
0x180018ba4  call    UnattendLogW
0x180018ba9  xor     esi, esi
0x180018bab  cmp     [rbp+700h+ExistingFileName], si
0x180018bb2  jz      loc_180018A30
0x180018bb8  xor     edx, edx; Val
0x180018bba  lea     rcx, [rbp+700h+NewFileName]; void *
0x180018bbe  mov     r8d, 25Ch; Size
0x180018bc4  call    memset_0
0x180018bc9  mov     r8, [rsp+800h+var_7A8]
0x180018bce  lea     rdx, aBcdCouldNotBeS; "BCD could not be set, Copying Winre.wim"...
0x180018bd5  add     r8, 10h
0x180018bd9  xor     ecx, ecx
0x180018bdb  call    UnattendLogW
0x180018be0  mov     r11d, 12Eh
0x180018be6  lea     rcx, [rbp+700h+NewFileName]; unsigned __int16 *
0x180018bea  mov     edx, r11d; unsigned __int64
0x180018bed  mov     r8, r15; unsigned __int16 *
0x180018bf0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018bf5  test    eax, eax
0x180018bf7  jns     short loc_180018C0F
0x180018bf9  mov     r8, r15
0x180018bfc  lea     rdx, aFailedToCopySt_0; "Failed to copy string %s "
0x180018c03  xor     ecx, ecx
0x180018c05  call    UnattendLogW
0x180018c0a  jmp     loc_180018A30
0x180018c0f  lea     r8, aWinreWim_0; "\\winre.wim"
0x180018c16  mov     rdx, r11; unsigned __int64
0x180018c19  lea     rcx, [rbp+700h+NewFileName]; unsigned __int16 *
0x180018c1d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180018c22  xor     ecx, ecx
0x180018c24  test    eax, eax
0x180018c26  jns     short loc_180018C39
0x180018c28  lea     rdx, aFailedToConcat_5; "Failed to concatenate string"
0x180018c2f  call    UnattendLogW
0x180018c34  jmp     loc_180018A30
0x180018c39  lea     r9, [rbp+700h+NewFileName]
0x180018c3d  lea     r8, [rbp+700h+ExistingFileName]
0x180018c44  lea     rdx, aMovingSToS; "Moving %s to %s"
0x180018c4b  call    UnattendLogW
0x180018c50  mov     r8d, 2; dwFlags
0x180018c56  lea     rdx, [rbp+700h+NewFileName]; lpNewFileName
0x180018c5a  lea     rcx, [rbp+700h+ExistingFileName]; lpExistingFileName
0x180018c61  call    cs:__imp_MoveFileExW
0x180018c67  test    eax, eax
0x180018c69  jnz     loc_180018A30
0x180018c6f  call    cs:__imp_GetLastError
0x180018c75  mov     r9, r15
0x180018c78  lea     r8, [rbp+700h+ExistingFileName]
0x180018c7f  lea     rdx, aFailedToMoveWi; "Failed to move winre.wim back %s %s err"...
0x180018c86  mov     dword ptr [rsp+800h+var_7E0], eax
0x180018c8a  xor     ecx, ecx
0x180018c8c  call    UnattendLogW
0x180018c91  jmp     loc_180018A30
0x180018c96  lea     rdx, [rsp+800h+var_788]
0x180018c9b  lea     rcx, aWinreCreatedBc; "WinRE created BCD entry: "
0x180018ca2  call    LogGuid
0x180018ca7  test    r12d, r12d
0x180018caa  jnz     short loc_180018CF6
0x180018cac  lea     rdx, aMovingWinreAnd; "Moving Winre and boot.sdi from staging "...
0x180018cb3  xor     ecx, ecx
0x180018cb5  call    UnattendLogW
0x180018cba  lea     rdx, [rbp+700h+var_2B0]
0x180018cc1  mov     rcx, r14
0x180018cc4  call    winreRenameWIMDir
0x180018cc9  xor     r12d, r12d
0x180018ccc  mov     ebx, eax
0x180018cce  test    eax, eax
0x180018cd0  jz      short loc_180018CE6
0x180018cd2  mov     dword ptr [rsp+800h+var_7D8], 2D3h
0x180018cda  lea     r8, aWinreRenamewim; "winre RenameWimDir failed"
0x180018ce1  jmp     loc_180018A10
0x180018ce6  lea     rdx, aMovedWinreAndB; "Moved Winre and boot.sdi from staging l"...
0x180018ced  xor     ecx, ecx
0x180018cef  call    UnattendLogW
0x180018cf4  jmp     short loc_180018CF9
0x180018cf6  xor     r12d, r12d
0x180018cf9  lea     rdx, aUpdatingReagen; "Updating reagent.xml"
0x180018d00  xor     ecx, ecx
0x180018d02  call    UnattendLogW
0x180018d07  lea     r8, [rbp+700h+var_2B0]
0x180018d0e  xor     ecx, ecx
0x180018d10  lea     rdx, aSetWinreLocati; "Set WinRE location path to: %s"
0x180018d17  call    UnattendLogW
0x180018d1c  mov     r9d, [r14+20h]; unsigned int
0x180018d20  lea     rax, [rbp+700h+var_2B0]
0x180018d27  mov     rdx, [r14+4F0h]; unsigned __int64
0x180018d2e  lea     r8, [r14+24h]; struct _GUID *
0x180018d32  mov     rcx, rsi; this
0x180018d35  mov     [rsp+800h+var_7E0], rax; unsigned __int16 *
0x180018d3a  call    ?SetWinreLocationPath@ReAgentConfig@@QEAAK_KPEAU_GUID@@KPEAG@Z; ReAgentConfig::SetWinreLocationPath(unsigned __int64,_GUID *,ulong,ushort *)
0x180018d3f  mov     ebx, eax
0x180018d41  test    eax, eax
0x180018d43  jz      short loc_180018D59
0x180018d45  mov     dword ptr [rsp+800h+var_7D8], 2E2h
0x180018d4d  lea     r8, aFailedToSetWin; "Failed to set WinRE location"
0x180018d54  jmp     loc_180018A10
0x180018d59  lea     rdx, aSetRecoveryGui; "Set recovery guid"
0x180018d60  xor     ecx, ecx
0x180018d62  call    UnattendLogW
0x180018d67  mov     rax, [rsi+40h]
0x180018d6b  lea     rdx, aSetScheduledOp; "Set scheduled operation: WinReNoOperati"...
0x180018d72  movups  xmm0, [rsp+800h+var_788]
0x180018d77  xor     ecx, ecx
  ... truncated ...
```
