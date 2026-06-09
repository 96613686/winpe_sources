# sub_1800EEC4C

- ea: `0x1800eec4c`
- end: `0x1800ef262`
- name: `sub_1800EEC4C`
- size: `1558`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800ead74`

## callees

- `0x18003b830`
- `0x1800ea1fc`
- `0x1800ea56c`
- `0x1800ed0d0`
- `0x1800eec4c`
- `0x1800f2ad4`
- `0x1800f3014`
- `0x1800f30bc`
- `0x1800f3280`

## string_xrefs

- `0x1800ef1d6`: `OobeEnableRtpAndSigUpdate`
- `0x1800eed45`: `DisableOnAccessProtection`
- `0x1800eecda`: `%MpConfig_ProductAppDataPath%\LocalCopy`
- `0x1800eed3e`: `AllowOnAccessProtection`
- `0x1800eecaa`: `LocalCopyDirectory`
- `0x1800eed5d`: `LocalSettingOverrideDisableOnAccessProtection`
- `0x1800eeee8`: `MpEngine_InMemoryScan_CacheSize`
- `0x1800eee92`: `DisableRawWriteNotification`
- `0x1800eef3e`: `AVOnAccessScanErrorRetryCount`
- `0x1800eef05`: `MpEngine_InMemoryScan_CacheMaxBuffer`
- `0x1800eef24`: `MpRtp_Delay_Normalized_Path_Query`
- `0x1800eefab`: `ScriptScanningCacheSharing`
- `0x1800eefc6`: `SendSynchronousProcessCreateNotification`
- `0x1800eef90`: `ScriptScanningCacheSize`
- `0x1800eefe4`: `NriServiceStopDelay`
- `0x1800ef0ff`: `EnableHardlinkMonitoring`
- `0x1800ef11a`: `LocalSettingOverrideEnableHardlinkMonitoring`
- `0x1800ef0c9`: `DirectoryMonitoringKillbit`
- `0x1800ef0e4`: `LocalSettingOverrideDirectoryMonitoringKillbit`
- `0x1800ef215`: `DisableNetworkFileAccessTimeSuppression`
- `0x1800ef1f7`: `DisableAsyncScanOnOpen`
- `0x1800ef20e`: `DisableNetworkFileAccessTimeRestoration`

## pseudocode

```c
__int64 __fastcall sub_1800EEC4C(__int64 a1, __int64 a2)
{
  __int64 v4; // [rsp+28h] [rbp-51h]
  __int64 v5; // [rsp+28h] [rbp-51h]
  __int64 v6; // [rsp+38h] [rbp-41h]
  int v7; // [rsp+38h] [rbp-41h]
  __int64 v8; // [rsp+40h] [rbp-39h]
  int v9; // [rsp+40h] [rbp-39h]
  _BYTE v10[80]; // [rsp+60h] [rbp-19h] BYREF

  sub_1800EA1FC(v10, L"Real-Time Protection", a2);
  if ( !(unsigned __int8)sub_1800F2AD4(
                           (unsigned int)v10,
                           (unsigned int)L"LocalCopyDirectory",
                           (unsigned int)L"LocalCopyDirectory",
                           0,
                           0,
                           2,
                           37) )
  {
    v9 = 37;
    v7 = 2;
    LODWORD(v4) = 0;
    sub_1800F3280(
      (unsigned int)v10,
      (unsigned int)L"LocalCopyDirectory",
      (unsigned int)L"LocalCopyDirectory",
      40,
      (__int64)L"%MpConfig_ProductAppDataPath%\\LocalCopy",
      v4,
      0,
      v7,
      v9);
  }
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"DisableRealtimeMonitoring",
    (unsigned int)L"AllowRealtimeMonitoring",
    0);
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"LocalSettingOverrideDisableRealtimeMonitoring",
    (unsigned int)L"LocalSettingOverrideDisableRealtimeMonitoring",
    0);
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"DisableOnAccessProtection",
    (unsigned int)L"AllowOnAccessProtection",
    0);
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"LocalSettingOverrideDisableOnAccessProtection",
    (unsigned int)L"LocalSettingOverrideDisableOnAccessProtection",
    0);
  sub_1800F30BC((unsigned int)v10, (unsigned int)L"DisableIOAVProtection", (unsigned int)L"AllowIOAVProtection", 0);
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"LocalSettingOverrideDisableIOAVProtection",
    (unsigned int)L"LocalSettingOverrideDisableIOAVProtection",
    0);
  sub_1800F30BC((unsigned int)v10, (unsigned int)L"DisableScriptScanning", (unsigned int)L"AllowScriptScanning", 0);
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"LocalSettingOverrideDisableScriptScanning",
    (unsigned int)L"LocalSettingOverrideDisableScriptScanning",
    0);
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"DisableBehaviorMonitoring",
    (unsigned int)L"AllowBehaviorMonitoring",
    0);
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"LocalSettingOverrideDisableBehaviorMonitoring",
    (unsigned int)L"LocalSettingOverrideDisableBehaviorMonitoring",
    0);
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"DisableScanOnRealtimeEnable",
    (unsigned int)L"DisableScanOnRealtimeEnable",
    0);
  sub_1800F30BC((unsigned int)v10, (unsigned int)L"IOAVMaxSize", (unsigned int)L"IOAVMaxSize", 0);
  sub_1800F30BC((unsigned int)v10, (unsigned int)L"RealTimeScanDirection", (unsigned int)L"RealTimeScanDirection", 0);
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"LocalSettingOverrideRealTimeScanDirection",
    (unsigned int)L"LocalSettingOverrideRealTimeScanDirection",
    0);
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"DisableRawWriteNotification",
    (unsigned int)L"DisableRawWriteNotification",
    0);
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"MpEngine_DisableScriptScanning",
    (unsigned int)L"MpEngine_DisableScriptScanning",
    0);
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"MpEngine_ScriptScanning_MinSize",
    (unsigned int)L"MpEngine_ScriptScanning_MinSize",
    32);
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"MpEngine_InMemoryScan_CacheSize",
    (unsigned int)L"MpEngine_InMemoryScan_CacheSize",
    2048);
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"MpEngine_InMemoryScan_CacheMaxBuffer",
    (unsigned int)L"MpEngine_InMemoryScan_CacheMaxBuffer",
    0x400000);
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"MpRtp_Delay_Normalized_Path_Query",
    (unsigned int)L"MpRtp_Delay_Normalized_Path_Query",
    1000);
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"AVOnAccessScanErrorRetryCount",
    (unsigned int)L"AVOnAccessScanErrorRetryCount",
    1000);
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"MpEngine_AllowedUrlExclusionDisabled",
    (unsigned int)L"MpEngine_AllowedUrlExclusionDisabled",
    0);
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"MpEngine_ZoneBasedUrlExclusionDisabled",
    (unsigned int)L"MpEngine_ZoneBasedUrlExclusionDisabled",
    0);
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"ScriptScanningCacheSize",
    (unsigned int)L"ScriptScanningCacheSize",
    8000);
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"ScriptScanningCacheSharing",
    (unsigned int)L"ScriptScanningCacheSharing",
    0);
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"SendSynchronousProcessCreateNotification",
    (unsigned int)L"SendSynchronousProcessCreateNotification",
    0);
  sub_1800F30BC((unsigned int)v10, (unsigned int)L"NriServiceStopDelay", (unsigned int)L"NriServiceStopDelay", 60000);
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"DisableDynamicRegHardening",
    (unsigned int)L"DisableDynamicRegHardening",
    0);
  sub_1800F3014(
    (unsigned int)v10,
    (unsigned int)L"DynamicFsHardeningState",
    (unsigned int)L"DynamicFsHardeningState",
    0,
    0);
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"SyncMonitorRequestDuration",
    (unsigned int)L"SyncMonitorRequestDuration",
    10000);
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"LocalSettingOverrideSyncMonitorRequestDuration",
    (unsigned int)L"LocalSettingOverrideSyncMonitorRequestDuration",
    0);
  sub_1800F30BC((unsigned int)v10, (unsigned int)L"SyncMonitorState", (unsigned int)L"SyncMonitorState", 1);
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"LocalSettingOverrideSyncMonitorState",
    (unsigned int)L"LocalSettingOverrideSyncMonitorState",
    0);
  sub_1800F30BC((unsigned int)v10, (unsigned int)L"DpaDisabled", (unsigned int)L"DpaDisabled", 0);
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"DirectoryMonitoringKillbit",
    (unsigned int)L"DirectoryMonitoringKillbit",
    0);
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"LocalSettingOverrideDirectoryMonitoringKillbit",
    (unsigned int)L"LocalSettingOverrideDirectoryMonitoringKillbit",
    0);
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"EnableHardlinkMonitoring",
    (unsigned int)L"EnableHardlinkMonitoring",
    0);
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"LocalSettingOverrideEnableHardlinkMonitoring",
    (unsigned int)L"LocalSettingOverrideEnableHardlinkMonitoring",
    0);
  if ( !(unsigned __int8)sub_1800F2AD4(
                           (unsigned int)v10,
                           (unsigned int)L"IncludedLocalDriveLetters",
                           (unsigned int)L"IncludedLocalDriveLetters",
                           0,
                           0,
                           2,
                           0) )
  {
    LODWORD(v8) = 0;
    LODWORD(v6) = 2;
    LODWORD(v5) = 0;
    sub_1800F3280(
      (unsigned int)v10,
      (unsigned int)L"IncludedLocalDriveLetters",
      (unsigned int)L"IncludedLocalDriveLetters",
      1,
      (__int64)&unk_180145838,
      v5,
      0,
      v6,
      v8);
  }
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"TrustLabelProtectionStatus",
    (unsigned int)L"TrustLabelProtectionStatus",
    0);
  sub_1800F30BC((unsigned int)v10, (unsigned int)L"DisableDriverUnload", (unsigned int)L"DisableDriverUnload", 1);
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"OobeEnableRtpAndSigUpdate",
    (unsigned int)L"OobeEnableRtpAndSigUpdate",
    0);
  sub_1800F30BC((unsigned int)v10, (unsigned int)L"DisableAsyncScanOnOpen", (unsigned int)L"PerformanceModeStatus", 0);
  sub_1800F30BC(
    (unsigned int)v10,
    (unsigned int)L"DisableNetworkFileAccessTimeSuppression",
    (unsigned int)L"DisableNetworkFileAccessTimeRestoration",
    0);
  sub_1800ED0D0(a1, v10);
  sub_1800EA56C(v10);
  return a1;
}

