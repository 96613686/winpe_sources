# CPITRBase::RestoreFromSnapshot(ushort const *,int,int,ushort const *,void *,PITR::IPITRRestoreProgress *)

- ea: `0x1800170f0`
- end: `0x18001b1cc`
- name: `?RestoreFromSnapshot@CPITRBase@@UEAAJPEBGHH0PEAXPEAUIPITRRestoreProgress@PITR@@@Z`
- size: `16604`
- prototype: `__int64 __fastcall(CPITRBase *__hidden this, const unsigned __int16 *, int, int, const unsigned __int16 *, void *, struct PITR::IPITRRestoreProgress *)`
- caller_count: `0`
- callee_count: `35`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000448c`
- `0x180005614`
- `0x180009e04`
- `0x18000b070`
- `0x18000b0d8`
- `0x18000f98c`
- `0x1800170f0`
- `0x18001c5bc`
- `0x18001de74`
- `0x18001def0`
- `0x180020408`
- `0x180020a10`
- `0x180020b20`
- `0x180020f58`
- `0x180021140`
- `0x18002125c`
- `0x180022750`
- `0x18002a6fc`
- `0x180035878`
- `0x180036624`
- `0x180039424`
- `0x18003a010`
- `0x18003a550`
- `0x18003ac10`
- `0x18003af54`
- `0x18003b094`
- `0x18003bfb0`
- `0x18003fec0`
- `0x1800401c4`
- `0x18004927c`
- `0x18004acc8`
- `0x18004d2a8`
- `0x1800502c2`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x180018272`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x180018272`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180018701`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180018701`
- `api-ms-win-core-registry-l1-1-0!RegRestoreKeyW` at `0x18001a662`
- `api-ms-win-core-registry-l1-1-0!RegRestoreKeyW` at `0x18001a662`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019123`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019139`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019457`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001946a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a234`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a376`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a394`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a3be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a738`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001aae3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001aaee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ab9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001abca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001abe0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001abfa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019123`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019139`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019457`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001946a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a234`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a376`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a394`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a3be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a738`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001aae3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001aaee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ab9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001abca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001abe0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001abfa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001a04f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001a5ca`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001a8fe`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001a04f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001a5ca`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001a8fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001745b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800174cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001753d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800175ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001764d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800176cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017733`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017940`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800179b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017a58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017c3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800180af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018154`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800181e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018280`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018296`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800182d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001834e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800183b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018428`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018477`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001850c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018568`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001870f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018725`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018753`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800188a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001897b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018993`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018a67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018a7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018cad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018d40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018ef3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019016`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800190a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001917b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019291`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001938e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800193dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001952a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019760`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800198c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019956`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800199ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019a19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019acb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ae5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019bed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019cc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019d10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019dd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019e25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ebc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ed6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019fc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a07f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a0d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a15c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a176`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a1cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a2a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a2f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a41d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a433`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a461`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a521`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a532`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a5d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a670`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a6be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a76b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a785`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a871`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a92e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a983`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ade0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001adf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ae23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aef6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001af4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001afd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001745b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800174cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001753d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800175ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001764d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800176cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017733`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017940`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800179b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017a58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017c3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800180af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018154`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800181e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018280`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018296`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800182d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001834e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800183b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018428`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018477`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001850c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018568`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001870f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018725`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018753`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800188a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001897b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018993`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018a67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018a7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018cad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018d40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018ef3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019016`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800190a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001917b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019291`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001938e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800193dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001952a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019760`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800198c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019956`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800199ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019a19`

## string_xrefs

