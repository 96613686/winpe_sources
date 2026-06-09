# WinReRepairEx

- ea: `0x180025560`
- end: `0x180025911`
- name: `WinReRepairEx`
- size: `945`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x1800055c8`
- `0x180005694`
- `0x1800059fc`
- `0x180008b94`
- `0x180010010`
- `0x1800109d0`
- `0x180011974`
- `0x1800121b0`
- `0x1800145f4`
- `0x180014754`
- `0x180024ff0`
- `0x180025560`
- `0x180030f18`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800258e8`
- `KERNEL32!SetLastError` at `0x1800258e8`

## string_xrefs

- `0x1800256cb`: `DisableUpdateEnhancedConfigInfo`
- `0x180025679`: `failed to get config file path`
- `0x180025708`: `failed to init agent config`
- `0x180025680`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x18002576a`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180025877`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x1800255a8`: `Enter WinReRepairEx`
- `0x18002568a`: `WinReRepairEx %s (0x%x) in file %S line %d`
- `0x180025774`: `WinReRepairEx %s (0x%x) in file %S line %d`
- `0x180025898`: `WinReRepairEx %s (0x%x) in file %S line %d`
- `0x1800256bd`: `Update config file %s`
- `0x18002572c`: `Update Disk info for WinRE location`
- `0x180025763`: `failed to convert Windows directory to partition info`
- `0x1800257e0`: `Update WinRE GUID`
- `0x180025816`: `Failed to update agent config`
- `0x180025841`: `Repair WinRE`
- `0x180025854`: `Repair should be called with NULL Windows directory`
- `0x18002588e`: `Failed to repair WinRE`
- `0x1800258a6`: `Failed to repair WinRE. Error: 0x%08X`
- `0x1800258ba`: `Successfully Repair WinRE`
- `0x1800258d0`: `Exit WinReRepairEx return value: %d, last error: 0x%x`

## pseudocode

```c
__int64 __fastcall WinReRepairEx(__int64 a1, const WCHAR *a2, _OWORD *a3)
{
  DWORD ConfigFilePathFromWinDir; // ebx
  const unsigned __int16 *v7; // r8
  __int64 v8; // r8
  const wchar_t *v9; // r8
  struct ReAgentConfigInfo *ConfigInfo; // r14
  unsigned int v11; // edi
  int v13; // [rsp+28h] [rbp-D8h]
  _BYTE v14[32]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v15; // [rsp+50h] [rbp-B0h]
  struct _GUID v16; // [rsp+54h] [rbp-ACh] BYREF
  unsigned __int16 *v17; // [rsp+560h] [rbp+460h] BYREF
  _QWORD v18[3]; // [rsp+570h] [rbp+470h] BYREF
  int v19; // [rsp+588h] [rbp+488h]
  int v20; // [rsp+58Ch] [rbp+48Ch]
  __int128 v21; // [rsp+590h] [rbp+490h]
  __int128 v22; // [rsp+5A0h] [rbp+4A0h]
  _OWORD *v23; // [rsp+5B0h] [rbp+4B0h]
  int v24; // [rsp+5B8h] [rbp+4B8h]

  v17 = 0;
  ConfigFilePathFromWinDir = 0;
  UnattendInitializeLogEx2(0);
  UnattendLogW(0, L"Enter WinReRepairEx");
  v7 = a2;
  if ( !a2 )
    v7 = L"NULL";
  UnattendLogW(0, L"Parameters: WinDir: %s, Flags: %llu", v7, a1);
  if ( a3 )
    LogGuid(L"New WinRE GUID: ", a3);
  if ( (a1 & 1) == 0 )
    goto LABEL_21;
  v18[1] = 0;
  v21 = 0;
  v22 = 0;
  v18[0] = &ReAgentConfig::`vftable';
  v18[2] = 0;
  v19 = 0;
  v20 = 2;
  v23 = 0;
  v24 = 0;
  memset_0(v14, 0, 0x530u);
  ConfigFilePathFromWinDir = winreGetConfigFilePathFromWinDir(a2, 0, v8, &v17);
  if ( !ConfigFilePathFromWinDir )
  {
    UnattendLogW(0, L"Update config file %s", v17);
    UnattendLogW(0, L"DisableUpdateEnhancedConfigInfo");
    v24 = 1;
    ConfigFilePathFromWinDir = ReAgentConfig::Init((ReAgentConfig *)v18, v17, 1);
    if ( ConfigFilePathFromWinDir )
    {
      v13 = 2546;
      v9 = L"failed to init agent config";
      goto LABEL_8;
    }
    ConfigInfo = ReAgentXMLParser::GetConfigInfo((ReAgentXMLParser *)v18);
    if ( a2 )
    {
      UnattendLogW(0, L"Update Disk info for WinRE location");
      ConfigFilePathFromWinDir = winreConvertDirNameToOffset(a2, 0, v14, 0, 0);
      if ( ConfigFilePathFromWinDir )
      {
        v13 = 2558;
        v9 = L"failed to convert Windows directory to partition info";
        goto LABEL_8;
      }
      ConfigFilePathFromWinDir = ReAgentConfig::SetWinreLocationPath(
                                   (ReAgentConfig *)v18,
                                   *((_QWORD *)ConfigInfo + 156),
                                   &v16,
                                   v15,
                                   (unsigned __int16 *)ConfigInfo + 310);
      if ( ConfigFilePathFromWinDir )
      {
        v13 = 2565;
        v9 = L"failed to set disk ID and Signature";
        goto LABEL_8;
      }
    }
    if ( a3 )
    {
      UnattendLogW(0, L"Update WinRE GUID");
      *v23 = *a3;
    }
    ConfigFilePathFromWinDir = ReAgentXMLParser::Update((ReAgentXMLParser *)v18);
    if ( ConfigFilePathFromWinDir )
    {
      v13 = 2576;
      v9 = L"Failed to update agent config";
      goto LABEL_8;
    }
    v18[0] = &ReAgentConfig::`vftable';
    ReAgentXMLParser::~ReAgentXMLParser((ReAgentXMLParser *)v18);
LABEL_21:
    if ( (a1 & 2) != 0 )
    {
      UnattendLogW(0, L"Repair WinRE");
      if ( a2 )
      {
        UnattendLogW(1, L"Repair should be called with NULL Windows directory");
        ConfigFilePathFromWinDir = 50;
        goto LABEL_26;
      }
      ConfigFilePathFromWinDir = WinReRepair();
      if ( ConfigFilePathFromWinDir )
      {
        UnattendLogW(
          2,
          L"WinReRepairEx %s (0x%x) in file %S line %d",
          L"Failed to repair WinRE",
          ConfigFilePathFromWinDir,
          "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
          2588);
        goto LABEL_26;
      }
    }
    v11 = 1;
    UnattendLogW(0, L"Successfully Repair WinRE");
    goto LABEL_28;
  }
  v13 = 2539;
  v9 = L"failed to get config file path";
