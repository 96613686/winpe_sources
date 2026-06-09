# WinReGetConfigInternal

- ea: `0x18000f044`
- end: `0x18000f656`
- name: `WinReGetConfigInternal`
- size: `1554`
- prototype: ``
- caller_count: `10`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000efb0`
- `0x180019240`
- `0x18001f75c`
- `0x180023b50`
- `0x180023fa0`
- `0x180024df0`
- `0x180026670`
- `0x18002eca0`
- `0x18002f080`
- `0x18002fc20`

## callees

- `0x180002786`
- `0x1800059fc`
- `0x180006ed8`
- `0x180008b94`
- `0x18000edec`
- `0x18000f044`
- `0x1800109d0`
- `0x180011074`
- `0x180011974`
- `0x1800121b0`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000f29b`
- `KERNEL32!SetLastError` at `0x18000f29b`
- `ADVAPI32!RegQueryValueExW` at `0x18000f58e`
- `ADVAPI32!RegQueryValueExW` at `0x18000f5fa`
- `ADVAPI32!RegQueryValueExW` at `0x18000f58e`
- `ADVAPI32!RegQueryValueExW` at `0x18000f5fa`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f555`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f555`
- `ADVAPI32!RegCloseKey` at `0x18000f275`
- `ADVAPI32!RegCloseKey` at `0x18000f275`
- `ole32!CoTaskMemFree` at `0x18000f266`
- `ole32!CoTaskMemFree` at `0x18000f266`

## string_xrefs

