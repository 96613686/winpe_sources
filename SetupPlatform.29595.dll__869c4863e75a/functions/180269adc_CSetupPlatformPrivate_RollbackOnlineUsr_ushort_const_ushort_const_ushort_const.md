# CSetupPlatformPrivate::RollbackOnlineUsr(ushort const *,ushort const *,ushort const *)

- ea: `0x180269adc`
- end: `0x18026a601`
- name: `?RollbackOnlineUsr@CSetupPlatformPrivate@@IEAAJPEBG00@Z`
- size: `2853`
- prototype: `__int64 __fastcall(CSetupPlatformPrivate *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1802645f0`

## callees

- `0x180057dec`
- `0x180267008`
- `0x180269adc`
- `0x18026a608`
- `0x1802cd66c`
- `0x1802cff64`
- `0x1802d1d08`
- `0x1802e2078`
- `0x1802e5a10`
- `0x180373754`
- `0x180373a0c`
- `0x1803755e8`
- `0x180509010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180269b5a`
- `ADVAPI32!RegCloseKey` at `0x180269b5a`
- `ADVAPI32!RegOpenKeyExW` at `0x180269b3f`
- `ADVAPI32!RegOpenKeyExW` at `0x180269b3f`
- `KERNEL32!GetLastError` at `0x180269b68`
- `KERNEL32!GetLastError` at `0x180269c75`
- `KERNEL32!GetLastError` at `0x180269ceb`
- `KERNEL32!GetLastError` at `0x180269e22`
- `KERNEL32!GetLastError` at `0x180269eda`
- `KERNEL32!GetLastError` at `0x180269ef2`
- `KERNEL32!GetLastError` at `0x180269f0a`
- `KERNEL32!GetLastError` at `0x180269fe9`
- `KERNEL32!GetLastError` at `0x18026a3a8`
- `KERNEL32!GetLastError` at `0x18026a40f`
- `KERNEL32!GetLastError` at `0x18026a474`
- `KERNEL32!GetLastError` at `0x18026a527`
- `KERNEL32!GetLastError` at `0x180269b68`
- `KERNEL32!GetLastError` at `0x180269c75`
- `KERNEL32!GetLastError` at `0x180269ceb`
- `KERNEL32!GetLastError` at `0x180269e22`
- `KERNEL32!GetLastError` at `0x180269eda`
- `KERNEL32!GetLastError` at `0x180269ef2`
- `KERNEL32!GetLastError` at `0x180269f0a`
- `KERNEL32!GetLastError` at `0x180269fe9`
- `KERNEL32!GetLastError` at `0x18026a3a8`
- `KERNEL32!GetLastError` at `0x18026a40f`
- `KERNEL32!GetLastError` at `0x18026a474`
- `KERNEL32!GetLastError` at `0x18026a527`
- `KERNEL32!SetLastError` at `0x180269b62`
- `KERNEL32!SetLastError` at `0x180269ce5`
- `KERNEL32!SetLastError` at `0x180269b62`
- `KERNEL32!SetLastError` at `0x180269ce5`
- `KERNEL32!SetEnvironmentVariableW` at `0x18026a127`
- `KERNEL32!SetEnvironmentVariableW` at `0x18026a127`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180269c0e`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180269dc9`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18026a0d2`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180269c0e`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180269dc9`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18026a0d2`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x18026a268`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x18026a2a3`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x18026a326`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x18026a35f`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x18026a268`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x18026a2a3`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x18026a326`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x18026a35f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180269c02`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180269dbd`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026a074`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026a0c6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026a108`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026a130`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026a153`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026a224`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026a259`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026a294`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026a2e4`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026a317`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026a350`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180269c02`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180269dbd`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026a074`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026a0c6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026a108`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026a130`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026a153`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026a224`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026a259`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026a294`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026a2e4`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026a317`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026a350`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180269c27`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180269de2`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18026a0ea`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18026a2c4`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18026a2da`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18026a380`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18026a392`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18026a515`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18026a521`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180269c27`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180269de2`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18026a0ea`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18026a2c4`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18026a2da`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18026a380`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18026a392`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18026a515`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18026a521`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180269bee`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180269dad`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18026a0ba`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18026a242`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18026a27d`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18026a302`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18026a33b`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18026a4e4`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18026a4f5`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180269bee`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180269dad`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18026a0ba`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18026a242`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18026a27d`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18026a302`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18026a33b`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18026a4e4`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18026a4f5`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180269c4f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180269dec`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180269eb6`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18026a1af`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18026a1ed`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180269c4f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180269dec`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180269eb6`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18026a1af`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18026a1ed`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180269c58`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180269df5`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180269e36`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180269ebf`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18026a1b8`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18026a1f6`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180269c58`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180269df5`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180269e36`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180269ebf`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18026a1b8`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18026a1f6`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18026a17e`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18026a5ce`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18026a5d9`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18026a5e4`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18026a17e`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18026a5ce`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18026a5d9`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18026a5e4`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180269c1c`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180269dd6`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18026a0df`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18026a1db`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18026a219`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180269c1c`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180269dd6`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18026a0df`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18026a1db`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18026a219`
- `WDSCORE!WdsSetupLogMessageW` at `0x180269bdd`
- `WDSCORE!WdsSetupLogMessageW` at `0x180269cd2`
- `WDSCORE!WdsSetupLogMessageW` at `0x180269d59`
- `WDSCORE!WdsSetupLogMessageW` at `0x180269e96`
- `WDSCORE!WdsSetupLogMessageW` at `0x180269f75`
- `WDSCORE!WdsSetupLogMessageW` at `0x18026a051`
- `WDSCORE!WdsSetupLogMessageW` at `0x18026a409`
- `WDSCORE!WdsSetupLogMessageW` at `0x18026a469`
- `WDSCORE!WdsSetupLogMessageW` at `0x18026a4d5`
- `WDSCORE!WdsSetupLogMessageW` at `0x18026a5c3`
- `WDSCORE!WdsSetupLogMessageW` at `0x180269bdd`
- `WDSCORE!WdsSetupLogMessageW` at `0x180269cd2`
- `WDSCORE!WdsSetupLogMessageW` at `0x180269d59`
- `WDSCORE!WdsSetupLogMessageW` at `0x180269e96`
- `WDSCORE!WdsSetupLogMessageW` at `0x180269f75`
- `WDSCORE!WdsSetupLogMessageW` at `0x18026a051`
- `WDSCORE!WdsSetupLogMessageW` at `0x18026a409`
- `WDSCORE!WdsSetupLogMessageW` at `0x18026a469`
- `WDSCORE!WdsSetupLogMessageW` at `0x18026a4d5`
- `WDSCORE!WdsSetupLogMessageW` at `0x18026a5c3`
- `WDSCORE!CurrentIP` at `0x180269b70`
- `WDSCORE!CurrentIP` at `0x180269c7d`
- `WDSCORE!CurrentIP` at `0x180269cf3`
- `WDSCORE!CurrentIP` at `0x180269e2a`
- `WDSCORE!CurrentIP` at `0x180269f12`
- `WDSCORE!CurrentIP` at `0x180269ff1`
- `WDSCORE!CurrentIP` at `0x18026a3b0`
- `WDSCORE!CurrentIP` at `0x18026a417`
- `WDSCORE!CurrentIP` at `0x18026a47c`
- `WDSCORE!CurrentIP` at `0x18026a52f`
- `WDSCORE!CurrentIP` at `0x180269b70`
- `WDSCORE!CurrentIP` at `0x180269c7d`
- `WDSCORE!CurrentIP` at `0x180269cf3`
- `WDSCORE!CurrentIP` at `0x180269e2a`
- `WDSCORE!CurrentIP` at `0x180269f12`
- `WDSCORE!CurrentIP` at `0x180269ff1`
- `WDSCORE!CurrentIP` at `0x18026a3b0`
- `WDSCORE!CurrentIP` at `0x18026a417`
- `WDSCORE!CurrentIP` at `0x18026a47c`
- `WDSCORE!CurrentIP` at `0x18026a52f`

## string_xrefs

- `0x180269be3`: `SetupPlatform.exe /rollbackonlineuser`
- `0x18026a1ff`: `ScenarioComplete`
- `0x180269d87`: `SP_ROLLBACK_INFO`
- `0x180269fa6`: `SP_ROLLBACK_INFO`
- `0x180269fda`: `SP_ROLLBACK_INFO`
- `0x180269bb0`: `base\ntsetup\setupplatform\lib\private\rollback.cpp`
- `0x180269d2c`: `base\ntsetup\setupplatform\lib\private\rollback.cpp`
- `0x180269e76`: `base\ntsetup\setupplatform\lib\private\rollback.cpp`
- `0x180269f55`: `base\ntsetup\setupplatform\lib\private\rollback.cpp`
- `0x18026a031`: `base\ntsetup\setupplatform\lib\private\rollback.cpp`
- `0x18026a3e9`: `base\ntsetup\setupplatform\lib\private\rollback.cpp`
- `0x18026a4b5`: `base\ntsetup\setupplatform\lib\private\rollback.cpp`
- `0x180269d80`: `RollbackBeginTime`
- `0x180269f1e`: `Rollback: Executing Sync commands: Failure while executing commands. hr = 0x%08X`
- `0x180269f9f`: `RollbackEndTime`
- `0x180269ffa`: `Attempting to stop the telemetry`
- `0x180269fd3`: `RollbackFailureCode`
- `0x180269c89`: `CSetupPlatformPrivate::RollbackOnlineUsr: Failed to register RollbackOnline for user. Error: 0x%08X`
- `0x180269b80`: `CSetupPlatformPrivate::RollbackOnlineUsr: Downlevel OS still hasn't rebooted. Re-register Rollback-Online and Exit.`
- `0x180269e3f`: `Will remove scratch directory: %s`
- `0x180269cfc`: `Rollback-Online-User started.`
- `0x180269b79`: `CSetupPlatformPrivate::RollbackOnlineUsr`
- `0x180269ba4`: `CSetupPlatformPrivate::RollbackOnlineUsr`
- `0x180269d20`: `CSetupPlatformPrivate::RollbackOnlineUsr`
- `0x180269e6a`: `CSetupPlatformPrivate::RollbackOnlineUsr`
- `0x180269f49`: `CSetupPlatformPrivate::RollbackOnlineUsr`
- `0x18026a025`: `CSetupPlatformPrivate::RollbackOnlineUsr`
- `0x18026a57f`: `Rollback-Online-User completed with error: 0x%08X`
- `0x18026a420`: `Rollback: Not upload Diagnostics on success`
- `0x18026a3b9`: `Rollback: Scenario completes, this is not failure`
- `0x18026a542`: `Rollback-Online-User completed successfully.`
- `0x18026a485`: `Rollback-Online-User submitting watson report synchronously`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall CSetupPlatformPrivate::RollbackOnlineUsr(
        CSetupPlatformPrivate *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  CSetupPlatformPrivate *v4; // rsi
  int v5; // r14d
  DWORD v6; // edi
  __int64 v7; // rbx
  struct tagLOG_PARTIAL_MSG *v8; // rax
  const struct UnBCL::String *v9; // rbx
  const struct UnBCL::String *v10; // rax
  struct UnBCL::String *v11; // rax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, const unsigned __int16 *); // rbx
  UnBCL::String *v14; // rax
  const unsigned __int16 *v15; // rax
  int v16; // r15d
  DWORD v17; // edi
  __int64 v18; // rbx
  struct tagLOG_PARTIAL_MSG *v19; // rax
  void ***v20; // rcx
  DWORD LastError; // edi
  __int64 v22; // rbx
  struct tagLOG_PARTIAL_MSG *v23; // rax
  __int64 v24; // rax
  const struct UnBCL::String *v25; // rbx
  const struct UnBCL::String *P; // rax
  struct UnBCL::String *v27; // rax
  UnBCL::String *v28; // rax
  const unsigned __int16 *CString; // rax
  void *v30; // rdx
  struct SetupPlatform::IGenericProgress *v31; // r8
  __int64 v32; // rcx
  UnBCL::String *v33; // rsi
  DWORD v34; // edi
  __int64 v35; // rbx
  const char *v36; // rax
  struct tagLOG_PARTIAL_MSG *v37; // rax
  int v38; // edx
  int v39; // r9d
  UnBCL::String *v40; // rax
  const WCHAR *v41; // rax
  signed int v42; // eax
  bool v43; // sf
  signed int v44; // eax
  unsigned int v45; // esi
  DWORD v46; // edi
  __int64 v47; // rbx
  struct tagLOG_PARTIAL_MSG *v48; // rax
  HKEY v49; // rbx
  __int64 v50; // rax
  __int64 v51; // rax
  DWORD v52; // edi
  __int64 v53; // rbx
  struct tagLOG_PARTIAL_MSG *v54; // rax
  char *v55; // rdi
  struct UnBCL::String *v56; // rax
  const struct UnBCL::String *v57; // rbx
  const struct UnBCL::String *v58; // rax
  struct UnBCL::String *v59; // rax
  struct UnBCL::String **v60; // rbx
  struct UnBCL::String *v61; // rax
  struct UnBCL::String *v62; // rdi
  struct UnBCL::String *v63; // rbx
  struct UnBCL::String *v64; // rax
  unsigned int v65; // r8d
  int v66; // r9d
  UnBCL::String *v67; // rax
  const WCHAR *v68; // rax
  struct UnBCL::String *v69; // rax
  UnBCL::String *v70; // rax
  const WCHAR *v71; // rax
  struct UnBCL::String *v72; // rax
  BOOL v73; // edi
  const struct UnBCL::String *v74; // rbx
  const struct UnBCL::String *v75; // rax
  const struct UnBCL::String *v76; // rbx
  const struct UnBCL::String *v77; // rax
  BOOL v78; // ebx
  const struct UnBCL::String *v79; // rbx
  int v80; // r14d
  const struct UnBCL::String *v81; // rax
  const struct UnBCL::String *v82; // rbx
  const struct UnBCL::String *v83; // rax
  DWORD v84; // edi
  __int64 v85; // rbx
  struct tagLOG_PARTIAL_MSG *v86; // rax
  DWORD v87; // edi
  __int64 v88; // rbx
  struct tagLOG_PARTIAL_MSG *v89; // rax
  DWORD v90; // edi
  __int64 v91; // rbx
  struct tagLOG_PARTIAL_MSG *v92; // rax
  struct UnBCL::String *v93; // rbx
  struct UnBCL::String *v94; // rdx
  int v95; // r9d
  DWORD v96; // edi
  __int64 v97; // rbx
  struct tagLOG_PARTIAL_MSG *v98; // rax
  struct tagLOG_PARTIAL_MSG *v99; // rax
  void **v101; // [rsp+68h] [rbp-A0h] BYREF
  void (__fastcall ***v102)(_QWORD, __int64); // [rsp+70h] [rbp-98h]
  _BYTE v103[24]; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v104[24]; // [rsp+90h] [rbp-78h] BYREF
  _BYTE v105[16]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v106[16]; // [rsp+B8h] [rbp-50h] BYREF
  struct CDiagnosticsHelper *v107; // [rsp+C8h] [rbp-40h]
  _BYTE v108[24]; // [rsp+D0h] [rbp-38h] BYREF
  _BYTE v109[16]; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v110; // [rsp+F8h] [rbp-10h]
  char *v113; // [rsp+168h] [rbp+60h]
  HKEY hKey; // [rsp+170h] [rbp+68h] BYREF

  v110 = -2;
  v4 = this;
  v5 = 0;
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup\\SetupPlatform\\DownlevelActive", 0, 0x20019u, &hKey) || !hKey )
  {
    SetLastError(0);
    LastError = GetLastError();
    v22 = CurrentIP();
    v23 = ConstructPartialMsgW(0x4000000u, "Rollback-Online-User started.");
    WdsSetupLogMessageW(
      v23,
      819200,
      L"D",
      0,
      1463,
      L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
      L"CSetupPlatformPrivate::RollbackOnlineUsr",
      v22,
      LastError,
      0,
      0);
    hKey = (HKEY)((char *)v4 + 192);
    v24 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v4 + 24) + 8LL))((__int64)v4 + 192);
    (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)v24 + 32LL))(
      v24,
      L"SP_ROLLBACK_INFO",
      L"RollbackBeginTime");
    v16 = CSetupPlatformPrivate::RollbackOnlineCommon(v4);
    v25 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v103, L"$WINDOWS.~BT");
    P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v4 + 224);
    v27 = UnBCL::Path::Combine(P, v25);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v109, v27);
    UnBCL::String::~String((UnBCL::String *)v103);
    v28 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v109);
    CString = UnBCL::String::get_CString(v28);
    SPCleanupAfterRollback(CString, v30, v31);
    v32 = *((_QWORD *)v4 + 37);
    if ( v32 )
    {
      v33 = (UnBCL::String *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      v34 = GetLastError();
      v35 = CurrentIP();
      v36 = (const char *)UnBCL::String::get_CString(v33);
      v37 = ConstructPartialMsgW(0x4000000u, "Will remove scratch directory: %s", v36);
      WdsSetupLogMessageW(
        v37,
        819200,
        L"D",
        0,
        1480,
        L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
        L"CSetupPlatformPrivate::RollbackOnlineUsr",
        v35,
        v34,
        0,
        0);
      SPDeleteFolder(v33, v38, 0, v39);
      v4 = this;
    }
    v113 = (char *)v4 + 24;
    v40 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)v4 + 24);
    v41 = UnBCL::String::get_CString(v40);
    if ( !(unsigned int)SPExecuteSyncCommands(v41, 0xAu) )
    {
      v42 = GetLastError();
      v43 = v42 < 0;
      if ( v42 > 0 )
        v43 = 1;
      if ( v43 )
      {
        v44 = GetLastError();
        v45 = v44;
        if ( v44 > 0 )
          v45 = (unsigned __int16)v44 | 0x80070000;
      }
      else
      {
        v45 = -2147467259;
      }
      v46 = GetLastError();
      v47 = CurrentIP();
      v48 = ConstructPartialMsgW(
              0x2000000u,
              "Rollback: Executing Sync commands: Failure while executing commands. hr = 0x%08X",
              v45);
      WdsSetupLogMessageW(
        v48,
        819200,
        L"D",
        0,
        1488,
        L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
        L"CSetupPlatformPrivate::RollbackOnlineUsr",
        v47,
        v46,
        0,
        0);
      if ( v16 >= 0 )
        v16 = v45;
    }
    v49 = hKey;
    v50 = (*(__int64 (__fastcall **)(HKEY))(*(_QWORD *)hKey + 8LL))(hKey);
    (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)v50 + 40LL))(
      v50,
      L"SP_ROLLBACK_INFO",
      L"RollbackEndTime");
    if ( v16 < 0 )
    {
      v51 = (*(__int64 (__fastcall **)(HKEY))(*(_QWORD *)v49 + 8LL))(v49);
      (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, _QWORD))(*(_QWORD *)v51 + 24LL))(
        v51,
        L"SP_ROLLBACK_INFO",
        L"RollbackFailureCode",
        (unsigned int)v16);
    }
    v52 = GetLastError();
    v53 = CurrentIP();
    v54 = ConstructPartialMsgW(0x4000000u, "Attempting to stop the telemetry");
    WdsSetupLogMessageW(
      v54,
      819200,
      L"D",
      0,
      1504,
      L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
      L"CSetupPlatformPrivate::RollbackOnlineUsr",
      v53,
      v52,
      0,
      0);
    CSetupPlatformPrivate::StopTelemetry(this);
    LODWORD(hKey) = 0;
    v55 = (char *)this + 208;
    v56 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 208);
    SPDiagTrackGetUploadBasedOnEnvVar(v56, (int *)&hKey);
    v107 = (CSetupPlatformPrivate *)((char *)this + 40);
    if ( *((_DWORD *)this + 14) || (_DWORD)hKey )
    {
      v102 = 0;
      v101 = &Mig::CAutoDelete<UnBCL::String *>::`vftable';
      v57 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v104, L"Panther");
      v58 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v55);
      v59 = UnBCL::Path::Combine(v58, v57);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v108, v59);
      UnBCL::String::~String((UnBCL::String *)v104);
      v60 = (struct UnBCL::String **)((__int64 (__fastcall *)(void ***))Mig::CAutoDelete<UnBCL::String *>::`vftable')(&v101);
      v61 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v55);
      SPDiagTrackGetCorrelationVector(v61, v60);
      SetEnvironmentVariableW(L"SP_ALWAYS_RESTART_DIAGTRACK", L"1");
      v62 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v55);
      v63 = (struct UnBCL::String *)((__int64 (__fastcall *)(void ***))v101[3])(&v101);
      v64 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v108);
      SPUploadTelemetryData(v64, 1, v65, v66, v63, v62, 0);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v108);
      v101 = &Mig::CAutoDelete<UnBCL::String *>::`vftable';
      if ( v102 )
        (**v102)(v102, 1);
    }
    v67 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v113);
    v68 = UnBCL::String::get_CString(v67);
    v69 = SPReadConfigValue(L"Parameters", L"NoDiagnosticsUploadOnSuccess", v68);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v106, v69);
    v70 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)this + 400);
    v71 = UnBCL::String::get_CString(v70);
    v72 = SPReadConfigValue(L"Flow", L"ScenarioComplete", v71);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v105, v72);
    if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v106) )
    {
      v74 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v103, L"TRUE");
      v5 = 1;
      LODWORD(hKey) = 1;
      v75 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v106);
      v73 = 1;
      if ( UnBCL::String::Compare(v75, v74, 0) )
      {
        v76 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v104, L"Yes");
        v5 = 3;
        LODWORD(hKey) = 3;
        v77 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v106);
        if ( UnBCL::String::Compare(v77, v76, 0) )
          v73 = 0;
      }
      if ( (v5 & 2) != 0 )
      {
        v5 &= ~2u;
        UnBCL::String::~String((UnBCL::String *)v104);
      }
      if ( (v5 & 1) != 0 )
      {
        v5 &= ~1u;
        UnBCL::String::~String((UnBCL::String *)v103);
      }
    }
    else
    {
      v73 = 0;
    }
    if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v105) )
    {
      v79 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v103, L"TRUE");
      v80 = v5 | 4;
      LODWORD(hKey) = v80;
      v81 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v105);
      v78 = 1;
      if ( UnBCL::String::Compare(v81, v79, 0) )
      {
        v82 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v104, L"Yes");
        v80 |= 8u;
        LODWORD(hKey) = v80;
        v83 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v105);
        if ( UnBCL::String::Compare(v83, v82, 0) )
          v78 = 0;
      }
      if ( (v80 & 8) != 0 )
      {
        LOBYTE(v80) = v80 & 0xF7;
        UnBCL::String::~String((UnBCL::String *)v104);
      }
      if ( (v80 & 4) != 0 )
        UnBCL::String::~String((UnBCL::String *)v103);
    }
    else
    {
      v78 = 0;
    }
    if ( v73 && v78 )
    {
      v84 = GetLastError();
      v85 = CurrentIP();
      v86 = ConstructPartialMsgW(0x4000000u, "Rollback: Scenario completes, this is not failure");
      WdsSetupLogMessageW(
        v86,
        819200,
        L"D",
        0,
        1542,
        L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
        L"CSetupPlatformPrivate::RollbackOnlineUsr",
        v85,
        v84,
        0,
        0);
      v87 = GetLastError();
      v88 = CurrentIP();
      v89 = ConstructPartialMsgW(0x4000000u, "Rollback: Not upload Diagnostics on success");
      WdsSetupLogMessageW(
        v89,
        819200,
        L"D",
        0,
        1543,
        L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
        L"CSetupPlatformPrivate::RollbackOnlineUsr",
        v88,
        v87,
        0,
        0);
    }
    else
    {
      v90 = GetLastError();
      v91 = CurrentIP();
      v92 = ConstructPartialMsgW(0x4000000u, "Rollback-Online-User submitting watson report synchronously");
      WdsSetupLogMessageW(
        v92,
        819200,
        L"D",
        0,
        1549,
        L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
        L"CSetupPlatformPrivate::RollbackOnlineUsr",
        v91,
        v90,
        0,
        0);
      v93 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v103, a2);
      UnBCL::String::String((UnBCL::String *)v104, a2);
      SPUploadDiagnosticsData(v107, v94, v93, v95, 1);
      UnBCL::String::~String((UnBCL::String *)v104);
      UnBCL::String::~String((UnBCL::String *)v103);
    }
    v96 = GetLastError();
    v97 = CurrentIP();
    if ( v16 < 0 )
    {
      v99 = ConstructPartialMsgW(0x4000000u, "Rollback-Online-User completed with error: 0x%08X", v16);
      WdsSetupLogMessageW(
        v99,
        819200,
        L"D",
        0,
        1559,
        L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
        L"CSetupPlatformPrivate::RollbackOnlineUsr",
        v97,
        v96,
        0,
        0);
    }
    else
    {
      v98 = ConstructPartialMsgW(0x4000000u, "Rollback-Online-User completed successfully.");
      WdsSetupLogMessageW(
        v98,
        819200,
        L"D",
        0,
        1555,
        L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
        L"CSetupPlatformPrivate::RollbackOnlineUsr",
        v97,
        v96,
        0,
        0);
    }
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v105);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v106);
    v20 = (void ***)v109;
  }
  else
  {
    RegCloseKey(hKey);
    SetLastError(0);
    v6 = GetLastError();
    v7 = CurrentIP();
    v8 = ConstructPartialMsgW(
           0x4000000u,
           "CSetupPlatformPrivate::RollbackOnlineUsr: Downlevel OS still hasn't rebooted. Re-register Rollback-Online and Exit.",
           "CSetupPlatformPrivate::RollbackOnlineUsr");
    WdsSetupLogMessageW(
      v8,
      819200,
      L"D",
      0,
      1452,
      L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
      L"CSetupPlatformPrivate::RollbackOnlineUsr",
      v7,
      v6,
      0,
      0);
    v9 = (const struct UnBCL::String *)UnBCL::String::String(
                                         (UnBCL::String *)v108,
                                         L"SetupPlatform.exe /rollbackonlineuser");
    v10 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 208);
    v11 = UnBCL::Path::Combine(v10, v9);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v101, v11);
    UnBCL::String::~String((UnBCL::String *)v108);
    v12 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 8LL))((char *)this + 176);
    v13 = *(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *))(*(_QWORD *)v12 + 32LL);
    v14 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v101);
    v15 = UnBCL::String::get_CString(v14);
    v16 = v13(v12, 0, v15);
    if ( v16 < 0 )
    {
      v17 = GetLastError();
      v18 = CurrentIP();
      v19 = ConstructPartialMsgW(
              0x2000000u,
              "CSetupPlatformPrivate::RollbackOnlineUsr: Failed to register RollbackOnline for user. Error: 0x%08X",
              v16);
      WdsSetupLogMessageW(
        v19,
        819200,
        L"D",
        0,
        1458,
        L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
        L"CSetupPlatformPrivate::RollbackOnlineUsr",
        v18,
        v17,
        0,
        0);
    }
    v20 = &v101;
  }
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v20);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180269adc  mov     rax, rsp
0x180269adf  mov     [rax+20h], r9
0x180269ae3  mov     [rax+18h], r8
0x180269ae7  mov     [rax+10h], rdx
0x180269aeb  mov     [rax+8], rcx
0x180269aef  push    rbp
0x180269af0  push    rbx
0x180269af1  push    rsi
0x180269af2  push    rdi
0x180269af3  push    r12
0x180269af5  push    r13
0x180269af7  push    r14
0x180269af9  push    r15
0x180269afb  lea     rbp, [rax-48h]
0x180269aff  sub     rsp, 108h
0x180269b06  mov     [rbp+40h+var_50], 0FFFFFFFFFFFFFFFEh
0x180269b0e  mov     rsi, rcx
0x180269b11  xor     r15d, r15d
0x180269b14  mov     r14d, r15d
0x180269b17  mov     dword ptr [rbp+40h+hKey], r15d
0x180269b1b  mov     [rbp+40h+hKey], r15
0x180269b1f  lea     rax, [rbp+40h+hKey]
0x180269b23  mov     [rsp+140h+phkResult], rax; phkResult
0x180269b28  mov     r9d, 20019h; samDesired
0x180269b2e  xor     r8d, r8d; ulOptions
0x180269b31  lea     rdx, aSystemSetupSet_1; "SYSTEM\\Setup\\SetupPlatform\\Downlevel"...
0x180269b38  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180269b3f  call    cs:__imp_RegOpenKeyExW
0x180269b45  test    eax, eax
0x180269b47  jnz     loc_180269CE3
0x180269b4d  mov     rcx, [rbp+40h+hKey]; hKey
0x180269b51  test    rcx, rcx
0x180269b54  jz      loc_180269CE3
0x180269b5a  call    cs:__imp_RegCloseKey
0x180269b60  xor     ecx, ecx; dwErrCode
0x180269b62  call    cs:__imp_SetLastError
0x180269b68  call    cs:__imp_GetLastError
0x180269b6e  mov     edi, eax
0x180269b70  call    cs:__imp_CurrentIP
0x180269b76  mov     rbx, rax
0x180269b79  lea     r8, aCsetupplatform_152; "CSetupPlatformPrivate::RollbackOnlineUs"...
0x180269b80  lea     rdx, aCsetupplatform_128; "CSetupPlatformPrivate::RollbackOnlineUs"...
0x180269b87  mov     ecx, 4000000h; unsigned int
0x180269b8c  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180269b91  mov     [rsp+50h], r15d
0x180269b96  mov     qword ptr [rsp+140h+var_F8], r15
0x180269b9b  mov     dword ptr [rsp+140h+var_100], edi
0x180269b9f  mov     qword ptr [rsp+140h+var_108], rbx
0x180269ba4  lea     rsi, aCsetupplatform_42; "CSetupPlatformPrivate::RollbackOnlineUs"...
0x180269bab  mov     [rsp+140h+var_110], rsi
0x180269bb0  lea     r14, aBaseNtsetupSet_35; "base\\ntsetup\\setupplatform\\lib\\priv"...
0x180269bb7  mov     [rsp+140h+var_118], r14
0x180269bbc  mov     dword ptr [rsp+140h+phkResult], 5ACh
0x180269bc4  xor     r9d, r9d
0x180269bc7  lea     r12, aD_0; "D"
0x180269bce  mov     r8, r12
0x180269bd1  mov     r13d, 0C8000h
0x180269bd7  mov     edx, r13d
0x180269bda  mov     rcx, rax
0x180269bdd  call    cs:__imp_WdsSetupLogMessageW
0x180269be3  lea     rdx, aSetupplatformE_8; "SetupPlatform.exe /rollbackonlineuser"
0x180269bea  lea     rcx, [rbp+40h+var_78]
0x180269bee  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180269bf4  mov     rbx, rax
0x180269bf7  mov     rdi, [rbp+40h+arg_0]
0x180269bfb  lea     rcx, [rdi+0D0h]
0x180269c02  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180269c08  mov     rdx, rbx
0x180269c0b  mov     rcx, rax
0x180269c0e  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x180269c14  mov     rdx, rax
0x180269c17  lea     rcx, [rsp+140h+var_E0]
0x180269c1c  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180269c22  nop
0x180269c23  lea     rcx, [rbp+40h+var_78]
0x180269c27  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180269c2d  lea     rcx, [rdi+0B0h]
0x180269c34  mov     rax, [rcx]
0x180269c37  mov     rax, [rax+8]
0x180269c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180269c40  mov     rdi, rax
0x180269c43  mov     rcx, [rax]
0x180269c46  mov     rbx, [rcx+20h]
0x180269c4a  lea     rcx, [rsp+140h+var_E0]
0x180269c4f  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180269c55  mov     rcx, rax
0x180269c58  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180269c5e  mov     r8, rax
0x180269c61  xor     edx, edx
0x180269c63  mov     rcx, rdi
0x180269c66  mov     rax, rbx
0x180269c69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180269c6e  mov     r15d, eax
0x180269c71  test    eax, eax
0x180269c73  jns     short loc_180269CD9
0x180269c75  call    cs:__imp_GetLastError
0x180269c7b  mov     edi, eax
0x180269c7d  call    cs:__imp_CurrentIP
0x180269c83  mov     rbx, rax
0x180269c86  mov     r8d, r15d
0x180269c89  lea     rdx, aCsetupplatform_49; "CSetupPlatformPrivate::RollbackOnlineUs"...
0x180269c90  mov     ecx, 2000000h; unsigned int
0x180269c95  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180269c9a  mov     dword ptr [rsp+50h], 0
0x180269ca2  mov     qword ptr [rsp+140h+var_F8], 0
0x180269cab  mov     dword ptr [rsp+140h+var_100], edi
0x180269caf  mov     qword ptr [rsp+140h+var_108], rbx
0x180269cb4  mov     [rsp+140h+var_110], rsi
0x180269cb9  mov     [rsp+140h+var_118], r14
0x180269cbe  mov     dword ptr [rsp+140h+phkResult], 5B2h
0x180269cc6  xor     r9d, r9d
0x180269cc9  mov     r8, r12
0x180269ccc  mov     edx, r13d
0x180269ccf  mov     rcx, rax
0x180269cd2  call    cs:__imp_WdsSetupLogMessageW
0x180269cd8  nop
0x180269cd9  lea     rcx, [rsp+140h+var_E0]
0x180269cde  jmp     loc_18026A5E4
0x180269ce3  xor     ecx, ecx; dwErrCode
0x180269ce5  call    cs:__imp_SetLastError
0x180269ceb  call    cs:__imp_GetLastError
0x180269cf1  mov     edi, eax
0x180269cf3  call    cs:__imp_CurrentIP
0x180269cf9  mov     rbx, rax
0x180269cfc  lea     rdx, aRollbackOnline_0; "Rollback-Online-User started."
0x180269d03  mov     ecx, 4000000h; unsigned int
0x180269d08  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180269d0d  mov     [rsp+50h], r15d
0x180269d12  mov     qword ptr [rsp+140h+var_F8], r15
0x180269d17  mov     dword ptr [rsp+140h+var_100], edi
0x180269d1b  mov     qword ptr [rsp+140h+var_108], rbx
0x180269d20  lea     rcx, aCsetupplatform_42; "CSetupPlatformPrivate::RollbackOnlineUs"...
0x180269d27  mov     [rsp+140h+var_110], rcx
0x180269d2c  lea     rcx, aBaseNtsetupSet_35; "base\\ntsetup\\setupplatform\\lib\\priv"...
0x180269d33  mov     [rsp+140h+var_118], rcx
0x180269d38  mov     dword ptr [rsp+140h+phkResult], 5B7h
0x180269d40  xor     r9d, r9d
0x180269d43  lea     r12, aD_0; "D"
0x180269d4a  mov     r8, r12
0x180269d4d  mov     r13d, 0C8000h
0x180269d53  mov     edx, r13d
0x180269d56  mov     rcx, rax
0x180269d59  call    cs:__imp_WdsSetupLogMessageW
0x180269d5f  lea     rcx, [rsi+0C0h]
0x180269d66  mov     [rbp+40h+hKey], rcx
0x180269d6a  mov     rax, [rcx]
0x180269d6d  mov     rax, [rax+8]
0x180269d71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180269d76  mov     r9, rax
0x180269d79  mov     rcx, [rax]
0x180269d7c  mov     rax, [rcx+20h]
0x180269d80  lea     r8, aRollbackbegint; "RollbackBeginTime"
0x180269d87  lea     rdx, aSpRollbackInfo; "SP_ROLLBACK_INFO"
0x180269d8e  mov     rcx, r9
0x180269d91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180269d96  mov     rcx, rsi; this
0x180269d99  call    ?RollbackOnlineCommon@CSetupPlatformPrivate@@IEAAJXZ; CSetupPlatformPrivate::RollbackOnlineCommon(void)
0x180269d9e  mov     r15d, eax
0x180269da1  lea     rdx, aWindowsBt_1; "$WINDOWS.~BT"
0x180269da8  lea     rcx, [rsp+70h]
0x180269dad  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180269db3  mov     rbx, rax
0x180269db6  lea     rcx, [rsi+0E0h]
0x180269dbd  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180269dc3  mov     rdx, rbx
0x180269dc6  mov     rcx, rax
0x180269dc9  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x180269dcf  mov     rdx, rax
0x180269dd2  lea     rcx, [rbp+40h+var_60]
0x180269dd6  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180269ddc  nop
0x180269ddd  lea     rcx, [rsp+70h]
0x180269de2  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180269de8  lea     rcx, [rbp+40h+var_60]
0x180269dec  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180269df2  mov     rcx, rax
0x180269df5  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180269dfb  mov     rcx, rax; unsigned __int16 *
0x180269dfe  call    ?SPCleanupAfterRollback@@YAJPEBGPEAXPEAUIGenericProgress@SetupPlatform@@@Z; SPCleanupAfterRollback(ushort const *,void *,SetupPlatform::IGenericProgress *)
0x180269e03  mov     rcx, [rsi+128h]
0x180269e0a  test    rcx, rcx
0x180269e0d  jz      loc_180269EAB
0x180269e13  mov     rax, [rcx]
0x180269e16  mov     rax, [rax+10h]
0x180269e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180269e1f  mov     rsi, rax
0x180269e22  call    cs:__imp_GetLastError
0x180269e28  mov     edi, eax
0x180269e2a  call    cs:__imp_CurrentIP
0x180269e30  mov     rbx, rax
0x180269e33  mov     rcx, rsi
0x180269e36  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180269e3c  mov     r8, rax
0x180269e3f  lea     rdx, aWillRemoveScra; "Will remove scratch directory: %s"
0x180269e46  mov     ecx, 4000000h; unsigned int
0x180269e4b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180269e50  mov     dword ptr [rsp+50h], 0
0x180269e58  mov     qword ptr [rsp+140h+var_F8], 0
0x180269e61  mov     dword ptr [rsp+140h+var_100], edi
0x180269e65  mov     qword ptr [rsp+140h+var_108], rbx
0x180269e6a  lea     rcx, aCsetupplatform_42; "CSetupPlatformPrivate::RollbackOnlineUs"...
0x180269e71  mov     [rsp+140h+var_110], rcx
0x180269e76  lea     rcx, aBaseNtsetupSet_35; "base\\ntsetup\\setupplatform\\lib\\priv"...
0x180269e7d  mov     [rsp+140h+var_118], rcx
0x180269e82  mov     dword ptr [rsp+140h+phkResult], 5C8h
0x180269e8a  xor     r9d, r9d
0x180269e8d  mov     r8, r12
0x180269e90  mov     edx, r13d
0x180269e93  mov     rcx, rax
0x180269e96  call    cs:__imp_WdsSetupLogMessageW
0x180269e9c  xor     r8d, r8d; int
0x180269e9f  mov     rcx, rsi; struct UnBCL::String *
0x180269ea2  call    ?SPDeleteFolder@@YAHPEAVString@UnBCL@@HHH@Z; SPDeleteFolder(UnBCL::String *,int,int,int)
0x180269ea7  mov     rsi, [rbp+40h+arg_0]
0x180269eab  lea     rax, [rsi+18h]
0x180269eaf  mov     [rbp+40h+arg_10], rax
0x180269eb3  mov     rcx, rax
0x180269eb6  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180269ebc  mov     rcx, rax
0x180269ebf  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180269ec5  mov     rcx, rax
0x180269ec8  mov     edx, 0Ah
0x180269ecd  call    ?SPExecuteSyncCommands@@YAHPEBGW4SYNCEXEC_PHASE@SetupPlatform@@@Z; SPExecuteSyncCommands(ushort const *,SetupPlatform::SYNCEXEC_PHASE)
0x180269ed2  test    eax, eax
0x180269ed4  jnz     loc_180269F82
0x180269eda  call    cs:__imp_GetLastError
0x180269ee0  mov     ebx, 80070000h
0x180269ee5  test    eax, eax
0x180269ee7  jle     short loc_180269EF0
0x180269ee9  movzx   eax, ax
0x180269eec  or      eax, ebx
0x180269eee  test    eax, eax
0x180269ef0  jns     short loc_180269F05
0x180269ef2  call    cs:__imp_GetLastError
0x180269ef8  mov     esi, eax
0x180269efa  test    eax, eax
0x180269efc  jle     short loc_180269F0A
0x180269efe  movzx   esi, ax
0x180269f01  or      esi, ebx
0x180269f03  jmp     short loc_180269F0A
0x180269f05  mov     esi, 80004005h
0x180269f0a  call    cs:__imp_GetLastError
0x180269f10  mov     edi, eax
0x180269f12  call    cs:__imp_CurrentIP
0x180269f18  mov     rbx, rax
0x180269f1b  mov     r8d, esi
0x180269f1e  lea     rdx, aRollbackExecut; "Rollback: Executing Sync commands: Fail"...
0x180269f25  mov     ecx, 2000000h; unsigned int
0x180269f2a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180269f2f  mov     dword ptr [rsp+50h], 0
0x180269f37  mov     qword ptr [rsp+140h+var_F8], 0
0x180269f40  mov     dword ptr [rsp+140h+var_100], edi
0x180269f44  mov     qword ptr [rsp+140h+var_108], rbx
0x180269f49  lea     rcx, aCsetupplatform_42; "CSetupPlatformPrivate::RollbackOnlineUs"...
0x180269f50  mov     [rsp+140h+var_110], rcx
0x180269f55  lea     rcx, aBaseNtsetupSet_35; "base\\ntsetup\\setupplatform\\lib\\priv"...
0x180269f5c  mov     [rsp+140h+var_118], rcx
0x180269f61  mov     dword ptr [rsp+140h+phkResult], 5D0h
0x180269f69  xor     r9d, r9d
0x180269f6c  mov     r8, r12
0x180269f6f  mov     edx, r13d
0x180269f72  mov     rcx, rax
0x180269f75  call    cs:__imp_WdsSetupLogMessageW
0x180269f7b  test    r15d, r15d
0x180269f7e  cmovns  r15d, esi
0x180269f82  mov     rbx, [rbp+40h+hKey]
0x180269f86  mov     rax, [rbx]
0x180269f89  mov     rcx, rbx
0x180269f8c  mov     rax, [rax+8]
0x180269f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180269f95  mov     rcx, rax
0x180269f98  mov     rdx, [rax]
0x180269f9b  mov     rax, [rdx+28h]
0x180269f9f  lea     r8, aRollbackendtim; "RollbackEndTime"
0x180269fa6  lea     rdx, aSpRollbackInfo; "SP_ROLLBACK_INFO"
0x180269fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180269fb2  test    r15d, r15d
0x180269fb5  jns     short loc_180269FE9
0x180269fb7  mov     rax, [rbx]
0x180269fba  mov     rcx, rbx
0x180269fbd  mov     rax, [rax+8]
0x180269fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180269fc6  mov     r10, rax
0x180269fc9  mov     rcx, [rax]
0x180269fcc  mov     rax, [rcx+18h]
0x180269fd0  mov     r9d, r15d
0x180269fd3  lea     r8, aRollbackfailur; "RollbackFailureCode"
0x180269fda  lea     rdx, aSpRollbackInfo; "SP_ROLLBACK_INFO"
0x180269fe1  mov     rcx, r10
0x180269fe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180269fe9  call    cs:__imp_GetLastError
0x180269fef  mov     edi, eax
0x180269ff1  call    cs:__imp_CurrentIP
0x180269ff7  mov     rbx, rax
0x180269ffa  lea     rdx, aAttemptingToSt; "Attempting to stop the telemetry"
0x18026a001  mov     ecx, 4000000h; unsigned int
0x18026a006  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18026a00b  mov     dword ptr [rsp+50h], 0
0x18026a013  mov     qword ptr [rsp+140h+var_F8], 0
0x18026a01c  mov     dword ptr [rsp+140h+var_100], edi
  ... truncated ...
```
