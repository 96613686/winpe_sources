# winreUnInstallInternal(_GUID *,int,int)

- ea: `0x18001fd7c`
- end: `0x180020119`
- name: `?winreUnInstallInternal@@YAKPEAU_GUID@@HH@Z`
- size: `925`
- prototype: `unsigned int __fastcall(struct _GUID *, int, int)`
- caller_count: `7`
- callee_count: `19`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180017248`
- `0x1800174a0`
- `0x180018870`
- `0x18001aa00`
- `0x180020760`
- `0x180024ff0`
- `0x1800281c0`

## callees

- `0x1800059fc`
- `0x180008b94`
- `0x18000ed74`
- `0x1800109d0`
- `0x180011344`
- `0x180011974`
- `0x1800121b0`
- `0x1800145f4`
- `0x180014754`
- `0x180018838`
- `0x18001fd7c`
- `0x1800295a0`
- `0x1800296ec`
- `0x180030fcc`
- `0x1800310a0`
- `0x18003591c`
- `0x1800361ac`
- `0x18003a248`
- `0x18005cf30`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800200d4`
- `ole32!CoTaskMemFree` at `0x1800200d4`

## string_xrefs

- `0x18001fea5`: `DisableUpdateEnhancedConfigInfo`
- `0x18001fe82`: `failed to get config file path`
- `0x18001fede`: `failed to init agent config`
- `0x18001fe73`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x18001fee5`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180020030`: `failed to update agent config`
- `0x18001fe42`: `winreUnInstallInternalfailed, winPE is not supported: : 0x%x`
- `0x18001fe89`: `winreUnInstallInternal %s (0x%x) in file %S line %d`
- `0x18001fef4`: `winreUnInstallInternal %s (0x%x) in file %S line %d`
- `0x18001ff25`: `Winre is already disabled, nothing to do here`
- `0x18001ff67`: `failed to copy wim back`
- `0x18001ff73`: `WinRE uninstall step 1 succeeded: copy WIM file back to its staging location`
- `0x18001ff90`: `Failed to delete backup setting file: 0x%x.`
- `0x18001ffce`: `failed to set winre location path`
- `0x18002003c`: `WinRE uninstall step 2 succeeded: update agent config for BCD id, install state, schedule operation.`
- `0x18002006d`: `WinRE uninstall step 3 succeeded: unregister winre.wim from recovery BCD.`
- `0x18002008b`: `WinRE uninstall step 4 succeeded: remove recovery related sequence from BCD.`
- `0x1800200b4`: `WinRE uninstall step 5 completed with return value %s: remove validation task.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winreUnInstallInternal(struct _GUID *a1, int a2, __int64 a3)
{
  int v5; // r15d
  unsigned __int16 *v6; // rsi
  unsigned int v7; // eax
  unsigned int ConfigFilePathFromWinDir; // ebx
  const wchar_t *v9; // r8
  struct ReAgentConfigInfo *ConfigInfo; // rax
  struct ReAgentConfigInfo *v11; // rdi
  unsigned int v12; // eax
  ReAgentXMLParser *v13; // rcx
  unsigned int v14; // eax
  int v15; // eax
  const wchar_t *v16; // r8
  int v18; // [rsp+30h] [rbp-51h]
  unsigned __int16 *v19; // [rsp+40h] [rbp-41h] BYREF
  __int128 v20; // [rsp+48h] [rbp-39h] BYREF
  _QWORD v21[3]; // [rsp+58h] [rbp-29h] BYREF
  int v22; // [rsp+70h] [rbp-11h]
  int v23; // [rsp+74h] [rbp-Dh]
  __int128 v24; // [rsp+78h] [rbp-9h]
  __int128 v25; // [rsp+88h] [rbp+7h]
  ReAgentXMLParser *v26; // [rsp+98h] [rbp+17h]
  int v27; // [rsp+A0h] [rbp+1Fh]

  v5 = 0;
  v6 = 0;
  v19 = 0;
  v21[1] = 0;
  v21[2] = 0;
  v22 = 0;
  v23 = 2;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v21[0] = &ReAgentConfig::`vftable';
  v27 = 0;
  v20 = 0;
  if ( (_DWORD)a3 )
  {
    v7 = SetWinReOperationSyncKey();
    if ( v7 )
    {
      ConfigFilePathFromWinDir = 0;
      if ( v7 != 1152 )
        ConfigFilePathFromWinDir = v7;
      goto LABEL_40;
    }
    v5 = 1;
  }
  if ( a1 || !(unsigned int)winreIsWinPE() )
  {
    ConfigFilePathFromWinDir = winreGetConfigFilePathFromWinDir(0, 0, a3, &v19);
    if ( ConfigFilePathFromWinDir )
    {
      UnattendLogW(
        2,
        L"winreUnInstallInternal %s (0x%x) in file %S line %d",
        L"failed to get config file path",
        ConfigFilePathFromWinDir,
        "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
        1610,
        -2);
      v6 = v19;
    }
    else
    {
      if ( !a2 )
      {
        UnattendLogW(0, L"DisableUpdateEnhancedConfigInfo");
        v27 = 1;
      }
      v6 = v19;
      ConfigFilePathFromWinDir = ReAgentConfig::Init((ReAgentConfig *)v21, v19, 1);
      if ( ConfigFilePathFromWinDir )
      {
        v18 = 1621;
        v9 = L"failed to init agent config";
      }
      else
      {
        ConfigInfo = ReAgentXMLParser::GetConfigInfo((ReAgentXMLParser *)v21);
        v11 = ConfigInfo;
        v20 = *(_OWORD *)ConfigInfo;
        if ( !*((_DWORD *)ConfigInfo + 1397) )
        {
          UnattendLogW(0, L"Winre is already disabled, nothing to do here");
          if ( !ReAgentError )
            ReAgentError = 18;
          ConfigFilePathFromWinDir = 2;
          goto LABEL_36;
        }
        ConfigFilePathFromWinDir = winreCopyWIMBack(a1, (__int64)ConfigInfo);
        if ( ConfigFilePathFromWinDir )
        {
          v18 = 1647;
          v9 = L"failed to copy wim back";
        }
        else
        {
          UnattendLogW(0, L"WinRE uninstall step 1 succeeded: copy WIM file back to its staging location");
          v12 = winreDeleteBackupSettingFile(v11);
          if ( v12 )
            UnattendLogW(2, L"Failed to delete backup setting file: 0x%x.", v12);
          ConfigFilePathFromWinDir = ReAgentConfig::SetWinreLocationPath(
                                       (ReAgentConfig *)v21,
                                       0,
                                       &ZeroGuid,
                                       0,
                                       (unsigned __int16 *)&Default);
          if ( ConfigFilePathFromWinDir )
          {
            v18 = 1664;
            v9 = L"failed to set winre location path";
          }
          else
          {
            *(_OWORD *)v26 = xmmword_180070D08;
            ReAgentConfig::SetInstallState((ReAgentConfig *)v21, 0);
            v13 = v26;
            *((_DWORD *)v26 + 1403) = 4;
            ReAgentXMLParser::CopyPathInfo(v13, (unsigned __int16 *)&qword_180070D18, (unsigned __int16 *)v26 + 2808);
            ConfigFilePathFromWinDir = ReAgentXMLParser::Update((ReAgentXMLParser *)v21);
            if ( !ConfigFilePathFromWinDir )
            {
              UnattendLogW(
                0,
                L"WinRE uninstall step 2 succeeded: update agent config for BCD id, install state, schedule operation.");
              v14 = winreUnregisterFromRecoveryBCD(&v20);
              ConfigFilePathFromWinDir = v14;
              if ( v14 )
              {
                UnattendLogW(
                  2,
                  L"Failed to unregister Winre.wim from recovery BCD: 0x%x, not critical error and will be ignored.",
                  v14);
                ConfigFilePathFromWinDir = 0;
              }
              UnattendLogW(0, L"WinRE uninstall step 3 succeeded: unregister winre.wim from recovery BCD.");
              winreRemoveRecoverySequenceEx(&GUID_CURRENT_BOOT_ENTRY, &v20);
              UnattendLogW(0, L"WinRE uninstall step 4 succeeded: remove recovery related sequence from BCD.");
              v15 = winreConfigureValidationTask(0);
              v16 = L"TRUE";
              if ( !v15 )
                v16 = L"FALSE";
              UnattendLogW(0, L"WinRE uninstall step 5 completed with return value %s: remove validation task.", v16);
              goto LABEL_36;
            }
            v18 = 1670;
            v9 = L"failed to update agent config";
          }
        }
      }
      UnattendLogW(
        2,
        L"winreUnInstallInternal %s (0x%x) in file %S line %d",
        v9,
        ConfigFilePathFromWinDir,
        "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
        v18,
        -2);
    }
  }
  else
  {
    ConfigFilePathFromWinDir = 50;
    if ( !ReAgentError )
      ReAgentError = 10;
    UnattendLogW(1, L"winreUnInstallInternalfailed, winPE is not supported: : 0x%x", 50);
  }