- `0x18000f0d4`: `DisableUpdateEnhancedConfigInfo`
- `0x18000f0e2`: `DisableUpdateEnhancedConfigInfo`
- `0x18000f63c`: `The size of WINRE_CONFIG is unexpected`
- `0x18000f127`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x18000f18a`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x18000f233`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x18000f13b`: `failed to get config file path`
- `0x18000f147`: `WinReGetConfigInternal %s (0x%x) in file %S line %d`
- `0x18000f1aa`: `WinReGetConfigInternal %s (0x%x) in file %S line %d`
- `0x18000f242`: `WinReGetConfigInternal %s (0x%x) in file %S line %d`
- `0x18000f163`: `WinRE config file path: %s`
- `0x18000f19e`: `failed to init agent config`
- `0x18000f1f5`: `WinRE is installed at: %s`
- `0x18000f22c`: `failed to copy wim installed location`
- `0x18000f33e`: `failed to copy operation param`
- `0x18000f3a4`: `OS install location: %s`
- `0x18000f3d7`: `failed to copy setup directory location`
- `0x18000f42f`: `failed to copy custom image location`
- `0x18000f46d`: `failed to copy wim directory location`
- `0x18000f4f9`: `failed to copy downlevel winre location`
- `0x18000f287`: `winre get config failed with error code 0x%x`

## pseudocode

```c
__int64 __fastcall WinReGetConfigInternal(__int64 a1, int a2, __int64 a3)
{
  unsigned int v3; // r15d
  unsigned __int16 *v6; // r12
  __int64 v7; // r8
  DWORD ConfigFilePathFromWinDir; // eax
  DWORD v9; // r14d
  DWORD v10; // eax
  struct ReAgentConfigInfo *ConfigInfo; // rsi
  int v12; // ebx
  const wchar_t *v13; // r8
  int IsImageStaged; // eax
  __int16 v16; // r11
  int v17; // ecx
  int v18; // eax
  _WORD *v19; // r11
  const wchar_t *v20; // r8
  HKEY v21; // rcx
  DWORD v22; // ebx
  int lpcbData; // [rsp+28h] [rbp-81h]
  HKEY hKey; // [rsp+30h] [rbp-79h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-71h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-69h] BYREF
  DWORD Type; // [rsp+44h] [rbp-65h] BYREF
  BYTE Data[8]; // [rsp+48h] [rbp-61h] BYREF
  _QWORD v29[3]; // [rsp+50h] [rbp-59h] BYREF
  int v30; // [rsp+68h] [rbp-41h]
  int v31; // [rsp+6Ch] [rbp-3Dh]
  __int128 v32; // [rsp+70h] [rbp-39h]
  __int128 v33; // [rsp+80h] [rbp-29h]
  __int64 v34; // [rsp+90h] [rbp-19h]
  int v35; // [rsp+98h] [rbp-11h]
  BYTE Src[16]; // [rsp+A0h] [rbp-9h] BYREF
  __int128 v37; // [rsp+B0h] [rbp+7h]

  v31 = 2;
  v29[1] = 0;
  v29[2] = 0;
  v30 = 0;
  v32 = 0;
  v3 = 1;
  v33 = 0;
  v34 = 0;
  v29[0] = &ReAgentConfig::`vftable';
  v6 = 0;
  v35 = 0;
  pv = 0;
  *(_DWORD *)Data = 0;
  Type = 0;
  cbData = 0;
  hKey = 0;
  *(_OWORD *)Src = 0;
  v37 = 0;
  if ( a2 )
  {
    UnattendLogW(0, L"DisableUpdateEnhancedConfigInfo");
    UnattendLogW(0, L"DisableUpdateEnhancedConfigInfo");
    v35 = 1;
  }
  if ( a3 && *(_QWORD *)a3 == 3744 )
  {
    PrivateFreePartitionList(0);
    ConfigFilePathFromWinDir = winreGetConfigFilePathFromWinDir(a1, 1, v7, &pv);
    v9 = ConfigFilePathFromWinDir;
    if ( ConfigFilePathFromWinDir )
    {
      UnattendLogW(
        2,
        L"WinReGetConfigInternal %s (0x%x) in file %S line %d",
        L"failed to get config file path",
        ConfigFilePathFromWinDir,
        "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
        234);
      v6 = (unsigned __int16 *)pv;
      goto LABEL_13;
    }
    v6 = (unsigned __int16 *)pv;
    UnattendLogW(0, L"WinRE config file path: %s", pv);
    v10 = ReAgentConfig::Init((ReAgentConfig *)v29, v6, 1);
    v9 = v10;
    if ( v10 )
    {
      UnattendLogW(
        2,
        L"WinReGetConfigInternal %s (0x%x) in file %S line %d",
        L"failed to init agent config",
        v10,
        "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
        239);
      goto LABEL_13;
    }
    ConfigInfo = ReAgentXMLParser::GetConfigInfo((ReAgentXMLParser *)v29);
    memset_0((void *)(a3 + 8), 0, 0xE98u);
    *(_QWORD *)a3 = 3744;
    if ( *((_DWORD *)ConfigInfo + 1397) )
    {
      UnattendLogW(0, L"WinRE is installed at: %s", (char *)ConfigInfo + 16);
      *(_DWORD *)(a3 + 8) = 1;
      v12 = StringCchCopyW((unsigned __int16 *)(a3 + 632), 0x12Eu, (const unsigned __int16 *)ConfigInfo + 8);
      if ( v12 < 0 )
      {
        lpcbData = 259;
        v13 = L"failed to copy wim installed location";
LABEL_12:
        UnattendLogW(
          2,
          L"WinReGetConfigInternal %s (0x%x) in file %S line %d",
          v13,
          (unsigned int)v12,
          "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
          lpcbData);
        v9 = (unsigned __int16)v12;
        goto LABEL_13;
      }
    }
    IsImageStaged = winreIsImageStaged(0, ConfigInfo, a3 + 28);
    v16 = 0;
    *(_DWORD *)(a3 + 12) = IsImageStaged;
    if ( IsImageStaged )
    {
      UnattendLogW(0, L"WinRE is staged");
      v16 = 0;
    }
    v17 = *((_DWORD *)ConfigInfo + 1403);
    if ( (unsigned int)(v17 - 1) > 0x15 )
    {
      *(_DWORD *)(a3 + 2468) = 4;
    }
    else
    {
      *(_DWORD *)(a3 + 2468) = v17;
      v12 = StringCchCopyW((unsigned __int16 *)(a3 + 2472), 0x12Eu, (const unsigned __int16 *)ConfigInfo + 2808);
      if ( v12 < 0 )
      {
        lpcbData = 284;
        v13 = L"failed to copy operation param";
        goto LABEL_12;
      }
      *(_DWORD *)(a3 + 3076) = *((_DWORD *)ConfigInfo + 1555);
    }
    *(_OWORD *)(a3 + 1236) = *(_OWORD *)ConfigInfo;
    *(_DWORD *)(a3 + 16) = *((_DWORD *)ConfigInfo + 1398);
    *(_DWORD *)(a3 + 3740) = *((_DWORD *)ConfigInfo + 1869);
    *(_DWORD *)(a3 + 20) = *((_DWORD *)ConfigInfo + 1399);
    *(_DWORD *)(a3 + 24) = *((_DWORD *)ConfigInfo + 1400);
    if ( *((_WORD *)ConfigInfo + 1248) != v16 )
    {
      UnattendLogW(0, L"OS install location: %s", (char *)ConfigInfo + 2496);
      v18 = StringCchCopyW((unsigned __int16 *)(a3 + 1252), 0x12Eu, (const unsigned __int16 *)ConfigInfo + 1248);
      v16 = 0;
      v12 = v18;
      if ( v18 < 0 )
      {
        lpcbData = 313;
        v13 = L"failed to copy setup directory location";
        goto LABEL_12;
      }
    }
    *(_DWORD *)(a3 + 1856) = *((_DWORD *)ConfigInfo + 1395);
    if ( *((_WORD *)ConfigInfo + 1868) != v16 )
    {
      UnattendLogW(0, L"Custom image location: %s", (char *)ConfigInfo + 3736);
      v12 = StringCchCopyW((unsigned __int16 *)(a3 + 1860), 0x12Eu, (const unsigned __int16 *)ConfigInfo + 1868);
      if ( v12 < 0 )
      {
        lpcbData = 325;
        v13 = L"failed to copy custom image location";
        goto LABEL_12;
      }
      *(_DWORD *)(a3 + 2464) = *((_DWORD *)ConfigInfo + 1396);
    }
    v12 = StringCchCopyW((unsigned __int16 *)(a3 + 28), 0x12Eu, (const unsigned __int16 *)ConfigInfo + 628);
    if ( v12 < 0 )
    {
      lpcbData = 332;
      v13 = L"failed to copy wim directory location";
      goto LABEL_12;
    }
    if ( v19 && *v19 )
      UnattendLogW(0, L"Wim dir location: %s", v19);
    *(_DWORD *)(a3 + 3080) = *((_DWORD *)ConfigInfo + 1556);
    *(_DWORD *)(a3 + 3084) = *((_DWORD *)ConfigInfo + 1402);
    *(_DWORD *)(a3 + 3088) = *((_DWORD *)ConfigInfo + 1557);
    if ( *((_WORD *)ConfigInfo + 3116) )
    {
      UnattendLogW(0, L"Downlevel WinRE location: %s", (char *)ConfigInfo + 6232);
      v12 = StringCchCopyW((unsigned __int16 *)(a3 + 3132), 0x12Eu, (const unsigned __int16 *)ConfigInfo + 3116);
      if ( v12 < 0 )
      {
        lpcbData = 351;
        v13 = L"failed to copy downlevel winre location";
        goto LABEL_12;
      }
    }
    v20 = L"TRUE";
    *(_DWORD *)(a3 + 3736) = *((_DWORD *)ConfigInfo + 1868);
    if ( !*((_DWORD *)ConfigInfo + 1868) )
      v20 = L"FALSE";
    UnattendLogW(0, L"System is WimBoot: %s", v20);
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Reliability\\WinRE",
            0,
            1u,
            &hKey) )
    {
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"WimValidated", 0, &Type, Data, &cbData)
        && Type == 4
        && cbData == 4
        && *(_DWORD *)Data == 1 )
      {
        UnattendLogW(0, L"WinRE image validated");
        v21 = hKey;
        *(_DWORD *)(a3 + 3092) = 1;
        cbData = 32;
        if ( !RegQueryValueExW(v21, L"WimHash", 0, &Type, Src, &cbData) && Type == 3 )
        {
          v22 = cbData;
          if ( cbData <= 0x20 )
          {
            memcpy_0((void *)(a3 + 3096), Src, cbData);
            *(_DWORD *)(a3 + 3128) = v22;
          }
        }
      }
    }
  }
  else
  {
    UnattendLogW(1, L"The size of WINRE_CONFIG is unexpected");
    v9 = 87;
  }
LABEL_13:
  if ( v6 )
    CoTaskMemFree(v6);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v9 )
  {
    UnattendLogW(2, L"winre get config failed with error code 0x%x", v9);
    SetLastError(v9);
    v3 = 0;
  }
  v29[0] = &ReAgentConfig::`vftable';
  ReAgentXMLParser::~ReAgentXMLParser((ReAgentXMLParser *)v29);
  return v3;
}