- `0x18001749f`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x18001758e`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x1800197c1`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x18001a57d`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x1800177c0`: `%hs: Failed to initialize COM. Error: 0x%08X`
- `0x180017827`: `SeBackupPrivilege`
- `0x18001b091`: `SeBackupPrivilege`
- `0x180017840`: `SeRestorePrivilege`
- `0x18001b0ac`: `SeRestorePrivilege`
- `0x180019196`: `Failed to open PITR snapshots key %s. Error: 0x%08X`
- `0x180017618`: `PITR_CONFIG_ENV_THOROUGH`
- `0x180017697`: `PITR_CONFIG_ENV_THOROUGH`
- `0x180017859`: `SeSecurityPrivilege`
- `0x18001b0c7`: `SeSecurityPrivilege`
- `0x180017c4f`: `Non-client accessible snapshots need to be exposed`
- `0x180017e4c`: `Real path      : %s`
- `0x180017ec2`: `Real path (NT) : %s`
- `0x180017f32`: `Snap path      : %s`
- `0x180017fa2`: `Snap path (NT) : %s`
- `0x180018767`: `Error creating the store directory: 0x%08X`
- `0x1800187c5`: `System32\config`
- `0x180018bc6`: `Failed to open Control key %s. Error: 0x%08X`
- `0x180019c1d`: `Failed to open Control key %s. Error: 0x%08X`
- `0x18001996c`: `Restoring from snapshot %s completed successfully.`
- `0x180019ea2`: `InstallType`
- `0x18001a74c`: `InstallType`
- `0x180019eec`: `Failed to write InstallType value after restore. Error: 0x%08X`
- `0x18001a79b`: `Failed to write InstallType value after restore. Error: 0x%08X`
- `0x180019fd8`: `Failed to calculate comparison mismatch value. Error: 0x%08X`
- `0x18001a887`: `Failed to calculate comparison mismatch value. Error: 0x%08X`
- `0x18001a045`: `Microsoft\Windows\CurrentVersion\Setup\Recovery\PITR\CompareMatch`
- `0x18001a095`: `Microsoft\Windows\CurrentVersion\Setup\Recovery\PITR\CompareMatch`
- `0x18001a0e8`: `Microsoft\Windows\CurrentVersion\Setup\Recovery\PITR\CompareMatch`
- `0x18001a8f4`: `Microsoft\Windows\CurrentVersion\Setup\Recovery\PITR\CompareMatch`
- `0x18001a944`: `Microsoft\Windows\CurrentVersion\Setup\Recovery\PITR\CompareMatch`
- `0x18001a997`: `Microsoft\Windows\CurrentVersion\Setup\Recovery\PITR\CompareMatch`
- `0x18001a09c`: `Failed to open/create comparison mismatch key %s. Error: 0x%08X`
- `0x18001a0ef`: `Failed to open/create comparison mismatch key %s. Error: 0x%08X`
- `0x18001a94b`: `Failed to open/create comparison mismatch key %s. Error: 0x%08X`
- `0x18001a99e`: `Failed to open/create comparison mismatch key %s. Error: 0x%08X`
- `0x18001a194`: `Failed to write comparison mismatch value %s. Error: 0x%08X`
- `0x18001aa43`: `Failed to write comparison mismatch value %s. Error: 0x%08X`
- `0x18001a1e5`: `Found mismatch comparisons, have set value %s for log collection`
- `0x18001aa94`: `Found mismatch comparisons, have set value %s for log collection`
- `0x18001a5ee`: `Failed to open PITR snapshots key. Error: 0x%08X`
- `0x18001ab3e`: `Failed to uninstall WinSetupBak. Error: 0x%08X`
- `0x18001aca5`: `Preserving driver store path %s for interrupted restore recovery`
- `0x18001ad7e`: `Failed to remove driver store path: %s. Error: 0x%08X`
- `0x18001ae53`: `Failed to remove driver store path: %s. Error: 0x%08X`
- `0x18001af14`: `Current VSS used size is %I64d. We are about to set back the max size to %I64d, some snapshots will be deleted`
- `0x18001af6a`: `Current VSS used size is %I64u. We are about to set back the max size to %I64u, some snapshots will be deleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
__int64 __fastcall CPITRBase::RestoreFromSnapshot(
        const unsigned __int16 **this,
        unsigned __int16 *a2,
        int a3,
        int a4,
        const unsigned __int16 *a5,
        void *a6,
        struct PITR::IPITRRestoreProgress *a7)
{
  DWORD LastError; // edi
  __int64 v11; // rbx
  struct tagLOG_PARTIAL_MSG *v12; // rax
  DWORD v13; // edi
  __int64 v14; // rbx
  const wchar_t *v15; // rsi
  const wchar_t *v16; // r8
  struct tagLOG_PARTIAL_MSG *v17; // rax
  DWORD v18; // edi
  __int64 v19; // rbx
  struct tagLOG_PARTIAL_MSG *v20; // rax
  DWORD v21; // edi
  __int64 v22; // rbx
  struct tagLOG_PARTIAL_MSG *v23; // rax
  const struct UnBCL::String *v24; // rax
  int IsEnvironmentVarSetTrue; // ebx
  DWORD v26; // edi
  __int64 v27; // rbx
  const struct UnBCL::String *v28; // rax
  int v29; // ebx
  DWORD v30; // edi
  __int64 v31; // rbx
  struct tagLOG_PARTIAL_MSG *v32; // rax
  DWORD v33; // edi
  __int64 v34; // rbx
  int SnapshotData; // r15d
  DWORD v36; // edi
  __int64 v37; // rbx
  struct tagLOG_PARTIAL_MSG *v38; // rax
  HKEY v39; // rbx
  HKEY v40; // rdi
  CPITRSnapshotEnumerator *v41; // rax
  CPITRSnapshotEnumerator *v42; // rbx
  __int64 v43; // rdi
  DWORD v44; // edi
  __int64 v45; // rbx
  struct tagLOG_PARTIAL_MSG *v46; // rax
  struct PITR::IPITRSnapshot *v47; // rbx
  DWORD v48; // edi
  __int64 v49; // rbx
  struct tagLOG_PARTIAL_MSG *v50; // rax
  const unsigned __int16 *v51; // rdx
  const char *v52; // rdi
  wchar_t *v53; // rcx
  struct tagLOG_PARTIAL_MSG *v54; // rax
  struct UnBCL::String *v55; // rax
  DWORD v56; // edi
  __int64 v57; // rbx
  struct tagLOG_PARTIAL_MSG *v58; // rax
  UnBCL::String *v59; // rax
  UnBCL::String *v60; // rbx
  DWORD v61; // edi
  __int64 v62; // rbx
  struct tagLOG_PARTIAL_MSG *v63; // rax
  UnBCL::String *v64; // rax
  struct UnBCL::String *P; // rax
  struct UnBCL::String *DevicePathNt; // rax
  UnBCL::String *v67; // rax
  UnBCL::String *v68; // rbx
  struct UnBCL::String *v69; // rax
  struct UnBCL::String *v70; // rax
  DWORD v71; // edi
  __int64 v72; // rbx
  UnBCL::String *v73; // rax
  const char *CString; // rax
  struct tagLOG_PARTIAL_MSG *v75; // rax
  DWORD v76; // edi
  __int64 v77; // rbx
  UnBCL::String *v78; // rax
  const char *v79; // rax
  struct tagLOG_PARTIAL_MSG *v80; // rax
  DWORD v81; // edi
  __int64 v82; // rbx
  UnBCL::String *v83; // rax
  const char *v84; // rax
  struct tagLOG_PARTIAL_MSG *v85; // rax
  DWORD v86; // edi
  __int64 v87; // rbx
  UnBCL::String *v88; // rax
  const char *v89; // rax
  struct tagLOG_PARTIAL_MSG *v90; // rax
  struct UnBCL::String *v91; // rax
  struct UnBCL::String **v92; // rdx
  int *v93; // r8
  struct UnBCL::String *VolumeNameFromPath; // rax
  UnBCL::String *v95; // rax
  UnBCL::String *v96; // rax
  const unsigned __int16 *v97; // rax
  struct UnBCL::String *v98; // rax
  DWORD v99; // edi
  __int64 v100; // rbx
  UnBCL::String *v101; // rax
  const char *v102; // rax
  struct tagLOG_PARTIAL_MSG *v103; // rax
  const struct UnBCL::String *v104; // rbx
  const struct UnBCL::String *v105; // rax
  DWORD v106; // edi
  __int64 v107; // rbx
  struct tagLOG_PARTIAL_MSG *v108; // rax
  struct UnBCL::String *v109; // rax
  DWORD v110; // edi
  __int64 v111; // rbx
  UnBCL::String *v112; // rax
  const char *v113; // rax
  struct tagLOG_PARTIAL_MSG *v114; // rax
  UnBCL::String *v115; // rax
  const WCHAR *v116; // rax
  signed int v117; // eax
  bool v118; // sf
  signed int v119; // eax
  DWORD v120; // edi
  __int64 v121; // rbx
  UnBCL::String *v122; // rax
  const char *v123; // rax
  struct tagLOG_PARTIAL_MSG *v124; // rax
  DWORD v125; // edi
  __int64 v126; // rbx
  UnBCL::String *v127; // rax
  const char *v128; // rax
  DWORD v129; // edi
  __int64 v130; // rbx
  struct tagLOG_PARTIAL_MSG *v131; // rax
  DWORD v132; // edi
  __int64 v133; // rbx
  struct tagLOG_PARTIAL_MSG *v134; // rax
  DWORD v135; // edi
  __int64 v136; // rbx
  DWORD v137; // edi
  __int64 v138; // rbx
  struct tagLOG_PARTIAL_MSG *v139; // rax
  DWORD v140; // edi
  __int64 v141; // rbx
  struct tagLOG_PARTIAL_MSG *v142; // rax
  struct UnBCL::String *v143; // rax
  DWORD v144; // edi
  __int64 v145; // rbx
  UnBCL::String *v146; // rax
  const char *v147; // rax
  struct tagLOG_PARTIAL_MSG *v148; // rax
  const struct UnBCL::String *v149; // rbx
  const struct UnBCL::String *v150; // rax
  struct UnBCL::String *v151; // rax
  const struct UnBCL::String *v152; // rax
  UnBCL::String *v153; // rax
  const WCHAR *v154; // rax
  signed int v155; // eax
  bool v156; // sf
  signed int v157; // eax
  DWORD v158; // edi
  __int64 v159; // rbx
  const struct UnBCL::String *v160; // rbx
  const struct UnBCL::String *v161; // rax
  struct UnBCL::String *v162; // rax
  const struct UnBCL::String *v163; // rbx
  const struct UnBCL::String *v164; // rax
  struct UnBCL::String *v165; // rax
  UnBCL::String *v166; // rax
  const char *v167; // rbx
  UnBCL::String *v168; // rax
  const char *v169; // rax
  const unsigned __int16 *v170; // r8
  DWORD v171; // edi
  __int64 v172; // rbx
  struct tagLOG_PARTIAL_MSG *v173; // rax
  UnBCL::String *v174; // rax
  const unsigned __int16 *v175; // rax
  HKEY v176; // rdi
  signed int v177; // eax
  DWORD v178; // edi
  __int64 v179; // rbx
  UnBCL::String *v180; // rax
  const char *v181; // rax
  struct tagLOG_PARTIAL_MSG *v182; // rax
  UnBCL::String *v183; // rax
  const unsigned __int16 *v184; // rax
  HKEY v185; // rax
  HKEY v186; // rbx
  signed int v187; // eax
  DWORD v188; // edi
  __int64 v189; // rbx
  UnBCL::String *v190; // rax
  const char *v191; // rax
  struct tagLOG_PARTIAL_MSG *v192; // rax
  unsigned int v193; // eax
  struct UnBCL::String *v194; // rax
  UnBCL::String *v195; // rax
  const WCHAR *v196; // rax
  int v197; // eax
  DWORD v198; // edi
  __int64 v199; // rbx
  UnBCL::String *v200; // rax
  const char *v201; // rax
  const struct UnBCL::String *v202; // rbx
  const struct UnBCL::String *v203; // rax
  struct UnBCL::String *v204; // rax
  UnBCL::String *v205; // rax
  const unsigned __int16 *v206; // rax
  DWORD v207; // edi
  __int64 v208; // rbx
  struct tagLOG_PARTIAL_MSG *v209; // rax
  DWORD v210; // edi
  __int64 v211; // rbx
  UnBCL::String *v212; // rax
  const char *v213; // rax
  const struct UnBCL::String *v214; // rbx
  const struct UnBCL::String *v215; // rax
  struct UnBCL::String *v216; // rax
  UnBCL::String *v217; // rax
  const unsigned __int16 *v218; // rax
  DWORD v219; // edi
  __int64 v220; // rbx
  struct tagLOG_PARTIAL_MSG *v221; // rax
  DWORD v222; // edi
  __int64 v223; // rbx
  UnBCL::String *v224; // rax
  const char *v225; // rax
  const struct UnBCL::String *v226; // rbx
  const struct UnBCL::String *v227; // rax
  struct UnBCL::String *v228; // rax
  UnBCL::String *v229; // rax
  const unsigned __int16 *v230; // rax
  DWORD v231; // edi
  __int64 v232; // rbx
  struct tagLOG_PARTIAL_MSG *v233; // rax
  DWORD v234; // edi
  __int64 v235; // rbx
  UnBCL::String *v236; // rax
  const char *v237; // rax
  HKEY v238; // rcx
  int v239; // eax
  DWORD v240; // edi
  __int64 v241; // rbx
  const struct UnBCL::String *v242; // rbx
  const struct UnBCL::String *v243; // rax
  struct UnBCL::String *v244; // rax
  const struct UnBCL::String *v245; // rax
  UnBCL::String *v246; // rax
  const unsigned __int16 *v247; // rax
  signed int v248; // eax
  bool v249; // sf
  signed int v250; // eax
  DWORD v251; // edi
  __int64 v252; // rbx
  UnBCL::String *v253; // rax
  const char *v254; // rax
  struct tagLOG_PARTIAL_MSG *v255; // rax
  UnBCL::String *v256; // rax
  const WCHAR *v257; // rax
  LSTATUS v258; // eax
  DWORD v259; // edi
  __int64 v260; // rbx
  DWORD v261; // edi
  __int64 v262; // rbx
  UnBCL::String *v263; // rax
  const char *v264; // rax
  struct tagLOG_PARTIAL_MSG *v265; // rax
  HKEY v266; // rcx
  struct UnBCL::String *v267; // rbx
  struct UnBCL::String *v268; // rax
  VSS_TIMESTAMP m_tsCreationTimestamp; // r8
  DWORD v270; // edi
  __int64 v271; // rbx
  struct tagLOG_PARTIAL_MSG *v272; // rax
  const struct UnBCL::String *v273; // rbx
  const struct UnBCL::String *v274; // rax
  struct UnBCL::String *v275; // rax
  const struct UnBCL::String *v276; // rax
  const struct UnBCL::String *v277; // rax
  struct UnBCL::FileStream *v278; // rax
  UnBCL::String *v279; // rax
  const struct UnBCL::String *v280; // rbx
  const struct UnBCL::String *v281; // rax
  const struct UnBCL::String *v282; // rax
  DWORD v283; // edi
  __int64 v284; // rbx
  struct tagLOG_PARTIAL_MSG *v285; // rax
  HKEY v286; // rdi
  UnBCL::String *v287; // rax
  const unsigned __int16 *v288; // rbx
  UnBCL::String *v289; // rax
  const unsigned __int16 *v290; // rax
  DWORD v291; // edi
  __int64 v292; // rbx
  struct tagLOG_PARTIAL_MSG *v293; // rax
  const unsigned __int16 *v294; // rcx
  DWORD v295; // edi
  __int64 v296; // rbx
  struct tagLOG_PARTIAL_MSG *v297; // rax
  UnBCL::String *v298; // rax
  const unsigned __int16 *v299; // rax
  signed int v300; // eax
  DWORD v301; // edi
  __int64 v302; // rbx
  UnBCL::String *v303; // rax
  const char *v304; // rax
  struct tagLOG_PARTIAL_MSG *v305; // rax
  UnBCL::String *v306; // rax
  const unsigned __int16 *v307; // rax
  HKEY v308; // rax
  HKEY v309; // rbx
  signed int v310; // eax
  DWORD v311; // edi
  __int64 v312; // rbx
  UnBCL::String *v313; // rax
  const char *v314; // rax
  struct tagLOG_PARTIAL_MSG *v315; // rax
  unsigned int Dword; // eax
  struct UnBCL::String *v317; // rax
  UnBCL::String *v318; // rax
  const WCHAR *v319; // rax
  int v320; // eax
  DWORD v321; // edi
  __int64 v322; // rbx
  UnBCL::String *v323; // rax
  const char *v324; // rax
  struct tagLOG_PARTIAL_MSG *v325; // rax
  HKEY v326; // rbx
  const struct UnBCL::String *v327; // rax
  UnBCL::String *v328; // rax
  const WCHAR *v329; // rax
  DWORD v330; // edi
  __int64 v331; // rbx
  struct tagLOG_PARTIAL_MSG *v332; // rax
  UnBCL::String *v333; // rax
  const char *v334; // rax
  const struct UnBCL::String *v335; // rax
  UnBCL::String *v336; // rax
  const WCHAR *v337; // rax
  DWORD v338; // edi
  __int64 v339; // rbx
  struct tagLOG_PARTIAL_MSG *v340; // rax
  UnBCL::String *v341; // rax
  const char *v342; // rax
  signed int v343; // eax
  DWORD v344; // edi
  __int64 v345; // rbx
  struct tagLOG_PARTIAL_MSG *v346; // rax
  DWORD v347; // edi
  __int64 v348; // rbx
  struct tagLOG_PARTIAL_MSG *v349; // rax
  LSTATUS v350; // eax
  DWORD v351; // edi
  __int64 v352; // rbx
  DWORD v353; // edi
  __int64 v354; // rbx
  signed int v355; // eax
  DWORD v356; // edi
  __int64 v357; // rbx
  struct tagLOG_PARTIAL_MSG *v358; // rax
  DWORD v359; // edi
  __int64 v360; // rbx
  const struct UnBCL::String *v361; // rax
  UnBCL::String *v362; // rax
  const WCHAR *v363; // rax
  DWORD v364; // edi
  __int64 v365; // rbx
  struct tagLOG_PARTIAL_MSG *v366; // rax
  UnBCL::String *v367; // rax
  const char *v368; // rax
  struct tagLOG_PARTIAL_MSG *v369; // rax
  HKEY v370; // rcx
  HKEY v371; // rcx
  const struct UnBCL::String *v372; // rax
  UnBCL::String *v373; // rax
  const unsigned __int16 *v374; // rax
  signed int v375; // eax
  bool v376; // sf
  signed int v377; // eax
  DWORD v378; // edi
  __int64 v379; // rbx
  UnBCL::String *v380; // rax
  const char *v381; // rax
  struct tagLOG_PARTIAL_MSG *v382; // rax
  UnBCL::String *v383; // rax
  const unsigned __int16 *v384; // rax
  HKEY v385; // rax
  DWORD v386; // esi
  __int64 v387; // rdi
  DWORD v388; // ebx
  UnBCL::String *v389; // rax
  const char *v390; // rax
  DWORD v391; // edi
  __int64 v392; // rbx
  struct tagLOG_PARTIAL_MSG *v393; // rax
  UnBCL::String *v394; // rax
  const WCHAR *v395; // rax
  DWORD v396; // edi
  __int64 v397; // rbx
  struct tagLOG_PARTIAL_MSG *v398; // rax
  UnBCL::String *v399; // rax
  const char *v400; // rax
  HKEY v401; // rbx
  signed int v402; // eax
  DWORD v403; // edi
  __int64 v404; // rbx
  struct tagLOG_PARTIAL_MSG *v405; // rax
  DWORD v406; // edi
  __int64 v407; // rbx
  struct tagLOG_PARTIAL_MSG *v408; // rax
  LSTATUS v409; // eax
  DWORD v410; // edi
  __int64 v411; // rbx
  DWORD v412; // edi
  __int64 v413; // rbx
  signed int v414; // eax
  DWORD v415; // edi
  __int64 v416; // rbx
  struct tagLOG_PARTIAL_MSG *v417; // rax
  DWORD v418; // edi
  __int64 v419; // rbx
  HKEY v420; // rcx
  DWORD v421; // edi
  __int64 v422; // rbx
  struct tagLOG_PARTIAL_MSG *v423; // rax
  HKEY v424; // rcx
  HKEY v425; // rcx
  const struct UnBCL::String *v426; // rax
  const struct UnBCL::String *v427; // rax
  DWORD v428; // edi
  __int64 v429; // rbx
  UnBCL::String *v430; // rax
  const char *v431; // rax
  struct tagLOG_PARTIAL_MSG *v432; // rax
  UnBCL::String *v433; // rax
  const WCHAR *v434; // rax
  signed int v435; // eax
  bool v436; // sf
  signed int v437; // eax
  DWORD v438; // edi
  __int64 v439; // rbx
  UnBCL::String *v440; // rax
  const char *v441; // rax
  struct tagLOG_PARTIAL_MSG *v442; // rax
  UnBCL::String *v443; // rax
  const WCHAR *v444; // rax
  signed int v445; // eax
  bool v446; // sf
  signed int v447; // eax
  DWORD v448; // edi
  __int64 v449; // rbx
  UnBCL::String *v450; // rax
  const char *v451; // rax
  struct tagLOG_PARTIAL_MSG *v452; // rax
  struct UnBCL::String *v453; // rax
  DWORD v454; // edi
  __int64 v455; // rbx
  struct tagLOG_PARTIAL_MSG *v456; // rax
  DWORD v457; // edi
  __int64 v458; // rbx
  struct tagLOG_PARTIAL_MSG *v459; // rax
  struct UnBCL::String *v460; // rax
  DWORD v461; // edi
  __int64 v462; // rbx
  UnBCL::String *v463; // rax
  const char *v464; // rax
  struct tagLOG_PARTIAL_MSG *v465; // rax
  void (__fastcall ***v466)(_QWORD, __int64); // r14
  __int64 v467; // rax
  DWORD v468; // esi
  __int64 v469; // rdi
  UnBCL::String *v470; // rax
  const char *v471; // rbx
  UnBCL::String *v472; // rax
  const char *v473; // rax
  struct tagLOG_PARTIAL_MSG *v474; // rax
  int dwOptions; // [rsp+20h] [rbp-2B8h]
  int dwOptionsa; // [rsp+20h] [rbp-2B8h]
  int dwOptionsb; // [rsp+20h] [rbp-2B8h]
  int dwOptionsc; // [rsp+20h] [rbp-2B8h]
  int dwOptionsd; // [rsp+20h] [rbp-2B8h]
  int dwOptionse; // [rsp+20h] [rbp-2B8h]
  int dwOptionsf; // [rsp+20h] [rbp-2B8h]
  int dwOptionsg; // [rsp+20h] [rbp-2B8h]
  int dwOptionsh; // [rsp+20h] [rbp-2B8h]
  int dwOptionsi; // [rsp+20h] [rbp-2B8h]
  DWORD dwOptionsj[2]; // [rsp+20h] [rbp-2B8h]
  int dwOptionsk; // [rsp+20h] [rbp-2B8h]
  int dwOptionsl; // [rsp+20h] [rbp-2B8h]
  int dwOptionsm; // [rsp+20h] [rbp-2B8h]
  int dwOptionsn; // [rsp+20h] [rbp-2B8h]
  DWORD dwOptionso[2]; // [rsp+20h] [rbp-2B8h]
  int dwOptionsp; // [rsp+20h] [rbp-2B8h]
  int dwOptionsq; // [rsp+20h] [rbp-2B8h]
  int dwOptionsr; // [rsp+20h] [rbp-2B8h]
  PHKEY phkResult; // [rsp+38h] [rbp-2A0h]
  PHKEY phkResulta; // [rsp+38h] [rbp-2A0h]
  PHKEY phkResultb; // [rsp+38h] [rbp-2A0h]
  PHKEY phkResultc; // [rsp+38h] [rbp-2A0h]
  PHKEY phkResultd; // [rsp+38h] [rbp-2A0h]
  PHKEY phkResulte; // [rsp+38h] [rbp-2A0h]
  PHKEY phkResultf; // [rsp+38h] [rbp-2A0h]
  PHKEY phkResultg; // [rsp+38h] [rbp-2A0h]
  unsigned int *phkResulth; // [rsp+38h] [rbp-2A0h]
  PHKEY phkResulti; // [rsp+38h] [rbp-2A0h]
  PHKEY phkResultj; // [rsp+38h] [rbp-2A0h]
  PHKEY phkResultk; // [rsp+38h] [rbp-2A0h]
  PHKEY phkResultl; // [rsp+38h] [rbp-2A0h]
  PHKEY phkResultm; // [rsp+38h] [rbp-2A0h]
  PHKEY phkResultn; // [rsp+38h] [rbp-2A0h]
  PHKEY phkResulto; // [rsp+38h] [rbp-2A0h]
  PHKEY phkResultp; // [rsp+38h] [rbp-2A0h]
  PHKEY phkResultq; // [rsp+38h] [rbp-2A0h]
  DWORD lpdwDisposition; // [rsp+40h] [rbp-298h]
  DWORD lpdwDispositiona; // [rsp+40h] [rbp-298h]
  DWORD lpdwDispositionb; // [rsp+40h] [rbp-298h]
  DWORD lpdwDispositionc; // [rsp+40h] [rbp-298h]
  DWORD lpdwDispositiond; // [rsp+40h] [rbp-298h]
  DWORD lpdwDispositione; // [rsp+40h] [rbp-298h]
  DWORD lpdwDispositionf; // [rsp+40h] [rbp-298h]
  DWORD lpdwDispositiong; // [rsp+40h] [rbp-298h]
  DWORD lpdwDispositionh; // [rsp+40h] [rbp-298h]
  DWORD lpdwDispositioni; // [rsp+40h] [rbp-298h]
  DWORD lpdwDispositionj; // [rsp+40h] [rbp-298h]
  DWORD lpdwDispositionk; // [rsp+40h] [rbp-298h]
  DWORD lpdwDispositionl; // [rsp+40h] [rbp-298h]
  DWORD lpdwDispositionm; // [rsp+40h] [rbp-298h]
  DWORD lpdwDispositionn; // [rsp+40h] [rbp-298h]
  DWORD lpdwDispositiono; // [rsp+40h] [rbp-298h]
  DWORD lpdwDispositionp; // [rsp+40h] [rbp-298h]
  DWORD v530; // [rsp+60h] [rbp-278h]
  unsigned int v531; // [rsp+60h] [rbp-278h]
  unsigned int v532; // [rsp+60h] [rbp-278h]
  unsigned int v533; // [rsp+60h] [rbp-278h]
  int v534; // [rsp+60h] [rbp-278h]
  int v535; // [rsp+60h] [rbp-278h]
  unsigned int v536; // [rsp+60h] [rbp-278h]
  int v537; // [rsp+60h] [rbp-278h]
  unsigned int v538; // [rsp+60h] [rbp-278h]
  unsigned int v539; // [rsp+60h] [rbp-278h]
  int v540; // [rsp+60h] [rbp-278h]
  LSTATUS v541; // [rsp+60h] [rbp-278h]
  LSTATUS v542; // [rsp+60h] [rbp-278h]
  unsigned int v543; // [rsp+60h] [rbp-278h]
  int v544; // [rsp+60h] [rbp-278h]
  unsigned int v545; // [rsp+60h] [rbp-278h]
  unsigned int v546; // [rsp+60h] [rbp-278h]
  int v547; // [rsp+60h] [rbp-278h]
  int v548; // [rsp+60h] [rbp-278h]
  int v550; // [rsp+64h] [rbp-274h]
  HKEY v552; // [rsp+68h] [rbp-270h]
  char *v553; // [rsp+70h] [rbp-268h]
  unsigned __int16 *v554; // [rsp+78h] [rbp-260h] BYREF
  __int64 v555; // [rsp+80h] [rbp-258h] BYREF
  int v556; // [rsp+88h] [rbp-250h] BYREF
  int v557; // [rsp+8Ch] [rbp-24Ch] BYREF
  int v558; // [rsp+90h] [rbp-248h] BYREF
  int v559; // [rsp+94h] [rbp-244h] BYREF
  _BYTE v560[24]; // [rsp+98h] [rbp-240h] BYREF
  void **v561; // [rsp+B0h] [rbp-228h] BYREF
  CPITRSnapshotEnumerator *v562; // [rsp+B8h] [rbp-220h]
  void *v563; // [rsp+C0h] [rbp-218h]
  struct PITR::IPITRSnapshot *v564; // [rsp+C8h] [rbp-210h] BYREF
  void (__fastcall ***v565)(_QWORD, __int64); // [rsp+D0h] [rbp-208h] BYREF
  HKEY v566; // [rsp+D8h] [rbp-200h] BYREF
  HKEY hKey; // [rsp+E0h] [rbp-1F8h] BYREF
  HKEY v568; // [rsp+E8h] [rbp-1F0h] BYREF
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+F0h] [rbp-1E8h] BYREF
  struct _VSS_SNAPSHOT_PROP v570; // [rsp+100h] [rbp-1D8h] BYREF
  _QWORD v571[3]; // [rsp+180h] [rbp-158h] BYREF
  HKEY v572[2]; // [rsp+198h] [rbp-140h] BYREF
  unsigned __int16 v573[4]; // [rsp+1A8h] [rbp-130h] BYREF
  CPITRSnapshotEnumerator *v574; // [rsp+1B0h] [rbp-128h]
  unsigned int v575; // [rsp+1C0h] [rbp-118h] BYREF
  _BYTE v576[16]; // [rsp+1C8h] [rbp-110h] BYREF
  _BYTE v577[16]; // [rsp+1D8h] [rbp-100h] BYREF
  _BYTE v578[16]; // [rsp+1E8h] [rbp-F0h] BYREF
  _BYTE v579[16]; // [rsp+1F8h] [rbp-E0h] BYREF
  _BYTE v580[16]; // [rsp+208h] [rbp-D0h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+218h] [rbp-C0h] BYREF
  _BYTE v582[16]; // [rsp+228h] [rbp-B0h] BYREF
  _BYTE v583[16]; // [rsp+238h] [rbp-A0h] BYREF
  _BYTE v584[16]; // [rsp+248h] [rbp-90h] BYREF
  _BYTE v585[16]; // [rsp+258h] [rbp-80h] BYREF
  _BYTE v586[16]; // [rsp+268h] [rbp-70h] BYREF
  _BYTE v587[16]; // [rsp+278h] [rbp-60h] BYREF
  unsigned __int16 *v588; // [rsp+288h] [rbp-50h] BYREF
  __int16 v589; // [rsp+290h] [rbp-48h] BYREF
  int v590; // [rsp+292h] [rbp-46h]

  v554 = a2;
  *(_QWORD *)&SystemTime.wYear = a5;
  v563 = a6;
  v566 = (HKEY)a7;
  v556 = 0;
  v557 = 0;
  v558 = 0;
  v561 = &UnBCL::SmartPtr<CPITRSnapshotEnumerator>::`vftable';
  v562 = 0;
  v564 = 0;
  memset_0(&v570, 0, sizeof(v570));
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v585);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v587);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v580);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v586);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v578);
  v575 = 0;
  v572[0] = 0;
  v555 = 0;
  TotalNumberOfFreeBytes.QuadPart = 0;
  v589 = 63;
  v590 = 58;
  v588 = (unsigned __int16 *)&v589;
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v576);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v579);
  v568 = 0;
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v577);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v584);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v583);
  hKey = 0;
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v582);
  v559 = 0;
  if ( !a2 )
  {
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v582);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v583);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v584);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v577);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v579);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v576);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v578);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v586);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v580);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v587);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v585);
    v561 = &UnBCL::SmartPtr<CPITRSnapshotEnumerator>::`vftable';
    UnBCL::SmartPtr<CPITRSnapshotEnumerator>::DeAssign(&v561);
    return 2147942487LL;
  }
  v553 = (char *)(this + 3);
  if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(this + 3) )
  {
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v582);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v583);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v584);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v577);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v579);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v576);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v578);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v586);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v580);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v587);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v585);
    v561 = &UnBCL::SmartPtr<CPITRSnapshotEnumerator>::`vftable';
    UnBCL::SmartPtr<CPITRSnapshotEnumerator>::DeAssign(&v561);
    return 2147942450LL;
  }
  LastError = GetLastError();
  v11 = CurrentIP();
  v12 = ConstructPartialMsgW(0x4000000, "Restoring from snapshot : %s", (const char *)a2);
  WdsSetupLogMessageW(
    v12,
    0,
    L"D",
    0,
    4550,
    L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
    L"CPITRBase::RestoreFromSnapshot",
    v11,
    LastError,
    0,
    0);
  v13 = GetLastError();
  v14 = CurrentIP();
  v15 = L"On";
  v16 = L"On";
  if ( !a3 )
    v16 = L"Off";
  v17 = ConstructPartialMsgW(0x4000000, "Thorough mode is: %s", (const char *)v16);
  WdsSetupLogMessageW(
    v17,
    0,
    L"D",
    0,
    4551,
    L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
    L"CPITRBase::RestoreFromSnapshot",
    v14,
    v13,
    0,
    0);
  v18 = GetLastError();
  v19 = CurrentIP();
  if ( !a4 )
    v15 = L"Off";
  v20 = ConstructPartialMsgW(0x4000000, "Verbose  mode is: %s", (const char *)v15);
  WdsSetupLogMessageW(
    v20,
    0,
    L"D",
    0,
    4552,
    L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
    L"CPITRBase::RestoreFromSnapshot",
    v19,
    v18,
    0,
    0);
  if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PITR_FastCompare>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PITR_FastCompare>::GetImpl'::`2'::impl) )
  {
    if ( a3 )
      goto LABEL_19;
    v21 = GetLastError();
    v22 = CurrentIP();
    v23 = ConstructPartialMsgW(0x4000000, "Thorough mode will be forced ON");
    lpdwDisposition = v21;
    phkResult = (PHKEY)v22;
    dwOptions = 4579;
    goto LABEL_18;
  }
  v24 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v571, L"PITR_CONFIG_ENV_THOROUGH");
  IsEnvironmentVarSetTrue = UnBCL::Environment::IsEnvironmentVarSetTrue(v24, 0);
  UnBCL::String::~String((UnBCL::String *)v571);
  if ( IsEnvironmentVarSetTrue )
  {
    v26 = GetLastError();
    v27 = CurrentIP();
    v23 = ConstructPartialMsgW(0x4000000, "Thorough mode forced ON by environment variable");
    lpdwDisposition = v26;
    phkResult = (PHKEY)v27;
    dwOptions = 4557;
LABEL_18:
    WdsSetupLogMessageW(
      v23,
      0,
      L"D",
      0,
      dwOptions,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"CPITRBase::RestoreFromSnapshot",
      phkResult,
      lpdwDisposition,
      0,
      0);
    a3 = 1;
    goto LABEL_19;
  }
  v28 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v571, L"PITR_CONFIG_ENV_THOROUGH");
  v29 = UnBCL::Environment::IsEnvironmentVarSetTrue(v28, 1);
  UnBCL::String::~String((UnBCL::String *)v571);
  if ( !v29 )
  {
    v30 = GetLastError();
    v31 = CurrentIP();
    v32 = ConstructPartialMsgW(0x4000000, "Thorough mode forced OFF by environment variable");
    WdsSetupLogMessageW(
      v32,
      0,
      L"D",
      0,
      4563,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"CPITRBase::RestoreFromSnapshot",
      v31,
      v30,
      0,
      0);
    a3 = 0;
    goto LABEL_19;
  }
  if ( !a3 )
  {
    v33 = GetLastError();
    v34 = CurrentIP();
    v23 = ConstructPartialMsgW(0x4000000, "Thorough mode will be forced ON for preview");
    lpdwDisposition = v33;
    phkResult = (PHKEY)v34;
    dwOptions = 4570;
    goto LABEL_18;
  }