LABEL_8:
  UnattendLogW(
    2,
    L"WinReRepairEx %s (0x%x) in file %S line %d",
    v9,
    ConfigFilePathFromWinDir,
    "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
    v13);
  v18[0] = &ReAgentConfig::`vftable';
  ReAgentXMLParser::~ReAgentXMLParser((ReAgentXMLParser *)v18);
LABEL_26:
  v11 = 0;
  UnattendLogW(1, L"Failed to repair WinRE. Error: 0x%08X", ConfigFilePathFromWinDir);
LABEL_28:
  UnattendLogW(0, L"Exit WinReRepairEx return value: %d, last error: 0x%x", v11, ConfigFilePathFromWinDir);
  UnattendFinalizeLog();
  SetLastError(ConfigFilePathFromWinDir);
  return v11;
}

```

## disassembly

```asm
0x180025560  push    rbp
0x180025562  push    rbx
0x180025563  push    rsi
0x180025564  push    rdi
0x180025565  push    r13
0x180025567  push    r14
0x180025569  push    r15
0x18002556b  lea     rbp, [rsp-4D0h]
0x180025573  sub     rsp, 5D0h
0x18002557a  mov     rax, cs:__security_cookie
0x180025581  xor     rax, rsp
0x180025584  mov     [rbp+500h+var_40], rax
0x18002558b  mov     r15, rcx
0x18002558e  mov     [rbp+500h+var_A0], 0
0x180025599  xor     ecx, ecx
0x18002559b  mov     rsi, r8
0x18002559e  mov     rdi, rdx
0x1800255a1  xor     ebx, ebx
0x1800255a3  call    UnattendInitializeLogEx2
0x1800255a8  lea     rdx, aEnterWinrerepa; "Enter WinReRepairEx"
0x1800255af  xor     ecx, ecx
0x1800255b1  call    UnattendLogW
0x1800255b6  lea     rax, aNull_0; "NULL"
0x1800255bd  test    rdi, rdi
0x1800255c0  mov     r8, rdi
0x1800255c3  lea     rdx, aParametersWind; "Parameters: WinDir: %s, Flags: %llu"
0x1800255ca  cmovz   r8, rax
0x1800255ce  mov     r9, r15
0x1800255d1  xor     ecx, ecx
0x1800255d3  call    UnattendLogW
0x1800255d8  test    rsi, rsi
0x1800255db  jz      short loc_1800255EC
0x1800255dd  mov     rdx, rsi
0x1800255e0  lea     rcx, aNewWinreGuid; "New WinRE GUID: "
0x1800255e7  call    LogGuid
0x1800255ec  mov     r13d, 2
0x1800255f2  test    r15b, 1
0x1800255f6  jz      loc_18002583C
0x1800255fc  xorps   xmm0, xmm0
0x1800255ff  mov     [rbp+500h+var_88], rbx
0x180025606  xorps   xmm1, xmm1
0x180025609  movdqa  [rbp+500h+var_70], xmm0
0x180025611  lea     r14, ??_7ReAgentConfig@@6B@; const ReAgentConfig::`vftable'
0x180025618  movdqa  [rbp+500h+var_60], xmm1
0x180025620  xor     edx, edx; Val
0x180025622  mov     [rbp+500h+var_90], r14
0x180025629  mov     r8d, 530h; Size
0x18002562f  mov     [rbp+500h+var_80], rbx
0x180025636  lea     rcx, [rsp+600h+var_5D0]; void *
0x18002563b  mov     [rbp+500h+var_78], ebx
0x180025641  mov     [rbp+500h+var_74], r13d
0x180025648  mov     [rbp+500h+var_50], rbx
0x18002564f  mov     [rbp+500h+var_48], ebx
0x180025655  call    memset_0
0x18002565a  lea     r9, [rbp+500h+var_A0]
0x180025661  xor     edx, edx
0x180025663  mov     rcx, rdi
0x180025666  call    winreGetConfigFilePathFromWinDir
0x18002566b  mov     ebx, eax
0x18002566d  test    eax, eax
0x18002566f  jz      short loc_1800256B6
0x180025671  mov     [rsp+600h+var_5D8], 9EBh
0x180025679  lea     r8, aFailedToGetCon_3; "failed to get config file path"
0x180025680  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180025687  mov     r9d, ebx
0x18002568a  lea     rdx, aWinrerepairexS; "WinReRepairEx %s (0x%x) in file %S line"...
0x180025691  mov     [rsp+600h+var_5E0], rax
0x180025696  mov     ecx, r13d
0x180025699  call    UnattendLogW
0x18002569e  mov     [rbp+500h+var_90], r14
0x1800256a5  lea     rcx, [rbp+500h+var_90]; this
0x1800256ac  call    ??1ReAgentXMLParser@@UEAA@XZ; ReAgentXMLParser::~ReAgentXMLParser(void)
0x1800256b1  jmp     loc_1800258A4
0x1800256b6  mov     r8, [rbp+500h+var_A0]
0x1800256bd  lea     rdx, aUpdateConfigFi; "Update config file %s"
0x1800256c4  xor     ecx, ecx
0x1800256c6  call    UnattendLogW
0x1800256cb  lea     rdx, aDisableupdatee; "DisableUpdateEnhancedConfigInfo"
0x1800256d2  xor     ecx, ecx
0x1800256d4  call    UnattendLogW
0x1800256d9  mov     rdx, [rbp+500h+var_A0]; unsigned __int16 *
0x1800256e0  lea     rcx, [rbp+500h+var_90]; this
0x1800256e7  mov     eax, 1
0x1800256ec  mov     r8d, eax; int
0x1800256ef  mov     [rbp+500h+var_48], eax
0x1800256f5  call    ?Init@ReAgentConfig@@UEAAKPEAGH@Z; ReAgentConfig::Init(ushort *,int)
0x1800256fa  mov     ebx, eax
0x1800256fc  test    eax, eax
0x1800256fe  jz      short loc_180025714
0x180025700  mov     [rsp+600h+var_5D8], 9F2h
0x180025708  lea     r8, aFailedToInitAg_2; "failed to init agent config"
0x18002570f  jmp     loc_180025680
0x180025714  lea     rcx, [rbp+500h+var_90]; this
0x18002571b  call    ?GetConfigInfo@ReAgentXMLParser@@QEAAPEAUReAgentConfigInfo@@XZ; ReAgentXMLParser::GetConfigInfo(void)
0x180025720  mov     r14, rax
0x180025723  test    rdi, rdi
0x180025726  jz      loc_1800257DB
0x18002572c  lea     rdx, aUpdateDiskInfo; "Update Disk info for WinRE location"
0x180025733  xor     ecx, ecx
0x180025735  call    UnattendLogW
0x18002573a  xor     r9d, r9d
0x18002573d  mov     [rsp+600h+var_5E0], 0; __int64
0x180025746  lea     r8, [rsp+600h+var_5D0]
0x18002574b  xor     edx, edx
0x18002574d  mov     rcx, rdi; lpszFileName
0x180025750  call    winreConvertDirNameToOffset
0x180025755  mov     ebx, eax
0x180025757  test    eax, eax
0x180025759  jz      short loc_18002579B
0x18002575b  mov     [rsp+600h+var_5D8], 9FEh
0x180025763  lea     r8, aFailedToConver_1; "failed to convert Windows directory to "...
0x18002576a  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180025771  mov     r9d, ebx
0x180025774  lea     rdx, aWinrerepairexS; "WinReRepairEx %s (0x%x) in file %S line"...
0x18002577b  mov     [rsp+600h+var_5E0], rax
0x180025780  mov     ecx, r13d
0x180025783  call    UnattendLogW
0x180025788  lea     rax, ??_7ReAgentConfig@@6B@; const ReAgentConfig::`vftable'
0x18002578f  mov     [rbp+500h+var_90], rax
0x180025796  jmp     loc_1800256A5
0x18002579b  mov     r9d, [rsp+600h+var_5B0]; unsigned int
0x1800257a0  lea     rax, [r14+26Ch]
0x1800257a7  mov     rdx, [r14+4E0h]; unsigned __int64
0x1800257ae  lea     r8, [rsp+600h+var_5AC]; struct _GUID *
0x1800257b3  lea     rcx, [rbp+500h+var_90]; this
0x1800257ba  mov     [rsp+600h+var_5E0], rax; unsigned __int16 *
0x1800257bf  call    ?SetWinreLocationPath@ReAgentConfig@@QEAAK_KPEAU_GUID@@KPEAG@Z; ReAgentConfig::SetWinreLocationPath(unsigned __int64,_GUID *,ulong,ushort *)
0x1800257c4  mov     ebx, eax
0x1800257c6  test    eax, eax
0x1800257c8  jz      short loc_1800257DB
0x1800257ca  mov     [rsp+600h+var_5D8], 0A05h
0x1800257d2  lea     r8, aFailedToSetDis; "failed to set disk ID and Signature"
0x1800257d9  jmp     short loc_18002576A
0x1800257db  test    rsi, rsi
0x1800257de  jz      short loc_1800257FC
0x1800257e0  lea     rdx, aUpdateWinreGui; "Update WinRE GUID"
0x1800257e7  xor     ecx, ecx
0x1800257e9  call    UnattendLogW
0x1800257ee  mov     rax, [rbp+500h+var_50]
0x1800257f5  movups  xmm0, xmmword ptr [rsi]
0x1800257f8  movdqu  xmmword ptr [rax], xmm0
0x1800257fc  lea     rcx, [rbp+500h+var_90]; this
0x180025803  call    ?Update@ReAgentXMLParser@@QEAAKXZ; ReAgentXMLParser::Update(void)
0x180025808  mov     ebx, eax
0x18002580a  test    eax, eax
0x18002580c  jz      short loc_180025822
0x18002580e  mov     [rsp+600h+var_5D8], 0A10h
0x180025816  lea     r8, aFailedToUpdate_10; "Failed to update agent config"
0x18002581d  jmp     loc_18002576A
0x180025822  lea     rax, ??_7ReAgentConfig@@6B@; const ReAgentConfig::`vftable'
0x180025829  lea     rcx, [rbp+500h+var_90]; this
0x180025830  mov     [rbp+500h+var_90], rax
0x180025837  call    ??1ReAgentXMLParser@@UEAA@XZ; ReAgentXMLParser::~ReAgentXMLParser(void)
0x18002583c  test    r13b, r15b
0x18002583f  jz      short loc_1800258BA
0x180025841  lea     rdx, aRepairWinre; "Repair WinRE"
0x180025848  xor     ecx, ecx
0x18002584a  call    UnattendLogW
0x18002584f  test    rdi, rdi
0x180025852  jz      short loc_18002586C
0x180025854  lea     rdx, aRepairShouldBe; "Repair should be called with NULL Windo"...
0x18002585b  mov     ecx, 1
0x180025860  call    UnattendLogW
0x180025865  mov     ebx, 32h ; '2'
0x18002586a  jmp     short loc_1800258A4
0x18002586c  call    WinReRepair
0x180025871  mov     ebx, eax
0x180025873  test    eax, eax
0x180025875  jz      short loc_1800258BA
0x180025877  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002587e  mov     [rsp+600h+var_5D8], 0A1Ch
0x180025886  mov     r9d, ebx
0x180025889  mov     [rsp+600h+var_5E0], rax
0x18002588e  lea     r8, aFailedToRepair_0; "Failed to repair WinRE"
0x180025895  mov     ecx, r13d
0x180025898  lea     rdx, aWinrerepairexS; "WinReRepairEx %s (0x%x) in file %S line"...
0x18002589f  call    UnattendLogW
0x1800258a4  xor     edi, edi
0x1800258a6  lea     rdx, aFailedToRepair; "Failed to repair WinRE. Error: 0x%08X"
0x1800258ad  mov     r8d, ebx
0x1800258b0  lea     ecx, [rdi+1]
0x1800258b3  call    UnattendLogW
0x1800258b8  jmp     short loc_1800258CD
0x1800258ba  lea     rdx, aSuccessfullyRe; "Successfully Repair WinRE"
0x1800258c1  xor     ecx, ecx
0x1800258c3  mov     edi, 1
0x1800258c8  call    UnattendLogW
0x1800258cd  mov     r9d, ebx
0x1800258d0  lea     rdx, aExitWinrerepai; "Exit WinReRepairEx return value: %d, la"...
0x1800258d7  mov     r8d, edi
0x1800258da  xor     ecx, ecx
0x1800258dc  call    UnattendLogW
0x1800258e1  call    UnattendFinalizeLog
0x1800258e6  mov     ecx, ebx; dwErrCode
0x1800258e8  call    cs:__imp_SetLastError
0x1800258ee  mov     eax, edi
0x1800258f0  mov     rcx, [rbp+500h+var_40]
0x1800258f7  xor     rcx, rsp; StackCookie
0x1800258fa  call    __security_check_cookie
0x1800258ff  add     rsp, 5D0h
0x180025906  pop     r15
0x180025908  pop     r14
0x18002590a  pop     r13
0x18002590c  pop     rdi
0x18002590d  pop     rsi
0x18002590e  pop     rbx
0x18002590f  pop     rbp
0x180025910  retn
```