```

## disassembly

```asm
0x18000f044  mov     [rsp-8+arg_8], rbx
0x18000f049  push    rbp
0x18000f04a  push    rsi
0x18000f04b  push    rdi
0x18000f04c  push    r12
0x18000f04e  push    r13
0x18000f050  push    r14
0x18000f052  push    r15
0x18000f054  lea     rbp, [rsp-27h]
0x18000f059  sub     rsp, 0D0h
0x18000f060  mov     rax, cs:__security_cookie
0x18000f067  xor     rax, rsp
0x18000f06a  mov     [rbp+57h+var_40], rax
0x18000f06e  xor     r13d, r13d
0x18000f071  mov     [rbp+57h+var_94], 2
0x18000f078  mov     [rbp+57h+var_A8], r13
0x18000f07c  xorps   xmm0, xmm0
0x18000f07f  mov     [rbp+57h+var_A0], r13
0x18000f083  xorps   xmm1, xmm1
0x18000f086  mov     [rbp+57h+var_98], r13d
0x18000f08a  lea     rsi, ??_7ReAgentConfig@@6B@; const ReAgentConfig::`vftable'
0x18000f091  movdqa  [rbp+57h+var_90], xmm0
0x18000f096  lea     r15d, [r13+1]
0x18000f09a  movdqa  [rbp+57h+var_80], xmm1
0x18000f09f  mov     rdi, r8
0x18000f0a2  mov     [rbp+57h+var_70], r13
0x18000f0a6  mov     rbx, rcx
0x18000f0a9  mov     [rbp+57h+var_B0], rsi
0x18000f0ad  mov     r12d, r13d
0x18000f0b0  mov     [rbp+57h+var_68], r13d
0x18000f0b4  mov     [rbp+57h+pv], r13
0x18000f0b8  mov     dword ptr [rbp+57h+Data], r13d
0x18000f0bc  mov     [rbp+57h+Type], r13d
0x18000f0c0  mov     [rbp+57h+cbData], r13d
0x18000f0c4  mov     [rbp+57h+hKey], r13
0x18000f0c8  movups  xmmword ptr [rbp+57h+Src], xmm0
0x18000f0cc  movups  [rbp+57h+var_50], xmm0
0x18000f0d0  test    edx, edx
0x18000f0d2  jz      short loc_18000F0F4
0x18000f0d4  lea     rdx, aDisableupdatee; "DisableUpdateEnhancedConfigInfo"
0x18000f0db  xor     ecx, ecx
0x18000f0dd  call    UnattendLogW
0x18000f0e2  lea     rdx, aDisableupdatee; "DisableUpdateEnhancedConfigInfo"
0x18000f0e9  xor     ecx, ecx
0x18000f0eb  call    UnattendLogW
0x18000f0f0  mov     [rbp+57h+var_68], r15d
0x18000f0f4  test    rdi, rdi
0x18000f0f7  jz      loc_18000F63C
0x18000f0fd  cmp     qword ptr [rdi], 0EA0h
0x18000f104  jnz     loc_18000F63C
0x18000f10a  xor     ecx, ecx; pv
0x18000f10c  call    PrivateFreePartitionList
0x18000f111  lea     r9, [rbp+57h+pv]
0x18000f115  mov     edx, r15d
0x18000f118  mov     rcx, rbx
0x18000f11b  call    winreGetConfigFilePathFromWinDir
0x18000f120  mov     r14d, eax
0x18000f123  test    eax, eax
0x18000f125  jz      short loc_18000F15F
0x18000f127  lea     rcx, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x18000f12e  mov     dword ptr [rsp+100h+lpcbData], 0EAh
0x18000f136  mov     [rsp+100h+phkResult], rcx
0x18000f13b  lea     r8, aFailedToGetCon_3; "failed to get config file path"
0x18000f142  mov     ecx, 2
0x18000f147  lea     rdx, aWinregetconfig_1; "WinReGetConfigInternal %s (0x%x) in fil"...
0x18000f14e  mov     r9d, eax
0x18000f151  call    UnattendLogW
0x18000f156  mov     r12, [rbp+57h+pv]
0x18000f15a  jmp     loc_18000F25E
0x18000f15f  mov     r12, [rbp+57h+pv]
0x18000f163  lea     rdx, aWinreConfigFil; "WinRE config file path: %s"
0x18000f16a  mov     r8, r12
0x18000f16d  xor     ecx, ecx
0x18000f16f  call    UnattendLogW
0x18000f174  mov     r8d, r15d; int
0x18000f177  lea     rcx, [rbp+57h+var_B0]; this
0x18000f17b  mov     rdx, r12; unsigned __int16 *
0x18000f17e  call    ?Init@ReAgentConfig@@UEAAKPEAGH@Z; ReAgentConfig::Init(ushort *,int)
0x18000f183  mov     r14d, eax
0x18000f186  test    eax, eax
0x18000f188  jz      short loc_18000F1BE
0x18000f18a  lea     rcx, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x18000f191  mov     dword ptr [rsp+100h+lpcbData], 0EFh
0x18000f199  mov     [rsp+100h+phkResult], rcx
0x18000f19e  lea     r8, aFailedToInitAg_2; "failed to init agent config"
0x18000f1a5  mov     ecx, 2
0x18000f1aa  lea     rdx, aWinregetconfig_1; "WinReGetConfigInternal %s (0x%x) in fil"...
0x18000f1b1  mov     r9d, eax
0x18000f1b4  call    UnattendLogW
0x18000f1b9  jmp     loc_18000F25E
0x18000f1be  lea     rcx, [rbp+57h+var_B0]; this
0x18000f1c2  call    ?GetConfigInfo@ReAgentXMLParser@@QEAAPEAUReAgentConfigInfo@@XZ; ReAgentXMLParser::GetConfigInfo(void)
0x18000f1c7  lea     rcx, [rdi+8]; void *
0x18000f1cb  xor     edx, edx; Val
0x18000f1cd  mov     r8d, 0E98h; Size
0x18000f1d3  mov     rsi, rax
0x18000f1d6  call    memset_0
0x18000f1db  mov     qword ptr [rdi], 0EA0h
0x18000f1e2  cmp     [rsi+15D4h], r13d
0x18000f1e9  jz      loc_18000F2DB
0x18000f1ef  lea     r8, [rsi+10h]
0x18000f1f3  xor     ecx, ecx
0x18000f1f5  lea     rdx, aWinreIsInstall_0; "WinRE is installed at: %s"
0x18000f1fc  call    UnattendLogW
0x18000f201  lea     rcx, [rdi+278h]; unsigned __int16 *
0x18000f208  mov     [rdi+8], r15d
0x18000f20c  lea     r8, [rsi+10h]; unsigned __int16 *
0x18000f210  mov     edx, 12Eh; unsigned __int64
0x18000f215  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f21a  mov     ebx, eax
0x18000f21c  test    eax, eax
0x18000f21e  jns     loc_18000F2DB
0x18000f224  mov     dword ptr [rsp+100h+lpcbData], 103h
0x18000f22c  lea     r8, aFailedToCopyWi_6; "failed to copy wim installed location"
0x18000f233  lea     rcx, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x18000f23a  mov     r9d, ebx
0x18000f23d  mov     [rsp+100h+phkResult], rcx
0x18000f242  lea     rdx, aWinregetconfig_1; "WinReGetConfigInternal %s (0x%x) in fil"...
0x18000f249  mov     ecx, 2
0x18000f24e  call    UnattendLogW
0x18000f253  movzx   r14d, bx
0x18000f257  lea     rsi, ??_7ReAgentConfig@@6B@; const ReAgentConfig::`vftable'
0x18000f25e  test    r12, r12
0x18000f261  jz      short loc_18000F26C
0x18000f263  mov     rcx, r12; pv
0x18000f266  call    cs:__imp_CoTaskMemFree
0x18000f26c  mov     rcx, [rbp+57h+hKey]; hKey
0x18000f270  test    rcx, rcx
0x18000f273  jz      short loc_18000F27F
0x18000f275  call    cs:__imp_RegCloseKey
0x18000f27b  mov     [rbp+57h+hKey], r13
0x18000f27f  test    r14d, r14d
0x18000f282  jz      short loc_18000F2A4
0x18000f284  mov     r8d, r14d
0x18000f287  lea     rdx, aWinreGetConfig; "winre get config failed with error code"...
0x18000f28e  mov     ecx, 2
0x18000f293  call    UnattendLogW
0x18000f298  mov     ecx, r14d; dwErrCode
0x18000f29b  call    cs:__imp_SetLastError
0x18000f2a1  mov     r15d, r13d
0x18000f2a4  lea     rcx, [rbp+57h+var_B0]; this
0x18000f2a8  mov     [rbp+57h+var_B0], rsi
0x18000f2ac  call    ??1ReAgentXMLParser@@UEAA@XZ; ReAgentXMLParser::~ReAgentXMLParser(void)
0x18000f2b1  mov     eax, r15d
0x18000f2b4  mov     rcx, [rbp+57h+var_40]
0x18000f2b8  xor     rcx, rsp; StackCookie
0x18000f2bb  call    __security_check_cookie
0x18000f2c0  mov     rbx, [rsp+100h+arg_8]
0x18000f2c8  add     rsp, 0D0h
0x18000f2cf  pop     r15
0x18000f2d1  pop     r14
0x18000f2d3  pop     r13
0x18000f2d5  pop     r12
0x18000f2d7  pop     rdi
0x18000f2d8  pop     rsi
0x18000f2d9  pop     rbp
0x18000f2da  retn
0x18000f2db  lea     r8, [rdi+1Ch]
0x18000f2df  mov     rdx, rsi
0x18000f2e2  xor     ecx, ecx
0x18000f2e4  call    winreIsImageStaged
0x18000f2e9  xor     r11d, r11d
0x18000f2ec  mov     [rdi+0Ch], eax
0x18000f2ef  test    eax, eax
0x18000f2f1  jz      short loc_18000F304
0x18000f2f3  lea     rdx, aWinreIsStaged; "WinRE is staged"
0x18000f2fa  xor     ecx, ecx
0x18000f2fc  call    UnattendLogW
0x18000f301  xor     r11d, r11d
0x18000f304  mov     ecx, [rsi+15ECh]
0x18000f30a  lea     eax, [rcx-1]
0x18000f30d  cmp     eax, 15h
0x18000f310  ja      short loc_18000F358
0x18000f312  mov     [rdi+9A4h], ecx
0x18000f318  lea     r8, [rsi+15F0h]; unsigned __int16 *
0x18000f31f  lea     rcx, [rdi+9A8h]; unsigned __int16 *
0x18000f326  mov     edx, 12Eh; unsigned __int64
0x18000f32b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f330  mov     ebx, eax
0x18000f332  test    eax, eax
0x18000f334  jns     short loc_18000F34A
0x18000f336  mov     dword ptr [rsp+100h+lpcbData], 11Ch
0x18000f33e  lea     r8, aFailedToCopyOp; "failed to copy operation param"
0x18000f345  jmp     loc_18000F233
0x18000f34a  mov     eax, [rsi+184Ch]
0x18000f350  mov     [rdi+0C04h], eax
0x18000f356  jmp     short loc_18000F362
0x18000f358  mov     dword ptr [rdi+9A4h], 4
0x18000f362  movups  xmm0, xmmword ptr [rsi]
0x18000f365  lea     rbx, [rsi+9C0h]
0x18000f36c  movdqu  xmmword ptr [rdi+4D4h], xmm0
0x18000f374  mov     eax, [rsi+15D8h]
0x18000f37a  mov     [rdi+10h], eax
0x18000f37d  mov     eax, [rsi+1D34h]
0x18000f383  mov     [rdi+0E9Ch], eax
0x18000f389  mov     eax, [rsi+15DCh]
0x18000f38f  mov     [rdi+14h], eax
0x18000f392  mov     eax, [rsi+15E0h]
0x18000f398  mov     [rdi+18h], eax
0x18000f39b  cmp     [rbx], r11w
0x18000f39f  jz      short loc_18000F3E3
0x18000f3a1  mov     r8, rbx
0x18000f3a4  lea     rdx, aOsInstallLocat; "OS install location: %s"
0x18000f3ab  xor     ecx, ecx
0x18000f3ad  call    UnattendLogW
0x18000f3b2  lea     rcx, [rdi+4E4h]; unsigned __int16 *
0x18000f3b9  mov     r8, rbx; unsigned __int16 *
0x18000f3bc  mov     edx, 12Eh; unsigned __int64
0x18000f3c1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f3c6  xor     r11d, r11d
0x18000f3c9  mov     ebx, eax
0x18000f3cb  test    eax, eax
0x18000f3cd  jns     short loc_18000F3E3
0x18000f3cf  mov     dword ptr [rsp+100h+lpcbData], 139h
0x18000f3d7  lea     r8, aFailedToCopySe; "failed to copy setup directory location"
0x18000f3de  jmp     loc_18000F233
0x18000f3e3  mov     eax, [rsi+15CCh]
0x18000f3e9  lea     rbx, [rsi+0E98h]
0x18000f3f0  mov     [rdi+740h], eax
0x18000f3f6  cmp     [rbx], r11w
0x18000f3fa  jz      short loc_18000F447
0x18000f3fc  mov     r8, rbx
0x18000f3ff  lea     rdx, aCustomImageLoc; "Custom image location: %s"
0x18000f406  xor     ecx, ecx
0x18000f408  call    UnattendLogW
0x18000f40d  lea     rcx, [rdi+744h]; unsigned __int16 *
0x18000f414  mov     r8, rbx; unsigned __int16 *
0x18000f417  mov     edx, 12Eh; unsigned __int64
0x18000f41c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f421  mov     ebx, eax
0x18000f423  test    eax, eax
0x18000f425  jns     short loc_18000F43B
0x18000f427  mov     dword ptr [rsp+100h+lpcbData], 145h
0x18000f42f  lea     r8, aFailedToCopyCu; "failed to copy custom image location"
0x18000f436  jmp     loc_18000F233
0x18000f43b  mov     eax, [rsi+15D0h]
0x18000f441  mov     [rdi+9A0h], eax
0x18000f447  lea     r11, [rsi+4E8h]
0x18000f44e  mov     edx, 12Eh; unsigned __int64
0x18000f453  mov     r8, r11; unsigned __int16 *
0x18000f456  lea     rcx, [rdi+1Ch]; unsigned __int16 *
0x18000f45a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f45f  mov     ebx, eax
0x18000f461  test    eax, eax
0x18000f463  jns     short loc_18000F479
0x18000f465  mov     dword ptr [rsp+100h+lpcbData], 14Ch
0x18000f46d  lea     r8, aFailedToCopyWi_4; "failed to copy wim directory location"
0x18000f474  jmp     loc_18000F233
0x18000f479  test    r11, r11
0x18000f47c  jz      short loc_18000F495
0x18000f47e  cmp     [r11], r13w
0x18000f482  jz      short loc_18000F495
0x18000f484  mov     r8, r11
0x18000f487  lea     rdx, aWimDirLocation; "Wim dir location: %s"
0x18000f48e  xor     ecx, ecx
0x18000f490  call    UnattendLogW
0x18000f495  mov     eax, [rsi+1850h]
0x18000f49b  lea     rbx, [rsi+1858h]
0x18000f4a2  mov     [rdi+0C08h], eax
0x18000f4a8  mov     eax, [rsi+15E8h]
0x18000f4ae  mov     [rdi+0C0Ch], eax
0x18000f4b4  mov     eax, [rsi+1854h]
0x18000f4ba  mov     [rdi+0C10h], eax
0x18000f4c0  cmp     [rbx], r13w
0x18000f4c4  jz      short loc_18000F505
0x18000f4c6  mov     r8, rbx
0x18000f4c9  lea     rdx, aDownlevelWinre_1; "Downlevel WinRE location: %s"
0x18000f4d0  xor     ecx, ecx
0x18000f4d2  call    UnattendLogW
0x18000f4d7  lea     rcx, [rdi+0C3Ch]; unsigned __int16 *
0x18000f4de  mov     r8, rbx; unsigned __int16 *
0x18000f4e1  mov     edx, 12Eh; unsigned __int64
0x18000f4e6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f4eb  mov     ebx, eax
0x18000f4ed  test    eax, eax
0x18000f4ef  jns     short loc_18000F505
0x18000f4f1  mov     dword ptr [rsp+100h+lpcbData], 15Fh
0x18000f4f9  lea     r8, aFailedToCopyDo; "failed to copy downlevel winre location"
0x18000f500  jmp     loc_18000F233
0x18000f505  mov     eax, [rsi+1D30h]
0x18000f50b  lea     r8, aTrue_0; "TRUE"
0x18000f512  mov     [rdi+0E98h], eax
0x18000f518  lea     rdx, aSystemIsWimboo; "System is WimBoot: %s"
0x18000f51f  cmp     [rsi+1D30h], r13d
0x18000f526  lea     rax, aFalse_0; "FALSE"
0x18000f52d  cmovz   r8, rax
0x18000f531  xor     ecx, ecx
0x18000f533  call    UnattendLogW
0x18000f538  lea     rax, [rbp+57h+hKey]
0x18000f53c  mov     r9d, r15d; samDesired
0x18000f53f  xor     r8d, r8d; ulOptions
0x18000f542  mov     [rsp+100h+phkResult], rax; phkResult
0x18000f547  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000f54e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f555  call    cs:__imp_RegOpenKeyExW
0x18000f55b  test    eax, eax
0x18000f55d  jnz     loc_18000F257
0x18000f563  mov     rcx, [rbp+57h+hKey]; hKey
0x18000f567  lea     rax, [rbp+57h+cbData]
0x18000f56b  mov     [rsp+100h+lpcbData], rax; lpcbData
  ... truncated ...
```