LABEL_19:
  SnapshotData = pInitializeCOM(&v559);
  if ( SnapshotData >= 0 )
  {
    pEnablePrivilege(L"SeBackupPrivilege", 1, &v556);
    pEnablePrivilege(L"SeRestorePrivilege", 1, &v557);
    pEnablePrivilege(L"SeSecurityPrivilege", 1, &v558);
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
    {
      v41 = (CPITRSnapshotEnumerator *)UnBCL::Object::operator new(0x30u);
      *(_QWORD *)v573 = v41;
      if ( v41 )
        v42 = CPITRSnapshotEnumerator::CPITRSnapshotEnumerator(v41, (struct CPITRBase *)this);
      else
        v42 = 0;
      *(_QWORD *)v573 = &UnBCL::SmartPtr<CPITRSnapshotEnumerator>::`vftable';
      v574 = 0;
      if ( v42 )
      {
        v43 = (__int64)v42 + 8;
        UnBCL::Object::AddRef((CPITRSnapshotEnumerator *)((char *)v42 + 8));
      }
      else
      {
        v43 = 8;
      }
      UnBCL::SmartPtr<CPITRSnapshotEnumerator>::DeAssign(v573);
      v574 = v42;
      if ( v42 )
        UnBCL::Object::AddRef((UnBCL::Object *)v43);
      UnBCL::SmartPtr<CPITRSnapshotEnumerator>::DeAssign(&v561);
      v562 = v42;
      *(_QWORD *)v573 = &UnBCL::SmartPtr<CPITRSnapshotEnumerator>::`vftable';
      UnBCL::SmartPtr<CPITRSnapshotEnumerator>::DeAssign(v573);
      SnapshotData = CPITRSnapshotEnumerator::GetSnapshotData(v42, v554, &v564);
      if ( SnapshotData < 0 )
      {
        v44 = GetLastError();
        v45 = CurrentIP();
        v46 = ConstructPartialMsgW(
                0x4000000,
                "Error retrieving snapshot data for %s. Error: 0x%08X",
                (const char *)v554,
                SnapshotData);
        WdsSetupLogMessageW(
          v46,
          0,
          L"D",
          0,
          4603,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRBase::RestoreFromSnapshot",
          v45,
          v44,
          0,
          0);
        goto LABEL_21;
      }
      v47 = v564;
      if ( !(*(unsigned int (__fastcall **)(struct PITR::IPITRSnapshot *))(*(_QWORD *)v564 + 8LL))(v564) )
      {
        SnapshotData = -2147023728;
        v48 = GetLastError();
        v49 = CurrentIP();
        v50 = ConstructPartialMsgW(
                0x4000000,
                "Snapshot %s is not present on the system. Error: 0x%08X",
                (const char *)v554,
                -2147023728);
        WdsSetupLogMessageW(
          v50,
          0,
          L"D",
          0,
          4609,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRBase::RestoreFromSnapshot",
          v49,
          v48,
          0,
          0);
        goto LABEL_21;
      }
      if ( (*(__int64 (__fastcall **)(struct PITR::IPITRSnapshot *))(*(_QWORD *)v47 + 40LL))(v47) )
        v51 = *(const unsigned __int16 **)((*(__int64 (__fastcall **)(struct PITR::IPITRSnapshot *))(*(_QWORD *)v47 + 40LL))(v47)
                                         + 24);
      else
        v51 = 0;
      if ( UnBCL::String::Compare(this[13], v51, 1) )
      {
        SnapshotData = -2147024846;
        v530 = GetLastError();
        v566 = (HKEY)CurrentIP();
        v52 = (const char *)L"unknown";
        v53 = L"unknown";
        if ( this[13] )
          v53 = (wchar_t *)this[13];
        v563 = v53;
        if ( (*(__int64 (__fastcall **)(struct PITR::IPITRSnapshot *))(*(_QWORD *)v47 + 40LL))(v47)
          && *(_QWORD *)((*(__int64 (__fastcall **)(struct PITR::IPITRSnapshot *))(*(_QWORD *)v47 + 40LL))(v47) + 24) )
        {
          v52 = *(const char **)((*(__int64 (__fastcall **)(struct PITR::IPITRSnapshot *))(*(_QWORD *)v47 + 40LL))(v47)
                               + 24);
        }
        v54 = ConstructPartialMsgW(
                0x4000000,
                "SKU mismatch, snapshot %s is %s, existing OS is %s",
                (const char *)v554,
                v52,
                (const char *)v563);
        WdsSetupLogMessageW(
          v54,
          0,
          L"D",
          0,
          4621,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRBase::RestoreFromSnapshot",
          v566,
          v530,
          0,
          0);
        goto LABEL_21;
      }
    }
    v55 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v571, v554);
    SnapshotData = VssGetSnapshotProp(v55, &v570);
    UnBCL::String::~String((UnBCL::String *)v571);
    if ( SnapshotData < 0 )
    {
      v56 = GetLastError();
      v57 = CurrentIP();
      v58 = ConstructPartialMsgW(
              0x4000000,
              "Error retrieving snapshot properties for %s. Error: 0x%08X",
              (const char *)v554,
              SnapshotData);
      WdsSetupLogMessageW(
        v58,
        0,
        L"D",
        0,
        4629,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"CPITRBase::RestoreFromSnapshot",
        v57,
        v56,
        0,
        0);
      goto LABEL_21;
    }
    if ( (v570.m_lSnapshotAttributes & 4) != 0 )
    {
      v59 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
      v60 = v59;
      *(_QWORD *)v573 = v59;
      if ( v59 )
      {
        UnBCL::String::String(v59, v570.m_pwszSnapshotDeviceObject);
        *(_QWORD *)v60 = &UnBCL::String::`local vftable';
      }
      else
      {
        v60 = 0;
      }
    }
    else
    {
      if ( !v570.m_pwszExposedPath )
      {
        v61 = GetLastError();
        v62 = CurrentIP();
        v63 = ConstructPartialMsgW(0x2000000, "Non-client accessible snapshots need to be exposed");
        WdsSetupLogMessageW(
          v63,
          0,
          L"D",
          0,
          4644,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRBase::RestoreFromSnapshot",
          v62,
          v61,
          0,
          0);
        SnapshotData = -2147212543;
        goto LABEL_21;
      }
      v64 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
      v60 = v64;
      *(_QWORD *)v573 = v64;
      if ( v64 )
      {
        UnBCL::String::String(v64, v570.m_pwszExposedPath);
        *(_QWORD *)v60 = &UnBCL::String::`local vftable';
      }
      else
      {
        v60 = 0;
      }
    }
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v571, v60);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v585, v571);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v571);
    P = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v585);
    DevicePathNt = GetDevicePathNt(P);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v571, DevicePathNt);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v587, v571);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v571);
    v67 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
    v68 = v67;
    *(_QWORD *)v573 = v67;
    if ( v67 )
    {
      UnBCL::String::String(v67, v570.m_pwszOriginalVolumeName);
      *(_QWORD *)v68 = &UnBCL::String::`local vftable';
    }
    else
    {
      v68 = 0;
    }
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v571, v68);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v580, v571);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v571);
    v69 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v580);
    v70 = GetDevicePathNt(v69);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v571, v70);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v586, v571);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v571);
    v71 = GetLastError();
    v72 = CurrentIP();
    v73 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v580);
    CString = (const char *)UnBCL::String::get_CString(v73);
    v75 = ConstructPartialMsgW(0x4000000, "Real path      : %s", CString);
    WdsSetupLogMessageW(
      v75,
      0,
      L"D",
      0,
      4653,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"CPITRBase::RestoreFromSnapshot",
      v72,
      v71,
      0,
      0);
    v76 = GetLastError();
    v77 = CurrentIP();
    v78 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v586);
    v79 = (const char *)UnBCL::String::get_CString(v78);
    v80 = ConstructPartialMsgW(0x4000000, "Real path (NT) : %s", v79);
    WdsSetupLogMessageW(
      v80,
      0,
      L"D",
      0,
      4654,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"CPITRBase::RestoreFromSnapshot",
      v77,
      v76,
      0,
      0);
    v81 = GetLastError();
    v82 = CurrentIP();
    v83 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v585);
    v84 = (const char *)UnBCL::String::get_CString(v83);
    v85 = ConstructPartialMsgW(0x4000000, "Snap path      : %s", v84);
    WdsSetupLogMessageW(
      v85,
      0,
      L"D",
      0,
      4655,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"CPITRBase::RestoreFromSnapshot",
      v82,
      v81,
      0,
      0);
    v86 = GetLastError();
    v87 = CurrentIP();
    v88 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v587);
    v89 = (const char *)UnBCL::String::get_CString(v88);
    v90 = ConstructPartialMsgW(0x4000000, "Snap path (NT) : %s", v89);
    WdsSetupLogMessageW(
      v90,
      0,
      L"D",
      0,
      4656,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"CPITRBase::RestoreFromSnapshot",
      v87,
      v86,
      0,
      0);
    v91 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v553);
    VolumeNameFromPath = GetVolumeNameFromPath(v91, v92, v93);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v571, VolumeNameFromPath);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v578, v571);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v571);
    v95 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v578);
    if ( !UnBCL::String::EndsWith(v95, 0x5Cu) )
    {
      v96 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v578);
      v97 = UnBCL::String::get_CString(v96);
      v98 = UnBCL::String::Concat(v97, L"\\");
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v571, v98);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v578, v571);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v571);
    }
    v99 = GetLastError();
    v100 = CurrentIP();
    v101 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v578);
    v102 = (const char *)UnBCL::String::get_CString(v101);
    v103 = ConstructPartialMsgW(0x4000000, "OS volume      : %s", v102);
    WdsSetupLogMessageW(
      v103,
      0,
      L"D",
      0,
      4664,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"CPITRBase::RestoreFromSnapshot",
      v100,
      v99,
      0,
      0);
    v104 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v578);
    v105 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v580);
    if ( UnBCL::String::Compare(v105, v104, 1) )
    {
      v106 = GetLastError();
      v107 = CurrentIP();
      v108 = ConstructPartialMsgW(0x2000000, "Snapshot is not on the OS volume");
      WdsSetupLogMessageW(
        v108,
        0,
        L"D",
        0,
        4667,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"CPITRBase::RestoreFromSnapshot",
        v107,
        v106,
        0,
        0);
      SnapshotData = -2147024879;
      goto LABEL_21;
    }
    v109 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v553);
    SnapshotData = VssGetSnapshotsSizeInfo(v109, (__int64 *)v572, 0, &v555);
    if ( SnapshotData < 0 )
    {
      v110 = GetLastError();
      v111 = CurrentIP();
      v112 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v578);
      v113 = (const char *)UnBCL::String::get_CString(v112);
      v114 = ConstructPartialMsgW(
               0x2000000,
               "Failed to get VSS disk space usage for volume %s. Error: 0x%08X",
               v113,
               SnapshotData);
      WdsSetupLogMessageW(
        v114,
        0,
        L"D",
        0,
        4679,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"CPITRBase::RestoreFromSnapshot",
        v111,
        v110,
        0,
        0);
      goto LABEL_21;
    }
    v115 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v553);
    v116 = UnBCL::String::get_CString(v115);
    if ( !GetDiskFreeSpaceExW(v116, 0, 0, &TotalNumberOfFreeBytes) )
    {
      v117 = GetLastError();
      v118 = v117 < 0;
      if ( v117 > 0 )
        v118 = 1;
      if ( v118 )
      {
        v119 = GetLastError();
        SnapshotData = v119;
        if ( v119 > 0 )
          SnapshotData = (unsigned __int16)v119 | 0x80070000;
        v550 = -2147467259;
      }
      else
      {
        v550 = -2147467259;
        SnapshotData = -2147467259;
      }
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
      {
        v120 = GetLastError();
        v121 = CurrentIP();
        v122 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v578);
        v123 = (const char *)UnBCL::String::get_CString(v122);
        v124 = ConstructPartialMsgW(
                 0x2000000,
                 "Failed to get free disk space for volume %s. Error: 0x%08X",
                 v123,
                 SnapshotData);
        lpdwDispositiona = v120;
        phkResulta = (PHKEY)v121;
        dwOptionsa = 4688;
      }
      else
      {
        v125 = GetLastError();
        v126 = CurrentIP();
        v127 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v578);
        v128 = (const char *)UnBCL::String::get_CString(v127);
        v124 = ConstructPartialMsgW(
                 0x2000000,
                 "Failed to get free disk apce for volume %s. Error: 0x%08X",
                 v128,
                 SnapshotData);
        lpdwDispositiona = v125;
        phkResulta = (PHKEY)v126;
        dwOptionsa = 4692;
      }
LABEL_76:
      WdsSetupLogMessageW(
        v124,
        0,
        L"D",
        0,
        dwOptionsa,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"CPITRBase::RestoreFromSnapshot",
        phkResulta,
        lpdwDispositiona,
        0,
        0);
      goto LABEL_22;
    }
    v129 = GetLastError();
    v130 = CurrentIP();
    v131 = ConstructPartialMsgW(0x4000000, "Free disk space: %I64u", TotalNumberOfFreeBytes.QuadPart);
    WdsSetupLogMessageW(
      v131,
      0,
      L"D",
      0,
      4696,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"CPITRBase::RestoreFromSnapshot",
      v130,
      v129,
      0,
      0);
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
    {
      v132 = GetLastError();
      v133 = CurrentIP();
      v134 = ConstructPartialMsgW(0x4000000, "VSS used space : %I64d", v572[0]);
      lpdwDispositionb = v132;
      phkResultb = (PHKEY)v133;
      dwOptionsb = 4699;
    }
    else
    {
      v135 = GetLastError();
      v136 = CurrentIP();
      v134 = ConstructPartialMsgW(0x4000000, "VSS used space : %I64u", v572[0]);
      lpdwDispositionb = v135;
      phkResultb = (PHKEY)v136;
      dwOptionsb = 4703;
    }
    WdsSetupLogMessageW(
      v134,
      0,
      L"D",
      0,
      dwOptionsb,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"CPITRBase::RestoreFromSnapshot",
      phkResultb,
      lpdwDispositionb,
      0,
      0);
    v572[0] = (HKEY)((__int64)v572[0] * 2);
    if ( (__int64)TotalNumberOfFreeBytes.QuadPart < (__int64)v572[0] )
    {
      SnapshotData = -2147024784;
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
      {
        v137 = GetLastError();
        v138 = CurrentIP();
        v139 = ConstructPartialMsgW(
                 0x2000000,
                 "Not enough disk space to restore the snapshot. Required: %I64d, available: %I64u",
                 v572[0],
                 TotalNumberOfFreeBytes.QuadPart);
        WdsSetupLogMessageW(
          v139,
          0,
          L"D",
          0,
          4710,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRBase::RestoreFromSnapshot",
          v138,
          v137,
          0,
          0);
      }
      else
      {
        v140 = GetLastError();
        v141 = CurrentIP();
        v142 = ConstructPartialMsgW(
                 0x2000000,
                 "Not enough disk space to restore the snapshot. Required: %I64u, available: %I64u",
                 v572[0],
                 TotalNumberOfFreeBytes.QuadPart);
        WdsSetupLogMessageW(
          v142,
          0,
          L"D",
          0,
          4714,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRBase::RestoreFromSnapshot",
          v141,
          v140,
          0,
          0);
      }
      goto LABEL_21;
    }
    v143 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v553);
    SnapshotData = VssSetSnapshotsMaxSize(v143, -1);
    if ( SnapshotData < 0 )
    {
      v144 = GetLastError();
      v145 = CurrentIP();
      v146 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v578);
      v147 = (const char *)UnBCL::String::get_CString(v146);
      v148 = ConstructPartialMsgW(
               0x2000000,
               "Failed to set maximum VSS limit for volume %s. Error: 0x%08X",
               v147,
               SnapshotData);
      WdsSetupLogMessageW(
        v148,
        0,
        L"D",
        0,
        4728,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"CPITRBase::RestoreFromSnapshot",
        v145,
        v144,
        0,
        0);
      goto LABEL_21;
    }
    v149 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v573, L"$WINDOWS.~BK");
    v150 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v580);
    v151 = UnBCL::Path::Combine(v150, v149);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v571, v151);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v576, v571);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v571);
    UnBCL::String::~String((UnBCL::String *)v573);
    v152 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v576);
    if ( !UnBCL::Directory::Exists(v152) )
    {
      v153 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v576);
      v154 = UnBCL::String::get_CString(v153);
      if ( !CreateDirectoryW(v154, 0) )
      {
        v155 = GetLastError();
        v156 = v155 < 0;
        if ( v155 > 0 )
          v156 = 1;
        if ( v156 )
        {
          v157 = GetLastError();
          SnapshotData = v157;
          if ( v157 > 0 )
            SnapshotData = (unsigned __int16)v157 | 0x80070000;
          v550 = -2147467259;
        }
        else
        {
          v550 = -2147467259;
          SnapshotData = -2147467259;
        }
        v158 = GetLastError();
        v159 = CurrentIP();
        v124 = ConstructPartialMsgW(0x2000000, "Error creating the store directory: 0x%08X", SnapshotData);
        lpdwDispositiona = v158;
        phkResulta = (PHKEY)v159;
        dwOptionsa = 4740;
        goto LABEL_76;
      }
    }
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl)
      && !*((_DWORD *)this + 20) )
    {
      v160 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v571, L"System32\\config");
      v161 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v553);
      v162 = UnBCL::Path::Combine(v161, v160);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v572, v162);
      UnBCL::String::~String((UnBCL::String *)v571);
      v163 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v560, L"SOFTWARE");
      v164 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v576);
      v165 = UnBCL::Path::Combine(v164, v163);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v573, v165);
      UnBCL::String::~String((UnBCL::String *)v560);
      v166 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v573);
      v167 = (const char *)UnBCL::String::get_CString(v166);
      v168 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v572);
      v169 = (const char *)UnBCL::String::get_CString(v168);
      SnapshotData = pCopyHiveFiles(v169, v167, v170);
      if ( SnapshotData < 0 )
      {
        v171 = GetLastError();
        v172 = CurrentIP();
        v173 = ConstructPartialMsgW(0x2000000, "Failed to backup SOFTWARE hive files. Error: 0x%08X", SnapshotData);
        WdsSetupLogMessageW(
          v173,
          0,
          L"D",
          0,
          4757,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRBase::RestoreFromSnapshot",
          v172,
          v171,
          0,
          0);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v573);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v572);
        goto LABEL_21;
      }
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v573);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v572);
    }
    v174 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v553);
    v175 = UnBCL::String::get_CString(v174);
    v176 = RecMountOfflineHive(v175, L"SOFTWARE", L"$OFFLINE_RW$SOFTWARE");
    v552 = v176;
    if ( !v176 )
    {
      v177 = GetLastError();
      SnapshotData = v177;
      if ( v177 > 0 )
        SnapshotData = (unsigned __int16)v177 | 0x80070000;
      v178 = GetLastError();
      v179 = CurrentIP();
      v180 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v553);
      v181 = (const char *)UnBCL::String::get_CString(v180);
      v182 = ConstructPartialMsgW(
               0x2000000,
               "Failed to load offline SOFTWARE hive from %s. Error: 0x%08X",
               v181,
               SnapshotData);
      lpdwDispositionc = v178;
      phkResultc = (PHKEY)v179;
      dwOptionsc = 4770;
LABEL_106:
      WdsSetupLogMessageW(
        v182,
        0,
        L"D",
        0,
        dwOptionsc,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"CPITRBase::RestoreFromSnapshot",
        phkResultc,
        lpdwDispositionc,
        0,
        0);
      v550 = -2147467259;
LABEL_107:
      v40 = 0;
LABEL_277:
      v39 = v552;
      goto LABEL_278;
    }
    if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
    {
      v239 = pOpenRegKeyMaxAccess(v176, L"Microsoft\\Windows\\CurrentVersion\\Setup\\Recovery\\PITR\\Snapshots", &v568);
      SnapshotData = v239;
      if ( v239 )
      {
        if ( v239 > 0 )
          SnapshotData = (unsigned __int16)v239 | 0x80070000;
        v240 = GetLastError();
        v241 = CurrentIP();
        v182 = ConstructPartialMsgW(
                 0x2000000,
                 "Failed to open PITR snapshots key %s. Error: 0x%08X",
                 (const char *)L"Microsoft\\Windows\\CurrentVersion\\Setup\\Recovery\\PITR\\Snapshots",
                 SnapshotData);
        lpdwDispositionc = v240;
        phkResultc = (PHKEY)v241;
        dwOptionsc = 4889;
        goto LABEL_106;
      }
      v242 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v560, L"Snapshots.hiv");
      v243 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v576);
      v244 = UnBCL::Path::Combine(v243, v242);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v571, v244);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v577, v571);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v571);
      UnBCL::String::~String((UnBCL::String *)v560);
      v245 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v577);
      if ( UnBCL::File::Exists(v245) )
      {
        v246 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v577);
        v247 = UnBCL::String::get_CString(v246);
        if ( !DeleteFileEx2((__int64)v247, 0) )
        {
          v248 = GetLastError();
          v249 = v248 < 0;
          if ( v248 > 0 )
            v249 = 1;
          if ( v249 )
          {
            v250 = GetLastError();
            SnapshotData = v250;
            if ( v250 > 0 )
              SnapshotData = (unsigned __int16)v250 | 0x80070000;
            v550 = -2147467259;
          }
          else
          {
            v550 = -2147467259;
            SnapshotData = -2147467259;
          }
          v251 = GetLastError();
          v252 = CurrentIP();
          v253 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v577);
          v254 = (const char *)UnBCL::String::get_CString(v253);
          v255 = ConstructPartialMsgW(
                   0x2000000,
                   "Failed to clear PITR snapshots key export file %s. Error: 0x%08X",
                   v254,
                   SnapshotData);
          WdsSetupLogMessageW(
            v255,
            0,
            L"D",
            0,
            4899,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
            L"CPITRBase::RestoreFromSnapshot",
            v252,
            v251,
            0,
            0);
          goto LABEL_107;
        }
      }
      v256 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v577);
      v257 = UnBCL::String::get_CString(v256);
      v258 = RegSaveKeyW(v568, v257, 0);
      SnapshotData = v258;
      if ( v258 )
      {
        if ( v258 > 0 )
          SnapshotData = (unsigned __int16)v258 | 0x80070000;
        v259 = GetLastError();
        v260 = CurrentIP();
        v182 = ConstructPartialMsgW(0x2000000, "Failed to export PITR snapshots key. Error: 0x%08X", SnapshotData);
        lpdwDispositionc = v259;
        phkResultc = (PHKEY)v260;
        dwOptionsc = 4907;
        goto LABEL_106;
      }
      v261 = GetLastError();
      v262 = CurrentIP();
      v263 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v577);
      v264 = (const char *)UnBCL::String::get_CString(v263);
      v265 = ConstructPartialMsgW(0x4000000, "Successfully exported snapshots key to %s", v264);
      WdsSetupLogMessageW(
        v265,
        0,
        L"D",
        0,
        4910,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"CPITRBase::RestoreFromSnapshot",
        v262,
        v261,
        0,
        0);
      RegCloseKey(v568);
      v568 = 0;
LABEL_153:
      RegCloseKey(v552);
      RecUnloadKey(v266, L"$OFFLINE_RW$SOFTWARE");
      v572[0] = 0;
      v552 = 0;
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PITR_FastCompare>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PITR_FastCompare>::GetImpl'::`2'::impl) )
      {
        v267 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v580);
        v268 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v585);
        phkResulth = &v575;
        m_tsCreationTimestamp = v570.m_tsCreationTimestamp;
      }
      else
      {
        v267 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v580);
        v268 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v585);
        phkResulth = 0;
        m_tsCreationTimestamp = 0;
      }
      SnapshotData = PrepareRestoreJournal(
                       v268,
                       v267,
                       m_tsCreationTimestamp,
                       a3,
                       a4,
                       v563,
                       (struct PITR::IPITRRestoreProgress *)v566,
                       phkResulth);
      if ( SnapshotData < 0 )
      {
        v270 = GetLastError();
        v271 = CurrentIP();
        v272 = ConstructPartialMsgW(0x2000000, "Failed to prepare restore journal. Error: 0x%08X", SnapshotData);
        lpdwDispositionh = v270;
        phkResulti = (PHKEY)v271;
        dwOptionsh = 4931;
LABEL_158:
        WdsSetupLogMessageW(
          v272,
          0,
          L"D",
          0,
          dwOptionsh,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRBase::RestoreFromSnapshot",
          phkResulti,
          lpdwDispositionh,
          0,
          0);
        v40 = 0;
        v550 = -2147467259;
        goto LABEL_277;
      }
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
      {
        v273 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v560, L"$RESTOREACTIVE.MKR");
        v274 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v576);
        v275 = UnBCL::Path::Combine(v274, v273);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v571, v275);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v579, v571);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v571);
        UnBCL::String::~String((UnBCL::String *)v560);
        v276 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v579);
        if ( !UnBCL::File::Exists(v276) )
        {
          try
          {
            v277 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v579);
            v278 = UnBCL::File::Create(v277);
            UnBCL::SmartPtr<UnBCL::FileStream>::SmartPtr<UnBCL::FileStream>(v571, v278);
            v571[0] = &UnBCL::SmartPtr<UnBCL::FileStream>::`vftable';
            UnBCL::SmartPtr<UnBCL::IEnumerator<unsigned long>>::DeAssign((__int64)v571);
          }
          catch ( UnBCL::Exception *v565 )
          {
            v466 = v565;
            v467 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, __int64)))(*v565)[4])(v565);
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v571, v467);
            v468 = GetLastError();
            v469 = CurrentIP();
            v470 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v571);
            v471 = (const char *)UnBCL::String::get_CString(v470);
            v472 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v579);
            v473 = (const char *)UnBCL::String::get_CString(v472);
            v474 = ConstructPartialMsgW(0x2000000, "Exception creating restore-active marker %s: %s", v473, v471);
            WdsSetupLogMessageW(
              v474,
              0,
              L"D",
              0,
              4948,
              L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
              L"CPITRBase::RestoreFromSnapshot",
              v469,
              v468,
              0,
              0);
            (**v466)(v466, 1);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v571);
            v40 = 0;
            v550 = -2147467259;
            v39 = v572[0];
            SnapshotData = -2147467259;
            goto LABEL_278;
          }
        }
      }
      v279 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v553);
      v589 = *UnBCL::String::get_CString(v279);
      if ( a4 )
      {
        v280 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v571, L"1");
        v281 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v560, L"WINSETUPBAK_VERBOSE");
        UnBCL::Environment::SetEnvironmentVar(v281, v280);
        UnBCL::String::~String((UnBCL::String *)v560);
        UnBCL::String::~String((UnBCL::String *)v571);
      }
      SnapshotData = WsbkInstall(0, 0, 0, 0, 1, 1, (const unsigned __int16 **const)&v588);
      if ( a4 )
      {
        v282 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v560, L"WINSETUPBAK_VERBOSE");
        UnBCL::Environment::SetEnvironmentVar(v282, 0);
        UnBCL::String::~String((UnBCL::String *)v560);
      }
      v283 = GetLastError();
      v284 = CurrentIP();
      if ( SnapshotData < 0 )
      {
        v272 = ConstructPartialMsgW(
                 0x2000000,
                 "Failed to start WinSetupBak in restore mode. Error: 0x%08X\n",
                 SnapshotData);
        lpdwDispositionh = v283;
        phkResulti = (PHKEY)v284;
        dwOptionsh = 4972;
        goto LABEL_158;
      }
      v285 = ConstructPartialMsgW(0x4000000, "Sending a message to the driver to process the journal...");
      WdsSetupLogMessageW(
        v285,
        0,
        L"D",
        0,
        4978,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"CPITRBase::RestoreFromSnapshot",
        v284,
        v283,
        0,
        0);
      v286 = v566;
      if ( v566 )
      {
        (**(void (__fastcall ***)(HKEY, __int64, __int64))v566)(v566, 3, 10000);
        (*(void (__fastcall **)(HKEY, _QWORD))(*(_QWORD *)v286 + 8LL))(v286, 0);
      }
      v287 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v587);
      v288 = UnBCL::String::get_CString(v287);
      v289 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v586);
      v290 = UnBCL::String::get_CString(v289);
      SnapshotData = WsbkExecuteRevertJournal(
                       v290,
                       v288,
                       *(const unsigned __int16 **)&SystemTime.wYear,
                       ProgressCallback,
                       v286);
      if ( SnapshotData < 0 )
      {
        v291 = GetLastError();
        v292 = CurrentIP();
        v293 = ConstructPartialMsgW(0x2000000, "Failed to process restore journal. Error: 0x%08X\n", SnapshotData);
        lpdwDispositioni = v291;
        phkResultj = (PHKEY)v292;
        dwOptionsi = 4989;
LABEL_171:
        WdsSetupLogMessageW(
          v293,
          0,
          L"D",
          0,
          dwOptionsi,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRBase::RestoreFromSnapshot",
          phkResultj,
          lpdwDispositioni,
          0,
          0);
        v39 = v552;
LABEL_272:
        v40 = 0;
        v572[0] = 0;
        goto LABEL_273;
      }
      if ( v286 )
      {
        (*(void (__fastcall **)(HKEY, __int64))(*(_QWORD *)v286 + 8LL))(v286, 10000);
        (**(void (__fastcall ***)(HKEY, __int64, _QWORD))v286)(v286, 4, 0);
      }
      v295 = GetLastError();
      v296 = CurrentIP();
      v297 = ConstructPartialMsgW(0x4000000, "Restoring from snapshot %s completed successfully.", (const char *)v554);
      WdsSetupLogMessageW(
        v297,
        0,
        L"D",
        0,
        5000,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"CPITRBase::RestoreFromSnapshot",
        v296,
        v295,
        0,
        0);
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
      {
        v298 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v553);
        v299 = UnBCL::String::get_CString(v298);
        v552 = RecMountOfflineHive(v299, L"SOFTWARE", L"$OFFLINE_RW$SOFTWARE");
        if ( !v552 )
        {
          v300 = GetLastError();
          v531 = v300;
          if ( v300 > 0 )
            v531 = (unsigned __int16)v300 | 0x80070000;
          v301 = GetLastError();
          v302 = CurrentIP();
          v303 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v553);
          v304 = (const char *)UnBCL::String::get_CString(v303);
          v305 = ConstructPartialMsgW(
                   0x2000000,
                   "Failed to load offline SOFTWARE hive from %s. Error: 0x%08X",
                   v304,
                   v531);
          WdsSetupLogMessageW(
            v305,
            0,
            L"D",
            0,
            5011,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
            L"CPITRBase::RestoreFromSnapshot",
            v302,
            v301,
            0,
            0);
        }
        v306 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v553);
        v307 = UnBCL::String::get_CString(v306);
        v308 = RecMountOfflineHive(v307, L"SYSTEM", L"$OFFLINE_RW$SYSTEM");
        v309 = v308;
        v572[0] = v308;
        if ( v308 )
        {
          Dword = RegGetDword(v308, L"Select", L"Default");
          v317 = UnBCL::String::Format(L"ControlSet%03d", Dword);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v571, v317);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v583, v571);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v571);
          v318 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v583);
          v319 = UnBCL::String::get_CString(v318);
          v320 = pOpenRegKeyMaxAccess(v309, v319, &hKey);
          v533 = v320;
          if ( v320 )
          {
            if ( v320 > 0 )
              v533 = (unsigned __int16)v320 | 0x80070000;
            v321 = GetLastError();
            v322 = CurrentIP();
            v323 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v583);
            v324 = (const char *)UnBCL::String::get_CString(v323);
            v325 = ConstructPartialMsgW(0x2000000, "Failed to open Control key %s. Error: 0x%08X", v324, v533);
            WdsSetupLogMessageW(
              v325,
              0,
              L"D",
              0,
              5034,
              L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
              L"CPITRBase::RestoreFromSnapshot",
              v322,
              v321,
              0,
              0);
          }
        }
        else
        {
          v310 = GetLastError();
          v532 = v310;
          if ( v310 > 0 )
            v532 = (unsigned __int16)v310 | 0x80070000;
          v311 = GetLastError();
          v312 = CurrentIP();
          v313 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v553);
          v314 = (const char *)UnBCL::String::get_CString(v313);
          v315 = ConstructPartialMsgW(
                   0x2000000,
                   "Failed to load offline SYSTEM hive from %s. Error: 0x%08X",
                   v314,
                   v532);
          WdsSetupLogMessageW(
            v315,
            0,
            L"D",
            0,
            5018,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
            L"CPITRBase::RestoreFromSnapshot",
            v312,
            v311,
            0,
            0);
        }
        v326 = v552;
        if ( !v552 )
          goto LABEL_220;
        v327 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v577);
        if ( UnBCL::File::Exists(v327) )
        {
          v328 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v577);
          v329 = UnBCL::String::get_CString(v328);
          v534 = pImportRegKey(v552, L"Microsoft\\Windows\\CurrentVersion\\Setup\\Recovery\\PITR\\Snapshots", v329);
          v330 = GetLastError();
          v331 = CurrentIP();
          if ( v534 >= 0 )
          {
            v333 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v577);
            v334 = (const char *)UnBCL::String::get_CString(v333);
            v332 = ConstructPartialMsgW(0x4000000, "Successfully imported snapshots key from %s", v334);
            lpdwDispositionj = v330;
            phkResultk = (PHKEY)v331;
            dwOptionsk = 5052;
          }
          else
          {
            v332 = ConstructPartialMsgW(0x2000000, "Failed to import PITR snapshots key. Error: 0x%08X", v534);
            lpdwDispositionj = v330;
            phkResultk = (PHKEY)v331;
            dwOptionsk = 5048;
          }
          WdsSetupLogMessageW(
            v332,
            0,
            L"D",
            0,
            dwOptionsk,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
            L"CPITRBase::RestoreFromSnapshot",
            phkResultk,
            lpdwDispositionj,
            0,
            0);
          v326 = v552;
        }
        v335 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v584);
        if ( UnBCL::File::Exists(v335) )
        {
          v336 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v584);
          v337 = UnBCL::String::get_CString(v336);
          v535 = pImportRegKey(v326, L"Microsoft\\Windows\\CurrentVersion\\Reliability\\WinRE", v337);
          v338 = GetLastError();
          v339 = CurrentIP();
          if ( v535 >= 0 )
          {
            v341 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v584);
            v342 = (const char *)UnBCL::String::get_CString(v341);
            v340 = ConstructPartialMsgW(0x4000000, "Successfully imported WinRE trust key from %s", v342);
            lpdwDispositionk = v338;
            phkResultl = (PHKEY)v339;
            dwOptionsl = 5066;
          }
          else
          {
            v340 = ConstructPartialMsgW(0x2000000, "Failed to import WinRE trust key. Error: 0x%08X", v535);
            lpdwDispositionk = v338;
            phkResultl = (PHKEY)v339;
            dwOptionsl = 5062;
          }
          WdsSetupLogMessageW(
            v340,
            0,
            L"D",
            0,
            dwOptionsl,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
            L"CPITRBase::RestoreFromSnapshot",
            phkResultl,
            lpdwDispositionk,
            0,
            0);
          v326 = v552;
        }
        if ( !RegSetDword(v326, L"Microsoft\\Windows\\CurrentVersion\\Setup\\OOBE", L"InstallType", 19) )
        {
          v343 = GetLastError();
          v536 = v343;
          if ( v343 > 0 )
            v536 = (unsigned __int16)v343 | 0x80070000;
          v344 = GetLastError();
          v345 = CurrentIP();
          v346 = ConstructPartialMsgW(0x2000000, "Failed to write InstallType value after restore. Error: 0x%08X", v536);
          WdsSetupLogMessageW(
            v346,
            0,
            L"D",
            0,
            5074,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
            L"CPITRBase::RestoreFromSnapshot",
            v345,
            v344,
            0,
            0);
          v326 = v552;
        }
        if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PITR_FastCompare>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PITR_FastCompare>::GetImpl'::`2'::impl)
          || !v575 )
        {
          goto LABEL_220;
        }
        *(_QWORD *)v573 = 0;
        LODWORD(v574) = 0;
        WORD2(v574) = 0;
        SystemTime = 0;
        GetLocalTime(&SystemTime);
        dwOptionsj[0] = SystemTime.wYear;
        v537 = StringCchPrintfW(v573, 7u, L"%02d%04d", SystemTime.wMonth, *(_QWORD *)dwOptionsj);
        if ( v537 >= 0 )
        {
          v566 = 0;
          v350 = RegCreateKeyExW(
                   v326,
                   L"Microsoft\\Windows\\CurrentVersion\\Setup\\Recovery\\PITR\\CompareMatch",
                   0,
                   0,
                   0,
                   0xF003Fu,
                   0,
                   &v566,
                   0);
          v538 = v350;
          if ( !v350 )
          {
            if ( RegSetDword(v566, 0, v573, 1) )
            {
              v359 = GetLastError();
              v360 = CurrentIP();
              v358 = ConstructPartialMsgW(
                       50331648,
                       "Found mismatch comparisons, have set value %s for log collection",
                       (const char *)v573);
              lpdwDispositionm = v359;
              phkResultn = (PHKEY)v360;
              dwOptionsn = 5116;
            }
            else
            {
              v355 = GetLastError();
              v539 = v355;
              if ( v355 > 0 )
                v539 = (unsigned __int16)v355 | 0x80070000;
              v356 = GetLastError();
              v357 = CurrentIP();
              v358 = ConstructPartialMsgW(
                       0x2000000,
                       "Failed to write comparison mismatch value %s. Error: 0x%08X",
                       (const char *)v573,
                       v539);
              lpdwDispositionm = v356;
              phkResultn = (PHKEY)v357;
              dwOptionsn = 5112;
            }
            WdsSetupLogMessageW(
              v358,
              0,
              L"D",
              0,
              dwOptionsn,
              L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
              L"CPITRBase::RestoreFromSnapshot",
              phkResultn,
              lpdwDispositionm,
              0,
              0);
            RegCloseKey(v566);
            goto LABEL_219;
          }
          if ( v350 > 0 )
            v538 = (unsigned __int16)v350 | 0x80070000;
          if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
          {
            v351 = GetLastError();
            v352 = CurrentIP();
            v349 = ConstructPartialMsgW(
                     0x2000000,
                     "Failed to open/create comparison mismatch key %s. Error: 0x%08X",
                     (const char *)L"Microsoft\\Windows\\CurrentVersion\\Setup\\Recovery\\PITR\\CompareMatch",
                     v538);
            lpdwDispositionl = v351;
            phkResultm = (PHKEY)v352;
            dwOptionsm = 5100;
          }
          else
          {
            v353 = GetLastError();
            v354 = CurrentIP();
            v349 = ConstructPartialMsgW(
                     0x2000000,
                     "Failed to open/create comparison mismatch key %s. Error: 0x%08X",
                     (const char *)L"Microsoft\\Windows\\CurrentVersion\\Setup\\Recovery\\PITR\\CompareMatch",
                     SnapshotData);
            lpdwDispositionl = v353;
            phkResultm = (PHKEY)v354;
            dwOptionsm = 5104;
          }
        }
        else
        {
          v347 = GetLastError();
          v348 = CurrentIP();
          v349 = ConstructPartialMsgW(0x2000000, "Failed to calculate comparison mismatch value. Error: 0x%08X", v537);
          lpdwDispositionl = v347;
          phkResultm = (PHKEY)v348;
          dwOptionsm = 5089;
        }
        WdsSetupLogMessageW(
          v349,
          0,
          L"D",
          0,
          dwOptionsm,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRBase::RestoreFromSnapshot",
          phkResultm,
          lpdwDispositionl,
          0,
          0);
