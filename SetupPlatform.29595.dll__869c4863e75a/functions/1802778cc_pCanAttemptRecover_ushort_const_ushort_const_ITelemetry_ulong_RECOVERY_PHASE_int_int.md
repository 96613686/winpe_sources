# pCanAttemptRecover(ushort const *,ushort const *,ITelemetry *,ulong *,RECOVERY_PHASE *,int *,int *)

- ea: `0x1802778cc`
- end: `0x1802787cc`
- name: `?pCanAttemptRecover@@YAHPEBG0PEAUITelemetry@@PEAKPEAW4RECOVERY_PHASE@@PEAH4@Z`
- size: `3840`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, struct ITelemetry *, unsigned int *, enum RECOVERY_PHASE *, int *, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1802724e8`

## callees

- `0x180057dec`
- `0x1802778cc`
- `0x18027b12c`
- `0x18027b3e4`
- `0x1802e2078`
- `0x18035219c`
- `0x180352658`
- `0x180352abc`
- `0x180352cc0`
- `0x18035734c`
- `0x180357748`
- `0x180509010`

## import_xrefs

- `msvcrt!_wcstoui64` at `0x180278315`
- `msvcrt!_wcstoui64` at `0x180278315`
- `ADVAPI32!RegCloseKey` at `0x1802786cd`
- `ADVAPI32!RegCloseKey` at `0x180278757`
- `ADVAPI32!RegCloseKey` at `0x1802786cd`
- `ADVAPI32!RegCloseKey` at `0x180278757`
- `ADVAPI32!RegCreateKeyExW` at `0x18027844e`
- `ADVAPI32!RegCreateKeyExW` at `0x18027844e`
- `ADVAPI32!RegQueryValueExW` at `0x180278493`
- `ADVAPI32!RegQueryValueExW` at `0x180278553`
- `ADVAPI32!RegQueryValueExW` at `0x180278493`
- `ADVAPI32!RegQueryValueExW` at `0x180278553`
- `KERNEL32!GetLastError` at `0x180277a93`
- `KERNEL32!GetLastError` at `0x180277b35`
- `KERNEL32!GetLastError` at `0x180277bca`
- `KERNEL32!GetLastError` at `0x180277c5f`
- `KERNEL32!GetLastError` at `0x180277cf4`
- `KERNEL32!GetLastError` at `0x180277de0`
- `KERNEL32!GetLastError` at `0x180277ef6`
- `KERNEL32!GetLastError` at `0x180277f6c`
- `KERNEL32!GetLastError` at `0x180278034`
- `KERNEL32!GetLastError` at `0x1802780f7`
- `KERNEL32!GetLastError` at `0x18027839a`
- `KERNEL32!GetLastError` at `0x1802783ab`
- `KERNEL32!GetLastError` at `0x1802784b1`
- `KERNEL32!GetLastError` at `0x180278571`
- `KERNEL32!GetLastError` at `0x1802785de`
- `KERNEL32!GetLastError` at `0x18027864d`
- `KERNEL32!GetLastError` at `0x1802786dd`
- `KERNEL32!GetLastError` at `0x180277a93`
- `KERNEL32!GetLastError` at `0x180277b35`
- `KERNEL32!GetLastError` at `0x180277bca`
- `KERNEL32!GetLastError` at `0x180277c5f`
- `KERNEL32!GetLastError` at `0x180277cf4`
- `KERNEL32!GetLastError` at `0x180277de0`
- `KERNEL32!GetLastError` at `0x180277ef6`
- `KERNEL32!GetLastError` at `0x180277f6c`
- `KERNEL32!GetLastError` at `0x180278034`
- `KERNEL32!GetLastError` at `0x1802780f7`
- `KERNEL32!GetLastError` at `0x18027839a`
- `KERNEL32!GetLastError` at `0x1802783ab`
- `KERNEL32!GetLastError` at `0x1802784b1`
- `KERNEL32!GetLastError` at `0x180278571`
- `KERNEL32!GetLastError` at `0x1802785de`
- `KERNEL32!GetLastError` at `0x18027864d`
- `KERNEL32!GetLastError` at `0x1802786dd`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18027795c`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18027795c`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x180277dc4`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x180277dc4`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180277aa8`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180277b4a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180277bdf`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180277c74`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180277d09`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180277db2`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180277e7c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180277e89`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180277e96`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180277ea3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802782ee`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180277aa8`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180277b4a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180277bdf`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180277c74`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180277d09`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180277db2`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180277e7c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180277e89`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180277e96`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180277ea3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802782ee`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180277974`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18027797f`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180277dda`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18027835b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180277974`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18027797f`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180277dda`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18027835b`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18027793f`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18027794f`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180277da5`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18027833f`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18027793f`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18027794f`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180277da5`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18027833f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180277989`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802779c3`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802779f6`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180277a29`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180277a60`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180277abe`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180277b59`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180277bee`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180277c83`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180277d18`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802782b7`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802782fd`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180277989`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802779c3`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802779f6`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180277a29`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180277a60`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180277abe`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180277b59`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180277bee`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180277c83`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180277d18`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802782b7`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802782fd`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180277992`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802779cc`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802779ff`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180277a32`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180277a69`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180277ac7`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180277b62`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180277bf7`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180277c8c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180277d21`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802782c0`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180278306`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180277992`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802779cc`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802779ff`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180277a32`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180277a69`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180277ac7`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180277b62`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180277bf7`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180277c8c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180277d21`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802782c0`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180278306`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180278331`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18027876e`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180278779`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180278784`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18027878f`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18027879a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802787a5`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180278331`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18027876e`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180278779`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180278784`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18027878f`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18027879a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802787a5`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180277969`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802779b8`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802779eb`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180277a1e`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180277a55`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180277a8c`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802782e3`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180277969`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802779b8`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802779eb`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180277a1e`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180277a55`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180277a8c`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802782e3`
- `WDSCORE!WdsSetupLogMessageW` at `0x180277b2f`
- `WDSCORE!WdsSetupLogMessageW` at `0x180277bc4`
- `WDSCORE!WdsSetupLogMessageW` at `0x180277c59`
- `WDSCORE!WdsSetupLogMessageW` at `0x180277cee`
- `WDSCORE!WdsSetupLogMessageW` at `0x180277d81`
- `WDSCORE!WdsSetupLogMessageW` at `0x180277e59`
- `WDSCORE!WdsSetupLogMessageW` at `0x180277f66`
- `WDSCORE!WdsSetupLogMessageW` at `0x180277fda`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802780e5`
- `WDSCORE!WdsSetupLogMessageW` at `0x180278168`
- `WDSCORE!WdsSetupLogMessageW` at `0x18027840a`
- `WDSCORE!WdsSetupLogMessageW` at `0x180278645`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802786bb`
- `WDSCORE!WdsSetupLogMessageW` at `0x18027874e`
- `WDSCORE!WdsSetupLogMessageW` at `0x180277b2f`
- `WDSCORE!WdsSetupLogMessageW` at `0x180277bc4`
- `WDSCORE!WdsSetupLogMessageW` at `0x180277c59`
- `WDSCORE!WdsSetupLogMessageW` at `0x180277cee`
- `WDSCORE!WdsSetupLogMessageW` at `0x180277d81`
- `WDSCORE!WdsSetupLogMessageW` at `0x180277e59`
- `WDSCORE!WdsSetupLogMessageW` at `0x180277f66`
- `WDSCORE!WdsSetupLogMessageW` at `0x180277fda`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802780e5`
- `WDSCORE!WdsSetupLogMessageW` at `0x180278168`
- `WDSCORE!WdsSetupLogMessageW` at `0x18027840a`
- `WDSCORE!WdsSetupLogMessageW` at `0x180278645`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802786bb`
- `WDSCORE!WdsSetupLogMessageW` at `0x18027874e`
- `WDSCORE!CurrentIP` at `0x180277a9b`
- `WDSCORE!CurrentIP` at `0x180277b3d`
- `WDSCORE!CurrentIP` at `0x180277bd2`
- `WDSCORE!CurrentIP` at `0x180277c67`
- `WDSCORE!CurrentIP` at `0x180277cfc`
- `WDSCORE!CurrentIP` at `0x180277de8`
- `WDSCORE!CurrentIP` at `0x180277efe`
- `WDSCORE!CurrentIP` at `0x180277f74`

## string_xrefs

- `0x180277934`: `rollbackinfo.ini`
- `0x18027821c`: `Setup\Status\ChildCompletion`
- `0x180278444`: `Setup\Status\ChildCompletion`
- `0x1802786f1`: `Setup\Status\ChildCompletion`
- `0x180277afd`: `pCanAttemptRecover`
- `0x180277b92`: `pCanAttemptRecover`
- `0x180277c27`: `pCanAttemptRecover`
- `0x180277cbc`: `pCanAttemptRecover`
- `0x180277d4f`: `pCanAttemptRecover`
- `0x180277e27`: `pCanAttemptRecover`
- `0x180277f34`: `pCanAttemptRecover`
- `0x180277fa8`: `pCanAttemptRecover`
- `0x180278073`: `pCanAttemptRecover`
- `0x1802780b3`: `pCanAttemptRecover`
- `0x180278136`: `pCanAttemptRecover`
- `0x1802783d8`: `pCanAttemptRecover`
- `0x1802784e6`: `pCanAttemptRecover`
- `0x1802785a6`: `pCanAttemptRecover`
- `0x180278613`: `pCanAttemptRecover`
- `0x180278689`: `pCanAttemptRecover`
- `0x18027871c`: `pCanAttemptRecover`
- `0x180278665`: `Past recovery phase %d does not match current phase %d. Resetting recovery attempts`
- `0x1802785ef`: `Maximum recovery attempts reached.`
- `0x180278547`: `RecoveryAttempts`
- `0x1802784c2`: `Cannot read the recovery phase.`
- `0x180278582`: `Cannot read the number of recovery attempts made so far.`
- `0x1802786f8`: `Cannot open HKLM\SYSTEM\%s. Error: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall pCanAttemptRecover(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct ITelemetry *a3,
        unsigned int *a4,
        enum RECOVERY_PHASE *a5,
        int *a6,
        int *a7)
{
  enum RECOVERY_PHASE *v9; // r14
  const struct UnBCL::String *v10; // rbx
  const struct UnBCL::String *v11; // rax
  struct UnBCL::String *v12; // rax
  UnBCL::String *v13; // rax
  const WCHAR *CString; // rax
  struct UnBCL::String *v15; // rax
  UnBCL::String *v16; // rax
  const WCHAR *v17; // rax
  struct UnBCL::String *v18; // rax
  UnBCL::String *v19; // rax
  const WCHAR *v20; // rax
  struct UnBCL::String *v21; // rax
  UnBCL::String *v22; // rax
  const WCHAR *v23; // rax
  struct UnBCL::String *v24; // rax
  UnBCL::String *v25; // rax
  const WCHAR *v26; // rax
  struct UnBCL::String *v27; // rax
  DWORD LastError; // edi
  __int64 v29; // rsi
  const wchar_t *v30; // rbx
  UnBCL::String *v31; // rax
  const wchar_t *v32; // rax
  struct tagLOG_PARTIAL_MSG *v33; // rax
  DWORD v34; // edi
  __int64 v35; // rsi
  UnBCL::String *v36; // rax
  const wchar_t *v37; // rax
  struct tagLOG_PARTIAL_MSG *v38; // rax
  DWORD v39; // edi
  __int64 v40; // rsi
  UnBCL::String *v41; // rax
  const wchar_t *v42; // rax
  struct tagLOG_PARTIAL_MSG *v43; // rax
  DWORD v44; // edi
  __int64 v45; // rsi
  UnBCL::String *v46; // rax
  const wchar_t *v47; // rax
  struct tagLOG_PARTIAL_MSG *v48; // rax
  DWORD v49; // edi
  __int64 v50; // rsi
  UnBCL::String *v51; // rax
  struct tagLOG_PARTIAL_MSG *v52; // rax
  int *v53; // r12
  const unsigned __int16 *v54; // rsi
  const struct UnBCL::String *v55; // rbx
  const struct UnBCL::String *P; // rax
  DWORD v57; // edi
  __int64 v58; // rbx
  struct tagLOG_PARTIAL_MSG *v59; // rax
  struct UnBCL::String *v60; // rsi
  struct UnBCL::String *v61; // rdi
  struct UnBCL::String *v62; // rbx
  struct UnBCL::String *v63; // rax
  __int64 v64; // rbx
  unsigned int v65; // r13d
  struct tagLOG_PARTIAL_MSG *v66; // rax
  __int64 v67; // rbx
  unsigned int v68; // r12d
  struct tagLOG_PARTIAL_MSG *v69; // rax
  struct ITelemetry *v70; // rbx
  __int64 v71; // rax
  __int64 v72; // rdx
  __int64 v73; // rax
  __int64 v74; // rdx
  DWORD v75; // edi
  __int64 v76; // rbx
  struct tagLOG_PARTIAL_MSG *v77; // rax
  struct tagLOG_PARTIAL_MSG *v78; // rax
  unsigned int v79; // esi
  DWORD v80; // edi
  __int64 v81; // rbx
  struct tagLOG_PARTIAL_MSG *v82; // rax
  unsigned int v83; // esi
  const unsigned __int16 *v84; // rdx
  const unsigned __int16 *v85; // r8
  const unsigned __int16 *v86; // r9
  unsigned int v87; // ebx
  UnBCL::String *v88; // rax
  const WCHAR *v89; // rax
  struct UnBCL::String *v90; // rax
  UnBCL::String *v91; // rax
  const wchar_t *v92; // rax
  unsigned __int64 v93; // rax
  __int64 v94; // rax
  HKEY v95; // r15
  DWORD v96; // edi
  __int64 v97; // rbx
  DWORD v98; // eax
  struct tagLOG_PARTIAL_MSG *v99; // rax
  LSTATUS v100; // r12d
  LSTATUS v101; // eax
  DWORD v102; // edi
  __int64 v103; // rbx
  struct tagLOG_PARTIAL_MSG *v104; // rax
  LSTATUS v105; // eax
  DWORD v106; // edi
  __int64 v107; // rbx
  struct tagLOG_PARTIAL_MSG *v108; // rax
  DWORD v109; // edi
  __int64 v110; // rbx
  struct tagLOG_PARTIAL_MSG *v111; // rax
  DWORD v112; // edi
  __int64 v113; // rbx
  struct tagLOG_PARTIAL_MSG *v114; // rax
  DWORD v115; // edi
  __int64 v116; // rbx
  struct tagLOG_PARTIAL_MSG *v117; // rax
  HKEY v118; // rcx
  DWORD Type; // [rsp+68h] [rbp-A0h] BYREF
  DWORD cbData; // [rsp+6Ch] [rbp-9Ch] BYREF
  unsigned int v122[2]; // [rsp+70h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-90h] BYREF
  int v124; // [rsp+80h] [rbp-88h] BYREF
  int v125; // [rsp+84h] [rbp-84h] BYREF
  _BYTE v126[16]; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v127[16]; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v128[16]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v129[16]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v130[16]; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v131[16]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v132[24]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v133[24]; // [rsp+100h] [rbp-8h] BYREF
  __int64 v134; // [rsp+118h] [rbp+10h]
  const unsigned __int16 *Data; // [rsp+168h] [rbp+60h] BYREF
  struct ITelemetry *v136; // [rsp+178h] [rbp+70h]
  unsigned int *v137; // [rsp+180h] [rbp+78h]

  v137 = a4;
  v136 = a3;
  Data = a1;
  v134 = -2;
  if ( a1 )
  {
    if ( a2 )
    {
      if ( a4 )
      {
        v9 = a5;
        if ( a5 )
        {
          v10 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v133, L"rollbackinfo.ini");
          v11 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v132, a1);
          v12 = UnBCL::Path::Combine(v11, v10);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v126, v12);
          UnBCL::String::~String((UnBCL::String *)v132);
          UnBCL::String::~String((UnBCL::String *)v133);
          v13 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v126);
          CString = UnBCL::String::get_CString(v13);
          v15 = SPReadConfigValue(L"Flow", L"CurrentPhase", CString);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v131, v15);
          v16 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v126);
          v17 = UnBCL::String::get_CString(v16);
          v18 = SPReadConfigValue(L"Flow", L"CurrentOperation", v17);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v130, v18);
          v19 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v126);
          v20 = UnBCL::String::get_CString(v19);
          v21 = SPReadConfigValue(L"Flow", L"OperationResult", v20);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v129, v21);
          v22 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v126);
          v23 = UnBCL::String::get_CString(v22);
          v24 = SPReadConfigValue(L"Bugcheck", L"Code", v23);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v128, v24);
          v25 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v126);
          v26 = UnBCL::String::get_CString(v25);
          v27 = SPReadConfigValue(L"OldOS", L"ConnectedStandby", v26);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v127, v27);
          LastError = GetLastError();
          v29 = CurrentIP();
          v30 = L"NULL";
          if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v131) )
          {
            v31 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v131);
            v32 = UnBCL::String::get_CString(v31);
          }
          else
          {
            v32 = L"NULL";
          }
          v33 = ConstructPartialMsgW(0x4000000u, "Current phase string : %s", (const char *)v32);
          WdsSetupLogMessageW(
            v33,
            819200,
            L"D",
            0,
            737,
            L"base\\ntsetup\\setupplatform\\lib\\private\\crashrecovery.cpp",
            L"pCanAttemptRecover",
            v29,
            LastError,
            0,
            0);
          v34 = GetLastError();
          v35 = CurrentIP();
          if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v130) )
          {
            v36 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v130);
            v37 = UnBCL::String::get_CString(v36);
          }
          else
          {
            v37 = L"NULL";
          }
          v38 = ConstructPartialMsgW(0x4000000u, "Current op string    : %s", (const char *)v37);
          WdsSetupLogMessageW(
            v38,
            819200,
            L"D",
            0,
            738,
            L"base\\ntsetup\\setupplatform\\lib\\private\\crashrecovery.cpp",
            L"pCanAttemptRecover",
            v35,
            v34,
            0,
            0);
          v39 = GetLastError();
          v40 = CurrentIP();
          if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v129) )
          {
            v41 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v129);
            v42 = UnBCL::String::get_CString(v41);
          }
          else
          {
            v42 = L"NULL";
          }
          v43 = ConstructPartialMsgW(0x4000000u, "Current result string: %s", (const char *)v42);
          WdsSetupLogMessageW(
            v43,
            819200,
            L"D",
            0,
            739,
            L"base\\ntsetup\\setupplatform\\lib\\private\\crashrecovery.cpp",
            L"pCanAttemptRecover",
            v40,
            v39,
            0,
            0);
          v44 = GetLastError();
          v45 = CurrentIP();
          if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v128) )
          {
            v46 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v128);
            v47 = UnBCL::String::get_CString(v46);
          }
          else
          {
            v47 = L"NULL";
          }
          v48 = ConstructPartialMsgW(0x4000000u, "Current bugcheck string: %s", (const char *)v47);
          WdsSetupLogMessageW(
            v48,
            819200,
            L"D",
            0,
            740,
            L"base\\ntsetup\\setupplatform\\lib\\private\\crashrecovery.cpp",
            L"pCanAttemptRecover",
            v45,
            v44,
            0,
            0);
          v49 = GetLastError();
          v50 = CurrentIP();
          if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v127) )
          {
            v51 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v127);
            v30 = UnBCL::String::get_CString(v51);
          }
          v52 = ConstructPartialMsgW(0x4000000u, "Connected standby str: %s", (const char *)v30);
          WdsSetupLogMessageW(
            v52,
            819200,
            L"D",
            0,
            741,
            L"base\\ntsetup\\setupplatform\\lib\\private\\crashrecovery.cpp",
            L"pCanAttemptRecover",
            v50,
            v49,
            0,
            0);
          v53 = a7;
          if ( a7 )
          {
            v54 = L"Yes";
            v55 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v133, L"Yes");
            P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v127);
            *v53 = UnBCL::String::Compare(P, v55, 1) == 0;
            UnBCL::String::~String((UnBCL::String *)v133);
            v57 = GetLastError();
            v58 = CurrentIP();
            if ( !*v53 )
              v54 = L"No";
            v59 = ConstructPartialMsgW(0x4000000u, "Connected standby    : %s", (const char *)v54);
            WdsSetupLogMessageW(
              v59,
              819200,
              L"D",
              0,
              745,
              L"base\\ntsetup\\setupplatform\\lib\\private\\crashrecovery.cpp",
              L"pCanAttemptRecover",
              v58,
              v57,
              0,
              0);
          }
          v124 = 0;
          v125 = 0;
          Type = 0;
          cbData = 0;
          v122[0] = 0;
          v60 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v128);
          v61 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v129);
          v62 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v130);
          v63 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v131);
          SPGetExternalPhaseAndOp(
            v63,
            v62,
            v61,
            v60,
            (enum SetupPlatform::SP_EXECUTION_PHASE *)&v124,
            (enum SetupPlatform::SP_EXECUTION_OPERATION *)&v125,
            (enum OP_OPERATION_ID *)&hKey,
            (int *)&Type,
            (int *)&cbData,
            v122);
          LODWORD(v61) = GetLastError();
          v64 = CurrentIP();
          v65 = v124;
          v66 = ConstructPartialMsgW(0x4000000u, "Current phase : %u", v124);
          WdsSetupLogMessageW(
            v66,
            819200,
            L"D",
            0,
            765,
            L"base\\ntsetup\\setupplatform\\lib\\private\\crashrecovery.cpp",
            L"pCanAttemptRecover",
            v64,
            (_DWORD)v61,
            0,
            0);
          LODWORD(v61) = GetLastError();
          v67 = CurrentIP();
          v68 = v125;
          v69 = ConstructPartialMsgW(0x4000000u, "Current op    : %u", v125);
          WdsSetupLogMessageW(
            v69,
            819200,
            L"D",
            0,
            766,
            L"base\\ntsetup\\setupplatform\\lib\\private\\crashrecovery.cpp",
            L"pCanAttemptRecover",
            v67,
            (_DWORD)v61,
            0,
            0);
          v70 = v136;
          v71 = SPGetPhaseStr(v65, *(_QWORD *)v136);
          (*(void (__fastcall **)(struct ITelemetry *, const wchar_t *, const wchar_t *, __int64))(v72 + 16))(
            v70,
            L"SP_RETRY_INFO",
            L"RetryPhase",
            v71);
          v73 = SPGetOperationStr(v68, *(_QWORD *)v70);
          (*(void (__fastcall **)(struct ITelemetry *, const wchar_t *, const wchar_t *, __int64))(v74 + 16))(
            v70,
            L"SP_RETRY_INFO",
            L"RetryOperation",
            v73);
          v75 = GetLastError();
          v76 = CurrentIP();
          if ( Type )
          {
            v77 = ConstructPartialMsgW(0x4000000u, "Current result: 0x%08X", cbData);
            WdsSetupLogMessageW(
              v77,
              819200,
              L"D",
              0,
              774,
              L"base\\ntsetup\\setupplatform\\lib\\private\\crashrecovery.cpp",
              L"pCanAttemptRecover",
              v76,
              v75,
              0,
              0);
          }
          else
          {
            v78 = ConstructPartialMsgW(0x4000000u, "Current result: Unknown");
            WdsSetupLogMessageW(
              v78,
              819200,
              L"D",
              0,
              778,
              L"base\\ntsetup\\setupplatform\\lib\\private\\crashrecovery.cpp",
              L"pCanAttemptRecover",
              v76,
              v75,
              0,
              0);
          }
          v79 = v122[0];
          if ( v122[0] )
          {
            v80 = GetLastError();
            v81 = CurrentIP();
            v82 = ConstructPartialMsgW(0x4000000u, "Bugcheck code : 0x%08X", v79);
            WdsSetupLogMessageW(
              v82,
              819200,
              L"D",
              0,
              782,
              L"base\\ntsetup\\setupplatform\\lib\\private\\crashrecovery.cpp",
              L"pCanAttemptRecover",
              v81,
              v80,
              0,
              0);
            (*(void (__fastcall **)(struct ITelemetry *, const wchar_t *, const wchar_t *, _QWORD))(*(_QWORD *)v136 + 8LL))(
              v136,
              L"SP_RETRY_INFO",
              L"RetryBugCheckCode",
              v79);
          }
          if ( v65 == 3 )
          {
            if ( v68 == 23 )
            {
              *(_DWORD *)v9 = 1;
LABEL_52:
              *a6 = 0;
              v83 = 1;
LABEL_53:
              v95 = SPMountOfflineHive(a2, L"SYSTEM", L"$OFFLINE_RW$SYSTEM");
              if ( v95 )
              {
                hKey = 0;
                v100 = RegCreateKeyExW(v95, L"Setup\\Status\\ChildCompletion", 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
                if ( v100 )
                {
                  v83 = 0;
                  v115 = GetLastError();
                  v116 = CurrentIP();
                  v117 = ConstructPartialMsgW(
                           0x4000000u,
                           "Cannot open HKLM\\SYSTEM\\%s. Error: 0x%08X",
                           (const char *)L"Setup\\Status\\ChildCompletion",
                           v100);
                  WdsSetupLogMessageW(
                    v117,
                    819200,
                    L"D",
                    0,
                    980,
                    L"base\\ntsetup\\setupplatform\\lib\\private\\crashrecovery.cpp",
                    L"pCanAttemptRecover",
                    v116,
                    v115,
                    0,
                    0);
                }
                else
                {
                  Type = 0;
                  LODWORD(Data) = 0;
                  cbData = 4;
                  v101 = RegQueryValueExW(hKey, L"RecoveryPhase", 0, &Type, (LPBYTE)&Data, &cbData);
                  if ( v101 == 2 || !v101 && Type == 4 || cbData == 4 )
                  {
                    if ( (_DWORD)Data && (_DWORD)Data == *(_DWORD *)v9 )
                    {
                      Type = 0;
                      LODWORD(Data) = 0;
                      cbData = 4;
                      v105 = RegQueryValueExW(hKey, L"RecoveryAttempts", 0, &Type, (LPBYTE)&Data, &cbData);
                      if ( v105 == 2 || !v105 && Type == 4 || cbData == 4 )
                      {
                        if ( (unsigned int)Data >= 3 )
                        {
                          v83 = 0;
                          v109 = GetLastError();
                          v110 = CurrentIP();
                          v111 = ConstructPartialMsgW(0x4000000u, "Maximum recovery attempts reached.");
                          WdsSetupLogMessageW(
                            v111,
                            819200,
                            L"D",
                            0,
                            958,
                            L"base\\ntsetup\\setupplatform\\lib\\private\\crashrecovery.cpp",
                            L"pCanAttemptRecover",
                            v110,
                            v109,
                            0,
                            0);
                        }
                        else
                        {
                          *v137 = (unsigned int)Data;
                        }
                      }
                      else
                      {
                        v83 = 0;
                        v106 = GetLastError();
                        v107 = CurrentIP();
                        v108 = ConstructPartialMsgW(
                                 0x4000000u,
                                 "Cannot read the number of recovery attempts made so far.");
                        WdsSetupLogMessageW(
                          v108,
                          819200,
                          L"D",
                          0,
                          964,
                          L"base\\ntsetup\\setupplatform\\lib\\private\\crashrecovery.cpp",
                          L"pCanAttemptRecover",
                          v107,
                          v106,
                          0,
                          0);
                      }
                    }
                    else
                    {
                      v112 = GetLastError();
                      v113 = CurrentIP();
                      v114 = ConstructPartialMsgW(
                               0x4000000u,
                               "Past recovery phase %d does not match current phase %d. Resetting recovery attempts",
                               (_DWORD)Data,
                               *(_DWORD *)v9);
                      WdsSetupLogMessageW(
                        v114,
                        819200,
                        L"D",
                        0,
                        930,
                        L"base\\ntsetup\\setupplatform\\lib\\private\\crashrecovery.cpp",
                        L"pCanAttemptRecover",
                        v113,
                        v112,
                        0,
                        0);
                      *v137 = 0;
                    }
                  }
                  else
                  {
                    v83 = 0;
                    v102 = GetLastError();
                    v103 = CurrentIP();
                    v104 = ConstructPartialMsgW(0x4000000u, "Cannot read the recovery phase.");
                    WdsSetupLogMessageW(
                      v104,
                      819200,
                      L"D",
                      0,
                      971,
                      L"base\\ntsetup\\setupplatform\\lib\\private\\crashrecovery.cpp",
                      L"pCanAttemptRecover",
                      v103,
                      v102,
                      0,
                      0);
                  }
                  RegCloseKey(hKey);
                  hKey = 0;
                }
                RegCloseKey(v95);
                SPUnloadKey(v118, L"$OFFLINE_RW$SYSTEM");
              }
              else
              {
                v96 = GetLastError();
                v97 = CurrentIP();
                v98 = GetLastError();
                v99 = ConstructPartialMsgW(
                        0x4000000u,
                        "Cannot load the system hive for the offline OS. Error: 0x%08X",
                        v98);
                WdsSetupLogMessageW(
                  v99,
                  819200,
                  L"D",
                  0,
                  887,
                  L"base\\ntsetup\\setupplatform\\lib\\private\\crashrecovery.cpp",
                  L"pCanAttemptRecover",
                  v97,
                  v96,
                  0,
                  0);
                v83 = 0;
              }
              goto LABEL_75;
            }
            if ( v68 == 24 && !cbData )
            {
              *(_DWORD *)v9 = 1;
              *a6 = 1;
              v83 = 1;
              goto LABEL_53;
            }
          }
          else if ( v65 == 4 && v68 == 23 )
          {
            *(_DWORD *)v9 = 2;
            goto LABEL_52;
          }
          v83 = 0;
          if ( v65 != 4
            || v68 != 25
            || (v122[0] = 0,
                !(unsigned int)pRegOfflineGetDWord(
                                 a2,
                                 L"SYSTEM",
                                 L"Setup\\Status\\ChildCompletion",
                                 L"oobeldr.exe",
                                 v122))
            || v122[0] != 1 )
          {
LABEL_75:
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v127);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v128);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v129);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v130);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v131);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v126);
            return v83;
          }
          v122[0] = 0;
          if ( (unsigned int)pRegOfflineGetDWord(
                               a2,
                               L"SOFTWARE",
                               L"Microsoft\\Windows\\CurrentVersion\\Setup\\OOBE",
                               L"OOBEFailure",
                               v122) )
          {
            if ( !Type )
            {
              v87 = v122[0];
              if ( v122[0] == -2147467260 )
              {
                hKey = 0;
                if ( (unsigned int)pRegOfflineGetQWord(a2, v84, v85, v86, (unsigned __int64 *)&hKey) )
                {
                  v88 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v126);
                  v89 = UnBCL::String::get_CString(v88);
                  v90 = SPReadConfigValue(L"Flow", L"OOBEStartTime", v89);
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v132, v90);
                  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v132) )
                  {
                    v91 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v132);
                    v92 = UnBCL::String::get_CString(v91);
                    v93 = _wcstoui64(v92, 0, 10);
                    if ( v93 )
                    {
                      if ( (unsigned __int64)hKey >= v93 )
                        v87 = -2147023294;
                    }
                  }
                  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v132);
                }
              }
              v94 = UnBCL::String::String((UnBCL::String *)v133, Data);
              SPWriteOperationEnd(v94, 172, v87);
              UnBCL::String::~String((UnBCL::String *)v133);
            }
            goto LABEL_75;
          }
          *(_DWORD *)v9 = 3;
          goto LABEL_52;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1802778cc  mov     rax, rsp
