# WinRePostBCDRepair

- ea: `0x180024a10`
- end: `0x180024dea`
- name: `WinRePostBCDRepair`
- size: `986`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x1800055c8`
- `0x180005694`
- `0x1800059fc`
- `0x180006ed8`
- `0x180008b94`
- `0x180010010`
- `0x1800109d0`
- `0x180011344`
- `0x180011974`
- `0x1800121b0`
- `0x1800145f4`
- `0x180014754`
- `0x180018838`
- `0x180024a10`
- `0x180028e30`
- `0x180030f18`
- `0x180034aa4`
- `0x1800356d4`
- `0x18003591c`
- `0x180035e88`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180024da4`
- `KERNEL32!SetLastError` at `0x180024da4`
- `ole32!CoTaskMemFree` at `0x180024d7c`
- `ole32!CoTaskMemFree` at `0x180024d7c`

## string_xrefs

- `0x180024af5`: `Parameters: configWinDir: %s`
- `0x180024b42`: `DisableUpdateEnhancedConfigInfo`
- `0x180024b36`: `failed to get config file path`
- `0x180024b7a`: `failed to init agent config`
- `0x180024c84`: `Updating reagent.xml`
- `0x180024d2b`: `ReAgent.xml`
- `0x180024d51`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180024ada`: `Enter WinRePostBCDRepair`
- `0x180024b0a`: `repairedOS: `
- `0x180024d5b`: `WinRePostBCDRepair %s (0x%x) in file %S line %d`
- `0x180024bce`: `failed to convert directory name to offset`
- `0x180024cf6`: `Failed to update recovery BCD: 0x%x`
- `0x180024d1d`: `failed to update agent config`
- `0x180024d4a`: `failed to back up config file`
- `0x180024d84`: `Exit WinRePostBCDRepair return value: %d, last error: 0x%x`

## pseudocode

```c
_BOOL8 __fastcall WinRePostBCDRepair(const unsigned __int16 *a1, struct _GUID *a2)
{
  const unsigned __int16 *v4; // r8
  __int64 v5; // r8
  DWORD ConfigFilePathFromWinDir; // edi
  const wchar_t *v7; // r8
  struct ReAgentConfigInfo *ConfigInfo; // rax
  struct ReAgentConfigInfo *v9; // rbx
  ReAgentXMLParser *v10; // rcx
  unsigned int v11; // eax
  int v13; // [rsp+28h] [rbp-D8h]
  LPVOID pv[2]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v15[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v16; // [rsp+58h] [rbp-A8h]
  int v17; // [rsp+5Ch] [rbp-A4h]
  __int128 v18; // [rsp+60h] [rbp-A0h]
  __int128 v19; // [rsp+70h] [rbp-90h]
  ReAgentXMLParser *v20; // [rsp+80h] [rbp-80h]
  int v21; // [rsp+88h] [rbp-78h]
  __int128 v22; // [rsp+90h] [rbp-70h] BYREF
  __int128 v23; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v24[32]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v25; // [rsp+D0h] [rbp-30h]
  struct _GUID v26; // [rsp+D4h] [rbp-2Ch] BYREF
  unsigned __int64 v27; // [rsp+5A0h] [rbp+4A0h]
  unsigned __int16 v28[304]; // [rsp+5E0h] [rbp+4E0h] BYREF

  pv[0] = 0;
  v23 = 0;
  v22 = 0;
  memset_0(v28, 0, 0x25Cu);
  v15[1] = 0;
  v18 = 0;
  v19 = 0;
  v15[0] = &ReAgentConfig::`vftable';
  v15[2] = 0;
  v16 = 0;
  v17 = 2;
  v20 = 0;
  v21 = 0;
  memset_0(v24, 0, 0x530u);
  UnattendInitializeLogEx2(0);
  UnattendLogW(0, L"Enter WinRePostBCDRepair");
  v4 = a1;
  if ( !a1 )
    v4 = L"NULL";
  UnattendLogW(0, L"Parameters: configWinDir: %s", v4);
  LogGuid(L"repairedOS: ", a2);
  ConfigFilePathFromWinDir = winreGetConfigFilePathFromWinDir(a1, 1, v5, pv);
  if ( ConfigFilePathFromWinDir )
  {
    v13 = 455;
    v7 = L"failed to get config file path";
  }
  else
  {
    UnattendLogW(0, L"DisableUpdateEnhancedConfigInfo");
    v21 = 1;
    ConfigFilePathFromWinDir = ReAgentConfig::Init((ReAgentConfig *)v15, (unsigned __int16 *)pv[0], 1);
    if ( ConfigFilePathFromWinDir )
    {
      v13 = 459;
      v7 = L"failed to init agent config";
    }
    else
    {
      ConfigInfo = ReAgentXMLParser::GetConfigInfo((ReAgentXMLParser *)v15);
      v9 = ConfigInfo;
      if ( !*((_DWORD *)ConfigInfo + 1397) )
        goto LABEL_21;
      ConfigFilePathFromWinDir = winreConvertDirNameToOffset((LPCWSTR)ConfigInfo + 8, (__int64)L"winre.wim", v24, 0, 0);
      if ( ConfigFilePathFromWinDir )
      {
        v13 = 471;
        v7 = L"failed to convert directory name to offset";
      }
      else
      {
        v23 = *(_OWORD *)v9;
        *(_OWORD *)v20 = xmmword_180070D08;
        ReAgentConfig::SetInstallState((ReAgentConfig *)v15, 0);
        v10 = v20;
        *((_DWORD *)v20 + 1403) = 4;
        ReAgentXMLParser::CopyPathInfo(v10, (unsigned __int16 *)&qword_180070D18, (unsigned __int16 *)v20 + 2808);
        winreRemoveRecoverySequenceEx(&GUID_CURRENT_BOOT_ENTRY, &v23);
        if ( !(unsigned int)winreCreateRecoveryEntryInBCD((struct PartitionNode *)v24)
          && !winreSetRecoverySequence(&v22, *((_DWORD *)v9 + 1556), a2)
          && StringCchCopyW(v28, 0x12Eu, L"\\Recovery\\WindowsRE") >= 0 )
        {
          UnattendLogW(0, L"Updating reagent.xml");
          if ( !ReAgentConfig::SetWinreLocationPath((ReAgentConfig *)v15, v27, &v26, v25, v28) )
          {
            *(_OWORD *)v20 = v22;
            *((_DWORD *)v20 + 1397) = 1;
            *((_DWORD *)v20 + 1401) = 0;
            v11 = winreRegisterInRecoveryBCD((struct PartitionNode *)v24, a2);
            if ( v11 )
              UnattendLogW(2, L"Failed to update recovery BCD: 0x%x", v11);
          }
        }
        ConfigFilePathFromWinDir = ReAgentXMLParser::Update((ReAgentXMLParser *)v15);
        if ( ConfigFilePathFromWinDir )
        {
          v13 = 534;
          v7 = L"failed to update agent config";
        }
        else
        {
          ConfigFilePathFromWinDir = winreBackupRecoveryFile(
                                       (unsigned __int16 *)pv[0],
                                       (ReAgentXMLParser *)v15,
                                       L"ReAgent.xml");
          if ( !ConfigFilePathFromWinDir )
            goto LABEL_21;
          v13 = 538;
          v7 = L"failed to back up config file";
        }
      }
    }
  }
  UnattendLogW(
    2,
    L"WinRePostBCDRepair %s (0x%x) in file %S line %d",
    v7,
    ConfigFilePathFromWinDir,
    "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
    v13);
LABEL_21:
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  UnattendLogW(
    0,
    L"Exit WinRePostBCDRepair return value: %d, last error: 0x%x",
    ConfigFilePathFromWinDir == 0,
    ConfigFilePathFromWinDir);
  UnattendFinalizeLog();
  SetLastError(ConfigFilePathFromWinDir);
  v15[0] = &ReAgentConfig::`vftable';
  ReAgentXMLParser::~ReAgentXMLParser((ReAgentXMLParser *)v15);
  return ConfigFilePathFromWinDir == 0;
}

```

## disassembly

```asm
0x180024a10  mov     [rsp-8+arg_10], rbx
0x180024a15  mov     [rsp-8+arg_18], rdi
0x180024a1a  push    rbp
0x180024a1b  push    r12
0x180024a1d  push    r14
0x180024a1f  lea     rbp, [rsp-750h]
0x180024a27  sub     rsp, 850h
0x180024a2e  mov     rax, cs:__security_cookie
0x180024a35  xor     rax, rsp
0x180024a38  mov     [rbp+760h+var_20], rax
0x180024a3f  mov     r14, rdx
0x180024a42  mov     [rsp+860h+pv], 0
0x180024a4b  mov     rbx, rcx
0x180024a4e  xorps   xmm0, xmm0
0x180024a51  xorps   xmm1, xmm1
0x180024a54  lea     rcx, [rbp+760h+var_280]; void *
0x180024a5b  xor     edx, edx; Val
0x180024a5d  mov     r8d, 25Ch; Size
0x180024a63  movups  [rbp+760h+var_7C0], xmm0
0x180024a67  movups  [rbp+760h+var_7D0], xmm1
0x180024a6b  call    memset_0
0x180024a70  xorps   xmm0, xmm0
0x180024a73  mov     [rsp+860h+var_818], 0
0x180024a7c  xorps   xmm1, xmm1
0x180024a7f  movdqa  [rsp+860h+var_800], xmm0
0x180024a85  lea     rax, ??_7ReAgentConfig@@6B@; const ReAgentConfig::`vftable'
0x180024a8c  movdqa  [rsp+860h+var_7F0], xmm1
0x180024a92  mov     r12d, 2
0x180024a98  mov     [rsp+860h+var_820], rax
0x180024a9d  xor     edx, edx; Val
0x180024a9f  mov     [rsp+860h+var_810], 0
0x180024aa8  mov     r8d, 530h; Size
0x180024aae  mov     [rsp+860h+var_808], 0
0x180024ab6  lea     rcx, [rbp+760h+var_7B0]; void *
0x180024aba  mov     [rsp+860h+var_804], r12d
0x180024abf  mov     [rbp+760h+var_7E0], 0
0x180024ac7  mov     [rbp+760h+var_7D8], 0
0x180024ace  call    memset_0
0x180024ad3  xor     ecx, ecx
0x180024ad5  call    UnattendInitializeLogEx2
0x180024ada  lea     rdx, aEnterWinrepost; "Enter WinRePostBCDRepair"
0x180024ae1  xor     ecx, ecx
0x180024ae3  call    UnattendLogW
0x180024ae8  lea     rax, aNull_0; "NULL"
0x180024aef  test    rbx, rbx
0x180024af2  mov     r8, rbx
0x180024af5  lea     rdx, aParametersConf_1; "Parameters: configWinDir: %s"
0x180024afc  cmovz   r8, rax
0x180024b00  xor     ecx, ecx
0x180024b02  call    UnattendLogW
0x180024b07  mov     rdx, r14
0x180024b0a  lea     rcx, aRepairedos; "repairedOS: "
0x180024b11  call    LogGuid
0x180024b16  lea     r9, [rsp+860h+pv]
0x180024b1b  mov     rcx, rbx
0x180024b1e  lea     edx, [r12-1]
0x180024b23  call    winreGetConfigFilePathFromWinDir
0x180024b28  mov     edi, eax
0x180024b2a  test    eax, eax
0x180024b2c  jz      short loc_180024B42
0x180024b2e  mov     [rsp+860h+var_838], 1C7h
0x180024b36  lea     r8, aFailedToGetCon_3; "failed to get config file path"
0x180024b3d  jmp     loc_180024D51
0x180024b42  lea     rdx, aDisableupdatee; "DisableUpdateEnhancedConfigInfo"
0x180024b49  xor     ecx, ecx
0x180024b4b  call    UnattendLogW
0x180024b50  mov     rdx, [rsp+860h+pv]; unsigned __int16 *
0x180024b55  lea     rcx, [rsp+860h+var_820]; this
0x180024b5a  mov     r8d, 1; int
0x180024b60  mov     [rbp+760h+var_7D8], 1
0x180024b67  call    ?Init@ReAgentConfig@@UEAAKPEAGH@Z; ReAgentConfig::Init(ushort *,int)
0x180024b6c  mov     edi, eax
0x180024b6e  test    eax, eax
0x180024b70  jz      short loc_180024B86
0x180024b72  mov     [rsp+860h+var_838], 1CBh
0x180024b7a  lea     r8, aFailedToInitAg_2; "failed to init agent config"
0x180024b81  jmp     loc_180024D51
0x180024b86  lea     rcx, [rsp+860h+var_820]; this
0x180024b8b  call    ?GetConfigInfo@ReAgentXMLParser@@QEAAPEAUReAgentConfigInfo@@XZ; ReAgentXMLParser::GetConfigInfo(void)
0x180024b90  mov     rbx, rax
0x180024b93  cmp     dword ptr [rax+15D4h], 0
0x180024b9a  jz      loc_180024D6F
0x180024ba0  lea     rcx, [rax+10h]; lpszFileName
0x180024ba4  mov     [rsp+860h+var_840], 0; __int64
0x180024bad  xor     r9d, r9d
0x180024bb0  lea     r8, [rbp+760h+var_7B0]
0x180024bb4  lea     rdx, aWinreWim_1; "winre.wim"
0x180024bbb  call    winreConvertDirNameToOffset
0x180024bc0  mov     edi, eax
0x180024bc2  test    eax, eax
0x180024bc4  jz      short loc_180024BDA
0x180024bc6  mov     [rsp+860h+var_838], 1D7h
0x180024bce  lea     r8, aFailedToConver_0; "failed to convert directory name to off"...
0x180024bd5  jmp     loc_180024D51
0x180024bda  movups  xmm0, xmmword ptr [rbx]
0x180024bdd  mov     rax, [rbp+760h+var_7E0]
0x180024be1  lea     rcx, [rsp+860h+var_820]; this
0x180024be6  movups  xmm1, cs:xmmword_180070D08
0x180024bed  xor     edx, edx; int
0x180024bef  movdqu  [rbp+760h+var_7C0], xmm0
0x180024bf4  movdqu  xmmword ptr [rax], xmm1
0x180024bf8  call    ?SetInstallState@ReAgentConfig@@QEAAXH@Z; ReAgentConfig::SetInstallState(int)
0x180024bfd  mov     rcx, [rbp+760h+var_7E0]; this
0x180024c01  lea     rdx, qword_180070D18; unsigned __int16 *
0x180024c08  mov     dword ptr [rcx+15ECh], 4
0x180024c12  mov     r8, [rbp+760h+var_7E0]
0x180024c16  add     r8, 15F0h; unsigned __int16 *
0x180024c1d  call    ?CopyPathInfo@ReAgentXMLParser@@IEAAKPEAG0@Z; ReAgentXMLParser::CopyPathInfo(ushort *,ushort *)
0x180024c22  lea     rdx, [rbp+760h+var_7C0]
0x180024c26  lea     rcx, GUID_CURRENT_BOOT_ENTRY
0x180024c2d  call    winreRemoveRecoverySequenceEx
0x180024c32  mov     r8, r14
0x180024c35  lea     rdx, [rbp+760h+var_7D0]
0x180024c39  lea     rcx, [rbp+760h+var_7B0]; struct PartitionNode *
0x180024c3d  call    winreCreateRecoveryEntryInBCD
0x180024c42  test    eax, eax
0x180024c44  jnz     loc_180024D05
0x180024c4a  mov     edx, [rbx+1850h]
0x180024c50  lea     rcx, [rbp+760h+var_7D0]
0x180024c54  mov     r8, r14
0x180024c57  call    winreSetRecoverySequence
0x180024c5c  test    eax, eax
0x180024c5e  jnz     loc_180024D05
0x180024c64  lea     r8, aRecoveryWindow; "\\Recovery\\WindowsRE"
0x180024c6b  mov     edx, 12Eh; unsigned __int64
0x180024c70  lea     rcx, [rbp+760h+var_280]; unsigned __int16 *
0x180024c77  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180024c7c  test    eax, eax
0x180024c7e  js      loc_180024D05
0x180024c84  lea     rdx, aUpdatingReagen; "Updating reagent.xml"
0x180024c8b  xor     ecx, ecx
0x180024c8d  call    UnattendLogW
0x180024c92  mov     r9d, [rbp+760h+var_790]; unsigned int
0x180024c96  lea     rax, [rbp+760h+var_280]
0x180024c9d  mov     rdx, [rbp+760h+var_2C0]; unsigned __int64
0x180024ca4  lea     r8, [rbp+760h+var_78C]; struct _GUID *
0x180024ca8  lea     rcx, [rsp+860h+var_820]; this
0x180024cad  mov     [rsp+860h+var_840], rax; unsigned __int16 *
0x180024cb2  call    ?SetWinreLocationPath@ReAgentConfig@@QEAAK_KPEAU_GUID@@KPEAG@Z; ReAgentConfig::SetWinreLocationPath(unsigned __int64,_GUID *,ulong,ushort *)
0x180024cb7  test    eax, eax
0x180024cb9  jnz     short loc_180024D05
0x180024cbb  mov     rax, [rbp+760h+var_7E0]
0x180024cbf  lea     rcx, [rbp+760h+var_7B0]; struct PartitionNode *
0x180024cc3  movups  xmm0, [rbp+760h+var_7D0]
0x180024cc7  mov     rdx, r14; struct _GUID *
0x180024cca  movdqu  xmmword ptr [rax], xmm0
0x180024cce  mov     rax, [rbp+760h+var_7E0]
0x180024cd2  mov     dword ptr [rax+15D4h], 1
0x180024cdc  mov     rax, [rbp+760h+var_7E0]
0x180024ce0  mov     dword ptr [rax+15E4h], 0
0x180024cea  call    winreRegisterInRecoveryBCD
0x180024cef  test    eax, eax
0x180024cf1  jz      short loc_180024D05
0x180024cf3  mov     r8d, eax
0x180024cf6  lea     rdx, aFailedToUpdate; "Failed to update recovery BCD: 0x%x"
0x180024cfd  mov     ecx, r12d
0x180024d00  call    UnattendLogW
0x180024d05  lea     rcx, [rsp+860h+var_820]; this
0x180024d0a  call    ?Update@ReAgentXMLParser@@QEAAKXZ; ReAgentXMLParser::Update(void)
0x180024d0f  mov     edi, eax
0x180024d11  test    eax, eax
0x180024d13  jz      short loc_180024D26
0x180024d15  mov     [rsp+860h+var_838], 216h
0x180024d1d  lea     r8, aFailedToUpdate_7; "failed to update agent config"
0x180024d24  jmp     short loc_180024D51
0x180024d26  mov     rcx, [rsp+860h+pv]; unsigned __int16 *
0x180024d2b  lea     r8, aReagentXml_1; "ReAgent.xml"
0x180024d32  lea     rdx, [rsp+860h+var_820]; this
0x180024d37  call    winreBackupRecoveryFile
0x180024d3c  mov     edi, eax
0x180024d3e  test    eax, eax
0x180024d40  jz      short loc_180024D6F
0x180024d42  mov     [rsp+860h+var_838], 21Ah
0x180024d4a  lea     r8, aFailedToBackUp; "failed to back up config file"
0x180024d51  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180024d58  mov     r9d, edi
0x180024d5b  lea     rdx, aWinrepostbcdre_0; "WinRePostBCDRepair %s (0x%x) in file %S"...
0x180024d62  mov     [rsp+860h+var_840], rax
0x180024d67  mov     ecx, r12d
0x180024d6a  call    UnattendLogW
0x180024d6f  cmp     [rsp+860h+pv], 0
0x180024d75  jz      short loc_180024D82
0x180024d77  mov     rcx, [rsp+860h+pv]; pv
0x180024d7c  call    cs:__imp_CoTaskMemFree
0x180024d82  xor     ebx, ebx
0x180024d84  lea     rdx, aExitWinrepostb; "Exit WinRePostBCDRepair return value: %"...
0x180024d8b  test    edi, edi
0x180024d8d  mov     r9d, edi
0x180024d90  setz    bl
0x180024d93  xor     ecx, ecx
0x180024d95  mov     r8d, ebx
0x180024d98  call    UnattendLogW
0x180024d9d  call    UnattendFinalizeLog
0x180024da2  mov     ecx, edi; dwErrCode
0x180024da4  call    cs:__imp_SetLastError
0x180024daa  lea     rax, ??_7ReAgentConfig@@6B@; const ReAgentConfig::`vftable'
0x180024db1  lea     rcx, [rsp+860h+var_820]; this
0x180024db6  mov     [rsp+860h+var_820], rax
0x180024dbb  call    ??1ReAgentXMLParser@@UEAA@XZ; ReAgentXMLParser::~ReAgentXMLParser(void)
0x180024dc0  mov     eax, ebx
0x180024dc2  mov     rcx, [rbp+760h+var_20]
0x180024dc9  xor     rcx, rsp; StackCookie
0x180024dcc  call    __security_check_cookie
0x180024dd1  lea     r11, [rsp+860h+var_10]
0x180024dd9  mov     rbx, [r11+30h]
0x180024ddd  mov     rdi, [r11+38h]
0x180024de1  mov     rsp, r11
0x180024de4  pop     r14
0x180024de6  pop     r12
0x180024de8  pop     rbp
0x180024de9  retn
```