LABEL_219:
        PITRTelemetry_CompareMismatch(v575);
LABEL_220:
        if ( hKey )
        {
          v361 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v582);
          if ( UnBCL::File::Exists(v361) )
          {
            v362 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v582);
            v363 = UnBCL::String::get_CString(v362);
            v540 = pImportRegKey(hKey, L"Control\\FVEAutoUnlock", v363);
            v364 = GetLastError();
            v365 = CurrentIP();
            if ( v540 >= 0 )
            {
              v367 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v582);
              v368 = (const char *)UnBCL::String::get_CString(v367);
              v369 = ConstructPartialMsgW(0x4000000, "Successfully imported FVE auto-unlock key from %s", v368);
              WdsSetupLogMessageW(
                v369,
                0,
                L"D",
                0,
                5140,
                L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
                L"CPITRBase::RestoreFromSnapshot",
                v365,
                v364,
                0,
                0);
            }
            else
            {
              v366 = ConstructPartialMsgW(0x2000000, "Failed to import FVE auto-unlock key. Error: 0x%08X", v540);
              WdsSetupLogMessageW(
                v366,
                0,
                L"D",
                0,
                5136,
                L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
                L"CPITRBase::RestoreFromSnapshot",
                v365,
                v364,
                0,
                0);
            }
          }
          if ( hKey )
          {
            RegCloseKey(hKey);
            hKey = 0;
          }
        }
        v40 = v572[0];
        if ( v572[0] )
        {
          RegCloseKey(v572[0]);
          RecUnloadKey(v370, L"$OFFLINE_RW$SYSTEM");
          v40 = 0;
          v572[0] = 0;
        }
        if ( v552 )
        {
          RegCloseKey(v552);
          RecUnloadKey(v371, L"$OFFLINE_RW$SOFTWARE");
          v552 = 0;
        }
        v372 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v579);
        if ( UnBCL::File::Exists(v372) )
        {
          v373 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v579);
          v374 = UnBCL::String::get_CString(v373);
          if ( !DeleteFileEx2((__int64)v374, 0) )
          {
            v375 = GetLastError();
            v376 = v375 < 0;
            if ( v375 > 0 )
              v376 = 1;
            if ( v376 )
            {
              v377 = GetLastError();
              SnapshotData = v377;
              if ( v377 > 0 )
                SnapshotData = (unsigned __int16)v377 | 0x80070000;
              v550 = -2147467259;
            }
            else
            {
              v550 = -2147467259;
              SnapshotData = -2147467259;
            }
            v378 = GetLastError();
            v379 = CurrentIP();
            v380 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v579);
            v381 = (const char *)UnBCL::String::get_CString(v380);
            v382 = ConstructPartialMsgW(
                     0x2000000,
                     "Failed to clear restore-active marker %s. Error: 0x%08X",
                     v381,
                     SnapshotData);
            WdsSetupLogMessageW(
              v382,
              0,
              L"D",
              0,
              5170,
              L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
              L"CPITRBase::RestoreFromSnapshot",
              v379,
              v378,
              0,
              0);
            v39 = v552;
            v40 = v572[0];
            goto LABEL_274;
          }
        }
        v39 = v552;