0x1802778cf  mov     [rax+20h], r9
0x1802778d3  mov     [rax+18h], r8
0x1802778d7  mov     [rax+8], rcx
0x1802778db  push    rbp
0x1802778dc  push    rsi
0x1802778dd  push    rdi
0x1802778de  push    r12
0x1802778e0  push    r13
0x1802778e2  push    r14
0x1802778e4  push    r15
0x1802778e6  lea     rbp, [rax-58h]
0x1802778ea  sub     rsp, 120h
0x1802778f1  mov     [rbp+50h+var_40], 0FFFFFFFFFFFFFFFEh
0x1802778f9  mov     [rax+10h], rbx
0x1802778fd  mov     rax, r9
0x180277900  mov     r15, rdx
0x180277903  mov     rdi, rcx
0x180277906  xor     r13d, r13d
0x180277909  test    rcx, rcx
0x18027790c  jz      loc_1802787AF
0x180277912  test    rdx, rdx
0x180277915  jz      loc_1802787AF
0x18027791b  test    rax, rax
0x18027791e  jz      loc_1802787AF
0x180277924  mov     r14, [rbp+50h+arg_20]
0x18027792b  test    r14, r14
0x18027792e  jz      loc_1802787AF
0x180277934  lea     rdx, aRollbackinfoIn; "rollbackinfo.ini"
0x18027793b  lea     rcx, [rbp+50h+var_58]
0x18027793f  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180277945  mov     rbx, rax
0x180277948  mov     rdx, rdi
0x18027794b  lea     rcx, [rbp+50h+var_70]
0x18027794f  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180277955  nop
0x180277956  mov     rdx, rbx
0x180277959  mov     rcx, rax
0x18027795c  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x180277962  mov     rdx, rax
0x180277965  lea     rcx, [rbp+50h+var_D0]
0x180277969  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18027796f  nop
0x180277970  lea     rcx, [rbp+50h+var_70]
0x180277974  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18027797a  nop
0x18027797b  lea     rcx, [rbp+50h+var_58]
0x18027797f  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180277985  lea     rcx, [rbp+50h+var_D0]
0x180277989  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18027798f  mov     rcx, rax
0x180277992  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180277998  mov     r8, rax; lpFileName
0x18027799b  lea     rdx, aCurrentphase; "CurrentPhase"
0x1802779a2  lea     rbx, aFlow; "Flow"
0x1802779a9  mov     rcx, rbx; lpAppName
0x1802779ac  call    ?SPReadConfigValue@@YAPEAVString@UnBCL@@PEBG00@Z; SPReadConfigValue(ushort const *,ushort const *,ushort const *)
0x1802779b1  mov     rdx, rax
0x1802779b4  lea     rcx, [rbp+50h+var_80]
0x1802779b8  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802779be  nop
0x1802779bf  lea     rcx, [rbp+50h+var_D0]
0x1802779c3  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802779c9  mov     rcx, rax
0x1802779cc  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802779d2  mov     r8, rax; lpFileName
0x1802779d5  lea     rdx, aCurrentoperati; "CurrentOperation"
0x1802779dc  mov     rcx, rbx; lpAppName
0x1802779df  call    ?SPReadConfigValue@@YAPEAVString@UnBCL@@PEBG00@Z; SPReadConfigValue(ushort const *,ushort const *,ushort const *)
0x1802779e4  mov     rdx, rax
0x1802779e7  lea     rcx, [rbp+50h+var_90]
0x1802779eb  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802779f1  nop
0x1802779f2  lea     rcx, [rbp+50h+var_D0]
0x1802779f6  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802779fc  mov     rcx, rax
0x1802779ff  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180277a05  mov     r8, rax; lpFileName
0x180277a08  lea     rdx, aOperationresul; "OperationResult"
0x180277a0f  mov     rcx, rbx; lpAppName
0x180277a12  call    ?SPReadConfigValue@@YAPEAVString@UnBCL@@PEBG00@Z; SPReadConfigValue(ushort const *,ushort const *,ushort const *)
0x180277a17  mov     rdx, rax
0x180277a1a  lea     rcx, [rbp+50h+var_A0]
0x180277a1e  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180277a24  nop
0x180277a25  lea     rcx, [rbp+50h+var_D0]
0x180277a29  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180277a2f  mov     rcx, rax
0x180277a32  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180277a38  mov     r8, rax; lpFileName
0x180277a3b  lea     rdx, aCode; "Code"
0x180277a42  lea     rcx, aBugcheck; "Bugcheck"
0x180277a49  call    ?SPReadConfigValue@@YAPEAVString@UnBCL@@PEBG00@Z; SPReadConfigValue(ushort const *,ushort const *,ushort const *)
0x180277a4e  mov     rdx, rax
0x180277a51  lea     rcx, [rbp+50h+var_B0]
0x180277a55  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180277a5b  nop
0x180277a5c  lea     rcx, [rbp+50h+var_D0]
0x180277a60  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180277a66  mov     rcx, rax
0x180277a69  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180277a6f  mov     r8, rax; lpFileName
0x180277a72  lea     rdx, aConnectedstand; "ConnectedStandby"
0x180277a79  lea     rcx, aOldos; "OldOS"
0x180277a80  call    ?SPReadConfigValue@@YAPEAVString@UnBCL@@PEBG00@Z; SPReadConfigValue(ushort const *,ushort const *,ushort const *)
0x180277a85  mov     rdx, rax
0x180277a88  lea     rcx, [rbp+50h+var_C0]
0x180277a8c  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180277a92  nop
0x180277a93  call    cs:__imp_GetLastError
0x180277a99  mov     edi, eax
0x180277a9b  call    cs:__imp_CurrentIP
0x180277aa1  mov     rsi, rax
0x180277aa4  lea     rcx, [rbp+50h+var_80]
0x180277aa8  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180277aae  lea     rbx, aNull_5; "NULL"
0x180277ab5  test    rax, rax
0x180277ab8  jz      short loc_180277ACF
0x180277aba  lea     rcx, [rbp+50h+var_80]
0x180277abe  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180277ac4  mov     rcx, rax
0x180277ac7  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180277acd  jmp     short loc_180277AD2
0x180277acf  mov     rax, rbx
0x180277ad2  mov     r8, rax
0x180277ad5  lea     rdx, aCurrentPhaseSt; "Current phase string : %s"
0x180277adc  mov     r12d, 4000000h
0x180277ae2  mov     ecx, r12d; unsigned int
0x180277ae5  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180277aea  mov     [rsp+50h], r13d
0x180277aef  mov     [rsp+150h+var_108], r13
0x180277af4  mov     dword ptr [rsp+150h+lpdwDisposition], edi
0x180277af8  mov     [rsp+150h+phkResult], rsi
0x180277afd  lea     rcx, aPcanattemptrec; "pCanAttemptRecover"
0x180277b04  mov     [rsp+150h+lpSecurityAttributes], rcx
0x180277b09  lea     rcx, aBaseNtsetupSet_57; "base\\ntsetup\\setupplatform\\lib\\priv"...
0x180277b10  mov     qword ptr [rsp+150h+samDesired], rcx
0x180277b15  mov     [rsp+150h+dwOptions], 2E1h
0x180277b1d  xor     r9d, r9d
0x180277b20  lea     r8, aD_0; "D"
0x180277b27  mov     edx, 0C8000h
0x180277b2c  mov     rcx, rax
0x180277b2f  call    cs:__imp_WdsSetupLogMessageW
0x180277b35  call    cs:__imp_GetLastError
0x180277b3b  mov     edi, eax
0x180277b3d  call    cs:__imp_CurrentIP
0x180277b43  mov     rsi, rax
0x180277b46  lea     rcx, [rbp+50h+var_90]
0x180277b4a  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180277b50  test    rax, rax
0x180277b53  jz      short loc_180277B6A
0x180277b55  lea     rcx, [rbp+50h+var_90]
0x180277b59  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180277b5f  mov     rcx, rax
0x180277b62  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180277b68  jmp     short loc_180277B6D
0x180277b6a  mov     rax, rbx
0x180277b6d  mov     r8, rax
0x180277b70  lea     rdx, aCurrentOpStrin; "Current op string    : %s"
0x180277b77  mov     ecx, r12d; unsigned int
0x180277b7a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180277b7f  mov     [rsp+50h], r13d
0x180277b84  mov     [rsp+150h+var_108], r13
0x180277b89  mov     dword ptr [rsp+150h+lpdwDisposition], edi
0x180277b8d  mov     [rsp+150h+phkResult], rsi
0x180277b92  lea     rcx, aPcanattemptrec; "pCanAttemptRecover"
0x180277b99  mov     [rsp+150h+lpSecurityAttributes], rcx
0x180277b9e  lea     rcx, aBaseNtsetupSet_57; "base\\ntsetup\\setupplatform\\lib\\priv"...
0x180277ba5  mov     qword ptr [rsp+150h+samDesired], rcx
0x180277baa  mov     [rsp+150h+dwOptions], 2E2h
0x180277bb2  xor     r9d, r9d
0x180277bb5  lea     r8, aD_0; "D"
0x180277bbc  mov     edx, 0C8000h
0x180277bc1  mov     rcx, rax
0x180277bc4  call    cs:__imp_WdsSetupLogMessageW
0x180277bca  call    cs:__imp_GetLastError
0x180277bd0  mov     edi, eax
0x180277bd2  call    cs:__imp_CurrentIP
0x180277bd8  mov     rsi, rax
0x180277bdb  lea     rcx, [rbp+50h+var_A0]
0x180277bdf  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180277be5  test    rax, rax
0x180277be8  jz      short loc_180277BFF
0x180277bea  lea     rcx, [rbp+50h+var_A0]
0x180277bee  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180277bf4  mov     rcx, rax
0x180277bf7  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180277bfd  jmp     short loc_180277C02
0x180277bff  mov     rax, rbx
0x180277c02  mov     r8, rax
0x180277c05  lea     rdx, aCurrentResultS_0; "Current result string: %s"
0x180277c0c  mov     ecx, r12d; unsigned int
0x180277c0f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180277c14  mov     [rsp+50h], r13d
0x180277c19  mov     [rsp+150h+var_108], r13
0x180277c1e  mov     dword ptr [rsp+150h+lpdwDisposition], edi
0x180277c22  mov     [rsp+150h+phkResult], rsi
0x180277c27  lea     rcx, aPcanattemptrec; "pCanAttemptRecover"
0x180277c2e  mov     [rsp+150h+lpSecurityAttributes], rcx
0x180277c33  lea     rcx, aBaseNtsetupSet_57; "base\\ntsetup\\setupplatform\\lib\\priv"...
0x180277c3a  mov     qword ptr [rsp+150h+samDesired], rcx
0x180277c3f  mov     [rsp+150h+dwOptions], 2E3h
0x180277c47  xor     r9d, r9d
0x180277c4a  lea     r8, aD_0; "D"
0x180277c51  mov     edx, 0C8000h
0x180277c56  mov     rcx, rax
0x180277c59  call    cs:__imp_WdsSetupLogMessageW
0x180277c5f  call    cs:__imp_GetLastError
0x180277c65  mov     edi, eax
0x180277c67  call    cs:__imp_CurrentIP
0x180277c6d  mov     rsi, rax
0x180277c70  lea     rcx, [rbp+50h+var_B0]
0x180277c74  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180277c7a  test    rax, rax
0x180277c7d  jz      short loc_180277C94
0x180277c7f  lea     rcx, [rbp+50h+var_B0]
0x180277c83  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180277c89  mov     rcx, rax
0x180277c8c  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180277c92  jmp     short loc_180277C97
0x180277c94  mov     rax, rbx
0x180277c97  mov     r8, rax
0x180277c9a  lea     rdx, aCurrentBugchec_0; "Current bugcheck string: %s"
0x180277ca1  mov     ecx, r12d; unsigned int
0x180277ca4  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180277ca9  mov     [rsp+50h], r13d
0x180277cae  mov     [rsp+150h+var_108], r13
0x180277cb3  mov     dword ptr [rsp+150h+lpdwDisposition], edi
0x180277cb7  mov     [rsp+150h+phkResult], rsi
0x180277cbc  lea     rcx, aPcanattemptrec; "pCanAttemptRecover"
0x180277cc3  mov     [rsp+150h+lpSecurityAttributes], rcx
0x180277cc8  lea     rcx, aBaseNtsetupSet_57; "base\\ntsetup\\setupplatform\\lib\\priv"...
0x180277ccf  mov     qword ptr [rsp+150h+samDesired], rcx
0x180277cd4  mov     [rsp+150h+dwOptions], 2E4h
0x180277cdc  xor     r9d, r9d
0x180277cdf  lea     r8, aD_0; "D"
0x180277ce6  mov     edx, 0C8000h
0x180277ceb  mov     rcx, rax
0x180277cee  call    cs:__imp_WdsSetupLogMessageW
0x180277cf4  call    cs:__imp_GetLastError
0x180277cfa  mov     edi, eax
0x180277cfc  call    cs:__imp_CurrentIP
0x180277d02  mov     rsi, rax
0x180277d05  lea     rcx, [rbp+50h+var_C0]
0x180277d09  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180277d0f  test    rax, rax
0x180277d12  jz      short loc_180277D2A
0x180277d14  lea     rcx, [rbp+50h+var_C0]
0x180277d18  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180277d1e  mov     rcx, rax
0x180277d21  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180277d27  mov     rbx, rax
0x180277d2a  mov     r8, rbx
0x180277d2d  lea     rdx, aConnectedStand_1; "Connected standby str: %s"
0x180277d34  mov     ecx, r12d; unsigned int
0x180277d37  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180277d3c  mov     [rsp+50h], r13d
0x180277d41  mov     [rsp+150h+var_108], r13
0x180277d46  mov     dword ptr [rsp+150h+lpdwDisposition], edi
0x180277d4a  mov     [rsp+150h+phkResult], rsi
0x180277d4f  lea     rcx, aPcanattemptrec; "pCanAttemptRecover"
0x180277d56  mov     [rsp+150h+lpSecurityAttributes], rcx
0x180277d5b  lea     rcx, aBaseNtsetupSet_57; "base\\ntsetup\\setupplatform\\lib\\priv"...
0x180277d62  mov     qword ptr [rsp+150h+samDesired], rcx
0x180277d67  mov     [rsp+150h+dwOptions], 2E5h
0x180277d6f  xor     r9d, r9d
0x180277d72  lea     r8, aD_0; "D"
0x180277d79  mov     edx, 0C8000h
0x180277d7e  mov     rcx, rax
0x180277d81  call    cs:__imp_WdsSetupLogMessageW
0x180277d87  mov     r12, [rbp+50h+arg_30]
0x180277d8e  test    r12, r12
0x180277d91  jz      loc_180277E5F
0x180277d97  lea     rsi, aYes_1; "Yes"
0x180277d9e  mov     rdx, rsi
0x180277da1  lea     rcx, [rbp+50h+var_58]
0x180277da5  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180277dab  mov     rbx, rax
0x180277dae  lea     rcx, [rbp+50h+var_C0]
0x180277db2  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180277db8  mov     r8d, 1
0x180277dbe  mov     rdx, rbx
0x180277dc1  mov     rcx, rax
0x180277dc4  call    cs:__imp_?Compare@String@UnBCL@@SAHPEBV12@0H@Z; UnBCL::String::Compare(UnBCL::String const *,UnBCL::String const *,int)
0x180277dca  mov     ecx, r13d
0x180277dcd  test    eax, eax
0x180277dcf  setz    cl
0x180277dd2  mov     [r12], ecx
0x180277dd6  lea     rcx, [rbp+50h+var_58]
0x180277dda  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180277de0  call    cs:__imp_GetLastError
0x180277de6  mov     edi, eax
0x180277de8  call    cs:__imp_CurrentIP
0x180277dee  mov     rbx, rax
0x180277df1  lea     rax, aNo; "No"
0x180277df8  cmp     [r12], r13d
0x180277dfc  cmovz   rsi, rax
0x180277e00  mov     r8, rsi
0x180277e03  lea     rdx, aConnectedStand; "Connected standby    : %s"
0x180277e0a  mov     ecx, 4000000h; unsigned int
  ... truncated ...
```
