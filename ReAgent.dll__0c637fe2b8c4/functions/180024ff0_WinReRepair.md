# WinReRepair

- ea: `0x180024ff0`
- end: `0x18002554d`
- name: `WinReRepair`
- size: `1373`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update`

## callers

- `0x180025560`

## callees

- `0x1800055c8`
- `0x180005694`
- `0x1800059fc`
- `0x180008b94`
- `0x1800109d0`
- `0x180011974`
- `0x1800121b0`
- `0x180014754`
- `0x180018838`
- `0x1800193e8`
- `0x18001fd7c`
- `0x180024ff0`
- `0x180030fcc`
- `0x180032dc8`
- `0x18003479c`
- `0x1800367b8`
- `0x18003a778`
- `0x18003bfbc`
- `0x18003cbe8`
- `0x18003d7e8`
- `0x18004d3a0`
- `0x18004d52c`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002517e`
- `KERNEL32!GetLastError` at `0x1800252d0`
- `KERNEL32!GetLastError` at `0x18002517e`
- `KERNEL32!GetLastError` at `0x1800252d0`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180025174`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180025174`
- `KERNEL32!CreateFileW` at `0x1800252c4`
- `KERNEL32!CreateFileW` at `0x1800252c4`
- `KERNEL32!CloseHandle` at `0x1800252f3`
- `KERNEL32!CloseHandle` at `0x1800252f3`

## string_xrefs