LABEL_273:
        v550 = -2147467259;
LABEL_274:
        v547 = WsbkUninstall(v294);
        if ( v547 >= 0 )
          goto LABEL_278;
        v421 = GetLastError();
        v422 = CurrentIP();
        v423 = ConstructPartialMsgW(50331648, "Failed to uninstall WinSetupBak. Error: 0x%08X", v547);
        WdsSetupLogMessageW(
          v423,
          0,
          L"D",
          0,
          5294,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRBase::RestoreFromSnapshot",
          v422,
          v421,
          0,
          0);
        goto LABEL_276;
      }
      v383 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v553);
      v384 = UnBCL::String::get_CString(v383);
      v385 = RecMountOfflineHive(v384, L"SOFTWARE", L"$OFFLINE_RW$SOFTWARE");
      v552 = v385;
      if ( !v385 )
      {
        v386 = GetLastError();
        v387 = CurrentIP();
        v388 = GetLastError();
        v389 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v553);
        v390 = (const char *)UnBCL::String::get_CString(v389);
        v293 = ConstructPartialMsgW(50331648, "Failed to load offline SOFTWARE hive from %s. Error: 0x%08X", v390, v388);
        lpdwDispositioni = v386;
        phkResultj = (PHKEY)v387;
        dwOptionsi = 5190;
        goto LABEL_171;
      }
      v541 = RegCreateKeyExW(
               v385,
               L"Microsoft\\Windows\\CurrentVersion\\Setup\\Recovery\\PITR\\Snapshots",
               0,
               0,
               0,
               0xF003Fu,
               0,
               &v568,
               0);
      if ( v541 )
      {
        v391 = GetLastError();
        v392 = CurrentIP();
        v393 = ConstructPartialMsgW(50331648, "Failed to open PITR snapshots key. Error: 0x%08X", v541);
        WdsSetupLogMessageW(
          v393,
          0,
          L"D",
          0,
          5209,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRBase::RestoreFromSnapshot",
          v392,
          v391,
          0,
          0);
      }
      else
      {
        v394 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v577);
        v395 = UnBCL::String::get_CString(v394);
        v542 = RegRestoreKeyW(v568, v395, 8u);
        v396 = GetLastError();
        v397 = CurrentIP();
        if ( v542 )
        {
          v398 = ConstructPartialMsgW(50331648, "Failed to import PITR snapshots key. Error: 0x%08X", v542);
          lpdwDispositionn = v396;
          phkResulto = (PHKEY)v397;
          dwOptionsp = 5218;
        }
        else
        {
          v399 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v577);
          v400 = (const char *)UnBCL::String::get_CString(v399);
          v398 = ConstructPartialMsgW(0x4000000, "Successfully imported snapshots key from %s", v400);
          lpdwDispositionn = v396;
          phkResulto = (PHKEY)v397;
          dwOptionsp = 5222;
        }
        WdsSetupLogMessageW(
          v398,
          0,
          L"D",
          0,
          dwOptionsp,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRBase::RestoreFromSnapshot",
          phkResulto,
          lpdwDispositionn,
          0,
          0);
        RegCloseKey(v568);
        v568 = 0;
      }
      v401 = v552;
      if ( !RegSetDword(v552, L"Microsoft\\Windows\\CurrentVersion\\Setup\\OOBE", L"InstallType", 19) )
      {
        v402 = GetLastError();
        v543 = v402;
        if ( v402 > 0 )
          v543 = (unsigned __int16)v402 | 0x80070000;
        v403 = GetLastError();
        v404 = CurrentIP();
        v405 = ConstructPartialMsgW(0x2000000, "Failed to write InstallType value after restore. Error: 0x%08X", v543);
        WdsSetupLogMessageW(
          v405,
          0,
          L"D",
          0,
          5232,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRBase::RestoreFromSnapshot",
          v404,
          v403,
          0,
          0);
        v401 = v552;
      }
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PITR_FastCompare>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PITR_FastCompare>::GetImpl'::`2'::impl)
        && v575 )
      {
        *(_QWORD *)v573 = 0;
        LODWORD(v574) = 0;
        WORD2(v574) = 0;
        SystemTime = 0;
        GetLocalTime(&SystemTime);
        dwOptionso[0] = SystemTime.wYear;
        v544 = StringCchPrintfW(v573, 7u, L"%02d%04d", SystemTime.wMonth, *(_QWORD *)dwOptionso);
        if ( v544 >= 0 )
        {
          v566 = 0;
          v409 = RegCreateKeyExW(
                   v401,
                   L"Microsoft\\Windows\\CurrentVersion\\Setup\\Recovery\\PITR\\CompareMatch",
                   0,
                   0,
                   0,
                   0xF003Fu,
                   0,
                   &v566,
                   0);
          v545 = v409;
          if ( !v409 )
          {
            if ( RegSetDword(v566, 0, v573, 1) )
            {
              v418 = GetLastError();
              v419 = CurrentIP();
              v417 = ConstructPartialMsgW(
                       50331648,
                       "Found mismatch comparisons, have set value %s for log collection",
                       (const char *)v573);
              lpdwDispositionp = v418;
              phkResultq = (PHKEY)v419;
              dwOptionsr = 5275;
            }
            else
            {
              v414 = GetLastError();
              v546 = v414;
              if ( v414 > 0 )
                v546 = (unsigned __int16)v414 | 0x80070000;
              v415 = GetLastError();
              v416 = CurrentIP();
              v417 = ConstructPartialMsgW(
                       0x2000000,
                       "Failed to write comparison mismatch value %s. Error: 0x%08X",
                       (const char *)v573,
                       v546);
              lpdwDispositionp = v415;
              phkResultq = (PHKEY)v416;
              dwOptionsr = 5271;
            }
            WdsSetupLogMessageW(
              v417,
              0,
              L"D",
              0,
              dwOptionsr,
              L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
              L"CPITRBase::RestoreFromSnapshot",
              phkResultq,
              lpdwDispositionp,
              0,
              0);
            RegCloseKey(v566);
            goto LABEL_271;
          }
          if ( v409 > 0 )
            v545 = (unsigned __int16)v409 | 0x80070000;
          if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
          {
            v410 = GetLastError();
            v411 = CurrentIP();
            v408 = ConstructPartialMsgW(
                     0x2000000,
                     "Failed to open/create comparison mismatch key %s. Error: 0x%08X",
                     (const char *)L"Microsoft\\Windows\\CurrentVersion\\Setup\\Recovery\\PITR\\CompareMatch",
                     v545);
            lpdwDispositiono = v410;
            phkResultp = (PHKEY)v411;
            dwOptionsq = 5259;
          }
          else
          {
            v412 = GetLastError();
            v413 = CurrentIP();
            v408 = ConstructPartialMsgW(
                     0x2000000,
                     "Failed to open/create comparison mismatch key %s. Error: 0x%08X",
                     (const char *)L"Microsoft\\Windows\\CurrentVersion\\Setup\\Recovery\\PITR\\CompareMatch",
                     SnapshotData);
            lpdwDispositiono = v412;
            phkResultp = (PHKEY)v413;
            dwOptionsq = 5263;
          }
        }
        else
        {
          v406 = GetLastError();
          v407 = CurrentIP();
          v408 = ConstructPartialMsgW(0x2000000, "Failed to calculate comparison mismatch value. Error: 0x%08X", v544);
          lpdwDispositiono = v406;
          phkResultp = (PHKEY)v407;
          dwOptionsq = 5248;
        }
        WdsSetupLogMessageW(
          v408,
          0,
          L"D",
          0,
          dwOptionsq,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRBase::RestoreFromSnapshot",
          phkResultp,
          lpdwDispositiono,
          0,
          0);
      }