```

## disassembly

```asm
0x1800eec4c  mov     [rsp-8+arg_8], rbx
0x1800eec51  mov     [rsp-8+arg_10], rsi
0x1800eec56  push    rbp
0x1800eec57  push    rdi
0x1800eec58  push    r14
0x1800eec5a  lea     rbp, [rsp-47h]
0x1800eec5f  sub     rsp, 0C0h
0x1800eec66  mov     rax, cs:__security_cookie
0x1800eec6d  xor     rax, rsp
0x1800eec70  mov     [rbp+57h+var_20], rax
0x1800eec74  mov     rbx, rcx
0x1800eec77  mov     [rbp+57h+var_78], rcx
0x1800eec7b  xor     r14d, r14d
0x1800eec7e  mov     r8, rdx
0x1800eec81  lea     rdx, aRealTimeProtec; "Real-Time Protection"
0x1800eec88  lea     rcx, [rbp+57h+var_70]
0x1800eec8c  call    sub_1800EA1FC
0x1800eec91  nop
0x1800eec92  lea     esi, [r14+25h]
0x1800eec96  mov     dword ptr [rsp+0D0h+var_A0], esi
0x1800eec9a  mov     dword ptr [rsp+0D0h+var_A8], 2
0x1800eeca2  mov     [rsp+0D0h+var_B0], r14
0x1800eeca7  xor     r9d, r9d
0x1800eecaa  lea     rdi, aLocalcopydirec; "LocalCopyDirectory"
0x1800eecb1  mov     r8, rdi
0x1800eecb4  mov     rdx, rdi
0x1800eecb7  lea     rcx, [rbp+57h+var_70]
0x1800eecbb  call    sub_1800F2AD4
0x1800eecc0  test    al, al
0x1800eecc2  jnz     short loc_1800EECF9
0x1800eecc4  mov     dword ptr [rsp+0D0h+var_90], esi
0x1800eecc8  mov     dword ptr [rsp+0D0h+var_98], 2
0x1800eecd0  mov     [rsp+0D0h+var_A0], r14
0x1800eecd5  mov     dword ptr [rsp+0D0h+var_A8], r14d
0x1800eecda  lea     rax, aMpconfigProduc_4; "%MpConfig_ProductAppDataPath%\\LocalCop"...
0x1800eece1  mov     [rsp+0D0h+var_B0], rax
0x1800eece6  lea     r9d, [r14+28h]
0x1800eecea  mov     r8, rdi
0x1800eeced  mov     rdx, rdi
0x1800eecf0  lea     rcx, [rbp+57h+var_70]
0x1800eecf4  call    sub_1800F3280
0x1800eecf9  mov     edi, 0C40h
0x1800eecfe  mov     dword ptr [rsp+0D0h+var_A0], edi
0x1800eed02  xor     r9d, r9d
0x1800eed05  lea     r8, aAllowrealtimem_0; "AllowRealtimeMonitoring"
0x1800eed0c  lea     rdx, aDisablerealtim; "DisableRealtimeMonitoring"
0x1800eed13  lea     rcx, [rbp+57h+var_70]
0x1800eed17  call    sub_1800F30BC
0x1800eed1c  mov     dword ptr [rsp+0D0h+var_A0], r14d
0x1800eed21  xor     r9d, r9d
0x1800eed24  lea     rdx, aLocalsettingov_2; "LocalSettingOverrideDisableRealtimeMoni"...
0x1800eed2b  mov     r8, rdx
0x1800eed2e  lea     rcx, [rbp+57h+var_70]
0x1800eed32  call    sub_1800F30BC
0x1800eed37  mov     dword ptr [rsp+0D0h+var_A0], edi
0x1800eed3b  xor     r9d, r9d
0x1800eed3e  lea     r8, aAllowonaccessp_0; "AllowOnAccessProtection"
0x1800eed45  lea     rdx, aDisableonacces; "DisableOnAccessProtection"
0x1800eed4c  lea     rcx, [rbp+57h+var_70]
0x1800eed50  call    sub_1800F30BC
0x1800eed55  mov     dword ptr [rsp+0D0h+var_A0], r14d
0x1800eed5a  xor     r9d, r9d
0x1800eed5d  lea     rdx, aLocalsettingov_3; "LocalSettingOverrideDisableOnAccessProt"...
0x1800eed64  mov     r8, rdx
0x1800eed67  lea     rcx, [rbp+57h+var_70]
0x1800eed6b  call    sub_1800F30BC
0x1800eed70  mov     dword ptr [rsp+0D0h+var_A0], edi
0x1800eed74  xor     r9d, r9d
0x1800eed77  lea     r8, aAllowioavprote_0; "AllowIOAVProtection"
0x1800eed7e  lea     rdx, aDisableioavpro; "DisableIOAVProtection"
0x1800eed85  lea     rcx, [rbp+57h+var_70]
0x1800eed89  call    sub_1800F30BC
0x1800eed8e  mov     dword ptr [rsp+0D0h+var_A0], r14d
0x1800eed93  xor     r9d, r9d
0x1800eed96  lea     rdx, aLocalsettingov_4; "LocalSettingOverrideDisableIOAVProtecti"...
0x1800eed9d  mov     r8, rdx
0x1800eeda0  lea     rcx, [rbp+57h+var_70]
0x1800eeda4  call    sub_1800F30BC
0x1800eeda9  mov     dword ptr [rsp+0D0h+var_A0], edi
0x1800eedad  xor     r9d, r9d
0x1800eedb0  lea     r8, aAllowscriptsca_0; "AllowScriptScanning"
0x1800eedb7  lea     rdx, aDisablescripts; "DisableScriptScanning"
0x1800eedbe  lea     rcx, [rbp+57h+var_70]
0x1800eedc2  call    sub_1800F30BC
0x1800eedc7  mov     dword ptr [rsp+0D0h+var_A0], r14d
0x1800eedcc  xor     r9d, r9d
0x1800eedcf  lea     rdx, aLocalsettingov_5; "LocalSettingOverrideDisableScriptScanni"...
0x1800eedd6  mov     r8, rdx
0x1800eedd9  lea     rcx, [rbp+57h+var_70]
0x1800eeddd  call    sub_1800F30BC
0x1800eede2  mov     dword ptr [rsp+0D0h+var_A0], edi
0x1800eede6  xor     r9d, r9d
0x1800eede9  lea     r8, aAllowbehaviorm_0; "AllowBehaviorMonitoring"
0x1800eedf0  lea     rdx, aDisablebehavio; "DisableBehaviorMonitoring"
0x1800eedf7  lea     rcx, [rbp+57h+var_70]
0x1800eedfb  call    sub_1800F30BC
0x1800eee00  mov     dword ptr [rsp+0D0h+var_A0], r14d
0x1800eee05  xor     r9d, r9d
0x1800eee08  lea     rdx, aLocalsettingov_6; "LocalSettingOverrideDisableBehaviorMoni"...
0x1800eee0f  mov     r8, rdx
0x1800eee12  lea     rcx, [rbp+57h+var_70]
0x1800eee16  call    sub_1800F30BC
0x1800eee1b  mov     dword ptr [rsp+0D0h+var_A0], r14d
0x1800eee20  xor     r9d, r9d
0x1800eee23  lea     rdx, aDisablescanonr; "DisableScanOnRealtimeEnable"
0x1800eee2a  mov     r8, rdx
0x1800eee2d  lea     rcx, [rbp+57h+var_70]
0x1800eee31  call    sub_1800F30BC
0x1800eee36  mov     dword ptr [rsp+0D0h+var_A0], r14d
0x1800eee3b  xor     r9d, r9d
0x1800eee3e  lea     rdx, aIoavmaxsize; "IOAVMaxSize"
0x1800eee45  mov     r8, rdx
0x1800eee48  lea     rcx, [rbp+57h+var_70]
0x1800eee4c  call    sub_1800F30BC
0x1800eee51  mov     dword ptr [rsp+0D0h+var_A0], 440h
0x1800eee59  xor     r9d, r9d
0x1800eee5c  lea     rdx, aRealtimescandi_0; "RealTimeScanDirection"
0x1800eee63  mov     r8, rdx
0x1800eee66  lea     rcx, [rbp+57h+var_70]
0x1800eee6a  call    sub_1800F30BC
0x1800eee6f  mov     dword ptr [rsp+0D0h+var_A0], r14d
0x1800eee74  xor     r9d, r9d
0x1800eee77  lea     rdx, aLocalsettingov_7; "LocalSettingOverrideRealTimeScanDirecti"...
0x1800eee7e  mov     r8, rdx
0x1800eee81  lea     rcx, [rbp+57h+var_70]
0x1800eee85  call    sub_1800F30BC
0x1800eee8a  mov     dword ptr [rsp+0D0h+var_A0], r14d
0x1800eee8f  xor     r9d, r9d
0x1800eee92  lea     rdx, aDisablerawwrit; "DisableRawWriteNotification"
0x1800eee99  mov     r8, rdx
0x1800eee9c  lea     rcx, [rbp+57h+var_70]
0x1800eeea0  call    sub_1800F30BC
0x1800eeea5  mov     esi, 20h ; ' '
0x1800eeeaa  mov     dword ptr [rsp+0D0h+var_A0], esi
0x1800eeeae  xor     r9d, r9d
0x1800eeeb1  lea     rdx, aMpengineDisabl; "MpEngine_DisableScriptScanning"
0x1800eeeb8  mov     r8, rdx
0x1800eeebb  lea     rcx, [rbp+57h+var_70]
0x1800eeebf  call    sub_1800F30BC
0x1800eeec4  mov     dword ptr [rsp+0D0h+var_A0], esi
0x1800eeec8  mov     r9d, esi
0x1800eeecb  lea     rdx, aMpengineScript; "MpEngine_ScriptScanning_MinSize"
0x1800eeed2  mov     r8, rdx
0x1800eeed5  lea     rcx, [rbp+57h+var_70]
0x1800eeed9  call    sub_1800F30BC
0x1800eeede  mov     dword ptr [rsp+0D0h+var_A0], esi
0x1800eeee2  mov     r9d, 800h
0x1800eeee8  lea     rdx, aMpengineInmemo; "MpEngine_InMemoryScan_CacheSize"
0x1800eeeef  mov     r8, rdx
0x1800eeef2  lea     rcx, [rbp+57h+var_70]
0x1800eeef6  call    sub_1800F30BC
0x1800eeefb  mov     dword ptr [rsp+0D0h+var_A0], esi
0x1800eeeff  mov     r9d, 400000h
0x1800eef05  lea     rdx, aMpengineInmemo_0; "MpEngine_InMemoryScan_CacheMaxBuffer"
0x1800eef0c  mov     r8, rdx
0x1800eef0f  lea     rcx, [rbp+57h+var_70]
0x1800eef13  call    sub_1800F30BC
0x1800eef18  mov     dword ptr [rsp+0D0h+var_A0], esi
0x1800eef1c  mov     edi, 3E8h
0x1800eef21  mov     r9d, edi
0x1800eef24  lea     rdx, aMprtpDelayNorm; "MpRtp_Delay_Normalized_Path_Query"
0x1800eef2b  mov     r8, rdx
0x1800eef2e  lea     rcx, [rbp+57h+var_70]
0x1800eef32  call    sub_1800F30BC
0x1800eef37  mov     dword ptr [rsp+0D0h+var_A0], esi
0x1800eef3b  mov     r9d, edi
0x1800eef3e  lea     rdx, aAvonaccessscan; "AVOnAccessScanErrorRetryCount"
0x1800eef45  mov     r8, rdx
0x1800eef48  lea     rcx, [rbp+57h+var_70]
0x1800eef4c  call    sub_1800F30BC
0x1800eef51  mov     dword ptr [rsp+0D0h+var_A0], esi
0x1800eef55  xor     r9d, r9d
0x1800eef58  lea     rdx, aMpengineAllowe; "MpEngine_AllowedUrlExclusionDisabled"
0x1800eef5f  mov     r8, rdx
0x1800eef62  lea     rcx, [rbp+57h+var_70]
0x1800eef66  call    sub_1800F30BC
0x1800eef6b  mov     dword ptr [rsp+0D0h+var_A0], esi
0x1800eef6f  xor     r9d, r9d
0x1800eef72  lea     rdx, aMpengineZoneba; "MpEngine_ZoneBasedUrlExclusionDisabled"
0x1800eef79  mov     r8, rdx
0x1800eef7c  lea     rcx, [rbp+57h+var_70]
0x1800eef80  call    sub_1800F30BC
0x1800eef85  mov     dword ptr [rsp+0D0h+var_A0], r14d
0x1800eef8a  mov     r9d, 1F40h
0x1800eef90  lea     rdx, aScriptscanning; "ScriptScanningCacheSize"
0x1800eef97  mov     r8, rdx
0x1800eef9a  lea     rcx, [rbp+57h+var_70]
0x1800eef9e  call    sub_1800F30BC
0x1800eefa3  mov     dword ptr [rsp+0D0h+var_A0], r14d
0x1800eefa8  xor     r9d, r9d
0x1800eefab  lea     rdx, aScriptscanning_0; "ScriptScanningCacheSharing"
0x1800eefb2  mov     r8, rdx
0x1800eefb5  lea     rcx, [rbp+57h+var_70]
0x1800eefb9  call    sub_1800F30BC
0x1800eefbe  mov     dword ptr [rsp+0D0h+var_A0], r14d
0x1800eefc3  xor     r9d, r9d
0x1800eefc6  lea     rdx, aSendsynchronou; "SendSynchronousProcessCreateNotificatio"...
0x1800eefcd  mov     r8, rdx
0x1800eefd0  lea     rcx, [rbp+57h+var_70]
0x1800eefd4  call    sub_1800F30BC
0x1800eefd9  mov     dword ptr [rsp+0D0h+var_A0], r14d
0x1800eefde  mov     r9d, 0EA60h
0x1800eefe4  lea     rdx, aNriservicestop; "NriServiceStopDelay"
0x1800eefeb  mov     r8, rdx
0x1800eefee  lea     rcx, [rbp+57h+var_70]
0x1800eeff2  call    sub_1800F30BC
0x1800eeff7  mov     dword ptr [rsp+0D0h+var_A0], r14d
0x1800eeffc  xor     r9d, r9d
0x1800eefff  lea     rdx, aDisabledynamic; "DisableDynamicRegHardening"
0x1800ef006  mov     r8, rdx
0x1800ef009  lea     rcx, [rbp+57h+var_70]
0x1800ef00d  call    sub_1800F30BC
0x1800ef012  mov     dword ptr [rsp+0D0h+var_A0], r14d
0x1800ef017  mov     dword ptr [rsp+0D0h+var_B0], r14d
0x1800ef01c  xor     r9d, r9d
0x1800ef01f  lea     rdx, aDynamicfsharde; "DynamicFsHardeningState"
0x1800ef026  mov     r8, rdx
0x1800ef029  lea     rcx, [rbp+57h+var_70]
0x1800ef02d  call    sub_1800F3014
0x1800ef032  mov     dword ptr [rsp+0D0h+var_A0], r14d
0x1800ef037  mov     r9d, 2710h
0x1800ef03d  lea     rdx, aSyncmonitorreq; "SyncMonitorRequestDuration"
0x1800ef044  mov     r8, rdx
0x1800ef047  lea     rcx, [rbp+57h+var_70]
0x1800ef04b  call    sub_1800F30BC
0x1800ef050  mov     dword ptr [rsp+0D0h+var_A0], r14d
0x1800ef055  xor     r9d, r9d
0x1800ef058  lea     rdx, aLocalsettingov_8; "LocalSettingOverrideSyncMonitorRequestD"...
0x1800ef05f  mov     r8, rdx
0x1800ef062  lea     rcx, [rbp+57h+var_70]
0x1800ef066  call    sub_1800F30BC
0x1800ef06b  mov     dword ptr [rsp+0D0h+var_A0], r14d
0x1800ef070  mov     esi, 1
0x1800ef075  mov     r9d, esi
0x1800ef078  lea     rdx, aSyncmonitorsta; "SyncMonitorState"
0x1800ef07f  mov     r8, rdx
0x1800ef082  lea     rcx, [rbp+57h+var_70]
0x1800ef086  call    sub_1800F30BC
0x1800ef08b  mov     dword ptr [rsp+0D0h+var_A0], r14d
0x1800ef090  xor     r9d, r9d
0x1800ef093  lea     rdx, aLocalsettingov_9; "LocalSettingOverrideSyncMonitorState"
0x1800ef09a  mov     r8, rdx
0x1800ef09d  lea     rcx, [rbp+57h+var_70]
0x1800ef0a1  call    sub_1800F30BC
0x1800ef0a6  mov     dword ptr [rsp+0D0h+var_A0], r14d
0x1800ef0ab  xor     r9d, r9d
0x1800ef0ae  lea     rdx, aDpadisabled; "DpaDisabled"
0x1800ef0b5  mov     r8, rdx
0x1800ef0b8  lea     rcx, [rbp+57h+var_70]
0x1800ef0bc  call    sub_1800F30BC
0x1800ef0c1  mov     dword ptr [rsp+0D0h+var_A0], r14d
0x1800ef0c6  xor     r9d, r9d
0x1800ef0c9  lea     rdx, aDirectorymonit; "DirectoryMonitoringKillbit"
0x1800ef0d0  mov     r8, rdx
0x1800ef0d3  lea     rcx, [rbp+57h+var_70]
0x1800ef0d7  call    sub_1800F30BC
0x1800ef0dc  mov     dword ptr [rsp+0D0h+var_A0], r14d
0x1800ef0e1  xor     r9d, r9d
0x1800ef0e4  lea     rdx, aLocalsettingov_10; "LocalSettingOverrideDirectoryMonitoring"...
0x1800ef0eb  mov     r8, rdx
0x1800ef0ee  lea     rcx, [rbp+57h+var_70]
0x1800ef0f2  call    sub_1800F30BC
0x1800ef0f7  mov     dword ptr [rsp+0D0h+var_A0], r14d
0x1800ef0fc  xor     r9d, r9d
0x1800ef0ff  lea     rdx, aEnablehardlink; "EnableHardlinkMonitoring"
0x1800ef106  mov     r8, rdx
0x1800ef109  lea     rcx, [rbp+57h+var_70]
0x1800ef10d  call    sub_1800F30BC
0x1800ef112  mov     dword ptr [rsp+0D0h+var_A0], r14d
0x1800ef117  xor     r9d, r9d
0x1800ef11a  lea     rdx, aLocalsettingov_11; "LocalSettingOverrideEnableHardlinkMonit"...
0x1800ef121  mov     r8, rdx
0x1800ef124  lea     rcx, [rbp+57h+var_70]
0x1800ef128  call    sub_1800F30BC
0x1800ef12d  mov     dword ptr [rsp+0D0h+var_A0], r14d
0x1800ef132  mov     dword ptr [rsp+0D0h+var_A8], 2
0x1800ef13a  mov     [rsp+0D0h+var_B0], r14
0x1800ef13f  xor     r9d, r9d
0x1800ef142  lea     rdi, aIncludedlocald; "IncludedLocalDriveLetters"
0x1800ef149  mov     r8, rdi
0x1800ef14c  mov     rdx, rdi
0x1800ef14f  lea     rcx, [rbp+57h+var_70]
0x1800ef153  call    sub_1800F2AD4
0x1800ef158  test    al, al
0x1800ef15a  jnz     short loc_1800EF191
0x1800ef15c  mov     dword ptr [rsp+0D0h+var_90], r14d
0x1800ef161  mov     dword ptr [rsp+0D0h+var_98], 2
0x1800ef169  mov     [rsp+0D0h+var_A0], r14
0x1800ef16e  mov     dword ptr [rsp+0D0h+var_A8], r14d
0x1800ef173  lea     rax, unk_180145838
0x1800ef17a  mov     [rsp+0D0h+var_B0], rax
0x1800ef17f  mov     r9d, esi
0x1800ef182  mov     r8, rdi
0x1800ef185  mov     rdx, rdi
0x1800ef188  lea     rcx, [rbp+57h+var_70]
0x1800ef18c  call    sub_1800F3280
0x1800ef191  mov     dword ptr [rsp+0D0h+var_A0], 8
0x1800ef199  xor     r9d, r9d
0x1800ef19c  lea     rdx, aTrustlabelprot; "TrustLabelProtectionStatus"
0x1800ef1a3  mov     r8, rdx
  ... truncated ...
```
