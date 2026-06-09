# _dynamic_initializer_for__g_rgFlowInfo__

- ea: `0x140002b40`
- end: `0x140003e3e`
- name: `_dynamic_initializer_for__g_rgFlowInfo__`
- size: `4862`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x140002b40`
- `0x14002ab34`
- `0x14006c99c`

## string_xrefs

- `0x140002e86`: `InstallInternalDeveloperModePackage`
- `0x140003094`: `UninstallOS`
- `0x1400030b0`: `SetDefaultSecurityProduct`
- `0x1400030cc`: `DeleteForceQualityLevelValue`
- `0x1400030e8`: `DeleteUseAutomaticRenderTargetSizeValue`
- `0x140003112`: `UninstallFonts`
- `0x140003120`: `ChangeStartupTaskStatus`
- `0x1400032e3`: `CompleteBrailleInstallation`
- `0x1400032ff`: `SetBrailleFodRegistry`
- `0x14000330d`: `DeleteBrailleFodRegistry`
- `0x140003329`: `AssignedAccessAdminHelper`
- `0x140003337`: `ConfigureGpuHardwareScheduling`
- `0x140003555`: `StorageDeletePartition`
- `0x140003563`: `StorageRenameVolume`
- `0x14000359b`: `StorageSetWriteCaching`
- `0x1400035a9`: `StorageRenamePool`
- `0x1400035c5`: `StorageDeletePool`
- `0x1400035d3`: `StorageRemoveDiskFromPool`
- `0x1400035ef`: `StorageRenameSpace`
- `0x1400035fd`: `StorageDeleteSpace`
- `0x1400037c1`: `StorageMountVolumeToPath`
- `0x1400037e4`: `StorageRemoveAccessPath`
- `0x1400037f2`: `UpdateCameraDeviceState`
- `0x14000380e`: `InstalledUpdatesAdminHelper`
- `0x140003a8d`: `AIComponentsAdminFlow`
- `0x140003a4f`: `ConfigureRenewableEnergyCharging`
- `0x140003aa5`: `CustomConfigFlightOption`
- `0x140003ab3`: `EnableLongPaths`
- `0x140003ac5`: `DisableLongPaths`
- `0x140003a6b`: `AdaptiveEnergySaverRegistry`
- `0x140003b20`: `CopyCurrentSettingsToWelcomeScreen`
- `0x140003cd4`: `UninstallUpdate`

## pseudocode

```c
const wchar_t *dynamic_initializer_for__g_rgFlowInfo__()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  int v2; // eax
  const wchar_t *result; // rax

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin_SFR>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin_SFR>::GetImpl'::`2'::impl)
    || (v2 = LUAIsShadowAdminEnabled(v1, v0), dword_1400A88F8 = 2, !v2) )
  {
    dword_1400A88F8 = 1;
  }
  dword_1400A8908 = 53;
  dword_1400A88FC = 0;
  qword_1400A8900 = (__int64)L"RemoteDesktopTurnOffNla";
  qword_1400A8918 = (__int64)L"RemoteDesktopTurnOnNla";
  qword_1400A8930 = (__int64)L"RemoteDesktopTurnOffRdp";
  qword_1400A8948 = (__int64)L"RemoteDesktopTurnOnRdp";
  qword_1400A8960 = (__int64)L"RemoteDesktopSelectUsers";
  qword_1400A8978 = (__int64)L"SecureAssessmentUrl";
  qword_1400A8990 = (__int64)L"SecureAssessmentCap";
  qword_1400A89A8 = (__int64)L"SecureAssessmentFinalize";
  qword_1400A89C0 = (__int64)L"PushButtonReset";
  qword_1400A89D8 = (__int64)L"TurnOnDevicePortal";
  qword_1400A89F0 = (__int64)L"TurnOffDevicePortal";
  qword_1400A8A08 = (__int64)L"TurnOnDeviceDiscovery";
  qword_1400A8A20 = (__int64)L"TurnOffDeviceDiscovery";
  qword_1400A8A38 = (__int64)L"TurnOnDevicePortalAuthentication";
  qword_1400A8A50 = (__int64)L"TurnOffDevicePortalAuthentication";
  qword_1400A8A68 = (__int64)L"TurnOnDevicePortalLoopbackRestriction";
  word_1400A890C = 0;
  qword_1400A8910 = 1;
  dword_1400A8920 = 54;
  word_1400A8924 = 0;
  qword_1400A8928 = 1;
  dword_1400A8938 = 55;
  word_1400A893C = 0;
  qword_1400A8940 = 1;
  dword_1400A8950 = 56;
  word_1400A8954 = 0;
  qword_1400A8958 = 1;
  dword_1400A8968 = 57;
  word_1400A896C = 0;
  qword_1400A8970 = 2;
  dword_1400A8980 = 59;
  word_1400A8984 = 256;
  qword_1400A8988 = 2;
  dword_1400A8998 = 60;
  word_1400A899C = 256;
  qword_1400A89A0 = 2;
  dword_1400A89B0 = 61;
  word_1400A89B4 = 256;
  qword_1400A89B8 = 2;
  dword_1400A89C8 = 63;
  word_1400A89CC = 0;
  qword_1400A89D0 = 2;
  dword_1400A89E0 = 64;
  word_1400A89E4 = 0;
  qword_1400A89E8 = 2;
  dword_1400A89F8 = 65;
  word_1400A89FC = 0;
  qword_1400A8A00 = 2;
  dword_1400A8A10 = 66;
  word_1400A8A14 = 0;
  qword_1400A8A18 = 2;
  dword_1400A8A28 = 67;
  word_1400A8A2C = 0;
  qword_1400A8A30 = 2;
  dword_1400A8A40 = 70;
  word_1400A8A44 = 0;
  qword_1400A8A48 = 2;
  dword_1400A8A58 = 71;
  word_1400A8A5C = 0;
  qword_1400A8A60 = 1;
  dword_1400A8A70 = 68;
  word_1400A8A74 = 0;
  qword_1400A8A78 = 2;
  qword_1400A8A80 = (__int64)L"TurnOffDevicePortalLoopbackRestriction";
  qword_1400A8A98 = (__int64)L"DeviceDiscoveryUnpairAllDevices";
  qword_1400A8AB0 = (__int64)L"SetDevicePortalAuthentication";
  qword_1400A8AC8 = (__int64)L"SetRemoteDesktopRegKeyFlow";
  qword_1400A8AE0 = (__int64)L"SetNLAConnectionsRegKeyFlow";
  qword_1400A8AF8 = (__int64)L"SetRunAsUserRegKeyFlow";
  qword_1400A8B10 = (__int64)L"ClearRunAsUserRegKeyFlow";
  qword_1400A8B28 = (__int64)L"TurnOnCDPBluetooth";
  qword_1400A8B40 = (__int64)L"TurnOffCDPBluetooth";
  qword_1400A8B58 = (__int64)L"EnableCDPUserAuthPolicy";
  qword_1400A8B70 = (__int64)L"DisableCDPUserAuthPolicy";
  qword_1400A8B88 = (__int64)L"InstallInternalDeveloperModePackage";
  qword_1400A8BA0 = (__int64)L"SetProxyInfoAutomaticDetect";
  qword_1400A8BB8 = (__int64)L"SetProxyInfoAutomaticScript";
  qword_1400A8BD0 = (__int64)L"SetProxyInfoManual";
  qword_1400A8BE8 = (__int64)L"EnterProductKey";
  dword_1400A8A88 = 69;
  word_1400A8A8C = 0;
  qword_1400A8A90 = 2;
  dword_1400A8AA0 = 72;
  word_1400A8AA4 = 0;
  qword_1400A8AA8 = 1;
  dword_1400A8AB8 = 73;
  word_1400A8ABC = 256;
  qword_1400A8AC0 = 1;
  dword_1400A8AD0 = 74;
  word_1400A8AD4 = 0;
  qword_1400A8AD8 = 2;
  dword_1400A8AE8 = 75;
  word_1400A8AEC = 0;
  qword_1400A8AF0 = 2;
  dword_1400A8B00 = 76;
  word_1400A8B04 = 0;
  qword_1400A8B08 = 2;
  dword_1400A8B18 = 77;
  word_1400A8B1C = 0;
  qword_1400A8B20 = 2;
  dword_1400A8B30 = 78;
  word_1400A8B34 = 0;
  qword_1400A8B38 = 2;
  dword_1400A8B48 = 79;
  word_1400A8B4C = 0;
  qword_1400A8B50 = 2;
  dword_1400A8B60 = 80;
  word_1400A8B64 = 0;
  qword_1400A8B68 = 2;
  dword_1400A8B78 = 81;
  word_1400A8B7C = 0;
  qword_1400A8B80 = 2;
  dword_1400A8B90 = 82;
  word_1400A8B94 = 0;
  qword_1400A8B98 = 2;
  dword_1400A8BA8 = 83;
  word_1400A8BAC = 256;
  qword_1400A8BB0 = 2;
  dword_1400A8BC0 = 84;
  word_1400A8BC4 = 256;
  qword_1400A8BC8 = 2;
  dword_1400A8BD8 = 85;
  word_1400A8BDC = 256;
  qword_1400A8BE0 = 2;
  dword_1400A8BF0 = 86;
  word_1400A8BF4 = 0;
  qword_1400A8BF8 = 1;
  dword_1400A8C08 = 179;
  qword_1400A8C00 = (__int64)L"LaunchClipESU";
  word_1400A8C0C = 0;
  qword_1400A8C18 = (__int64)L"LaunchClipRenew";
  qword_1400A8C30 = (__int64)L"FeaturedResetPC";
  qword_1400A8C48 = (__int64)L"UninstallOS";
  qword_1400A8C60 = (__int64)L"TroubleshootActivation";
  qword_1400A8C78 = (__int64)L"SetDefaultSecurityProduct";
  qword_1400A8C90 = (__int64)L"SetForceQualityLevelValue";
  qword_1400A8CA8 = (__int64)L"DeleteForceQualityLevelValue";
  qword_1400A8CC0 = (__int64)L"SetUseAutomaticRenderTargetSizeValue";
  qword_1400A8CD8 = (__int64)L"DeleteUseAutomaticRenderTargetSizeValue";
  qword_1400A8CF0 = (__int64)L"SetInboxATAutoStartAtLogonDesktop";
  qword_1400A8D08 = (__int64)L"Shutdown";
  qword_1400A8D20 = (__int64)L"UninstallFonts";
  qword_1400A8D38 = (__int64)L"ChangeStartupTaskStatus";
  qword_1400A8D50 = (__int64)L"SetCamSystemGlobal";
  qword_1400A8D68 = (__int64)L"CleanmgrAdminHelper";
  qword_1400A8C10 = 2;
  dword_1400A8C20 = 150;
  word_1400A8C24 = 0;
  qword_1400A8C28 = 2;
  dword_1400A8C38 = 87;
  word_1400A8C3C = 0;
  qword_1400A8C40 = 1;
  dword_1400A8C50 = 88;
  word_1400A8C54 = 0;
  qword_1400A8C58 = 1;
  dword_1400A8C68 = 89;
  word_1400A8C6C = 0;
  qword_1400A8C70 = 1;
  dword_1400A8C80 = 90;
  word_1400A8C84 = 256;
  qword_1400A8C88 = 2;
  dword_1400A8C98 = 91;
  word_1400A8C9C = 256;
  qword_1400A8CA0 = 2;
  dword_1400A8CB0 = 92;
  word_1400A8CB4 = 256;
  qword_1400A8CB8 = 2;
  dword_1400A8CC8 = 93;
  word_1400A8CCC = 256;
  qword_1400A8CD0 = 2;
  dword_1400A8CE0 = 94;
  word_1400A8CE4 = 0;
  qword_1400A8CE8 = 2;
  dword_1400A8CF8 = 96;
  word_1400A8CFC = 256;
  qword_1400A8D00 = 2;
  dword_1400A8D10 = 98;
  word_1400A8D14 = 256;
  qword_1400A8D18 = 2;
  dword_1400A8D28 = 99;
  word_1400A8D2C = 256;
  qword_1400A8D30 = 2;
  dword_1400A8D40 = 100;
  word_1400A8D44 = 256;
  qword_1400A8D48 = 2;
  dword_1400A8D58 = 101;
  word_1400A8D5C = 256;
  qword_1400A8D60 = 2;
  dword_1400A8D70 = 102;
  word_1400A8D74 = 0;
  qword_1400A8D78 = 3;
  dword_1400A8D88 = 103;
  qword_1400A8D80 = (__int64)L"UseNarratorSettingsBeforeSignIn";
  qword_1400A8D98 = (__int64)L"CompleteBrailleInstallation";
  qword_1400A8DB0 = (__int64)L"SetBrailleDisplayDriver";
  qword_1400A8DC8 = (__int64)L"SetBrailleFodRegistry";
  qword_1400A8DE0 = (__int64)L"DeleteBrailleFodRegistry";
  qword_1400A8DF8 = (__int64)L"ReenableBrailleDisplay";
  qword_1400A8E10 = (__int64)L"AssignedAccessAdminHelper";
  qword_1400A8E28 = (__int64)L"ConfigureGpuHardwareScheduling";
  qword_1400A8E40 = (__int64)L"EnableFamilyRosterAutomaticRefresh";
  qword_1400A8E58 = (__int64)L"SetDevicePasswordLessSetting";
  qword_1400A8E70 = (__int64)L"UnsetDevicePasswordLessSetting";
  qword_1400A8E88 = (__int64)L"SetDeviceAutologinAfterRestartSettingBugFix";
  qword_1400A8EA0 = (__int64)L"UnsetDeviceAutologinAfterRestartSetting";
  qword_1400A8EB8 = (__int64)L"SpecializeDisplay";
  qword_1400A8ED0 = (__int64)L"StorageAdminHelper";
  qword_1400A8EE8 = (__int64)L"StorageSetDriveLetter";
  word_1400A8D8C = 0;
  qword_1400A8D90 = 2;
  dword_1400A8DA0 = 104;
  word_1400A8DA4 = 0;
  qword_1400A8DA8 = 2;
  dword_1400A8DB8 = 105;
  word_1400A8DBC = 256;
  qword_1400A8DC0 = 2;
  dword_1400A8DD0 = 143;
  word_1400A8DD4 = 256;
  qword_1400A8DD8 = 2;
  dword_1400A8DE8 = 144;
  word_1400A8DEC = 0;
  qword_1400A8DF0 = 2;
  dword_1400A8E00 = 106;
  word_1400A8E04 = 256;
  qword_1400A8E08 = 2;
  dword_1400A8E18 = 107;
  word_1400A8E1C = 0;
  qword_1400A8E20 = 3;
  dword_1400A8E30 = 109;
  word_1400A8E34 = 256;
  qword_1400A8E38 = 2;
  dword_1400A8E48 = 110;
  word_1400A8E4C = 256;
  qword_1400A8E50 = 2;
  dword_1400A8E60 = 111;
  word_1400A8E64 = 0;
  qword_1400A8E68 = 2;
  dword_1400A8E78 = 112;
  word_1400A8E7C = 0;
  qword_1400A8E80 = 2;
  dword_1400A8E90 = 113;
  word_1400A8E94 = 0;
  qword_1400A8E98 = 1;
  dword_1400A8EA8 = 114;
  word_1400A8EAC = 0;
  qword_1400A8EB0 = 2;
  dword_1400A8EC0 = 115;
  word_1400A8EC4 = 256;
  qword_1400A8EC8 = 2;
  dword_1400A8ED8 = 117;
  word_1400A8EDC = 0;
  qword_1400A8EE0 = 3;
  dword_1400A8EF0 = 118;
  word_1400A8EF4 = 256;
  qword_1400A8EF8 = 2;
  qword_1400A8F00 = (__int64)L"StorageInitializeDisk";
  qword_1400A8F18 = (__int64)L"StorageResizePartition";
  qword_1400A8F30 = (__int64)L"StorageDeletePartition";
  qword_1400A8F48 = (__int64)L"StorageRenameVolume";
  qword_1400A8F60 = (__int64)L"StorageMakeDiskOnline";
  qword_1400A8F78 = (__int64)L"StorageMakeDiskOffline";
  qword_1400A8F90 = (__int64)L"StorageSwitchPartitionStyle";
  qword_1400A8FA8 = (__int64)L"StorageSetWriteCaching";
  qword_1400A8FC0 = (__int64)L"StorageRenamePool";
  qword_1400A8FD8 = (__int64)L"StorageUpgradePool";
  qword_1400A8FF0 = (__int64)L"StorageDeletePool";
  qword_1400A9008 = (__int64)L"StorageRemoveDiskFromPool";
  qword_1400A9020 = (__int64)L"StorageUnretireDisk";
  qword_1400A9038 = (__int64)L"StorageRenameSpace";
  qword_1400A9050 = (__int64)L"StorageDeleteSpace";
  qword_1400A9068 = (__int64)L"StoragePrepareDiskForRemoval";
  dword_1400A8F08 = 119;
  word_1400A8F0C = 256;
  qword_1400A8F10 = 2;
  dword_1400A8F20 = 120;
  word_1400A8F24 = 256;
  qword_1400A8F28 = 2;
  dword_1400A8F38 = 121;
  word_1400A8F3C = 256;
  qword_1400A8F40 = 2;
  dword_1400A8F50 = 122;
  word_1400A8F54 = 256;
  dword_1400A8F58 = 2;
  dword_1400A8F5C = 3;
  dword_1400A8F68 = 123;
  word_1400A8F6C = 256;
  qword_1400A8F70 = 2;
  dword_1400A8F80 = 124;
  word_1400A8F84 = 256;
  qword_1400A8F88 = 2;
  dword_1400A8F98 = 125;
  word_1400A8F9C = 256;
  qword_1400A8FA0 = 2;
  dword_1400A8FB0 = 126;
  word_1400A8FB4 = 256;
  qword_1400A8FB8 = 2;
  dword_1400A8FC8 = 127;
  word_1400A8FCC = 256;
  dword_1400A8FD0 = 2;
  dword_1400A8FD4 = 3;
  dword_1400A8FE0 = 128;
  word_1400A8FE4 = 256;
  qword_1400A8FE8 = 2;
  dword_1400A8FF8 = 129;
  word_1400A8FFC = 256;
  qword_1400A9000 = 2;
  dword_1400A9010 = 130;
  word_1400A9014 = 256;
  qword_1400A9018 = 2;
  dword_1400A9028 = 131;
  word_1400A902C = 256;
  qword_1400A9030 = 2;
  dword_1400A9040 = 132;
  word_1400A9044 = 256;
  dword_1400A9048 = 2;
  dword_1400A904C = 3;
  dword_1400A9058 = 133;
  word_1400A905C = 256;
  qword_1400A9060 = 2;
  dword_1400A9070 = 134;
  word_1400A9074 = 256;
  qword_1400A9078 = 2;
  qword_1400A9080 = (__int64)L"StorageMountVolumeToPath";
  qword_1400A9098 = (__int64)L"StorageExtendSpace";
  qword_1400A90B0 = (__int64)L"StorageRemoveAccessPath";
  qword_1400A90C8 = (__int64)L"UpdateCameraDeviceState";
  qword_1400A90E0 = (__int64)L"SetAllow3DofTrackingValue";
  qword_1400A90F8 = (__int64)L"InstalledUpdatesAdminHelper";
  qword_1400A9110 = (__int64)L"ViewWifiPassword";
  qword_1400A9128 = (__int64)L"StoreShareFriendlyDeviceNameToRegisty";
  qword_1400A9140 = (__int64)L"RunInPlaceUpgrade";
  qword_1400A9158 = (__int64)L"PhoneActivation";
  qword_1400A9170 = (__int64)L"EnablePeripheralsWithESS";
  qword_1400A9188 = (__int64)L"DisablePeripheralsWithESS";
  qword_1400A91A0 = (__int64)L"SetSudoMode";
  qword_1400A91B8 = (__int64)L"PrinterPause";
  qword_1400A91D0 = (__int64)L"PrinterResume";
  qword_1400A91E8 = (__int64)L"EnableWindowsProtectedPrint";
  dword_1400A9088 = 135;
  word_1400A908C = 256;
  dword_1400A9090 = 2;
  dword_1400A9094 = 3;
  dword_1400A90A0 = 136;
  word_1400A90A4 = 256;
  qword_1400A90A8 = 2;
  dword_1400A90B8 = 137;
  word_1400A90BC = 256;
  dword_1400A90C0 = 2;
  dword_1400A90C4 = 3;
  dword_1400A90D0 = 139;
  word_1400A90D4 = 256;
  qword_1400A90D8 = 2;
  dword_1400A90E8 = 140;
  word_1400A90EC = 256;
  qword_1400A90F0 = 2;
  dword_1400A9100 = 141;
  word_1400A9104 = 0;
  qword_1400A9108 = 3;
  dword_1400A9118 = 142;
  word_1400A911C = 256;
  qword_1400A9120 = 1;
  dword_1400A9130 = 148;
  word_1400A9134 = 256;
  qword_1400A9138 = 2;
  dword_1400A9148 = 149;
  word_1400A914C = 256;
  qword_1400A9150 = 1;
  dword_1400A9160 = 145;
  word_1400A9164 = 0;
  qword_1400A9168 = 1;
  dword_1400A9178 = 146;
  word_1400A917C = 0;
  qword_1400A9180 = 2;
  dword_1400A9190 = 147;
  word_1400A9194 = 0;
  qword_1400A9198 = 2;
  dword_1400A91A8 = 151;
  word_1400A91AC = 256;
  qword_1400A91B0 = 2;
  dword_1400A91C0 = 152;
  word_1400A91C4 = 256;
  qword_1400A91C8 = 2;
  dword_1400A91D8 = 153;
  word_1400A91DC = 256;
  qword_1400A91E0 = 2;
  dword_1400A91F0 = 154;
  qword_1400A9258 = 3;
  qword_1400A9200 = (__int64)L"DisableWindowsProtectedPrint";
  word_1400A91F4 = 0;
  qword_1400A9218 = (__int64)L"SetSystemDefaultColorProfile";
  qword_1400A91F8 = 1;
  qword_1400A9230 = (__int64)L"FindMyFiles";
  dword_1400A9208 = 155;
  qword_1400A9248 = (__int64)L"AIComponentsAdminFlow";
  qword_1400A9278 = (__int64)L"CustomConfigFlightOption";
  qword_1400A9290 = (__int64)L"EnableLongPaths";
  word_1400A920C = 0;
  qword_1400A92A8 = (__int64)L"DisableLongPaths";
  qword_1400A92C0 = (__int64)L"EnableFeature";
  qword_1400A92D8 = (__int64)L"DisableFeature";
  qword_1400A92F0 = (__int64)L"HelloFaceCheckEAS";
  qword_1400A9308 = (__int64)L"HelloFaceUncheckEAS";
  qword_1400A9338 = (__int64)L"SetLanguageUnicodeAdminFlow";
  qword_1400A9350 = (__int64)L"CopyCurrentSettingsToWelcomeScreen";
  qword_1400A9368 = (__int64)L"QuickMachineRecovery";
  qword_1400A9210 = 1;
  dword_1400A9220 = 156;
  word_1400A9224 = 256;
  qword_1400A9228 = 2;
  dword_1400A9238 = 157;
  word_1400A923C = 256;
  qword_1400A9240 = 2;
  dword_1400A9250 = 158;
  word_1400A9254 = 0;
  qword_1400A9260 = (__int64)L"ConfigureRenewableEnergyCharging";
  dword_1400A9268 = 159;
  word_1400A926C = 256;
  qword_1400A9270 = 2;
  dword_1400A9280 = 160;
  word_1400A9284 = 0;
  qword_1400A9288 = 1;
  dword_1400A9298 = 161;
  word_1400A929C = 0;
  qword_1400A92A0 = 2;
  dword_1400A92B0 = 162;
  word_1400A92B4 = 0;
  qword_1400A92B8 = 2;
  dword_1400A92C8 = 163;
  word_1400A92CC = 256;
  qword_1400A92D0 = 2;
  dword_1400A92E0 = 164;
  word_1400A92E4 = 256;
  qword_1400A92E8 = 2;
  dword_1400A92F8 = 165;
  word_1400A92FC = 0;
  qword_1400A9300 = 2;
  dword_1400A9310 = 166;
  word_1400A9314 = 0;
  qword_1400A9318 = 2;
  qword_1400A9320 = (__int64)L"AdaptiveEnergySaverRegistry";
  dword_1400A9328 = 167;
  word_1400A932C = 256;
  qword_1400A9330 = 2;
  dword_1400A9340 = 168;
  word_1400A9344 = 256;
  qword_1400A9348 = 2;
  dword_1400A9358 = 169;
  word_1400A935C = 256;
  qword_1400A9360 = 2;
  word_1400A938C = 0;
  qword_1400A9380 = (__int64)L"TurnOnEss";
  qword_1400A9398 = (__int64)L"TurnOffEss";
  qword_1400A93B0 = (__int64)L"SetTimeServer";
  qword_1400A93C8 = (__int64)L"UninstallUpdate";
  qword_1400A9410 = (__int64)L"EnableIsolationEnvironment";
  qword_1400A9428 = (__int64)L"DisableIsolationEnvironment";
  qword_1400A9440 = (__int64)L"PointInTimeRestore";
  result = L"SetConnectorEnvironmentPolicy";
  word_1400A93A4 = 0;
  word_1400A93BC = 0;
  qword_1400A93C0 = 1;
  qword_1400A93D8 = 1;
  word_1400A941C = 0;
  qword_1400A9420 = 1;
  word_1400A9434 = 0;
  qword_1400A9458 = (__int64)L"SetConnectorEnvironmentPolicy";
  dword_1400A9370 = 170;
  word_1400A9374 = 256;
  qword_1400A9378 = 2;
  dword_1400A9388 = 176;
  qword_1400A9390 = 2;
  dword_1400A93A0 = 177;
  qword_1400A93A8 = 2;
  dword_1400A93B8 = 178;
  dword_1400A93D0 = 180;
  word_1400A93D4 = 256;
  qword_1400A93E0 = (__int64)L"AdaptiveEnergySaverRegistry";
  dword_1400A93E8 = 167;
  word_1400A93EC = 256;
  qword_1400A93F0 = 2;
  qword_1400A93F8 = (__int64)L"ConfigureRenewableEnergyCharging";
  dword_1400A9400 = 159;
  word_1400A9404 = 256;
  qword_1400A9408 = 2;
  dword_1400A9418 = 181;
  dword_1400A9430 = 182;
  qword_1400A9438 = 2;
  dword_1400A9448 = 183;
  word_1400A944C = 256;
  qword_1400A9450 = 2;
  dword_1400A9460 = 184;
  word_1400A9464 = 256;
  qword_1400A9468 = 2;
  return result;
}