LABEL_271:
      RegCloseKey(v552);
      RecUnloadKey(v420, L"$OFFLINE_RW$SOFTWARE");
      v39 = 0;
      v552 = 0;
      goto LABEL_272;
    }
    v183 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v553);
    v184 = UnBCL::String::get_CString(v183);
    v185 = RecMountOfflineHive(v184, L"SYSTEM", L"$OFFLINE_RW$SYSTEM");
    v186 = v185;
    v572[0] = v185;
    if ( !v185 )
    {
      v187 = GetLastError();
      SnapshotData = v187;
      if ( v187 > 0 )
        SnapshotData = (unsigned __int16)v187 | 0x80070000;
      v188 = GetLastError();
      v189 = CurrentIP();
      v190 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v553);
      v191 = (const char *)UnBCL::String::get_CString(v190);
      v192 = ConstructPartialMsgW(
               0x2000000,
               "Failed to load offline SYSTEM hive from %s. Error: 0x%08X",
               v191,
               SnapshotData);
      lpdwDispositiond = v188;
      phkResultd = (PHKEY)v189;
      dwOptionsd = 4780;
      goto LABEL_113;
    }
    v193 = RegGetDword(v185, L"Select", L"Default");
    v194 = UnBCL::String::Format(L"ControlSet%03d", v193);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v571, v194);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v583, v571);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v571);
    v195 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v583);
    v196 = UnBCL::String::get_CString(v195);
    v197 = pOpenRegKeyMaxAccess(v186, v196, &hKey);
    SnapshotData = v197;
    if ( v197 )
    {
      if ( v197 > 0 )
        SnapshotData = (unsigned __int16)v197 | 0x80070000;
      v198 = GetLastError();
      v199 = CurrentIP();
      v200 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v583);
      v201 = (const char *)UnBCL::String::get_CString(v200);
      v192 = ConstructPartialMsgW(0x2000000, "Failed to open Control key %s. Error: 0x%08X", v201, SnapshotData);
      lpdwDispositiond = v198;
      phkResultd = (PHKEY)v199;
      dwOptionsd = 4795;
      goto LABEL_113;
    }
    v202 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v560, L"Snapshots.hiv");
    v203 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v576);
    v204 = UnBCL::Path::Combine(v203, v202);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v571, v204);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v577, v571);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v571);
    UnBCL::String::~String((UnBCL::String *)v560);
    v205 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v577);
    v206 = UnBCL::String::get_CString(v205);
    SnapshotData = pExportRegKey(
                     v176,
                     (const char *)L"Microsoft\\Windows\\CurrentVersion\\Setup\\Recovery\\PITR\\Snapshots",
                     v206);
    if ( SnapshotData >= 0 )
    {
      v210 = GetLastError();
      v211 = CurrentIP();
      v212 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v577);
      v213 = (const char *)UnBCL::String::get_CString(v212);
      v209 = ConstructPartialMsgW(0x4000000, "Successfully exported snapshots key to %s", v213);
      lpdwDispositione = v210;
      phkResulte = (PHKEY)v211;
      dwOptionse = 4818;
    }
    else
    {
      v207 = GetLastError();
      v208 = CurrentIP();
      if ( SnapshotData != -2147024894 )
      {
        v192 = ConstructPartialMsgW(0x2000000, "Failed to export PITR snapshots key. Error: 0x%08X", SnapshotData);
        lpdwDispositiond = v207;
        phkResultd = (PHKEY)v208;
        dwOptionsd = 4812;
        goto LABEL_113;
      }
      v209 = ConstructPartialMsgW(0x4000000, "Snapshots key does not exist, nothing to export");
      lpdwDispositione = v207;
      phkResulte = (PHKEY)v208;
      dwOptionse = 4808;
    }
    WdsSetupLogMessageW(
      v209,
      0,
      L"D",
      0,
      dwOptionse,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"CPITRBase::RestoreFromSnapshot",
      phkResulte,
      lpdwDispositione,
      0,
      0);
    v214 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v560, L"WinRETrust.hiv");
    v215 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v576);
    v216 = UnBCL::Path::Combine(v215, v214);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v571, v216);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v584, v571);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v571);
    UnBCL::String::~String((UnBCL::String *)v560);
    v217 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v584);
    v218 = UnBCL::String::get_CString(v217);
    SnapshotData = pExportRegKey(v552, (const char *)L"Microsoft\\Windows\\CurrentVersion\\Reliability\\WinRE", v218);
    if ( SnapshotData >= 0 )
    {
      v222 = GetLastError();
      v223 = CurrentIP();
      v224 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v584);
      v225 = (const char *)UnBCL::String::get_CString(v224);
      v221 = ConstructPartialMsgW(0x4000000, "Successfully exported WinRE trust key to %s", v225);
      lpdwDispositionf = v222;
      phkResultf = (PHKEY)v223;
      dwOptionsf = 4840;
    }
    else
    {
      v219 = GetLastError();
      v220 = CurrentIP();
      if ( SnapshotData != -2147024894 )
      {
        v192 = ConstructPartialMsgW(0x2000000, "Failed to export WinRE trust key. Error: 0x%08X", SnapshotData);
        lpdwDispositiond = v219;
        phkResultd = (PHKEY)v220;
        dwOptionsd = 4834;
        goto LABEL_113;
      }
      v221 = ConstructPartialMsgW(0x4000000, "WinRE trust key does not exist, nothing to export");
      lpdwDispositionf = v219;
      phkResultf = (PHKEY)v220;
      dwOptionsf = 4830;
    }
    WdsSetupLogMessageW(
      v221,
      0,
      L"D",
      0,
      dwOptionsf,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"CPITRBase::RestoreFromSnapshot",
      phkResultf,
      lpdwDispositionf,
      0,
      0);
    v226 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v560, L"FVEAutoUnlock.hiv");
    v227 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v576);
    v228 = UnBCL::Path::Combine(v227, v226);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v571, v228);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v582, v571);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v571);
    UnBCL::String::~String((UnBCL::String *)v560);
    v229 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v582);
    v230 = UnBCL::String::get_CString(v229);
    SnapshotData = pExportRegKey(hKey, (const char *)L"Control\\FVEAutoUnlock", v230);
    if ( SnapshotData >= 0 )
    {
      v234 = GetLastError();
      v235 = CurrentIP();
      v236 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v582);
      v237 = (const char *)UnBCL::String::get_CString(v236);
      v233 = ConstructPartialMsgW(0x4000000, "Successfully exported FVE auto-unlock key to %s", v237);
      lpdwDispositiong = v234;
      phkResultg = (PHKEY)v235;
      dwOptionsg = 4862;
      goto LABEL_133;
    }
    v231 = GetLastError();
    v232 = CurrentIP();
    if ( SnapshotData == -2147024894 )
    {
      v233 = ConstructPartialMsgW(0x4000000, "FVE auto-unlock key does not exist, nothing to export");
      lpdwDispositiong = v231;
      phkResultg = (PHKEY)v232;
      dwOptionsg = 4852;
LABEL_133:
      WdsSetupLogMessageW(
        v233,
        0,
        L"D",
        0,
        dwOptionsg,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"CPITRBase::RestoreFromSnapshot",
        phkResultg,
        lpdwDispositiong,
        0,
        0);
      RegCloseKey(hKey);
      hKey = 0;
      RegCloseKey(v572[0]);
      RecUnloadKey(v238, L"$OFFLINE_RW$SYSTEM");
      goto LABEL_153;
    }
    v192 = ConstructPartialMsgW(0x2000000, "Failed to export FVE auto-unlock key. Error: 0x%08X", SnapshotData);
    lpdwDispositiond = v231;
    phkResultd = (PHKEY)v232;
    dwOptionsd = 4856;
