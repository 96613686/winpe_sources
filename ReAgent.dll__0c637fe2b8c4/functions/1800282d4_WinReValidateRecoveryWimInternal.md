# WinReValidateRecoveryWimInternal

- ea: `0x1800282d4`
- end: `0x18002876e`
- name: `WinReValidateRecoveryWimInternal`
- size: `1178`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180028270`
- `0x1800295a0`

## callees

- `0x180001f54`
- `0x1800059fc`
- `0x18000c6c0`
- `0x18000c6f0`
- `0x1800109d0`
- `0x180011974`
- `0x18001fbc0`
- `0x1800282d4`
- `0x180029ee4`
- `0x180029f9c`
- `0x18004d3a0`
- `0x18004f8d0`
- `0x18005cee2`
- `0x18005cf30`
- `0x18005f010`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x180028331`
- `KERNEL32!GetTickCount64` at `0x18002870c`
- `KERNEL32!GetTickCount64` at `0x180028331`
- `KERNEL32!GetTickCount64` at `0x18002870c`
- `KERNEL32!SetLastError` at `0x18002873e`
- `KERNEL32!SetLastError` at `0x18002873e`
- `ADVAPI32!RegOpenKeyExW` at `0x1800285be`
- `ADVAPI32!RegOpenKeyExW` at `0x1800285be`
- `ADVAPI32!RegSetValueExW` at `0x180028602`
- `ADVAPI32!RegSetValueExW` at `0x180028641`
- `ADVAPI32!RegSetValueExW` at `0x180028602`
- `ADVAPI32!RegSetValueExW` at `0x180028641`
- `ADVAPI32!RegCloseKey` at `0x180028701`
- `ADVAPI32!RegCloseKey` at `0x180028701`
- `ole32!CoTaskMemFree` at `0x1800286d9`
- `ole32!CoTaskMemFree` at `0x1800286d9`

## string_xrefs

- `0x180028359`: `failed to get config file path`
- `0x1800283f8`: `failed to init agent config`
- `0x180028367`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180028698`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180028689`: `failed to append path`
- `0x180028670`: `Failed to publish the configuration change notification: 0x%x`
- `0x180028415`: `Failed to find winre.wim because WinRE is not installed.`
- `0x1800285d2`: `failed to open key`

## pseudocode