LABEL_36:
  if ( v5 )
    RemoveWinReOperationSyncKey();
  if ( v6 )
    CoTaskMemFree(v6);
LABEL_40:
  v21[0] = &ReAgentConfig::`vftable';
  ReAgentXMLParser::~ReAgentXMLParser((ReAgentXMLParser *)v21);
  return ConfigFilePathFromWinDir;
}

```

## disassembly

```asm
0x18001fd7c  mov     rax, rsp
0x18001fd7f  push    rbp
0x18001fd80  push    rdi
0x18001fd81  push    r13
0x18001fd83  push    r14
0x18001fd85  push    r15
0x18001fd87  lea     rbp, [rax-5Fh]
0x18001fd8b  sub     rsp, 0B0h
0x18001fd92  mov     [rbp+57h+var_A0], 0FFFFFFFFFFFFFFFEh
0x18001fd9a  mov     [rax+10h], rbx
0x18001fd9e  mov     [rax+18h], rsi
0x18001fda2  mov     rax, cs:__security_cookie
0x18001fda9  xor     rax, rsp
0x18001fdac  mov     [rbp+57h+var_30], rax
0x18001fdb0  mov     edi, edx
0x18001fdb2  mov     r14, rcx
0x18001fdb5  xor     r15d, r15d
0x18001fdb8  xor     esi, esi
0x18001fdba  mov     [rbp+57h+var_98], rsi
0x18001fdbe  mov     [rbp+57h+var_78], rsi
0x18001fdc2  mov     [rbp+57h+var_70], rsi
0x18001fdc6  mov     [rbp+57h+var_68], esi
0x18001fdc9  lea     r13d, [r15+2]
0x18001fdcd  mov     [rbp+57h+var_64], r13d
0x18001fdd1  xorps   xmm0, xmm0
0x18001fdd4  movdqa  [rbp+57h+var_60], xmm0
0x18001fdd9  xorps   xmm1, xmm1
0x18001fddc  movdqa  [rbp+57h+var_50], xmm1
0x18001fde1  mov     [rbp+57h+var_40], rsi
0x18001fde5  lea     rax, ??_7ReAgentConfig@@6B@; const ReAgentConfig::`vftable'
0x18001fdec  mov     [rbp+57h+var_80], rax
0x18001fdf0  mov     [rbp+57h+var_38], esi
0x18001fdf3  movups  [rbp+57h+var_90], xmm0
0x18001fdf7  test    r8d, r8d
0x18001fdfa  jz      short loc_18001FE1A
0x18001fdfc  call    SetWinReOperationSyncKey
0x18001fe01  test    eax, eax
0x18001fe03  jz      short loc_18001FE14
0x18001fe05  xor     ebx, ebx
0x18001fe07  cmp     eax, 480h
0x18001fe0c  cmovnz  ebx, eax
0x18001fe0f  jmp     loc_1800200DB
0x18001fe14  mov     r15d, 1
0x18001fe1a  test    r14, r14
0x18001fe1d  jnz     short loc_18001FE58
0x18001fe1f  call    ?winreIsWinPE@@YAHXZ; winreIsWinPE(void)
0x18001fe24  test    eax, eax
0x18001fe26  jz      short loc_18001FE58
0x18001fe28  lea     ebx, [r14+32h]
0x18001fe2c  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, r14d; _ReAgentErrorCodes ReAgentError
0x18001fe33  jnz     short loc_18001FE3F
0x18001fe35  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 0Ah; _ReAgentErrorCodes ReAgentError
0x18001fe3f  mov     r8d, ebx
0x18001fe42  lea     rdx, aWinreuninstall_0; "winreUnInstallInternalfailed, winPE is "...
0x18001fe49  mov     ecx, 1
0x18001fe4e  call    UnattendLogW
0x18001fe53  jmp     loc_1800200C2
0x18001fe58  lea     r9, [rbp+57h+var_98]
0x18001fe5c  xor     edx, edx
0x18001fe5e  xor     ecx, ecx
0x18001fe60  call    winreGetConfigFilePathFromWinDir
0x18001fe65  mov     ebx, eax
0x18001fe67  test    eax, eax
0x18001fe69  jz      short loc_18001FEA1
0x18001fe6b  mov     [rsp+0D0h+var_A8], 64Ah
0x18001fe73  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18001fe7a  mov     [rsp+0D0h+var_B0], rax
0x18001fe7f  mov     r9d, ebx
0x18001fe82  lea     r8, aFailedToGetCon_3; "failed to get config file path"
0x18001fe89  lea     rdx, aWinreuninstall_2; "winreUnInstallInternal %s (0x%x) in fil"...
0x18001fe90  mov     ecx, r13d
0x18001fe93  call    UnattendLogW
0x18001fe98  mov     rsi, [rbp+57h+var_98]
0x18001fe9c  jmp     loc_1800200C2
0x18001fea1  test    edi, edi
0x18001fea3  jnz     short loc_18001FEBA
0x18001fea5  lea     rdx, aDisableupdatee; "DisableUpdateEnhancedConfigInfo"
0x18001feac  xor     ecx, ecx
0x18001feae  call    UnattendLogW
0x18001feb3  mov     [rbp+57h+var_38], 1
0x18001feba  mov     r8d, 1; int
0x18001fec0  mov     rsi, [rbp+57h+var_98]
0x18001fec4  mov     rdx, rsi; unsigned __int16 *
0x18001fec7  lea     rcx, [rbp+57h+var_80]; this
0x18001fecb  call    ?Init@ReAgentConfig@@UEAAKPEAGH@Z; ReAgentConfig::Init(ushort *,int)
0x18001fed0  mov     ebx, eax
0x18001fed2  test    eax, eax
0x18001fed4  jz      short loc_18001FF08
0x18001fed6  mov     [rsp+0D0h+var_A8], 655h
0x18001fede  lea     r8, aFailedToInitAg_2; "failed to init agent config"
0x18001fee5  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18001feec  mov     r9d, ebx
0x18001feef  mov     [rsp+0D0h+var_B0], rax
0x18001fef4  lea     rdx, aWinreuninstall_2; "winreUnInstallInternal %s (0x%x) in fil"...
0x18001fefb  mov     ecx, r13d
0x18001fefe  call    UnattendLogW
0x18001ff03  jmp     loc_1800200C2
0x18001ff08  lea     rcx, [rbp+57h+var_80]; this
0x18001ff0c  call    ?GetConfigInfo@ReAgentXMLParser@@QEAAPEAUReAgentConfigInfo@@XZ; ReAgentXMLParser::GetConfigInfo(void)
0x18001ff11  mov     rdi, rax
0x18001ff14  movups  xmm0, xmmword ptr [rax]
0x18001ff17  movdqu  [rbp+57h+var_90], xmm0
0x18001ff1c  cmp     dword ptr [rax+15D4h], 0
0x18001ff23  jnz     short loc_18001FF4E
0x18001ff25  lea     rdx, aWinreIsAlready; "Winre is already disabled, nothing to d"...
0x18001ff2c  xor     ecx, ecx
0x18001ff2e  call    UnattendLogW
0x18001ff33  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 0; _ReAgentErrorCodes ReAgentError
0x18001ff3a  jnz     short loc_18001FF46
0x18001ff3c  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 12h; _ReAgentErrorCodes ReAgentError
0x18001ff46  mov     ebx, r13d
0x18001ff49  jmp     loc_1800200C2
0x18001ff4e  mov     rdx, rdi
0x18001ff51  mov     rcx, r14
0x18001ff54  call    winreCopyWIMBack
0x18001ff59  mov     ebx, eax
0x18001ff5b  test    eax, eax
0x18001ff5d  jz      short loc_18001FF73
0x18001ff5f  mov     [rsp+0D0h+var_A8], 66Fh
0x18001ff67  lea     r8, aFailedToCopyWi_5; "failed to copy wim back"
0x18001ff6e  jmp     loc_18001FEE5
0x18001ff73  lea     rdx, aWinreUninstall_3; "WinRE uninstall step 1 succeeded: copy "...
0x18001ff7a  xor     ecx, ecx
0x18001ff7c  call    UnattendLogW
0x18001ff81  mov     rcx, rdi
0x18001ff84  call    winreDeleteBackupSettingFile
0x18001ff89  test    eax, eax
0x18001ff8b  jz      short loc_18001FF9F
0x18001ff8d  mov     r8d, eax
0x18001ff90  lea     rdx, aFailedToDelete_3; "Failed to delete backup setting file: 0"...
0x18001ff97  mov     ecx, r13d
0x18001ff9a  call    UnattendLogW
0x18001ff9f  lea     rax, Default
0x18001ffa6  mov     [rsp+0D0h+var_B0], rax; unsigned __int16 *
0x18001ffab  xor     r9d, r9d; unsigned int
0x18001ffae  lea     r8, ZeroGuid; struct _GUID *
0x18001ffb5  xor     edx, edx; unsigned __int64
0x18001ffb7  lea     rcx, [rbp+57h+var_80]; this
0x18001ffbb  call    ?SetWinreLocationPath@ReAgentConfig@@QEAAK_KPEAU_GUID@@KPEAG@Z; ReAgentConfig::SetWinreLocationPath(unsigned __int64,_GUID *,ulong,ushort *)
0x18001ffc0  mov     ebx, eax
0x18001ffc2  test    eax, eax
0x18001ffc4  jz      short loc_18001FFDA
0x18001ffc6  mov     [rsp+0D0h+var_A8], 680h
0x18001ffce  lea     r8, aFailedToSetWin_3; "failed to set winre location path"
0x18001ffd5  jmp     loc_18001FEE5
0x18001ffda  movups  xmm0, cs:xmmword_180070D08
0x18001ffe1  mov     rax, [rbp+57h+var_40]
0x18001ffe5  movdqu  xmmword ptr [rax], xmm0
0x18001ffe9  xor     edx, edx; int
0x18001ffeb  lea     rcx, [rbp+57h+var_80]; this
0x18001ffef  call    ?SetInstallState@ReAgentConfig@@QEAAXH@Z; ReAgentConfig::SetInstallState(int)
0x18001fff4  mov     rcx, [rbp+57h+var_40]; this
0x18001fff8  mov     dword ptr [rcx+15ECh], 4
0x180020002  mov     r8, [rbp+57h+var_40]
0x180020006  add     r8, 15F0h; unsigned __int16 *
0x18002000d  lea     rdx, qword_180070D18; unsigned __int16 *
0x180020014  call    ?CopyPathInfo@ReAgentXMLParser@@IEAAKPEAG0@Z; ReAgentXMLParser::CopyPathInfo(ushort *,ushort *)
0x180020019  lea     rcx, [rbp+57h+var_80]; this
0x18002001d  call    ?Update@ReAgentXMLParser@@QEAAKXZ; ReAgentXMLParser::Update(void)
0x180020022  mov     ebx, eax
0x180020024  test    eax, eax
0x180020026  jz      short loc_18002003C
0x180020028  mov     [rsp+0D0h+var_A8], 686h
0x180020030  lea     r8, aFailedToUpdate_7; "failed to update agent config"
0x180020037  jmp     loc_18001FEE5
0x18002003c  lea     rdx, aWinreUninstall_1; "WinRE uninstall step 2 succeeded: updat"...
0x180020043  xor     ecx, ecx
0x180020045  call    UnattendLogW
0x18002004a  lea     rcx, [rbp+57h+var_90]
0x18002004e  call    winreUnregisterFromRecoveryBCD
0x180020053  mov     ebx, eax
0x180020055  test    eax, eax
0x180020057  jz      short loc_18002006D
0x180020059  mov     r8d, eax
0x18002005c  lea     rdx, aFailedToUnregi; "Failed to unregister Winre.wim from rec"...
0x180020063  mov     ecx, r13d
0x180020066  call    UnattendLogW
0x18002006b  xor     ebx, ebx
0x18002006d  lea     rdx, aWinreUninstall; "WinRE uninstall step 3 succeeded: unreg"...
0x180020074  xor     ecx, ecx
0x180020076  call    UnattendLogW
0x18002007b  lea     rdx, [rbp+57h+var_90]
0x18002007f  lea     rcx, GUID_CURRENT_BOOT_ENTRY
0x180020086  call    winreRemoveRecoverySequenceEx
0x18002008b  lea     rdx, aWinreUninstall_2; "WinRE uninstall step 4 succeeded: remov"...
0x180020092  xor     ecx, ecx
0x180020094  call    UnattendLogW
0x180020099  xor     ecx, ecx
0x18002009b  call    winreConfigureValidationTask
0x1800200a0  lea     rcx, aFalse_0; "FALSE"
0x1800200a7  lea     r8, aTrue_0; "TRUE"
0x1800200ae  test    eax, eax
0x1800200b0  cmovz   r8, rcx
0x1800200b4  lea     rdx, aWinreUninstall_0; "WinRE uninstall step 5 completed with r"...
0x1800200bb  xor     ecx, ecx
0x1800200bd  call    UnattendLogW
0x1800200c2  test    r15d, r15d
0x1800200c5  jz      short loc_1800200CC
0x1800200c7  call    RemoveWinReOperationSyncKey
0x1800200cc  test    rsi, rsi
0x1800200cf  jz      short loc_1800200DB
0x1800200d1  mov     rcx, rsi; pv
0x1800200d4  call    cs:__imp_CoTaskMemFree
0x1800200da  nop
0x1800200db  lea     rax, ??_7ReAgentConfig@@6B@; const ReAgentConfig::`vftable'
0x1800200e2  mov     [rbp+57h+var_80], rax
0x1800200e6  lea     rcx, [rbp+57h+var_80]; this
0x1800200ea  call    ??1ReAgentXMLParser@@UEAA@XZ; ReAgentXMLParser::~ReAgentXMLParser(void)
0x1800200ef  mov     eax, ebx
0x1800200f1  mov     rcx, [rbp+57h+var_30]
0x1800200f5  xor     rcx, rsp; StackCookie
0x1800200f8  call    __security_check_cookie
0x1800200fd  lea     r11, [rsp+0D0h+var_20]
0x180020105  mov     rbx, [r11+38h]
0x180020109  mov     rsi, [r11+40h]
0x18002010d  mov     rsp, r11
0x180020110  pop     r15
0x180020112  pop     r14
0x180020114  pop     r13
0x180020116  pop     rdi
0x180020117  pop     rbp
0x180020118  retn
```