- `0x1800251b7`: `failed to get config file path`
- `0x180025317`: `failed to init agent config`
- `0x180025090`: `SeRestorePrivilege`
- `0x1800251c0`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180025069`: `SeBackupPrivilege`
- `0x1800250a3`: `Enter WinReRepair`
- `0x1800250ce`: ` %lu OS loaders found in the BCD store, not attempting repair`
- `0x180025184`: `GetSystemWindowsDirectoryW failed, err 0x%x`
- `0x1800251ca`: `WinReRepair %s (0x%x) in file %S line %d`
- `0x180025213`: `Attempting to restore xml from the backup location`
- `0x180025238`: `Loading restored xml`
- `0x18002525a`: `Restored xml could not be parsed`
- `0x180025279`: `Attempting to recreate the XML`
- `0x1800252d9`: `CreateFile (%s) failed , 0x%x`
- `0x180025340`: `failed to reconstruct config xml`
- `0x180025349`: `Loading reconstructed xml`
- `0x180025391`: `WinRE Installed, verifying BCD state`
- `0x180025475`: `Repair needed, uninstalling winre`
- `0x1800254e0`: `Installing winre`
- `0x18002545f`: `WinRE state valid, no repair required`
- `0x180025533`: `Successfully repaired winre`
- `0x1800250ef`: `Repair failed`
- `0x180025101`: `Exit WinReRepair return value: %d, last error: 0x%x`

## pseudocode

```c
_BOOL8 WinReRepair()
{
  unsigned int ConfigFilePathFromWinDir; // ebx
  BOOL v1; // r15d
  __int64 v3; // r8
  DWORD v4; // eax
  const wchar_t *v5; // r8
  unsigned __int16 *v6; // rsi
  int v7; // edi
  int v8; // r14d
  HANDLE FileW; // rax
  DWORD LastError; // eax
  struct ReAgentConfigInfo *ConfigInfo; // r14
  __int64 v12; // rcx
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  int v14; // [rsp+60h] [rbp-A0h] BYREF
  int v15; // [rsp+64h] [rbp-9Ch] BYREF
  LPCWSTR lpFileName; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v17[3]; // [rsp+70h] [rbp-90h] BYREF
  int v18; // [rsp+88h] [rbp-78h]
  int v19; // [rsp+8Ch] [rbp-74h]
  __int128 v20; // [rsp+90h] [rbp-70h]
  __int128 v21; // [rsp+A0h] [rbp-60h]
  __int64 v22; // [rsp+B0h] [rbp-50h]
  int v23; // [rsp+B8h] [rbp-48h]
  WCHAR Buffer; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v25[606]; // [rsp+C2h] [rbp-3Eh] BYREF

  lpFileName = 0;
  v15 = 0;
  ConfigFilePathFromWinDir = 0;
  Buffer = 0;
  memset_0(v25, 0, 0x25Au);
  v14 = 0;
  v20 = 0;
  v21 = 0;
  v17[0] = &ReAgentConfig::`vftable';
  v17[1] = 0;
  v1 = 0;
  v17[2] = 0;
  v18 = 0;
  v19 = 2;
  v22 = 0;
  v23 = 0;
  winreSetPriviledge(L"SeBackupPrivilege");
  winreSetPriviledge(L"SeRestorePrivilege");
  UnattendInitializeLogEx2(0);
  UnattendLogW(0, L"Enter WinReRepair");
  winreCountOsLoaderEntries(&v15);
  if ( v15 != 1 )
  {
    UnattendLogW(0, L" %lu OS loaders found in the BCD store, not attempting repair");
    if ( !ReAgentError )
      ReAgentError = 38;
    goto LABEL_4;
  }
  RemoveWinReOperationSyncKey();
  if ( !ReAgentError )
    ReAgentError = 27;
  if ( GetSystemWindowsDirectoryW(&Buffer, 0x12Eu) )
  {
    ConfigFilePathFromWinDir = winreGetConfigFilePathFromWinDir(0, 0, v3, &lpFileName);
    if ( ConfigFilePathFromWinDir )
    {
      LODWORD(dwFlagsAndAttributes) = 2386;
      v5 = L"failed to get config file path";
LABEL_12:
      UnattendLogW(
        2,
        L"WinReRepair %s (0x%x) in file %S line %d",
        v5,
        ConfigFilePathFromWinDir,
        "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
        dwFlagsAndAttributes);
      goto LABEL_4;
    }
    v6 = (unsigned __int16 *)lpFileName;
    v7 = 0;
    if ( (unsigned int)ReAgentConfig::Init((ReAgentConfig *)v17, (unsigned __int16 *)lpFileName, 1) )
    {
      if ( !ReAgentError )
        ReAgentError = 4;
      v7 = 1;
      UnattendLogW(0, L"Attempting to restore xml from the backup location");
      winreRestoreBackupXML(&v14);
      v8 = v14;
      if ( !v14 )
        goto LABEL_20;
      UnattendLogW(0, L"Loading restored xml");
      if ( (unsigned int)ReAgentConfig::Init((ReAgentConfig *)v17, v6, 1) )
      {
        UnattendLogW(0, L"Restored xml could not be parsed");
        v8 = 0;
        v14 = 0;
      }
      if ( !v8 )
      {
LABEL_20:
        UnattendLogW(1, L"Attempting to recreate the XML");
        if ( Utils::DoesPathExist(v6) )
        {
          if ( !ReAgentError )
            ReAgentError = 1;
          FileW = CreateFileW(v6, 0x40000000u, 0, 0, 1u, 0x80u, 0);
          if ( FileW == (HANDLE)-1LL )
          {
            LastError = GetLastError();
            UnattendLogW(1, L"CreateFile (%s) failed , 0x%x", v6, LastError);
            goto LABEL_4;
          }
          CloseHandle(FileW);
        }
        ConfigFilePathFromWinDir = ReAgentConfig::Init((ReAgentConfig *)v17, v6, 0);
        if ( ConfigFilePathFromWinDir )
        {
          LODWORD(dwFlagsAndAttributes) = 2419;
LABEL_28:
          v5 = L"failed to init agent config";
          goto LABEL_12;
        }
        ConfigFilePathFromWinDir = winreReconstructConfigXML((ReAgentConfig *)v17);
        if ( ConfigFilePathFromWinDir )
        {
          LODWORD(dwFlagsAndAttributes) = 2420;
          v5 = L"failed to reconstruct config xml";
          goto LABEL_12;
        }
        UnattendLogW(0, L"Loading reconstructed xml");
        ConfigFilePathFromWinDir = ReAgentConfig::Init((ReAgentConfig *)v17, v6, 1);
        if ( ConfigFilePathFromWinDir )
        {
          LODWORD(dwFlagsAndAttributes) = 2422;
          goto LABEL_28;
        }
      }
    }
    ConfigInfo = ReAgentXMLParser::GetConfigInfo((ReAgentXMLParser *)v17);
    if ( *(_DWORD *)(v22 + 5588) )
    {
      UnattendLogW(0, L"WinRE Installed, verifying BCD state");
      winreVerifyWinReBcdState(v12, ConfigInfo, &v14);
      if ( !v14 )
        v7 = 1;
      UnattendLogW(0, L"Verifying WinRE files");
      winreVerifyWinReFiles(ConfigInfo, &v14);
      if ( v14 )
      {
LABEL_44:
        winreCopyWIMBackFromTempStaging(ConfigInfo);
        if ( v14 || v7 )
        {
          UnattendLogW(0, L"Repair needed, uninstalling winre");
          *(_DWORD *)(v22 + 5588) = 1;
          *(_DWORD *)(v22 + 5604) = 0;
          ReAgentXMLParser::Update((ReAgentXMLParser *)v17);
          winreUnInstallInternal(0, 1, 1);
          ReAgentConfig::Init((ReAgentConfig *)v17, v6, 1);
          ReAgentXMLParser::GetConfigInfo((ReAgentXMLParser *)v17);
          ReAgentConfig::SetInstallState((ReAgentConfig *)v17, 0);
          ReAgentXMLParser::Update((ReAgentXMLParser *)v17);
          UnattendLogW(0, L"Installing winre");
          ConfigFilePathFromWinDir = WinReInstallOnTargetOSInternal(0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0);
          v1 = ConfigFilePathFromWinDir == 0;
          if ( ConfigFilePathFromWinDir )
            goto LABEL_4;
        }
        else
        {
          UnattendLogW(0, L"WinRE state valid, no repair required");
          v1 = 1;
        }
        ReAgentError = 0;
        UnattendLogW(0, L"Successfully repaired winre");
        goto LABEL_5;
      }
    }
    else
    {
      UnattendLogW(0, L"WinRE Disabled, verifying state consistency");
      v14 = 0;
      if ( *((_DWORD *)ConfigInfo + 1397) )
      {
        UnattendLogW(0, L"WinRE enabled");
      }
      else
      {
        if ( !*((_WORD *)ConfigInfo + 628)
          || Utils::DoesFileExist((const unsigned __int16 *)ConfigInfo + 628, L"boot.sdi") )
        {
          v14 = 1;
          goto LABEL_44;
        }
        UnattendLogW(0, L"boot.sdi found at %s\\%s", (char *)ConfigInfo + 1256, L"boot.sdi");
      }
    }
    v7 = 1;
    goto LABEL_44;
  }
  v4 = GetLastError();
  UnattendLogW(1, L"GetSystemWindowsDirectoryW failed, err 0x%x", v4);
LABEL_4:
  UnattendLogW(1, L"Repair failed");
LABEL_5:
  UnattendLogW(0, L"Exit WinReRepair return value: %d, last error: 0x%x", v1, ConfigFilePathFromWinDir);
  UnattendFinalizeLog();
  v17[0] = &ReAgentConfig::`vftable';
  ReAgentXMLParser::~ReAgentXMLParser((ReAgentXMLParser *)v17);
  return v1;
}