```c
__int64 WinReValidateRecoveryWimInternal()
{
  ULONGLONG TickCount64; // r12
  __int64 v1; // r8
  unsigned int ConfigFilePathFromWinDir; // eax
  signed int DoesFileExist; // ebx
  ReAgentXMLParser *v4; // rdi
  const wchar_t *v5; // r8
  __int64 v6; // r9
  ReAgentXMLParser *v7; // rax
  unsigned __int16 *v8; // rdx
  struct ReAgentConfigInfo *ConfigInfo; // rax
  const unsigned __int16 *v10; // rsi
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  const unsigned __int16 *v13; // r8
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  struct _WNF_TYPE_ID *v17; // rdx
  unsigned int v18; // r9d
  unsigned int v19; // eax
  ULONGLONG v20; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v24; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  BYTE Data[4]; // [rsp+48h] [rbp-B8h] BYREF
  int v28; // [rsp+4Ch] [rbp-B4h] BYREF
  BYTE v29[32]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v30; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v31[606]; // [rsp+72h] [rbp-8Eh] BYREF

  pv = 0;
  v30 = 0;
  memset_0(v31, 0, 0x25Au);
  hKey = 0;
  *(_DWORD *)Data = 0;
  v28 = 3;
  TickCount64 = GetTickCount64();
  ConfigFilePathFromWinDir = winreGetConfigFilePathFromWinDir(0, 0, v1, &pv);
  DoesFileExist = ConfigFilePathFromWinDir;
  if ( ConfigFilePathFromWinDir )
  {
    v4 = 0;
    cbData = 3826;
    v5 = L"failed to get config file path";
LABEL_3:
    v6 = ConfigFilePathFromWinDir;
LABEL_4:
    UnattendLogW(
      2,
      L"WinReValidateRecoveryWimInternal %s (0x%x) in file %S line %d",
      v5,
      v6,
      "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
      cbData);
    goto LABEL_44;
  }
  v7 = (ReAgentXMLParser *)operator new(0x50u);
  v4 = v7;
  if ( !v7 )
  {
    DoesFileExist = 8;
    UnattendLogW(
      2,
      L"WinReValidateRecoveryWimInternal %s (0x%x) in file %S line %d",
      L"failed to allocate memory",
      8,
      "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
      3828);
    v4 = 0;
    goto LABEL_44;
  }
  v8 = (unsigned __int16 *)pv;
  *((_QWORD *)v7 + 1) = 0;
  *((_QWORD *)v7 + 2) = 0;
  *((_DWORD *)v7 + 6) = 0;
  *((_DWORD *)v7 + 7) = 2;
  *((_QWORD *)v7 + 4) = 0;
  *((_QWORD *)v7 + 5) = 0;
  *((_QWORD *)v7 + 6) = 0;
  *((_QWORD *)v7 + 7) = 0;
  *((_QWORD *)v7 + 8) = 0;
  *(_QWORD *)v7 = &ReAgentConfig::`vftable';
  *((_DWORD *)v7 + 18) = 0;
  ConfigFilePathFromWinDir = ReAgentConfig::Init(v7, v8, 1);
  DoesFileExist = ConfigFilePathFromWinDir;
  if ( ConfigFilePathFromWinDir )
  {
    cbData = 3831;
    v5 = L"failed to init agent config";
    goto LABEL_3;
  }
  ConfigInfo = ReAgentXMLParser::GetConfigInfo(v4);
  if ( !*((_DWORD *)ConfigInfo + 1397) )
  {
    UnattendLogW(0, L"Failed to find winre.wim because WinRE is not installed.");
    DoesFileExist = 1168;
    goto LABEL_44;
  }
  v10 = (const unsigned __int16 *)((char *)ConfigInfo + 16);
  DoesFileExist = Utils::DoesFileExist((const unsigned __int16 *)ConfigInfo + 8, L"Winre.wim");
  if ( DoesFileExist )
  {
    UnattendLogW(0, L"Winre.wim is available at %s\\%s", v10, L"Winre.wim");
    goto LABEL_44;
  }
  v24 = 0;
  if ( !v10 )
  {
    DoesFileExist = 87;
    goto LABEL_42;
  }
  DoesFileExist = StringCchLengthW(v10, 0x7FFFFFFFu, &v24);
  if ( DoesFileExist >= 0 )
  {
    if ( !v24 || (v13 = L"%s\\%s", v10[v24 - 1] == 92) )
      v13 = L"%s%s";
    DoesFileExist = StringCchPrintfW(&v30, 0x12Eu, v13, v10, L"Winre.wim");
    if ( DoesFileExist >= 0 )
      goto LABEL_26;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v12 = 15;
      goto LABEL_24;
    }
  }
  else
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v12 = 14;
LABEL_24:
      WPP_SF_d(v11[2], v12, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)DoesFileExist);
    }
  }
  DoesFileExist = (unsigned __int16)DoesFileExist;
  if ( (_WORD)DoesFileExist )
  {
LABEL_42:
    cbData = 3854;
    v5 = L"failed to append path";
    v6 = (unsigned int)DoesFileExist;
    goto LABEL_4;
  }
LABEL_26:
  ConfigFilePathFromWinDir = winreValidateWimFile(&v30);
  DoesFileExist = ConfigFilePathFromWinDir;
  if ( ConfigFilePathFromWinDir )
  {
    cbData = 3861;
    v5 = L"failed to validate trust";
    goto LABEL_3;
  }
  if ( *(_DWORD *)Data )
  {
    v14 = winreHashWimFile(&v30, v29);
    DoesFileExist = v14;
    if ( v14 )
    {
      UnattendLogW(0, L"Failed to generate hash of winre.wim: 0x%x", v14);
    }
    else
    {
      ConfigFilePathFromWinDir = RegOpenKeyExW(
                                   HKEY_LOCAL_MACHINE,
                                   L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Reliability\\WinRE",
                                   0,
                                   2u,
                                   &hKey);
      DoesFileExist = ConfigFilePathFromWinDir;
      if ( ConfigFilePathFromWinDir )
      {
        cbData = 3888;
        v5 = L"failed to open key";
        goto LABEL_3;
      }
      v15 = RegSetValueExW(hKey, L"WimValidated", 0, 4u, Data, 4u);
      DoesFileExist = v15;
      if ( v15 )
      {
        UnattendLogW(0, L"Failed to store WIM file trusted state: 0x%x", v15);
      }
      else
      {
        v16 = RegSetValueExW(hKey, L"WimHash", 0, 3u, v29, 0x20u);
        DoesFileExist = v16;
        if ( v16 )
        {
          UnattendLogW(0, L"Failed to store WIM file hash: 0x%x", v16);
        }
        else
        {
          v19 = winrePublishWnfStateData(WNF_SRT_WINRE_CONFIGURATION_CHANGE, v17, &v28, v18, phkResult);
          DoesFileExist = v19;
          if ( v19 )
            UnattendLogW(0, L"Failed to publish the configuration change notification: 0x%x", v19);
        }
      }
    }
  }
  else
  {
    UnattendLogW(0, L"WinReValidateRecoveryWimInternal: The WIM file is not trusted");
    DoesFileExist = 1790;
  }