LABEL_113:
    WdsSetupLogMessageW(
      v192,
      0,
      L"D",
      0,
      dwOptionsd,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"CPITRBase::RestoreFromSnapshot",
      phkResultd,
      lpdwDispositiond,
      0,
      0);
    v550 = -2147467259;
LABEL_276:
    v40 = v572[0];
    goto LABEL_277;
  }
  v36 = GetLastError();
  v37 = CurrentIP();
  v38 = ConstructPartialMsgW(
          0x2000000,
          "%hs: Failed to initialize COM. Error: 0x%08X",
          "CPITRBase::RestoreFromSnapshot",
          SnapshotData);
  WdsSetupLogMessageW(
    v38,
    0,
    L"D",
    0,
    4588,
    L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
    L"CPITRBase::RestoreFromSnapshot",
    v37,
    v36,
    0,
    0);
LABEL_21:
  v550 = -2147467259;
LABEL_22:
  v39 = 0;
  v40 = 0;
LABEL_278:
  if ( v568 )
  {
    RegCloseKey(v568);
    v568 = 0;
  }
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
  {
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    if ( v40 )
    {
      RegCloseKey(v40);
      RecUnloadKey(v424, L"$OFFLINE_RW$SYSTEM");
    }
  }
  if ( v39 )
  {
    RegCloseKey(v39);
    RecUnloadKey(v425, L"$OFFLINE_RW$SOFTWARE");
  }
  v426 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v576);
  if ( UnBCL::Directory::Exists(v426) )
  {
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
    {
      if ( SnapshotData < 0
        && UnBCL::SmartPtr<UnBCL::String>::get_P(v579)
        && (v427 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v579), UnBCL::File::Exists(v427)) )
      {
        v428 = GetLastError();
        v429 = CurrentIP();
        v430 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v576);
        v431 = (const char *)UnBCL::String::get_CString(v430);
        v432 = ConstructPartialMsgW(0x4000000, "Preserving driver store path %s for interrupted restore recovery", v431);
        WdsSetupLogMessageW(
          v432,
          0,
          L"D",
          0,
          5335,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRBase::RestoreFromSnapshot",
          v429,
          v428,
          0,
          0);
      }
      else
      {
        v433 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v576);
        v434 = UnBCL::String::get_CString(v433);
        if ( !(unsigned int)DeletePathEx(v434) )
        {
          v435 = GetLastError();
          v436 = v435 < 0;
          if ( v435 > 0 )
            v436 = 1;
          if ( !v436 )
            goto LABEL_301;
          v437 = GetLastError();
          v550 = v437;
          if ( v437 > 0 )
          {
            v437 = (unsigned __int16)v437 | 0x80070000;
            v550 = v437;
          }
          if ( v437 <= -2147024895 || (unsigned int)(v437 + 2147024892) <= 0x7FF8FFFB )
          {
LABEL_301:
            v438 = GetLastError();
            v439 = CurrentIP();
            v440 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v576);
            v441 = (const char *)UnBCL::String::get_CString(v440);
            v442 = ConstructPartialMsgW(50331648, "Failed to remove driver store path: %s. Error: 0x%08X", v441, v550);
            WdsSetupLogMessageW(
              v442,
              0,
              L"D",
              0,
              5351,
              L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
              L"CPITRBase::RestoreFromSnapshot",
              v439,
              v438,
              0,
              0);
          }
        }
      }
    }
    else
    {
      v443 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v576);
      v444 = UnBCL::String::get_CString(v443);
      if ( !(unsigned int)DeletePathEx(v444) )
      {
        v445 = GetLastError();
        v446 = v445 < 0;
        if ( v445 > 0 )
          v446 = 1;
        if ( !v446 )
          goto LABEL_310;
        v447 = GetLastError();
        v550 = v447;
        if ( v447 > 0 )
        {
          v447 = (unsigned __int16)v447 | 0x80070000;
          v550 = v447;
        }
        if ( v447 <= -2147024895 || (unsigned int)(v447 + 2147024892) <= 0x7FF8FFFB )
        {
LABEL_310:
          v448 = GetLastError();
          v449 = CurrentIP();
          v450 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v576);
          v451 = (const char *)UnBCL::String::get_CString(v450);
          v452 = ConstructPartialMsgW(50331648, "Failed to remove driver store path: %s. Error: 0x%08X", v451, v550);
          WdsSetupLogMessageW(
            v452,
            0,
            L"D",
            0,
            5369,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
            L"CPITRBase::RestoreFromSnapshot",
            v449,
            v448,
            0,
            0);
        }
      }
    }
  }
  if ( v555 > 0 )
  {
    v554 = 0;
    v453 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v553);
    if ( (int)VssGetSnapshotsSizeInfo(v453, (__int64 *)&v554, 0, 0) >= 0 && (__int64)v554 > v555 )
    {
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
      {
        v454 = GetLastError();
        v455 = CurrentIP();
        v456 = ConstructPartialMsgW(
                 50331648,
                 "Current VSS used size is %I64d. We are about to set back the max size to %I64d, some snapshots will be deleted",
                 v554,
                 v555);
        WdsSetupLogMessageW(
          v456,
          0,
          L"D",
          0,
          5393,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRBase::RestoreFromSnapshot",
          v455,
          v454,
          0,
          0);
      }
      else
      {
        v457 = GetLastError();
        v458 = CurrentIP();
        v459 = ConstructPartialMsgW(
                 50331648,
                 "Current VSS used size is %I64u. We are about to set back the max size to %I64u, some snapshots will be deleted",
                 v554,
                 v555);
        WdsSetupLogMessageW(
          v459,
          0,
          L"D",
          0,
          5402,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRBase::RestoreFromSnapshot",
          v458,
          v457,
          0,
          0);
      }
    }
    v460 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v553);
    v548 = VssSetSnapshotsMaxSize(v460, v555);
    if ( v548 < 0 )
    {
      v461 = GetLastError();
      v462 = CurrentIP();
      v463 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v578);
      v464 = (const char *)UnBCL::String::get_CString(v463);
      v465 = ConstructPartialMsgW(
               0x2000000,
               "Failed to set back maximum VSS limit for volume %s. Error: 0x%08X",
               v464,
               v548);
      WdsSetupLogMessageW(
        v465,
        0,
        L"D",
        0,
        5409,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"CPITRBase::RestoreFromSnapshot",
        v462,
        v461,
        0,
        0);
    }
  }
  VssFreeSnapshotPropertiesInternal(&v570);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl)
    && v564 )
  {
    (*(void (__fastcall **)(struct PITR::IPITRSnapshot *))(*(_QWORD *)v564 + 64LL))(v564);
  }
  if ( v556 )
    pEnablePrivilege(L"SeBackupPrivilege", 0, 0);
  if ( v557 )
    pEnablePrivilege(L"SeRestorePrivilege", 0, 0);
  if ( v558 )
    pEnablePrivilege(L"SeSecurityPrivilege", 0, 0);
  if ( v559 )
    CoUninitialize();
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v582);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v583);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v584);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v577);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v579);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v576);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v578);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v586);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v580);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v587);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v585);
  v561 = &UnBCL::SmartPtr<CPITRSnapshotEnumerator>::`vftable';
  UnBCL::SmartPtr<CPITRSnapshotEnumerator>::DeAssign(&v561);
  return (unsigned int)SnapshotData;
}

```

## disassembly