```

## disassembly

```asm
0x140002b40  mov     [rsp+arg_0], rbx
0x140002b45  mov     [rsp+arg_8], rsi
0x140002b4a  push    rdi
0x140002b4b  sub     rsp, 20h
0x140002b4f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin_SFR@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin_SFR@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin_SFR> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin_SFR>::GetImpl(void)'::`2'::impl
0x140002b56  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin_SFR@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin_SFR>::__private_IsEnabled(void)
0x140002b5b  mov     esi, 1
0x140002b60  xor     ebx, ebx
0x140002b62  lea     edi, [rsi+1]
0x140002b65  test    al, al
0x140002b67  jz      short loc_140002B78
0x140002b69  call    LUAIsShadowAdminEnabled
0x140002b6e  mov     cs:dword_1400A88F8, edi
0x140002b74  test    eax, eax
0x140002b76  jnz     short loc_140002B7E
0x140002b78  mov     cs:dword_1400A88F8, esi
0x140002b7e  xor     eax, eax
0x140002b80  mov     cs:dword_1400A8908, 35h ; '5'
0x140002b8a  mov     cs:dword_1400A88FC, eax
0x140002b90  lea     rax, aRemotedesktopt_1; "RemoteDesktopTurnOffNla"
0x140002b97  mov     cs:qword_1400A8900, rax
0x140002b9e  lea     rax, aRemotedesktopt; "RemoteDesktopTurnOnNla"
0x140002ba5  mov     cs:qword_1400A8918, rax
0x140002bac  lea     rax, aRemotedesktopt_2; "RemoteDesktopTurnOffRdp"
0x140002bb3  mov     cs:qword_1400A8930, rax
0x140002bba  lea     rax, aRemotedesktopt_0; "RemoteDesktopTurnOnRdp"
0x140002bc1  mov     cs:qword_1400A8948, rax
0x140002bc8  lea     rax, aRemotedesktops; "RemoteDesktopSelectUsers"
0x140002bcf  mov     cs:qword_1400A8960, rax
0x140002bd6  lea     rax, aSecureassessme; "SecureAssessmentUrl"
0x140002bdd  mov     cs:qword_1400A8978, rax
0x140002be4  lea     rax, aSecureassessme_0; "SecureAssessmentCap"
0x140002beb  mov     cs:qword_1400A8990, rax
0x140002bf2  lea     rax, aSecureassessme_1; "SecureAssessmentFinalize"
0x140002bf9  mov     cs:qword_1400A89A8, rax
0x140002c00  lea     rax, aPushbuttonrese; "PushButtonReset"
0x140002c07  mov     cs:qword_1400A89C0, rax
0x140002c0e  lea     rax, aTurnondevicepo_3; "TurnOnDevicePortal"
0x140002c15  mov     cs:qword_1400A89D8, rax
0x140002c1c  lea     rax, aTurnoffdevicep_1; "TurnOffDevicePortal"
0x140002c23  mov     cs:qword_1400A89F0, rax
0x140002c2a  lea     rax, aTurnondevicedi; "TurnOnDeviceDiscovery"
0x140002c31  mov     cs:qword_1400A8A08, rax
0x140002c38  lea     rax, aTurnoffdeviced; "TurnOffDeviceDiscovery"
0x140002c3f  mov     cs:qword_1400A8A20, rax
0x140002c46  lea     rax, aTurnondevicepo_1; "TurnOnDevicePortalAuthentication"
0x140002c4d  mov     cs:qword_1400A8A38, rax
0x140002c54  lea     rax, aTurnoffdevicep_2; "TurnOffDevicePortalAuthentication"
0x140002c5b  mov     cs:qword_1400A8A50, rax
0x140002c62  lea     rax, aTurnondevicepo_0; "TurnOnDevicePortalLoopbackRestriction"
0x140002c69  mov     cs:qword_1400A8A68, rax
0x140002c70  mov     cs:word_1400A890C, bx
0x140002c77  mov     cs:qword_1400A8910, rsi
0x140002c7e  mov     cs:dword_1400A8920, 36h ; '6'
0x140002c88  mov     cs:word_1400A8924, bx
0x140002c8f  mov     cs:qword_1400A8928, rsi
0x140002c96  mov     cs:dword_1400A8938, 37h ; '7'
0x140002ca0  mov     cs:word_1400A893C, bx
0x140002ca7  mov     cs:qword_1400A8940, rsi
0x140002cae  mov     cs:dword_1400A8950, 38h ; '8'
0x140002cb8  mov     cs:word_1400A8954, bx
0x140002cbf  mov     cs:qword_1400A8958, rsi
0x140002cc6  mov     cs:dword_1400A8968, 39h ; '9'
0x140002cd0  mov     cs:word_1400A896C, bx
0x140002cd7  mov     cs:qword_1400A8970, rdi
0x140002cde  mov     cs:dword_1400A8980, 3Bh ; ';'
0x140002ce8  mov     cs:word_1400A8984, 100h
0x140002cf1  mov     cs:qword_1400A8988, rdi
0x140002cf8  mov     cs:dword_1400A8998, 3Ch ; '<'
0x140002d02  mov     cs:word_1400A899C, 100h
0x140002d0b  mov     cs:qword_1400A89A0, rdi
0x140002d12  mov     cs:dword_1400A89B0, 3Dh ; '='
0x140002d1c  mov     cs:word_1400A89B4, 100h
0x140002d25  mov     cs:qword_1400A89B8, rdi
0x140002d2c  mov     cs:dword_1400A89C8, 3Fh ; '?'
0x140002d36  mov     cs:word_1400A89CC, bx
0x140002d3d  mov     cs:qword_1400A89D0, rdi
0x140002d44  mov     cs:dword_1400A89E0, 40h ; '@'
0x140002d4e  mov     cs:word_1400A89E4, bx
0x140002d55  mov     cs:qword_1400A89E8, rdi
0x140002d5c  mov     cs:dword_1400A89F8, 41h ; 'A'
0x140002d66  mov     cs:word_1400A89FC, bx
0x140002d6d  mov     cs:qword_1400A8A00, rdi
0x140002d74  mov     cs:dword_1400A8A10, 42h ; 'B'
0x140002d7e  mov     cs:word_1400A8A14, bx
0x140002d85  mov     cs:qword_1400A8A18, rdi
0x140002d8c  mov     cs:dword_1400A8A28, 43h ; 'C'
0x140002d96  mov     cs:word_1400A8A2C, bx
0x140002d9d  mov     cs:qword_1400A8A30, rdi
0x140002da4  mov     cs:dword_1400A8A40, 46h ; 'F'
0x140002dae  mov     cs:word_1400A8A44, bx
0x140002db5  mov     cs:qword_1400A8A48, rdi
0x140002dbc  mov     cs:dword_1400A8A58, 47h ; 'G'
0x140002dc6  mov     cs:word_1400A8A5C, bx
0x140002dcd  mov     cs:qword_1400A8A60, rsi
0x140002dd4  mov     cs:dword_1400A8A70, 44h ; 'D'
0x140002dde  mov     cs:word_1400A8A74, bx
0x140002de5  lea     rax, aTurnoffdevicep; "TurnOffDevicePortalLoopbackRestriction"
0x140002dec  mov     cs:qword_1400A8A78, rdi
0x140002df3  mov     cs:qword_1400A8A80, rax
0x140002dfa  lea     rax, aDevicediscover; "DeviceDiscoveryUnpairAllDevices"
0x140002e01  mov     cs:qword_1400A8A98, rax
0x140002e08  lea     rax, aSetdeviceporta; "SetDevicePortalAuthentication"
0x140002e0f  mov     cs:qword_1400A8AB0, rax
0x140002e16  lea     rax, aSetremotedeskt; "SetRemoteDesktopRegKeyFlow"
0x140002e1d  mov     cs:qword_1400A8AC8, rax
0x140002e24  lea     rax, aSetnlaconnecti; "SetNLAConnectionsRegKeyFlow"
0x140002e2b  mov     cs:qword_1400A8AE0, rax
0x140002e32  lea     rax, aSetrunasuserre; "SetRunAsUserRegKeyFlow"
0x140002e39  mov     cs:qword_1400A8AF8, rax
0x140002e40  lea     rax, aClearrunasuser; "ClearRunAsUserRegKeyFlow"
0x140002e47  mov     cs:qword_1400A8B10, rax
0x140002e4e  lea     rax, aTurnoncdpbluet; "TurnOnCDPBluetooth"
0x140002e55  mov     cs:qword_1400A8B28, rax
0x140002e5c  lea     rax, aTurnoffcdpblue; "TurnOffCDPBluetooth"
0x140002e63  mov     cs:qword_1400A8B40, rax
0x140002e6a  lea     rax, aEnablecdpusera; "EnableCDPUserAuthPolicy"
0x140002e71  mov     cs:qword_1400A8B58, rax
0x140002e78  lea     rax, aDisablecdpuser; "DisableCDPUserAuthPolicy"
0x140002e7f  mov     cs:qword_1400A8B70, rax
0x140002e86  lea     rax, aInstallinterna; "InstallInternalDeveloperModePackage"
0x140002e8d  mov     cs:qword_1400A8B88, rax
0x140002e94  lea     rax, aSetproxyinfoau_0; "SetProxyInfoAutomaticDetect"
0x140002e9b  mov     cs:qword_1400A8BA0, rax
0x140002ea2  lea     rax, aSetproxyinfoau; "SetProxyInfoAutomaticScript"
0x140002ea9  mov     cs:qword_1400A8BB8, rax
0x140002eb0  lea     rax, aSetproxyinfoma; "SetProxyInfoManual"
0x140002eb7  mov     cs:qword_1400A8BD0, rax
0x140002ebe  lea     rax, aEnterproductke; "EnterProductKey"
0x140002ec5  mov     cs:qword_1400A8BE8, rax
0x140002ecc  mov     cs:dword_1400A8A88, 45h ; 'E'
0x140002ed6  mov     cs:word_1400A8A8C, bx
0x140002edd  mov     cs:qword_1400A8A90, rdi
0x140002ee4  mov     cs:dword_1400A8AA0, 48h ; 'H'
0x140002eee  mov     cs:word_1400A8AA4, bx
0x140002ef5  mov     cs:qword_1400A8AA8, rsi
0x140002efc  mov     cs:dword_1400A8AB8, 49h ; 'I'
0x140002f06  mov     cs:word_1400A8ABC, 100h
0x140002f0f  mov     cs:qword_1400A8AC0, rsi
0x140002f16  mov     cs:dword_1400A8AD0, 4Ah ; 'J'
0x140002f20  mov     cs:word_1400A8AD4, bx
0x140002f27  mov     cs:qword_1400A8AD8, rdi
0x140002f2e  mov     cs:dword_1400A8AE8, 4Bh ; 'K'
0x140002f38  mov     cs:word_1400A8AEC, bx
0x140002f3f  mov     cs:qword_1400A8AF0, rdi
0x140002f46  mov     cs:dword_1400A8B00, 4Ch ; 'L'
0x140002f50  mov     cs:word_1400A8B04, bx
0x140002f57  mov     cs:qword_1400A8B08, rdi
0x140002f5e  mov     cs:dword_1400A8B18, 4Dh ; 'M'
0x140002f68  mov     cs:word_1400A8B1C, bx
0x140002f6f  mov     cs:qword_1400A8B20, rdi
0x140002f76  mov     cs:dword_1400A8B30, 4Eh ; 'N'
0x140002f80  mov     cs:word_1400A8B34, bx
0x140002f87  mov     cs:qword_1400A8B38, rdi
0x140002f8e  mov     cs:dword_1400A8B48, 4Fh ; 'O'
0x140002f98  mov     cs:word_1400A8B4C, bx
0x140002f9f  mov     cs:qword_1400A8B50, rdi
0x140002fa6  mov     cs:dword_1400A8B60, 50h ; 'P'
0x140002fb0  mov     cs:word_1400A8B64, bx
0x140002fb7  mov     cs:qword_1400A8B68, rdi
0x140002fbe  mov     cs:dword_1400A8B78, 51h ; 'Q'
0x140002fc8  mov     cs:word_1400A8B7C, bx
0x140002fcf  mov     cs:qword_1400A8B80, rdi
0x140002fd6  mov     cs:dword_1400A8B90, 52h ; 'R'
0x140002fe0  mov     cs:word_1400A8B94, bx
0x140002fe7  mov     cs:qword_1400A8B98, rdi
0x140002fee  mov     cs:dword_1400A8BA8, 53h ; 'S'
0x140002ff8  mov     cs:word_1400A8BAC, 100h
0x140003001  mov     cs:qword_1400A8BB0, rdi
0x140003008  mov     cs:dword_1400A8BC0, 54h ; 'T'
0x140003012  mov     cs:word_1400A8BC4, 100h
0x14000301b  mov     cs:qword_1400A8BC8, rdi
0x140003022  mov     cs:dword_1400A8BD8, 55h ; 'U'
0x14000302c  mov     cs:word_1400A8BDC, 100h
0x140003035  mov     cs:qword_1400A8BE0, rdi
0x14000303c  mov     cs:dword_1400A8BF0, 56h ; 'V'
0x140003046  mov     cs:word_1400A8BF4, bx
0x14000304d  mov     cs:qword_1400A8BF8, rsi
0x140003054  lea     rax, aLaunchclipesu; "LaunchClipESU"
0x14000305b  mov     cs:dword_1400A8C08, 0B3h
0x140003065  mov     cs:qword_1400A8C00, rax
0x14000306c  mov     ecx, 3
0x140003071  lea     rax, aLaunchcliprene; "LaunchClipRenew"
0x140003078  mov     cs:word_1400A8C0C, bx
0x14000307f  mov     cs:qword_1400A8C18, rax
0x140003086  lea     rax, aFeaturedresetp; "FeaturedResetPC"
0x14000308d  mov     cs:qword_1400A8C30, rax
0x140003094  lea     rax, aUninstallos; "UninstallOS"
0x14000309b  mov     cs:qword_1400A8C48, rax
0x1400030a2  lea     rax, aTroubleshootac; "TroubleshootActivation"
0x1400030a9  mov     cs:qword_1400A8C60, rax
0x1400030b0  lea     rax, aSetdefaultsecu; "SetDefaultSecurityProduct"
0x1400030b7  mov     cs:qword_1400A8C78, rax
0x1400030be  lea     rax, aSetforcequalit; "SetForceQualityLevelValue"
0x1400030c5  mov     cs:qword_1400A8C90, rax
0x1400030cc  lea     rax, aDeleteforcequa; "DeleteForceQualityLevelValue"
0x1400030d3  mov     cs:qword_1400A8CA8, rax
0x1400030da  lea     rax, aSetuseautomati; "SetUseAutomaticRenderTargetSizeValue"
0x1400030e1  mov     cs:qword_1400A8CC0, rax
0x1400030e8  lea     rax, aDeleteuseautom; "DeleteUseAutomaticRenderTargetSizeValue"
0x1400030ef  mov     cs:qword_1400A8CD8, rax
0x1400030f6  lea     rax, aSetinboxatauto; "SetInboxATAutoStartAtLogonDesktop"
0x1400030fd  mov     cs:qword_1400A8CF0, rax
0x140003104  lea     rax, aShutdown; "Shutdown"
0x14000310b  mov     cs:qword_1400A8D08, rax
0x140003112  lea     rax, aUninstallfonts; "UninstallFonts"
0x140003119  mov     cs:qword_1400A8D20, rax
0x140003120  lea     rax, aChangestartupt; "ChangeStartupTaskStatus"
0x140003127  mov     cs:qword_1400A8D38, rax
0x14000312e  lea     rax, aSetcamsystemgl; "SetCamSystemGlobal"
0x140003135  mov     cs:qword_1400A8D50, rax
0x14000313c  lea     rax, aCleanmgradminh; "CleanmgrAdminHelper"
0x140003143  mov     cs:qword_1400A8D68, rax
0x14000314a  mov     cs:qword_1400A8C10, rdi
0x140003151  mov     cs:dword_1400A8C20, 96h
0x14000315b  mov     cs:word_1400A8C24, bx
0x140003162  mov     cs:qword_1400A8C28, rdi
0x140003169  mov     cs:dword_1400A8C38, 57h ; 'W'
0x140003173  mov     cs:word_1400A8C3C, bx
0x14000317a  mov     cs:qword_1400A8C40, rsi
0x140003181  mov     cs:dword_1400A8C50, 58h ; 'X'
0x14000318b  mov     cs:word_1400A8C54, bx
0x140003192  mov     cs:qword_1400A8C58, rsi
0x140003199  mov     cs:dword_1400A8C68, 59h ; 'Y'
0x1400031a3  mov     cs:word_1400A8C6C, bx
0x1400031aa  mov     cs:qword_1400A8C70, rsi
0x1400031b1  mov     cs:dword_1400A8C80, 5Ah ; 'Z'
0x1400031bb  mov     cs:word_1400A8C84, 100h
0x1400031c4  mov     cs:qword_1400A8C88, rdi
0x1400031cb  mov     cs:dword_1400A8C98, 5Bh ; '['
0x1400031d5  mov     cs:word_1400A8C9C, 100h
0x1400031de  mov     cs:qword_1400A8CA0, rdi
0x1400031e5  mov     cs:dword_1400A8CB0, 5Ch ; '\'
0x1400031ef  mov     cs:word_1400A8CB4, 100h
0x1400031f8  mov     cs:qword_1400A8CB8, rdi
0x1400031ff  mov     cs:dword_1400A8CC8, 5Dh ; ']'
0x140003209  mov     cs:word_1400A8CCC, 100h
0x140003212  mov     cs:qword_1400A8CD0, rdi
0x140003219  mov     cs:dword_1400A8CE0, 5Eh ; '^'
0x140003223  mov     cs:word_1400A8CE4, bx
0x14000322a  mov     cs:qword_1400A8CE8, rdi
0x140003231  mov     cs:dword_1400A8CF8, 60h ; '`'
0x14000323b  mov     cs:word_1400A8CFC, 100h
0x140003244  mov     cs:qword_1400A8D00, rdi
0x14000324b  mov     cs:dword_1400A8D10, 62h ; 'b'
0x140003255  mov     cs:word_1400A8D14, 100h
0x14000325e  mov     cs:qword_1400A8D18, rdi
0x140003265  mov     cs:dword_1400A8D28, 63h ; 'c'
0x14000326f  mov     cs:word_1400A8D2C, 100h
0x140003278  mov     cs:qword_1400A8D30, rdi
0x14000327f  mov     cs:dword_1400A8D40, 64h ; 'd'
0x140003289  mov     cs:word_1400A8D44, 100h
0x140003292  mov     cs:qword_1400A8D48, rdi
0x140003299  mov     cs:dword_1400A8D58, 65h ; 'e'
0x1400032a3  mov     cs:word_1400A8D5C, 100h
0x1400032ac  mov     cs:qword_1400A8D60, rdi
0x1400032b3  mov     cs:dword_1400A8D70, 66h ; 'f'
0x1400032bd  mov     cs:word_1400A8D74, bx
0x1400032c4  mov     cs:qword_1400A8D78, rcx
0x1400032cb  lea     rax, aUsenarratorset; "UseNarratorSettingsBeforeSignIn"
0x1400032d2  mov     cs:dword_1400A8D88, 67h ; 'g'
0x1400032dc  mov     cs:qword_1400A8D80, rax
0x1400032e3  lea     rax, aCompletebraill; "CompleteBrailleInstallation"
0x1400032ea  mov     cs:qword_1400A8D98, rax
0x1400032f1  lea     rax, aSetbrailledisp; "SetBrailleDisplayDriver"
0x1400032f8  mov     cs:qword_1400A8DB0, rax
0x1400032ff  lea     rax, aSetbraillefodr; "SetBrailleFodRegistry"
0x140003306  mov     cs:qword_1400A8DC8, rax
0x14000330d  lea     rax, aDeletebraillef; "DeleteBrailleFodRegistry"
0x140003314  mov     cs:qword_1400A8DE0, rax
0x14000331b  lea     rax, aReenablebraill; "ReenableBrailleDisplay"
0x140003322  mov     cs:qword_1400A8DF8, rax
0x140003329  lea     rax, aAssignedaccess; "AssignedAccessAdminHelper"
0x140003330  mov     cs:qword_1400A8E10, rax
0x140003337  lea     rax, aConfiguregpuha; "ConfigureGpuHardwareScheduling"
0x14000333e  mov     cs:qword_1400A8E28, rax
0x140003345  lea     rax, aEnablefamilyro; "EnableFamilyRosterAutomaticRefresh"
0x14000334c  mov     cs:qword_1400A8E40, rax
0x140003353  lea     rax, aSetdevicepassw; "SetDevicePasswordLessSetting"
0x14000335a  mov     cs:qword_1400A8E58, rax
0x140003361  lea     rax, aUnsetdevicepas; "UnsetDevicePasswordLessSetting"
0x140003368  mov     cs:qword_1400A8E70, rax
0x14000336f  lea     rax, aSetdeviceautol; "SetDeviceAutologinAfterRestartSettingBu"...
0x140003376  mov     cs:qword_1400A8E88, rax
0x14000337d  lea     rax, aUnsetdeviceaut; "UnsetDeviceAutologinAfterRestartSetting"
0x140003384  mov     cs:qword_1400A8EA0, rax
0x14000338b  lea     rax, aSpecializedisp; "SpecializeDisplay"
0x140003392  mov     cs:qword_1400A8EB8, rax
0x140003399  lea     rax, aStorageadminhe; "StorageAdminHelper"
0x1400033a0  mov     cs:qword_1400A8ED0, rax
0x1400033a7  lea     rax, aStoragesetdriv; "StorageSetDriveLetter"
0x1400033ae  mov     cs:qword_1400A8EE8, rax
0x1400033b5  lea     rax, aStorageinitial; "StorageInitializeDisk"
0x1400033bc  mov     cs:word_1400A8D8C, bx
0x1400033c3  mov     cs:qword_1400A8D90, rdi
0x1400033ca  mov     cs:dword_1400A8DA0, 68h ; 'h'
0x1400033d4  mov     cs:word_1400A8DA4, bx
0x1400033db  mov     cs:qword_1400A8DA8, rdi
0x1400033e2  mov     cs:dword_1400A8DB8, 69h ; 'i'
0x1400033ec  mov     cs:word_1400A8DBC, 100h
  ... truncated ...
```