LABEL_44:
  if ( pv )
    CoTaskMemFree(pv);
  if ( v4 )
    (**(void (__fastcall ***)(ReAgentXMLParser *, __int64))v4)(v4, 1);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v20 = GetTickCount64();
  UnattendLogW(0, L"WinReValidateRecoveryWimInternal took %llu ms.", v20 - TickCount64);
  if ( !DoesFileExist )
    return 1;
  UnattendLogW(2, L"WinReValidateRecoveryWimInternal failed: 0x%x", (unsigned int)DoesFileExist);
  SetLastError(DoesFileExist);
  return 0;
}

```

## disassembly

```asm
0x1800282d4  push    rbp
0x1800282d6  push    rbx
0x1800282d7  push    rsi
0x1800282d8  push    rdi
0x1800282d9  push    r12
0x1800282db  push    r13
0x1800282dd  push    r14
0x1800282df  lea     rbp, [rsp-1E0h]
0x1800282e7  sub     rsp, 2E0h
0x1800282ee  mov     rax, cs:__security_cookie
0x1800282f5  xor     rax, rsp
0x1800282f8  mov     [rbp+210h+var_40], rax
0x1800282ff  xor     r13d, r13d
0x180028302  lea     rcx, [rsp+310h+var_29E]; void *
0x180028307  xor     edx, edx; Val
0x180028309  mov     [rsp+310h+pv], r13
0x18002830e  mov     r8d, 25Ah; Size
0x180028314  mov     [rsp+310h+var_2A0], r13w
0x18002831a  call    memset_0
0x18002831f  mov     [rsp+310h+hKey], r13
0x180028324  mov     dword ptr [rsp+310h+Data], r13d
0x180028329  mov     [rsp+310h+var_2C4], 3
0x180028331  call    cs:__imp_GetTickCount64
0x180028337  lea     r9, [rsp+310h+pv]
0x18002833c  xor     edx, edx
0x18002833e  xor     ecx, ecx
0x180028340  mov     r12, rax
0x180028343  call    winreGetConfigFilePathFromWinDir
0x180028348  mov     ebx, eax
0x18002834a  test    eax, eax
0x18002834c  jz      short loc_180028387
0x18002834e  mov     edi, r13d
0x180028351  mov     [rsp+310h+cbData], 0EF2h
0x180028359  lea     r8, aFailedToGetCon_3; "failed to get config file path"
0x180028360  lea     r14d, [r13+2]
0x180028364  mov     r9d, eax
0x180028367  lea     rcx, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002836e  mov     [rsp+310h+phkResult], rcx
0x180028373  lea     rdx, aWinrevalidater_3; "WinReValidateRecoveryWimInternal %s (0x"...
0x18002837a  mov     ecx, r14d
0x18002837d  call    UnattendLogW
0x180028382  jmp     loc_1800286CD
0x180028387  mov     ecx, 50h ; 'P'; Size
0x18002838c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180028391  mov     rdi, rax
0x180028394  mov     r14d, 2
0x18002839a  test    rax, rax
0x18002839d  jz      loc_180028698
0x1800283a3  mov     rdx, [rsp+310h+pv]
0x1800283a8  lea     r8d, [r14-1]
0x1800283ac  mov     [rax+8], r13
0x1800283b0  mov     rcx, rdi
0x1800283b3  mov     [rax+10h], r13
0x1800283b7  mov     [rax+18h], r13d
0x1800283bb  mov     [rax+1Ch], r14d
0x1800283bf  mov     [rax+20h], r13
0x1800283c3  mov     [rax+28h], r13
0x1800283c7  mov     [rax+30h], r13
0x1800283cb  mov     [rax+38h], r13
0x1800283cf  mov     [rax+40h], r13
0x1800283d3  lea     rax, ??_7ReAgentConfig@@6B@; const ReAgentConfig::`vftable'
0x1800283da  mov     [rdi], rax
0x1800283dd  mov     rax, [rax+8]
0x1800283e1  mov     [rdi+48h], r13d
0x1800283e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283ea  mov     ebx, eax
0x1800283ec  test    eax, eax
0x1800283ee  jz      short loc_180028404
0x1800283f0  mov     [rsp+310h+cbData], 0EF7h
0x1800283f8  lea     r8, aFailedToInitAg_2; "failed to init agent config"
0x1800283ff  jmp     loc_180028364
0x180028404  mov     rcx, rdi; this
0x180028407  call    ?GetConfigInfo@ReAgentXMLParser@@QEAAPEAUReAgentConfigInfo@@XZ; ReAgentXMLParser::GetConfigInfo(void)
0x18002840c  cmp     [rax+15D4h], r13d
0x180028413  jnz     short loc_18002842D
0x180028415  lea     rdx, aFailedToFindWi_0; "Failed to find winre.wim because WinRE "...
0x18002841c  xor     ecx, ecx
0x18002841e  call    UnattendLogW
0x180028423  mov     ebx, 490h
0x180028428  jmp     loc_1800286CD
0x18002842d  lea     rsi, [rax+10h]
0x180028431  mov     rcx, rsi; unsigned __int16 *
0x180028434  lea     rdx, aWinreWim; "Winre.wim"
0x18002843b  call    ?DoesFileExist@Utils@@SAKPEBG0@Z; Utils::DoesFileExist(ushort const *,ushort const *)
0x180028440  mov     ebx, eax
0x180028442  test    eax, eax
0x180028444  jz      short loc_180028463
0x180028446  lea     r9, aWinreWim; "Winre.wim"
0x18002844d  mov     r8, rsi
0x180028450  lea     rdx, aWinreWimIsAvai; "Winre.wim is available at %s\\%s"
0x180028457  xor     ecx, ecx
0x180028459  call    UnattendLogW
0x18002845e  jmp     loc_1800286CD
0x180028463  mov     [rsp+310h+var_2E0], r13
0x180028468  test    rsi, rsi
0x18002846b  jz      loc_18002867C
0x180028471  lea     r8, [rsp+310h+var_2E0]; unsigned __int64 *
0x180028476  mov     edx, 7FFFFFFFh; unsigned __int64
0x18002847b  mov     rcx, rsi; unsigned __int16 *
0x18002847e  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180028483  mov     ebx, eax
0x180028485  test    eax, eax
0x180028487  jns     short loc_1800284AD
0x180028489  mov     rcx, cs:WPP_GLOBAL_Control
0x180028490  lea     rax, WPP_GLOBAL_Control
0x180028497  cmp     rcx, rax
0x18002849a  jz      loc_180028522
0x1800284a0  test    [rcx+1Ch], r14b
0x1800284a4  jz      short loc_180028522
0x1800284a6  mov     edx, 0Eh
0x1800284ab  jmp     short loc_18002850F
0x1800284ad  mov     rax, [rsp+310h+var_2E0]
0x1800284b2  test    rax, rax
0x1800284b5  jz      short loc_1800284C6
0x1800284b7  cmp     word ptr [rsi+rax*2-2], 5Ch ; '\'
0x1800284bd  lea     r8, aSS_1; "%s\\%s"
0x1800284c4  jnz     short loc_1800284CD
0x1800284c6  lea     r8, aSS_2; "%s%s"
0x1800284cd  lea     rax, aWinreWim; "Winre.wim"
0x1800284d4  mov     r9, rsi
0x1800284d7  mov     edx, 12Eh; unsigned __int64
0x1800284dc  mov     [rsp+310h+phkResult], rax
0x1800284e1  lea     rcx, [rsp+310h+var_2A0]; unsigned __int16 *
0x1800284e6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800284eb  mov     ebx, eax
0x1800284ed  test    eax, eax
0x1800284ef  jns     short loc_18002852D
0x1800284f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800284f8  lea     rax, WPP_GLOBAL_Control
0x1800284ff  cmp     rcx, rax
0x180028502  jz      short loc_180028522
0x180028504  test    [rcx+1Ch], r14b
0x180028508  jz      short loc_180028522
0x18002850a  mov     edx, 0Fh
0x18002850f  mov     rcx, [rcx+10h]
0x180028513  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18002851a  mov     r9d, ebx
0x18002851d  call    WPP_SF_d
0x180028522  movzx   ebx, bx
0x180028525  test    ebx, ebx
0x180028527  jnz     loc_180028681
0x18002852d  lea     rdx, [rsp+310h+Data]
0x180028532  lea     rcx, [rsp+310h+var_2A0]; unsigned __int16 *
0x180028537  call    winreValidateWimFile
0x18002853c  mov     ebx, eax
0x18002853e  test    eax, eax
0x180028540  jz      short loc_180028556
0x180028542  mov     [rsp+310h+cbData], 0F15h
0x18002854a  lea     r8, aFailedToValida; "failed to validate trust"
0x180028551  jmp     loc_180028364
0x180028556  cmp     dword ptr [rsp+310h+Data], r13d
0x18002855b  jnz     short loc_180028575
0x18002855d  lea     rdx, aWinrevalidater_0; "WinReValidateRecoveryWimInternal: The W"...
0x180028564  xor     ecx, ecx
0x180028566  call    UnattendLogW
0x18002856b  mov     ebx, 6FEh
0x180028570  jmp     loc_1800286CD
0x180028575  lea     rdx, [rsp+310h+var_2C0]
0x18002857a  lea     rcx, [rsp+310h+var_2A0]
0x18002857f  call    winreHashWimFile
0x180028584  mov     ebx, eax
0x180028586  test    eax, eax
0x180028588  jz      short loc_1800285A0
0x18002858a  lea     rdx, aFailedToGenera; "Failed to generate hash of winre.wim: 0"...
0x180028591  mov     r8d, eax
0x180028594  xor     ecx, ecx
0x180028596  call    UnattendLogW
0x18002859b  jmp     loc_1800286CD
0x1800285a0  lea     rax, [rsp+310h+hKey]
0x1800285a5  mov     r9d, r14d; samDesired
0x1800285a8  xor     r8d, r8d; ulOptions
0x1800285ab  mov     [rsp+310h+phkResult], rax; phkResult
0x1800285b0  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800285b7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800285be  call    cs:__imp_RegOpenKeyExW
0x1800285c4  mov     ebx, eax
0x1800285c6  test    eax, eax
0x1800285c8  jz      short loc_1800285DE
0x1800285ca  mov     [rsp+310h+cbData], 0F30h
0x1800285d2  lea     r8, aFailedToOpenKe; "failed to open key"
0x1800285d9  jmp     loc_180028364
0x1800285de  mov     rcx, [rsp+310h+hKey]; hKey
0x1800285e3  lea     rax, [rsp+310h+Data]
0x1800285e8  mov     r9d, 4; dwType
0x1800285ee  lea     rdx, aWimvalidated_0; "WimValidated"
0x1800285f5  mov     [rsp+310h+cbData], r9d; cbData
0x1800285fa  xor     r8d, r8d; Reserved
0x1800285fd  mov     [rsp+310h+phkResult], rax; lpData
0x180028602  call    cs:__imp_RegSetValueExW
0x180028608  mov     ebx, eax
0x18002860a  test    eax, eax
0x18002860c  jz      short loc_18002861A
0x18002860e  lea     rdx, aFailedToStoreW_1; "Failed to store WIM file trusted state:"...
0x180028615  jmp     loc_180028591
0x18002861a  mov     rcx, [rsp+310h+hKey]; hKey
0x18002861f  lea     rax, [rsp+310h+var_2C0]
0x180028624  mov     [rsp+310h+cbData], 20h ; ' '; cbData
0x18002862c  lea     rdx, aWimhash_0; "WimHash"
0x180028633  mov     r9d, 3; dwType
0x180028639  mov     [rsp+310h+phkResult], rax; void *
0x18002863e  xor     r8d, r8d; Reserved
0x180028641  call    cs:__imp_RegSetValueExW
0x180028647  mov     ebx, eax
0x180028649  test    eax, eax
0x18002864b  jz      short loc_180028659
0x18002864d  lea     rdx, aFailedToStoreW_2; "Failed to store WIM file hash: 0x%x"
0x180028654  jmp     loc_180028591
0x180028659  mov     rcx, qword ptr cs:WNF_SRT_WINRE_CONFIGURATION_CHANGE.Data; struct _WNF_STATE_NAME
0x180028660  lea     r8, [rsp+310h+var_2C4]; void *
0x180028665  call    ?winrePublishWnfStateData@@YAKU_WNF_STATE_NAME@@PEAU_WNF_TYPE_ID@@PEBXKQEAX@Z; winrePublishWnfStateData(_WNF_STATE_NAME,_WNF_TYPE_ID *,void const *,ulong,void * const)
0x18002866a  mov     ebx, eax
0x18002866c  test    eax, eax
0x18002866e  jz      short loc_1800286CD
0x180028670  lea     rdx, aFailedToPublis; "Failed to publish the configuration cha"...
0x180028677  jmp     loc_180028591
0x18002867c  mov     ebx, 57h ; 'W'
0x180028681  mov     [rsp+310h+cbData], 0F0Eh
0x180028689  lea     r8, aFailedToAppend_7; "failed to append path"
0x180028690  mov     r9d, ebx
0x180028693  jmp     loc_180028367
0x180028698  lea     rcx, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002869f  mov     [rsp+310h+cbData], 0EF4h
0x1800286a7  mov     [rsp+310h+phkResult], rcx
0x1800286ac  lea     r8, aFailedToAlloca; "failed to allocate memory"
0x1800286b3  mov     ebx, 8
0x1800286b8  lea     rdx, aWinrevalidater_3; "WinReValidateRecoveryWimInternal %s (0x"...
0x1800286bf  mov     ecx, r14d
0x1800286c2  mov     r9d, ebx
0x1800286c5  call    UnattendLogW
0x1800286ca  mov     rdi, r13
0x1800286cd  cmp     [rsp+310h+pv], r13
0x1800286d2  jz      short loc_1800286DF
0x1800286d4  mov     rcx, [rsp+310h+pv]; pv
0x1800286d9  call    cs:__imp_CoTaskMemFree
0x1800286df  test    rdi, rdi
0x1800286e2  jz      short loc_1800286F7
0x1800286e4  mov     rax, [rdi]
0x1800286e7  mov     edx, 1
0x1800286ec  mov     rcx, rdi
0x1800286ef  mov     rax, [rax]
0x1800286f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800286f7  mov     rcx, [rsp+310h+hKey]; hKey
0x1800286fc  test    rcx, rcx
0x1800286ff  jz      short loc_18002870C
0x180028701  call    cs:__imp_RegCloseKey
0x180028707  mov     [rsp+310h+hKey], r13
0x18002870c  call    cs:__imp_GetTickCount64
0x180028712  lea     rdx, aWinrevalidater_2; "WinReValidateRecoveryWimInternal took %"...
0x180028719  xor     ecx, ecx
0x18002871b  sub     rax, r12
0x18002871e  mov     r8, rax
0x180028721  call    UnattendLogW
0x180028726  test    ebx, ebx
0x180028728  jz      short loc_180028748
0x18002872a  mov     r8d, ebx
0x18002872d  lea     rdx, aWinrevalidater_1; "WinReValidateRecoveryWimInternal failed"...
0x180028734  mov     ecx, r14d
0x180028737  call    UnattendLogW
0x18002873c  mov     ecx, ebx; dwErrCode
0x18002873e  call    cs:__imp_SetLastError
0x180028744  xor     eax, eax
0x180028746  jmp     short loc_18002874D
0x180028748  mov     eax, 1
0x18002874d  mov     rcx, [rbp+210h+var_40]
0x180028754  xor     rcx, rsp; StackCookie
0x180028757  call    __security_check_cookie
0x18002875c  add     rsp, 2E0h
0x180028763  pop     r14
0x180028765  pop     r13
0x180028767  pop     r12
0x180028769  pop     rdi
0x18002876a  pop     rsi
0x18002876b  pop     rbx
0x18002876c  pop     rbp
0x18002876d  retn
```