```

## disassembly

```asm
0x180024ff0  push    rbp
0x180024ff2  push    rbx
0x180024ff3  push    rsi
0x180024ff4  push    rdi
0x180024ff5  push    r12
0x180024ff7  push    r13
0x180024ff9  push    r14
0x180024ffb  push    r15
0x180024ffd  lea     rbp, [rsp-238h]
0x180025005  sub     rsp, 338h
0x18002500c  mov     rax, cs:__security_cookie
0x180025013  xor     rax, rsp
0x180025016  mov     [rbp+270h+var_50], rax
0x18002501d  xor     r12d, r12d
0x180025020  lea     rcx, [rbp+270h+var_2AE]; void *
0x180025024  xor     edx, edx; Val
0x180025026  mov     [rsp+370h+lpFileName], r12
0x18002502b  mov     r8d, 25Ah; Size
0x180025031  mov     [rsp+370h+var_30C], r12d
0x180025036  mov     ebx, r12d
0x180025039  mov     [rbp+270h+Buffer], r12w
0x18002503e  call    memset_0
0x180025043  xorps   xmm0, xmm0
0x180025046  mov     [rsp+370h+var_310], r12d
0x18002504b  xorps   xmm1, xmm1
0x18002504e  movdqa  [rbp+270h+var_2E0], xmm0
0x180025053  lea     rax, ??_7ReAgentConfig@@6B@; const ReAgentConfig::`vftable'
0x18002505a  movdqa  [rbp+270h+var_2D0], xmm1
0x18002505f  lea     edi, [r12+2]
0x180025064  mov     [rsp+370h+var_300], rax
0x180025069  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x180025070  mov     [rsp+370h+var_2F8], r12
0x180025075  mov     r15d, r12d
0x180025078  mov     [rbp+270h+var_2F0], r12
0x18002507c  mov     [rbp+270h+var_2E8], r12d
0x180025080  mov     [rbp+270h+var_2E4], edi
0x180025083  mov     [rbp+270h+var_2C0], r12
0x180025087  mov     [rbp+270h+var_2B8], r12d
0x18002508b  call    winreSetPriviledge
0x180025090  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x180025097  call    winreSetPriviledge
0x18002509c  xor     ecx, ecx
0x18002509e  call    UnattendInitializeLogEx2
0x1800250a3  lea     rdx, aEnterWinrerepa_0; "Enter WinReRepair"
0x1800250aa  xor     ecx, ecx
0x1800250ac  call    UnattendLogW
0x1800250b1  lea     rcx, [rsp+370h+var_30C]
0x1800250b6  call    winreCountOsLoaderEntries
0x1800250bb  mov     r8d, [rsp+370h+var_30C]
0x1800250c0  lea     r13d, [r12+1]
0x1800250c5  cmp     r8d, r13d
0x1800250c8  jz      loc_180025153
0x1800250ce  lea     rdx, aLuOsLoadersFou; " %lu OS loaders found in the BCD store,"...
0x1800250d5  xor     ecx, ecx
0x1800250d7  call    UnattendLogW
0x1800250dc  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, r12d; _ReAgentErrorCodes ReAgentError
0x1800250e3  jnz     short loc_1800250EF
0x1800250e5  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 26h ; '&'; _ReAgentErrorCodes ReAgentError
0x1800250ef  lea     rdx, aRepairFailed; "Repair failed"
0x1800250f6  mov     ecx, r13d
0x1800250f9  call    UnattendLogW
0x1800250fe  mov     r9d, ebx
0x180025101  lea     rdx, aExitWinrerepai_0; "Exit WinReRepair return value: %d, last"...
0x180025108  mov     r8d, r15d
0x18002510b  xor     ecx, ecx
0x18002510d  call    UnattendLogW
0x180025112  call    UnattendFinalizeLog
0x180025117  lea     rax, ??_7ReAgentConfig@@6B@; const ReAgentConfig::`vftable'
0x18002511e  lea     rcx, [rsp+370h+var_300]; this
0x180025123  mov     [rsp+370h+var_300], rax
0x180025128  call    ??1ReAgentXMLParser@@UEAA@XZ; ReAgentXMLParser::~ReAgentXMLParser(void)
0x18002512d  mov     eax, r15d
0x180025130  mov     rcx, [rbp+270h+var_50]
0x180025137  xor     rcx, rsp; StackCookie
0x18002513a  call    __security_check_cookie
0x18002513f  add     rsp, 338h
0x180025146  pop     r15
0x180025148  pop     r14
0x18002514a  pop     r13
0x18002514c  pop     r12
0x18002514e  pop     rdi
0x18002514f  pop     rsi
0x180025150  pop     rbx
0x180025151  pop     rbp
0x180025152  retn
0x180025153  call    RemoveWinReOperationSyncKey
0x180025158  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, r12d; _ReAgentErrorCodes ReAgentError
0x18002515f  jnz     short loc_18002516B
0x180025161  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 1Bh; _ReAgentErrorCodes ReAgentError
0x18002516b  mov     edx, 12Eh; uSize
0x180025170  lea     rcx, [rbp+270h+Buffer]; lpBuffer
0x180025174  call    cs:__imp_GetSystemWindowsDirectoryW
0x18002517a  test    eax, eax
0x18002517c  jnz     short loc_18002519B
0x18002517e  call    cs:__imp_GetLastError
0x180025184  lea     rdx, aGetsystemwindo; "GetSystemWindowsDirectoryW failed, err "...
0x18002518b  mov     ecx, r13d
0x18002518e  mov     r8d, eax
0x180025191  call    UnattendLogW
0x180025196  jmp     loc_1800250EF
0x18002519b  lea     r9, [rsp+370h+lpFileName]
0x1800251a0  xor     edx, edx
0x1800251a2  xor     ecx, ecx
0x1800251a4  call    winreGetConfigFilePathFromWinDir
0x1800251a9  mov     ebx, eax
0x1800251ab  test    eax, eax
0x1800251ad  jz      short loc_1800251E0
0x1800251af  mov     dword ptr [rsp+370h+dwFlagsAndAttributes], 952h
0x1800251b7  lea     r8, aFailedToGetCon_3; "failed to get config file path"
0x1800251be  mov     ecx, edi
0x1800251c0  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x1800251c7  mov     r9d, ebx
0x1800251ca  lea     rdx, aWinrerepairS0x; "WinReRepair %s (0x%x) in file %S line %"...
0x1800251d1  mov     qword ptr [rsp+370h+dwCreationDisposition], rax
0x1800251d6  call    UnattendLogW
0x1800251db  jmp     loc_1800250EF
0x1800251e0  mov     rsi, [rsp+370h+lpFileName]
0x1800251e5  lea     rcx, [rsp+370h+var_300]; this
0x1800251ea  mov     rdx, rsi; unsigned __int16 *
0x1800251ed  mov     r8d, r13d; int
0x1800251f0  mov     edi, r12d
0x1800251f3  call    ?Init@ReAgentConfig@@UEAAKPEAGH@Z; ReAgentConfig::Init(ushort *,int)
0x1800251f8  test    eax, eax
0x1800251fa  jz      loc_180025377
0x180025200  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, r12d; _ReAgentErrorCodes ReAgentError
0x180025207  jnz     short loc_180025213
0x180025209  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 4; _ReAgentErrorCodes ReAgentError
0x180025213  lea     rdx, aAttemptingToRe_0; "Attempting to restore xml from the back"...
0x18002521a  xor     ecx, ecx
0x18002521c  mov     edi, r13d
0x18002521f  call    UnattendLogW
0x180025224  lea     rcx, [rsp+370h+var_310]
0x180025229  call    winreRestoreBackupXML
0x18002522e  mov     r14d, [rsp+370h+var_310]
0x180025233  test    r14d, r14d
0x180025236  jz      short loc_180025279
0x180025238  lea     rdx, aLoadingRestore; "Loading restored xml"
0x18002523f  xor     ecx, ecx
0x180025241  call    UnattendLogW
0x180025246  mov     r8d, r13d; int
0x180025249  lea     rcx, [rsp+370h+var_300]; this
0x18002524e  mov     rdx, rsi; unsigned __int16 *
0x180025251  call    ?Init@ReAgentConfig@@UEAAKPEAGH@Z; ReAgentConfig::Init(ushort *,int)
0x180025256  test    eax, eax
0x180025258  jz      short loc_180025270
0x18002525a  lea     rdx, aRestoredXmlCou; "Restored xml could not be parsed"
0x180025261  xor     ecx, ecx
0x180025263  call    UnattendLogW
0x180025268  mov     r14d, r12d
0x18002526b  mov     [rsp+370h+var_310], r12d
0x180025270  test    r14d, r14d
0x180025273  jnz     loc_180025377
0x180025279  lea     rdx, aAttemptingToRe; "Attempting to recreate the XML"
0x180025280  mov     ecx, r13d
0x180025283  call    UnattendLogW
0x180025288  mov     rcx, rsi; unsigned __int16 *
0x18002528b  call    ?DoesPathExist@Utils@@SAKPEBG@Z; Utils::DoesPathExist(ushort const *)
0x180025290  test    eax, eax
0x180025292  jz      short loc_1800252F9
0x180025294  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, r12d; _ReAgentErrorCodes ReAgentError
0x18002529b  jnz     short loc_1800252A4
0x18002529d  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, r13d; _ReAgentErrorCodes ReAgentError
0x1800252a4  mov     [rsp+370h+hTemplateFile], r12; hTemplateFile
0x1800252a9  xor     r9d, r9d; lpSecurityAttributes
0x1800252ac  mov     dword ptr [rsp+370h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800252b4  xor     r8d, r8d; dwShareMode
0x1800252b7  mov     edx, 40000000h; dwDesiredAccess
0x1800252bc  mov     [rsp+370h+dwCreationDisposition], r13d; dwCreationDisposition
0x1800252c1  mov     rcx, rsi; lpFileName
0x1800252c4  call    cs:__imp_CreateFileW
0x1800252ca  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800252ce  jnz     short loc_1800252F0
0x1800252d0  call    cs:__imp_GetLastError
0x1800252d6  mov     r8, rsi
0x1800252d9  lea     rdx, aCreatefileSFai; "CreateFile (%s) failed , 0x%x"
0x1800252e0  mov     r9d, eax
0x1800252e3  mov     ecx, r13d
0x1800252e6  call    UnattendLogW
0x1800252eb  jmp     loc_1800250EF
0x1800252f0  mov     rcx, rax; hObject
0x1800252f3  call    cs:__imp_CloseHandle
0x1800252f9  xor     r8d, r8d; int
0x1800252fc  lea     rcx, [rsp+370h+var_300]; this
0x180025301  mov     rdx, rsi; unsigned __int16 *
0x180025304  call    ?Init@ReAgentConfig@@UEAAKPEAGH@Z; ReAgentConfig::Init(ushort *,int)
0x180025309  mov     ebx, eax
0x18002530b  test    eax, eax
0x18002530d  jz      short loc_180025328
0x18002530f  mov     dword ptr [rsp+370h+dwFlagsAndAttributes], 973h
0x180025317  lea     r8, aFailedToInitAg_2; "failed to init agent config"
0x18002531e  mov     ecx, 2
0x180025323  jmp     loc_1800251C0
0x180025328  lea     rcx, [rsp+370h+var_300]
0x18002532d  call    winreReconstructConfigXML
0x180025332  mov     ebx, eax
0x180025334  test    eax, eax
0x180025336  jz      short loc_180025349
0x180025338  mov     dword ptr [rsp+370h+dwFlagsAndAttributes], 974h
0x180025340  lea     r8, aFailedToRecons; "failed to reconstruct config xml"
0x180025347  jmp     short loc_18002531E
0x180025349  lea     rdx, aLoadingReconst; "Loading reconstructed xml"
0x180025350  xor     ecx, ecx
0x180025352  call    UnattendLogW
0x180025357  mov     r8d, r13d; int
0x18002535a  lea     rcx, [rsp+370h+var_300]; this
0x18002535f  mov     rdx, rsi; unsigned __int16 *
0x180025362  call    ?Init@ReAgentConfig@@UEAAKPEAGH@Z; ReAgentConfig::Init(ushort *,int)
0x180025367  mov     ebx, eax
0x180025369  test    eax, eax
0x18002536b  jz      short loc_180025377
0x18002536d  mov     dword ptr [rsp+370h+dwFlagsAndAttributes], 976h
0x180025375  jmp     short loc_180025317
0x180025377  lea     rcx, [rsp+370h+var_300]; this
0x18002537c  call    ?GetConfigInfo@ReAgentXMLParser@@QEAAPEAUReAgentConfigInfo@@XZ; ReAgentXMLParser::GetConfigInfo(void)
0x180025381  mov     rcx, [rbp+270h+var_2C0]
0x180025385  mov     r14, rax
0x180025388  cmp     [rcx+15D4h], r12d
0x18002538f  jz      short loc_1800253DC
0x180025391  lea     rdx, aWinreInstalled; "WinRE Installed, verifying BCD state"
0x180025398  xor     ecx, ecx
0x18002539a  call    UnattendLogW
0x18002539f  lea     r8, [rsp+370h+var_310]
0x1800253a4  mov     rdx, r14
0x1800253a7  call    winreVerifyWinReBcdState
0x1800253ac  cmp     [rsp+370h+var_310], r12d
0x1800253b1  lea     rdx, aVerifyingWinre; "Verifying WinRE files"
0x1800253b8  cmovz   edi, r13d
0x1800253bc  xor     ecx, ecx
0x1800253be  call    UnattendLogW
0x1800253c3  lea     rdx, [rsp+370h+var_310]
0x1800253c8  mov     rcx, r14
0x1800253cb  call    winreVerifyWinReFiles
0x1800253d0  cmp     [rsp+370h+var_310], r12d
0x1800253d5  jnz     short loc_180025447
0x1800253d7  mov     edi, r13d
0x1800253da  jmp     short loc_180025447
0x1800253dc  lea     rdx, aWinreDisabledV; "WinRE Disabled, verifying state consist"...
0x1800253e3  xor     ecx, ecx
0x1800253e5  call    UnattendLogW
0x1800253ea  mov     [rsp+370h+var_310], r12d
0x1800253ef  cmp     [r14+15D4h], r12d
0x1800253f6  jz      short loc_180025408
0x1800253f8  lea     rdx, aWinreEnabled; "WinRE enabled"
0x1800253ff  xor     ecx, ecx
0x180025401  call    UnattendLogW
0x180025406  jmp     short loc_1800253D7
0x180025408  lea     r15, [r14+4E8h]
0x18002540f  cmp     [r15], r12w
0x180025413  jz      short loc_180025442
0x180025415  lea     rdx, aBootSdi; "boot.sdi"
0x18002541c  mov     rcx, r15; unsigned __int16 *
0x18002541f  call    ?DoesFileExist@Utils@@SAKPEBG0@Z; Utils::DoesFileExist(ushort const *,ushort const *)
0x180025424  test    eax, eax
0x180025426  jnz     short loc_180025442
0x180025428  lea     r9, aBootSdi; "boot.sdi"
0x18002542f  mov     r8, r15
0x180025432  lea     rdx, aBootSdiFoundAt; "boot.sdi found at %s\\%s"
0x180025439  xor     ecx, ecx
0x18002543b  call    UnattendLogW
0x180025440  jmp     short loc_1800253D7
0x180025442  mov     [rsp+370h+var_310], r13d
0x180025447  lea     rdx, [rsp+370h+var_310]
0x18002544c  mov     rcx, r14; struct ReAgentConfigInfo *
0x18002544f  call    winreCopyWIMBackFromTempStaging
0x180025454  cmp     [rsp+370h+var_310], r12d
0x180025459  jnz     short loc_180025475
0x18002545b  test    edi, edi
0x18002545d  jnz     short loc_180025475
0x18002545f  lea     rdx, aWinreStateVali; "WinRE state valid, no repair required"
0x180025466  xor     ecx, ecx
0x180025468  call    UnattendLogW
0x18002546d  mov     r15d, r13d
0x180025470  jmp     loc_180025533
0x180025475  lea     rdx, aRepairNeededUn; "Repair needed, uninstalling winre"
0x18002547c  xor     ecx, ecx
0x18002547e  call    UnattendLogW
0x180025483  mov     rax, [rbp+270h+var_2C0]
0x180025487  lea     rcx, [rsp+370h+var_300]; this
0x18002548c  mov     [rax+15D4h], r13d
0x180025493  mov     rax, [rbp+270h+var_2C0]
0x180025497  mov     [rax+15E4h], r12d
0x18002549e  call    ?Update@ReAgentXMLParser@@QEAAKXZ; ReAgentXMLParser::Update(void)
0x1800254a3  mov     r8d, r13d; int
0x1800254a6  mov     edx, r13d; int
0x1800254a9  xor     ecx, ecx; struct _GUID *
0x1800254ab  call    ?winreUnInstallInternal@@YAKPEAU_GUID@@HH@Z; winreUnInstallInternal(_GUID *,int,int)
0x1800254b0  mov     r8d, r13d; int
0x1800254b3  lea     rcx, [rsp+370h+var_300]; this
0x1800254b8  mov     rdx, rsi; unsigned __int16 *
0x1800254bb  call    ?Init@ReAgentConfig@@UEAAKPEAGH@Z; ReAgentConfig::Init(ushort *,int)
0x1800254c0  lea     rcx, [rsp+370h+var_300]; this
0x1800254c5  call    ?GetConfigInfo@ReAgentXMLParser@@QEAAPEAUReAgentConfigInfo@@XZ; ReAgentXMLParser::GetConfigInfo(void)
0x1800254ca  xor     edx, edx; int
0x1800254cc  lea     rcx, [rsp+370h+var_300]; this
0x1800254d1  call    ?SetInstallState@ReAgentConfig@@QEAAXH@Z; ReAgentConfig::SetInstallState(int)
0x1800254d6  lea     rcx, [rsp+370h+var_300]; this
0x1800254db  call    ?Update@ReAgentXMLParser@@QEAAKXZ; ReAgentXMLParser::Update(void)
0x1800254e0  lea     rdx, aInstallingWinr; "Installing winre"
0x1800254e7  xor     ecx, ecx
0x1800254e9  call    UnattendLogW
  ... truncated ...
```