```asm
0x1800170f0  mov     r11, rsp
0x1800170f3  push    rbx
0x1800170f4  push    rsi
0x1800170f5  push    rdi
0x1800170f6  push    r12
0x1800170f8  push    r13
0x1800170fa  push    r14
0x1800170fc  push    r15
0x1800170fe  sub     rsp, 2A0h
0x180017105  mov     rax, cs:__security_cookie
0x18001710c  xor     rax, rsp
0x18001710f  mov     [rsp+2D8h+var_40], rax
0x180017117  mov     [rsp+2D8h+var_278], r9d
0x18001711c  mov     [rsp+2D8h+var_274], r8d
0x180017121  mov     rsi, rdx
0x180017124  mov     [rsp+2D8h+var_260], rdx
0x180017129  mov     rbx, rcx
0x18001712c  mov     [rsp+2D8h+var_270], rcx
0x180017131  mov     rax, [rsp+2D8h+arg_20]
0x180017139  mov     qword ptr [rsp+2D8h+SystemTime.wYear], rax
0x180017141  mov     rax, [rsp+2D8h+arg_28]
0x180017149  mov     [rsp+2D8h+var_218], rax
0x180017151  mov     rax, [rsp+2D8h+arg_30]
0x180017159  mov     [rsp+2D8h+var_200], rax
0x180017161  xor     r14d, r14d
0x180017164  mov     [r11-250h], r14d
0x18001716b  mov     [r11-24Ch], r14d
0x180017172  mov     [r11-248h], r14d
0x180017179  lea     rdi, ??_7?$SmartPtr@VCPITRSnapshotEnumerator@@@UnBCL@@6B@; const UnBCL::SmartPtr<CPITRSnapshotEnumerator>::`vftable'
0x180017180  mov     [r11-228h], rdi
0x180017187  mov     [r11-220h], r14
0x18001718e  mov     [r11-210h], r14
0x180017195  xor     edx, edx; Val
0x180017197  mov     r8d, 80h; Size
0x18001719d  lea     rcx, [r11-1D8h]; void *
0x1800171a4  call    memset_0
0x1800171a9  lea     rcx, [rsp+2D8h+var_80]
0x1800171b1  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x1800171b7  nop
0x1800171b8  lea     rcx, [rsp+2D8h+var_60]
0x1800171c0  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x1800171c6  nop
0x1800171c7  lea     rcx, [rsp+2D8h+var_D0]
0x1800171cf  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x1800171d5  nop
0x1800171d6  lea     rcx, [rsp+2D8h+var_70]
0x1800171de  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x1800171e4  nop
0x1800171e5  lea     rcx, [rsp+2D8h+var_F0]
0x1800171ed  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x1800171f3  nop
0x1800171f4  mov     [rsp+2D8h+var_118], r14d
0x1800171fc  mov     [rsp+2D8h+var_140], r14
0x180017204  mov     [rsp+2D8h+var_258], r14
0x18001720c  mov     qword ptr [rsp+2D8h+TotalNumberOfFreeBytes], r14
0x180017214  lea     eax, [r14+3Fh]
0x180017218  mov     [rsp+2D8h+var_48], ax
0x180017220  mov     [rsp+2D8h+var_46], 3Ah ; ':'
0x18001722b  lea     rax, [rsp+2D8h+var_48]
0x180017233  mov     [rsp+2D8h+var_50], rax
0x18001723b  lea     rcx, [rsp+2D8h+var_110]
0x180017243  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x180017249  nop
0x18001724a  lea     rcx, [rsp+2D8h+var_E0]
0x180017252  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x180017258  nop
0x180017259  mov     [rsp+2D8h+var_1F0], r14
0x180017261  lea     rcx, [rsp+2D8h+var_100]
0x180017269  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x18001726f  nop
0x180017270  lea     rcx, [rsp+2D8h+var_90]
0x180017278  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x18001727e  nop
0x18001727f  lea     rcx, [rsp+2D8h+var_A0]
0x180017287  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x18001728d  nop
0x18001728e  mov     [rsp+2D8h+hKey], r14
0x180017296  lea     rcx, [rsp+2D8h+var_B0]
0x18001729e  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x1800172a4  nop
0x1800172a5  mov     [rsp+2D8h+var_244], r14d
0x1800172ad  test    rsi, rsi
0x1800172b0  jnz     loc_18001737B
0x1800172b6  lea     rcx, [rsp+2D8h+var_B0]
0x1800172be  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800172c4  nop
0x1800172c5  lea     rcx, [rsp+2D8h+var_A0]
0x1800172cd  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800172d3  nop
0x1800172d4  lea     rcx, [rsp+2D8h+var_90]
0x1800172dc  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800172e2  nop
0x1800172e3  lea     rcx, [rsp+2D8h+var_100]
0x1800172eb  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800172f1  nop
0x1800172f2  lea     rcx, [rsp+2D8h+var_E0]
0x1800172fa  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180017300  nop
0x180017301  lea     rcx, [rsp+2D8h+var_110]
0x180017309  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18001730f  nop
0x180017310  lea     rcx, [rsp+2D8h+var_F0]
0x180017318  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18001731e  nop
0x18001731f  lea     rcx, [rsp+2D8h+var_70]
0x180017327  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18001732d  nop
0x18001732e  lea     rcx, [rsp+2D8h+var_D0]
0x180017336  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18001733c  nop
0x18001733d  lea     rcx, [rsp+2D8h+var_60]
0x180017345  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18001734b  nop
0x18001734c  lea     rcx, [rsp+2D8h+var_80]
0x180017354  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18001735a  nop
0x18001735b  mov     [rsp+2D8h+var_228], rdi
0x180017363  lea     rcx, [rsp+2D8h+var_228]
0x18001736b  call    ?DeAssign@?$SmartPtr@VCPITRSnapshotEnumerator@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<CPITRSnapshotEnumerator>::DeAssign(void)
0x180017370  nop
0x180017371  mov     eax, 80070057h
0x180017376  jmp     loc_18001B1A9
0x18001737b  lea     rax, [rbx+18h]
0x18001737f  mov     [rsp+2D8h+var_268], rax
0x180017384  mov     rcx, rax
0x180017387  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18001738d  test    rax, rax
0x180017390  jnz     loc_18001745B
0x180017396  lea     rcx, [rsp+2D8h+var_B0]
0x18001739e  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800173a4  nop
0x1800173a5  lea     rcx, [rsp+2D8h+var_A0]
0x1800173ad  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800173b3  nop
0x1800173b4  lea     rcx, [rsp+2D8h+var_90]
0x1800173bc  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800173c2  nop
0x1800173c3  lea     rcx, [rsp+2D8h+var_100]
0x1800173cb  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800173d1  nop
0x1800173d2  lea     rcx, [rsp+2D8h+var_E0]
0x1800173da  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800173e0  nop
0x1800173e1  lea     rcx, [rsp+2D8h+var_110]
0x1800173e9  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800173ef  nop
0x1800173f0  lea     rcx, [rsp+2D8h+var_F0]
0x1800173f8  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800173fe  nop
0x1800173ff  lea     rcx, [rsp+2D8h+var_70]
0x180017407  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18001740d  nop
0x18001740e  lea     rcx, [rsp+2D8h+var_D0]
0x180017416  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18001741c  nop
0x18001741d  lea     rcx, [rsp+2D8h+var_60]
0x180017425  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18001742b  nop
0x18001742c  lea     rcx, [rsp+2D8h+var_80]
0x180017434  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18001743a  nop
0x18001743b  mov     [rsp+2D8h+var_228], rdi
0x180017443  lea     rcx, [rsp+2D8h+var_228]
0x18001744b  call    ?DeAssign@?$SmartPtr@VCPITRSnapshotEnumerator@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<CPITRSnapshotEnumerator>::DeAssign(void)
0x180017450  nop
0x180017451  mov     eax, 80070032h
0x180017456  jmp     loc_18001B1A9
0x18001745b  call    cs:__imp_GetLastError
0x180017461  mov     edi, eax
0x180017463  call    cs:__imp_CurrentIP
0x180017469  mov     rbx, rax
0x18001746c  mov     r8, rsi
0x18001746f  lea     rdx, aRestoringFromS_0; "Restoring from snapshot : %s"
0x180017476  mov     ecx, 4000000h; unsigned int
0x18001747b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180017480  mov     [rsp+2D8h+var_288], r14d
0x180017485  mov     [rsp+2D8h+var_290], r14
0x18001748a  mov     dword ptr [rsp+2D8h+lpdwDisposition], edi
0x18001748e  mov     [rsp+2D8h+phkResult], rbx
0x180017493  lea     r13, aCpitrbaseResto; "CPITRBase::RestoreFromSnapshot"
0x18001749a  mov     [rsp+2D8h+lpSecurityAttributes], r13
0x18001749f  lea     r15, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x1800174a6  mov     qword ptr [rsp+2D8h+samDesired], r15
0x1800174ab  mov     [rsp+2D8h+dwOptions], 11C6h
0x1800174b3  xor     r9d, r9d
0x1800174b6  lea     r12, aD; "D"
0x1800174bd  mov     r8, r12
0x1800174c0  xor     edx, edx
0x1800174c2  mov     rcx, rax
0x1800174c5  call    cs:__imp_WdsSetupLogMessageW
0x1800174cb  call    cs:__imp_GetLastError
0x1800174d1  mov     edi, eax
0x1800174d3  call    cs:__imp_CurrentIP
0x1800174d9  mov     rbx, rax
0x1800174dc  lea     rax, aOff; "Off"
0x1800174e3  lea     rsi, aOn; "On"
0x1800174ea  mov     r8, rsi
0x1800174ed  cmp     [rsp+2D8h+var_274], r14d
0x1800174f2  cmovz   r8, rax
0x1800174f6  lea     rdx, aThoroughModeIs; "Thorough mode is: %s"
0x1800174fd  mov     ecx, 4000000h; unsigned int
0x180017502  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180017507  mov     [rsp+2D8h+var_288], r14d
0x18001750c  mov     [rsp+2D8h+var_290], r14
0x180017511  mov     dword ptr [rsp+2D8h+lpdwDisposition], edi
0x180017515  mov     [rsp+2D8h+phkResult], rbx
0x18001751a  mov     [rsp+2D8h+lpSecurityAttributes], r13
0x18001751f  mov     qword ptr [rsp+2D8h+samDesired], r15
0x180017524  mov     [rsp+2D8h+dwOptions], 11C7h
0x18001752c  xor     r9d, r9d
0x18001752f  mov     r8, r12
0x180017532  xor     edx, edx
0x180017534  mov     rcx, rax
0x180017537  call    cs:__imp_WdsSetupLogMessageW
0x18001753d  call    cs:__imp_GetLastError
0x180017543  mov     edi, eax
0x180017545  call    cs:__imp_CurrentIP
0x18001754b  mov     rbx, rax
0x18001754e  cmp     [rsp+2D8h+var_278], r14d
0x180017553  lea     rax, aOff; "Off"
0x18001755a  cmovz   rsi, rax
0x18001755e  mov     r8, rsi
0x180017561  lea     rdx, aVerboseModeIsS; "Verbose  mode is: %s"
0x180017568  mov     r15d, 4000000h
0x18001756e  mov     ecx, r15d; unsigned int
0x180017571  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180017576  mov     [rsp+2D8h+var_288], r14d
0x18001757b  mov     [rsp+2D8h+var_290], r14
0x180017580  mov     dword ptr [rsp+2D8h+lpdwDisposition], edi
0x180017584  mov     [rsp+2D8h+phkResult], rbx
0x180017589  mov     [rsp+2D8h+lpSecurityAttributes], r13
0x18001758e  lea     rsi, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x180017595  mov     qword ptr [rsp+2D8h+samDesired], rsi
0x18001759a  mov     [rsp+2D8h+dwOptions], 11C8h
0x1800175a2  xor     r9d, r9d
0x1800175a5  mov     r8, r12
0x1800175a8  xor     edx, edx
0x1800175aa  mov     rcx, rax
0x1800175ad  call    cs:__imp_WdsSetupLogMessageW
0x1800175b3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PITR_FastCompare@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PITR_FastCompare@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PITR_FastCompare> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PITR_FastCompare>::GetImpl(void)'::`2'::impl
0x1800175ba  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PITR_FastCompare@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PITR_FastCompare>::__private_IsEnabled(void)
0x1800175bf  test    al, al
0x1800175c1  jnz     short loc_180017618
0x1800175c3  cmp     [rsp+2D8h+var_274], r14d
0x1800175c8  jnz     loc_180017791
0x1800175ce  call    cs:__imp_GetLastError
0x1800175d4  mov     edi, eax
0x1800175d6  call    cs:__imp_CurrentIP
0x1800175dc  mov     rbx, rax
0x1800175df  lea     rdx, aThoroughModeWi_0; "Thorough mode will be forced ON"
0x1800175e6  mov     ecx, r15d; unsigned int
0x1800175e9  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800175ee  mov     [rsp+2D8h+var_288], r14d
0x1800175f3  mov     [rsp+2D8h+var_290], r14
0x1800175f8  mov     dword ptr [rsp+2D8h+lpdwDisposition], edi
0x1800175fc  mov     [rsp+2D8h+phkResult], rbx
0x180017601  mov     [rsp+2D8h+lpSecurityAttributes], r13
0x180017606  mov     qword ptr [rsp+2D8h+samDesired], rsi
0x18001760b  mov     [rsp+2D8h+dwOptions], 11E3h
0x180017613  jmp     loc_180017778
0x180017618  lea     rdx, aPitrConfigEnvT; "PITR_CONFIG_ENV_THOROUGH"
0x18001761f  lea     rcx, [rsp+2D8h+var_158]
0x180017627  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18001762d  nop
0x18001762e  xor     edx, edx
0x180017630  mov     rcx, rax
0x180017633  call    cs:__imp_?IsEnvironmentVarSetTrue@Environment@UnBCL@@SAHPEBVString@2@H@Z; UnBCL::Environment::IsEnvironmentVarSetTrue(UnBCL::String const *,int)
0x180017639  mov     ebx, eax
0x18001763b  lea     rcx, [rsp+2D8h+var_158]
0x180017643  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180017649  test    ebx, ebx
0x18001764b  jz      short loc_180017697
0x18001764d  call    cs:__imp_GetLastError
0x180017653  mov     edi, eax
0x180017655  call    cs:__imp_CurrentIP
0x18001765b  mov     rbx, rax
0x18001765e  lea     rdx, aThoroughModeFo; "Thorough mode forced ON by environment "...
0x180017665  mov     ecx, r15d; unsigned int
0x180017668  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18001766d  mov     [rsp+2D8h+var_288], r14d
0x180017672  mov     [rsp+2D8h+var_290], r14
0x180017677  mov     dword ptr [rsp+2D8h+lpdwDisposition], edi
0x18001767b  mov     [rsp+2D8h+phkResult], rbx
0x180017680  mov     [rsp+2D8h+lpSecurityAttributes], r13
0x180017685  mov     qword ptr [rsp+2D8h+samDesired], rsi
0x18001768a  mov     [rsp+2D8h+dwOptions], 11CDh
0x180017692  jmp     loc_180017778
0x180017697  lea     rdx, aPitrConfigEnvT; "PITR_CONFIG_ENV_THOROUGH"
0x18001769e  lea     rcx, [rsp+2D8h+var_158]
0x1800176a6  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800176ac  nop
0x1800176ad  mov     edx, 1
0x1800176b2  mov     rcx, rax
0x1800176b5  call    cs:__imp_?IsEnvironmentVarSetTrue@Environment@UnBCL@@SAHPEBVString@2@H@Z; UnBCL::Environment::IsEnvironmentVarSetTrue(UnBCL::String const *,int)
0x1800176bb  mov     ebx, eax
0x1800176bd  lea     rcx, [rsp+2D8h+var_158]
0x1800176c5  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800176cb  test    ebx, ebx
0x1800176cd  jnz     short loc_18001772C
0x1800176cf  call    cs:__imp_GetLastError
  ... truncated ...
```
