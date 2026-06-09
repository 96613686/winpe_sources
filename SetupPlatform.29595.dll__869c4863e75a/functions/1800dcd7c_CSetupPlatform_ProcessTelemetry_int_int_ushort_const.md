# CSetupPlatform::ProcessTelemetry(int,int,ushort const *)

- ea: `0x1800dcd7c`
- end: `0x1800dd848`
- name: `?ProcessTelemetry@CSetupPlatform@@QEAAXHHPEBG@Z`
- size: `2764`
- prototype: `void(CSetupPlatform *__hidden this, int, int, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `16`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x180106c10`
- `0x180114760`
- `0x18024c320`

## callees

- `0x180057dec`
- `0x1800dcd7c`
- `0x1802d74cc`
- `0x1802d7cd8`
- `0x180373754`
- `0x180373b4c`
- `0x180375300`
- `0x1803755e8`
- `0x180379de8`
- `0x18037fc2c`
- `0x1803821e0`
- `0x1804086f8`
- `0x1804bbf46`
- `0x1804bbf62`
- `0x1804bbfa0`
- `0x180509010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800dcf99`
- `msvcrt!_wcsicmp` at `0x1800dcf99`
- `msvcrt!swscanf_s` at `0x1800dd480`
- `msvcrt!swscanf_s` at `0x1800dd480`
- `KERNEL32!GetLastError` at `0x1800dce3d`
- `KERNEL32!GetLastError` at `0x1800dcee2`
- `KERNEL32!GetLastError` at `0x1800dcfa3`
- `KERNEL32!GetLastError` at `0x1800dd0b1`
- `KERNEL32!GetLastError` at `0x1800dd196`
- `KERNEL32!GetLastError` at `0x1800dd2c8`
- `KERNEL32!GetLastError` at `0x1800dd2e0`
- `KERNEL32!GetLastError` at `0x1800dd2f8`
- `KERNEL32!GetLastError` at `0x1800dd39c`
- `KERNEL32!GetLastError` at `0x1800dd4a8`
- `KERNEL32!GetLastError` at `0x1800dce3d`
- `KERNEL32!GetLastError` at `0x1800dcee2`
- `KERNEL32!GetLastError` at `0x1800dcfa3`
- `KERNEL32!GetLastError` at `0x1800dd0b1`
- `KERNEL32!GetLastError` at `0x1800dd196`
- `KERNEL32!GetLastError` at `0x1800dd2c8`
- `KERNEL32!GetLastError` at `0x1800dd2e0`
- `KERNEL32!GetLastError` at `0x1800dd2f8`
- `KERNEL32!GetLastError` at `0x1800dd39c`
- `KERNEL32!GetLastError` at `0x1800dd4a8`
- `KERNEL32!CopyFileW` at `0x1800dd2ba`
- `KERNEL32!CopyFileW` at `0x1800dd2ba`
- `KERNEL32!GetEnvironmentVariableW` at `0x1800dd454`
- `KERNEL32!GetEnvironmentVariableW` at `0x1800dd454`
- `unbcl!?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800dd265`
- `unbcl!?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800dd265`
- `unbcl!?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800dd54d`
- `unbcl!?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800dd54d`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1800dd6bb`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1800dd6bb`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x1800dd244`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x1800dd244`
- `unbcl!?GetPathRoot@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800dd760`
- `unbcl!?GetPathRoot@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800dd760`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x1800dd5de`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x1800dd5de`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800dd068`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800dd27e`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800dd614`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800dd068`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800dd27e`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800dd614`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dce52`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dcf66`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dd05c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dd223`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dd23b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dd272`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dd565`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dd608`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dd689`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dd6af`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dd71f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dd742`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dd757`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dd778`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dd785`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dd7a8`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dce52`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dcf66`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dd05c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dd223`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dd23b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dd272`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dd565`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dd608`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dd689`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dd6af`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dd71f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dd742`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dd757`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dd778`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dd785`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dd7a8`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1800dcdca`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1800dd5e9`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1800dcdca`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1800dd5e9`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800dd080`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800dd297`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800dd646`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800dd080`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800dd297`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800dd646`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800dd047`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800dd25b`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800dd5fb`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800dd66e`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800dd047`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800dd25b`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800dd5fb`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800dd66e`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800dd656`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800dd699`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800dd656`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800dd699`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800dce2c`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800dd630`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800dce2c`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800dd630`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800dce6d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800dcf84`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800dd08a`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800dd2a1`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800dd30d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800dce6d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800dcf84`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800dd08a`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800dd2a1`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800dd30d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800dce76`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800dcf8d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800dd093`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800dd2aa`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800dd316`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800dce76`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800dcf8d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800dd093`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800dd2aa`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800dd316`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dce37`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dd389`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dd394`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dd424`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dd578`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dd63b`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dd7cc`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dd7d7`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dd7e2`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dd7ed`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dd818`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dce37`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dd389`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dd394`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dd424`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dd578`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dd63b`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dd7cc`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dd7d7`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dd7e2`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dd7ed`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dd818`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800dce1d`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800dd075`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800dd230`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800dd28b`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800dd55a`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800dd5cf`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800dd621`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800dd76d`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800dce1d`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800dd075`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800dd230`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800dd28b`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800dd55a`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800dd5cf`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800dd621`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800dd76d`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800dcedc`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800dcf5c`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800dd00e`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800dd208`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800dd37e`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800dd407`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800dd510`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800dcedc`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800dcf5c`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800dd00e`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800dd208`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800dd37e`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800dd407`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800dd510`
- `WDSCORE!CurrentIP` at `0x1800dce45`
- `WDSCORE!CurrentIP` at `0x1800dceea`
- `WDSCORE!CurrentIP` at `0x1800dcfab`
- `WDSCORE!CurrentIP` at `0x1800dd0b9`
- `WDSCORE!CurrentIP` at `0x1800dd19e`
- `WDSCORE!CurrentIP` at `0x1800dd300`
- `WDSCORE!CurrentIP` at `0x1800dd3a4`
- `WDSCORE!CurrentIP` at `0x1800dd4b0`
- `WDSCORE!CurrentIP` at `0x1800dce45`
- `WDSCORE!CurrentIP` at `0x1800dceea`
- `WDSCORE!CurrentIP` at `0x1800dcfab`
- `WDSCORE!CurrentIP` at `0x1800dd0b9`
- `WDSCORE!CurrentIP` at `0x1800dd19e`
- `WDSCORE!CurrentIP` at `0x1800dd300`
- `WDSCORE!CurrentIP` at `0x1800dd3a4`
- `WDSCORE!CurrentIP` at `0x1800dd4b0`

## string_xrefs

- `0x1800dceb6`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800dcf34`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800dcfeb`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800dd0fc`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800dd1e2`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800dd358`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800dd3e1`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800dd4ea`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800dd327`: `Failed to copy file %s to %s. Error: 0x%08X`
- `0x1800dd3b0`: `Failed to copy file name. hr = 0X%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
void __fastcall CSetupPlatform::ProcessTelemetry(CSetupPlatform *this, int a2, int a3, const unsigned __int16 *a4)
{
  char *v7; // r12
  __int64 v8; // rax
  CTelemetry *v9; // rax
  CTelemetry *v10; // r14
  struct UnBCL::String *CorrelationVector; // rax
  DWORD LastError; // ebx
  __int64 v13; // rdi
  const wchar_t *v14; // rsi
  const wchar_t *CString; // rax
  UnBCL::String *v16; // rax
  struct tagLOG_PARTIAL_MSG *v17; // rax
  DWORD v18; // edi
  __int64 v19; // rbx
  struct tagLOG_PARTIAL_MSG *v20; // rax
  UnBCL::String *v21; // rax
  const wchar_t *v22; // rax
  DWORD v23; // edi
  __int64 v24; // rbx
  struct tagLOG_PARTIAL_MSG *v25; // rax
  const struct UnBCL::String *v26; // rbx
  __int64 v27; // r13
  const struct UnBCL::String *P; // rax
  struct UnBCL::String *v29; // rax
  UnBCL::String *v30; // rax
  const unsigned __int16 *v31; // rax
  unsigned int v32; // r9d
  int v33; // esi
  DWORD v34; // edi
  __int64 v35; // rbx
  struct tagLOG_PARTIAL_MSG *v36; // rax
  __int64 v37; // rax
  const wchar_t *v38; // rcx
  __int64 v39; // rdx
  WCHAR *v40; // r8
  wchar_t v41; // r9
  unsigned int v42; // esi
  WCHAR *v43; // rcx
  struct UnBCL::String *v44; // rax
  int v45; // esi
  DWORD v46; // edi
  __int64 v47; // rbx
  struct tagLOG_PARTIAL_MSG *v48; // rax
  __int64 v49; // rax
  const struct UnBCL::String *v50; // rax
  const struct UnBCL::String *v51; // rax
  const struct UnBCL::String *FileName; // rbx
  const struct UnBCL::String *v53; // rax
  struct UnBCL::String *v54; // rax
  UnBCL::String *v55; // rax
  const WCHAR *v56; // rax
  signed int v57; // eax
  bool v58; // sf
  signed int v59; // eax
  unsigned int v60; // esi
  DWORD v61; // edi
  __int64 v62; // rbx
  UnBCL::String *v63; // rax
  const char *v64; // rax
  struct tagLOG_PARTIAL_MSG *v65; // rax
  DWORD v66; // edi
  __int64 v67; // rbx
  struct tagLOG_PARTIAL_MSG *v68; // rax
  int v69; // esi
  DWORD v70; // edi
  __int64 v71; // rbx
  struct tagLOG_PARTIAL_MSG *v72; // rax
  struct UnBCL::String **v73; // rax
  const struct UnBCL::String *v74; // rax
  struct UnBCL::String *ParentPath; // rax
  struct UnBCL::String *v76; // rax
  int v77; // edx
  struct UnBCL::String *v78; // rax
  const struct UnBCL::String *v79; // rbx
  const struct UnBCL::String *v80; // rax
  struct UnBCL::String *v81; // rax
  UnBCL::String *v82; // rax
  UnBCL::String *v83; // rbx
  const struct UnBCL::String *v84; // rax
  struct UnBCL::String *v85; // rbx
  struct UnBCL::String *v86; // rax
  struct UnBCL::String **v87; // rbx
  struct UnBCL::String *v88; // rax
  const struct UnBCL::String *v89; // rax
  struct UnBCL::String *PathRoot; // rax
  struct UnBCL::String *v91; // rsi
  struct UnBCL::String *v92; // rdi
  struct UnBCL::String *v93; // rbx
  struct UnBCL::String *v94; // rax
  unsigned int v95; // r8d
  int v96; // r9d
  unsigned int v97; // [rsp+28h] [rbp-E0h]
  void **v98; // [rsp+68h] [rbp-A0h] BYREF
  void (__fastcall ***v99)(_QWORD, __int64); // [rsp+70h] [rbp-98h]
  DWORD EnvironmentVariableW; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v101[16]; // [rsp+88h] [rbp-80h] BYREF
  _QWORD v102[2]; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v103[16]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v104[16]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v105[16]; // [rsp+C8h] [rbp-40h] BYREF
  int v106; // [rsp+D8h] [rbp-30h]
  _BYTE v107[24]; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v108; // [rsp+F8h] [rbp-10h]
  _BYTE v109[24]; // [rsp+100h] [rbp-8h] BYREF
  WCHAR Buffer[8]; // [rsp+118h] [rbp+10h] BYREF
  __int128 v111; // [rsp+128h] [rbp+20h]
  WCHAR ExistingFileName[264]; // [rsp+138h] [rbp+30h] BYREF
  unsigned __int16 v113[264]; // [rsp+348h] [rbp+240h] BYREF

  v108 = -2;
  v106 = a3;
  v102[0] = this;
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v103);
  v7 = (char *)this + 208;
  v8 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 26) + 24LL))((char *)this + 208);
  v9 = (CTelemetry *)_RTDynamicCast_0(v8, 0, &ITelemetry `RTTI Type Descriptor', &CTelemetry `RTTI Type Descriptor', 0);
  v10 = v9;
  if ( v9 )
  {
    CorrelationVector = CTelemetry::GetCorrelationVector(v9);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v101, CorrelationVector);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v103, v101);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v101);
  }
  LastError = GetLastError();
  v13 = CurrentIP();
  v14 = L"NULL";
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v103) )
  {
    v16 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v103);
    CString = UnBCL::String::get_CString(v16);
  }
  else
  {
    CString = L"NULL";
  }
  v17 = ConstructPartialMsgW(0x4000000u, "Existing CV from Telemetry : [%s]", (const char *)CString);
  WdsSetupLogMessageW(
    v17,
    819200,
    L"D",
    0,
    16696,
    L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
    L"CSetupPlatform::ProcessTelemetry",
    v13,
    LastError,
    0,
    0);
  v18 = GetLastError();
  v19 = CurrentIP();
  if ( a4 )
    v14 = a4;
  v20 = ConstructPartialMsgW(0x4000000u, "Input CV : [%s]", (const char *)v14);
  WdsSetupLogMessageW(
    v20,
    819200,
    L"D",
    0,
    16697,
    L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
    L"CSetupPlatform::ProcessTelemetry",
    v19,
    v18,
    0,
    0);
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v103) )
  {
    if ( a4 )
    {
      v21 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v103);
      v22 = UnBCL::String::get_CString(v21);
      if ( _wcsicmp(v22, a4) )
      {
        v23 = GetLastError();
        v24 = CurrentIP();
        v25 = ConstructPartialMsgW(0x3000000u, "Input CV is different form existing CV");
        WdsSetupLogMessageW(
          v25,
          819200,
          L"D",
          0,
          16703,
          L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
          L"CSetupPlatform::ProcessTelemetry",
          v24,
          v23,
          0,
          0);
      }
    }
  }
  if ( v10 && a2 )
  {
    memset_0(v113, 0, 0x208u);
    v26 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v107, L"SetupPlatform.cfg");
    v27 = v102[0];
    P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(*(_QWORD *)(v102[0] + 40LL) + 24LL);
    v29 = UnBCL::Path::Combine(P, v26);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v101, v29);
    UnBCL::String::~String((UnBCL::String *)v107);
    v30 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v101);
    v31 = UnBCL::String::get_CString(v30);
    v33 = CTelemetry::StopTelemetry(v10, v31, v113, v32);
    if ( v33 >= 0 )
    {
      v37 = 2147483646;
      v38 = L"DlTel-Merge.etl";
      v39 = 260;
      v40 = ExistingFileName;
      do
      {
        if ( !v37 )
          break;
        v41 = *v38;
        if ( !*v38 )
          break;
        ++v38;
        *v40++ = v41;
        --v37;
        --v39;
      }
      while ( v39 );
      v42 = v39 == 0 ? 0x8007007A : 0;
      v43 = v40 - 1;
      if ( v39 )
        v43 = v40;
      *v43 = 0;
      if ( v39 )
      {
        v44 = SPGetPlatformDir();
        v45 = SPMergeEtlFiles(v44, 0, v113, ExistingFileName, v97, 0);
        if ( v45 < 0 )
        {
          v46 = GetLastError();
          v47 = CurrentIP();
          v48 = ConstructPartialMsgW(
                  0x2000000u,
                  "Failed to merge telemetry file: %s. hr = 0X%x",
                  (const char *)v113,
                  v45);
          WdsSetupLogMessageW(
            v48,
            819200,
            L"D",
            0,
            16728,
            L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
            L"CSetupPlatform::ProcessTelemetry",
            v47,
            v46,
            0,
            0);
        }
        if ( (unsigned int)IsDriveTypeRamDrive(ExistingFileName[0]) )
        {
          v49 = UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v10 + 48);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v104, v49);
          v50 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v104);
          if ( UnBCL::Directory::Exists(v50) )
          {
            v51 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v98, ExistingFileName);
            FileName = UnBCL::Path::GetFileName(v51);
            v53 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v104);
            v54 = UnBCL::Path::Combine(v53, FileName);
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v105, v54);
            UnBCL::String::~String((UnBCL::String *)&v98);
            v55 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v105);
            v56 = UnBCL::String::get_CString(v55);
            if ( !CopyFileW(ExistingFileName, v56, 0) )
            {
              v57 = GetLastError();
              v58 = v57 < 0;
              if ( v57 > 0 )
                v58 = 1;
              if ( v58 )
              {
                v59 = GetLastError();
                v60 = v59;
                if ( v59 > 0 )
                  v60 = (unsigned __int16)v59 | 0x80070000;
              }
              else
              {
                v60 = -2147467259;
              }
              v61 = GetLastError();
              v62 = CurrentIP();
              v63 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v105);
              v64 = (const char *)UnBCL::String::get_CString(v63);
              v65 = ConstructPartialMsgW(
                      0x2000000u,
                      "Failed to copy file %s to %s. Error: 0x%08X",
                      (const char *)ExistingFileName,
                      v64,
                      v60);
              WdsSetupLogMessageW(
                v65,
                819200,
                L"D",
                0,
                16741,
                L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
                L"CSetupPlatform::ProcessTelemetry",
                v62,
                v61,
                0,
                0);
            }
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v105);
          }
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v104);
        }
      }
      else
      {
        v66 = GetLastError();
        v67 = CurrentIP();
        v68 = ConstructPartialMsgW(0x2000000u, "Failed to copy file name. hr = 0X%x", v42);
        WdsSetupLogMessageW(
          v68,
          819200,
          L"D",
          0,
          16748,
          L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
          L"CSetupPlatform::ProcessTelemetry",
          v67,
          v66,
          0,
          0);
      }
    }
    else
    {
      v34 = GetLastError();
      v35 = CurrentIP();
      v36 = ConstructPartialMsgW(0x2000000u, "Failed to stop telemetry. hr = 0X%x", v33);
      WdsSetupLogMessageW(
        v36,
        819200,
        L"D",
        0,
        16717,
        L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
        L"CSetupPlatform::ProcessTelemetry",
        v35,
        v34,
        0,
        0);
    }
    (*(void (__fastcall **)(char *, _QWORD))(*(_QWORD *)v7 + 32LL))(v7, 0);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v101);
  }
  else
  {
    v27 = v102[0];
  }
  EnvironmentVariableW = 0;
  *(_OWORD *)Buffer = 0;
  v111 = 0;
  v69 = 0;
  EnvironmentVariableW = GetEnvironmentVariableW(L"SP_UPLOAD_ASIMOV", Buffer, 0x10u);
  if ( EnvironmentVariableW - 1 <= 0xE
    && swscanf_s(Buffer, L"%x", &EnvironmentVariableW) > 0
    && EnvironmentVariableW == 1 )
  {
    v99 = 0;
    v98 = &RAII::CAutoDelete<UnBCL::String *>::`vftable';
    v69 = 1;
    v70 = GetLastError();
    v71 = CurrentIP();
    v72 = ConstructPartialMsgW(0x4000000u, "Upload telemetry data based on environment variable");
    WdsSetupLogMessageW(
      v72,
      819200,
      L"D",
      0,
      16767,
      L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
      L"CSetupPlatform::ProcessTelemetry",
      v71,
      v70,
      0,
      0);
    v73 = (struct UnBCL::String **)((__int64 (__fastcall *)(void ***))v98[1])(&v98);
    if ( (int)SPGetLogDir(v73) >= 0 )
    {
      v74 = (const struct UnBCL::String *)((__int64 (__fastcall *)(void ***))v98[4])(&v98);
      ParentPath = UnBCL::Path::GetParentPath(v74);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v101, ParentPath);
      v76 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v101);
      SPDiagTrackSetUploadBasedOnEnvVar(v76, v77);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v101);
    }
    v98 = &RAII::CAutoDelete<UnBCL::String *>::`vftable';
    if ( v99 )
      (**v99)(v99, 1);
  }
  if ( v106 )
  {
    if ( !*(_DWORD *)(v27 + 244) )
      goto LABEL_65;
  }
  else if ( !v69 )
  {
    goto LABEL_65;
  }
  v99 = 0;
  v98 = &RAII::CAutoDelete<UnBCL::String *>::`vftable';
  v78 = SPGetPlatformDir();
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v105, v78);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v104, v105);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v101);
  v79 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v109, L"Panther");
  v80 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v105);
  v81 = UnBCL::Path::Combine(v80, v79);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v102, v81);
  UnBCL::SmartPtr<UnBCL::String>::operator=(v101, v102);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v102);
  UnBCL::String::~String((UnBCL::String *)v109);
  if ( a4 )
  {
    v82 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
    v83 = v82;
    v102[0] = v82;
    if ( v82 )
    {
      UnBCL::String::String(v82, a4);
      *(_QWORD *)v83 = &UnBCL::String::`local vftable';
    }
    else
    {
      v83 = 0;
    }
LABEL_59:
    ((void (__fastcall *)(void ***, UnBCL::String *))v98[6])(&v98, v83);
    goto LABEL_60;
  }
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v103) )
  {
    v83 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
    v102[0] = v83;
    if ( v83 )
    {
      v84 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v103);
      UnBCL::String::String(v83, v84);
      *(_QWORD *)v83 = &UnBCL::String::`local vftable';
    }
    else
    {
      v83 = 0;
    }
    goto LABEL_59;
  }
LABEL_60:
  v102[0] = 0;
  if ( ((unsigned __int8 (__fastcall *)(void ***, _QWORD *))v98[8])(&v98, v102) )
  {
    v85 = (struct UnBCL::String *)((__int64 (__fastcall *)(void ***))v98[4])(&v98);
    v86 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v104);
    SPDiagTrackSetCorrelationVector(v86, v85);
  }
  else
  {
    v87 = (struct UnBCL::String **)((__int64 (__fastcall *)(void ***))v98[1])(&v98);
    v88 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v104);
    SPDiagTrackGetCorrelationVector(v88, v87);
  }
  v89 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v105);
  PathRoot = UnBCL::Path::GetPathRoot(v89);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v107, PathRoot);
  v91 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v107);
  v92 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v104);
  v93 = (struct UnBCL::String *)((__int64 (__fastcall *)(void ***))v98[4])(&v98);
  v94 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v101);
  SPUploadTelemetryData(v94, 0, v95, v96, v93, v92, v91);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v107);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v101);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v104);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v105);
  v98 = &RAII::CAutoDelete<UnBCL::String *>::`vftable';
  if ( v99 )
    (**v99)(v99, 1);
LABEL_65:
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v103);
}

```

## disassembly

```asm
0x1800dcd7c  mov     rax, rsp
0x1800dcd7f  push    rbp
0x1800dcd80  push    rsi
0x1800dcd81  push    rdi
0x1800dcd82  push    r12
0x1800dcd84  push    r13
0x1800dcd86  push    r14
0x1800dcd88  push    r15
0x1800dcd8a  lea     rbp, [rax-498h]
0x1800dcd91  sub     rsp, 560h
0x1800dcd98  mov     [rbp+490h+var_4A0], 0FFFFFFFFFFFFFFFEh
0x1800dcda0  mov     [rax+10h], rbx
0x1800dcda4  mov     rax, cs:__security_cookie
0x1800dcdab  xor     rax, rsp
0x1800dcdae  mov     [rbp+490h+var_40], rax
0x1800dcdb5  mov     r15, r9
0x1800dcdb8  mov     [rbp+490h+var_4C0], r8d
0x1800dcdbc  mov     r13d, edx
0x1800dcdbf  mov     rbx, rcx
0x1800dcdc2  mov     [rbp+490h+var_500], rcx
0x1800dcdc6  lea     rcx, [rbp+490h+var_4F0]
0x1800dcdca  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x1800dcdd0  nop
0x1800dcdd1  lea     r12, [rbx+0D0h]
0x1800dcdd8  mov     rax, [r12]
0x1800dcddc  mov     rcx, r12
0x1800dcddf  mov     rax, [rax+18h]
0x1800dcde3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dcde8  mov     rcx, rax
0x1800dcdeb  xor     ebx, ebx
0x1800dcded  mov     dword ptr [rsp+590h+var_570], ebx
0x1800dcdf1  lea     r9, ??_R0?AVCTelemetry@@@8; CTelemetry `RTTI Type Descriptor'
0x1800dcdf8  lea     r8, ??_R0?AUITelemetry@@@8; ITelemetry `RTTI Type Descriptor'
0x1800dcdff  xor     edx, edx
0x1800dce01  call    __RTDynamicCast_0
0x1800dce06  mov     r14, rax
0x1800dce09  test    rax, rax
0x1800dce0c  jz      short loc_1800DCE3D
0x1800dce0e  mov     rcx, rax; this
0x1800dce11  call    ?GetCorrelationVector@CTelemetry@@QEAAPEAVString@UnBCL@@XZ; CTelemetry::GetCorrelationVector(void)
0x1800dce16  mov     rdx, rax
0x1800dce19  lea     rcx, [rbp+490h+var_510]
0x1800dce1d  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800dce23  nop
0x1800dce24  lea     rdx, [rbp+490h+var_510]
0x1800dce28  lea     rcx, [rbp+490h+var_4F0]
0x1800dce2c  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1800dce32  nop
0x1800dce33  lea     rcx, [rbp+490h+var_510]
0x1800dce37  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800dce3d  call    cs:__imp_GetLastError
0x1800dce43  mov     ebx, eax
0x1800dce45  call    cs:__imp_CurrentIP
0x1800dce4b  mov     rdi, rax
0x1800dce4e  lea     rcx, [rbp+490h+var_4F0]
0x1800dce52  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800dce58  lea     rsi, aNull_5; "NULL"
0x1800dce5f  test    rax, rax
0x1800dce62  jnz     short loc_1800DCE69
0x1800dce64  mov     rax, rsi
0x1800dce67  jmp     short loc_1800DCE7C
0x1800dce69  lea     rcx, [rbp+490h+var_4F0]
0x1800dce6d  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1800dce73  mov     rcx, rax
0x1800dce76  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1800dce7c  mov     r8, rax
0x1800dce7f  lea     rdx, aExistingCvFrom; "Existing CV from Telemetry : [%s]"
0x1800dce86  mov     ecx, 4000000h; unsigned int
0x1800dce8b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800dce90  mov     dword ptr [rsp+50h], 0
0x1800dce98  mov     qword ptr [rsp+590h+var_548], 0
0x1800dcea1  mov     dword ptr [rsp+590h+var_550], ebx
0x1800dcea5  mov     qword ptr [rsp+590h+var_558], rdi
0x1800dceaa  lea     rcx, aCsetupplatform_85; "CSetupPlatform::ProcessTelemetry"
0x1800dceb1  mov     [rsp+590h+var_560], rcx
0x1800dceb6  lea     rcx, aBaseNtsetupSet_34; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1800dcebd  mov     [rsp+590h+var_568], rcx
0x1800dcec2  mov     dword ptr [rsp+590h+var_570], 4138h
0x1800dceca  xor     r9d, r9d
0x1800dcecd  lea     r8, aD_0; "D"
0x1800dced4  mov     edx, 0C8000h
0x1800dced9  mov     rcx, rax
0x1800dcedc  call    cs:__imp_WdsSetupLogMessageW
0x1800dcee2  call    cs:__imp_GetLastError
0x1800dcee8  mov     edi, eax
0x1800dceea  call    cs:__imp_CurrentIP
0x1800dcef0  mov     rbx, rax
0x1800dcef3  test    r15, r15
0x1800dcef6  cmovnz  rsi, r15
0x1800dcefa  mov     r8, rsi
0x1800dcefd  lea     rdx, aInputCvS; "Input CV : [%s]"
0x1800dcf04  mov     ecx, 4000000h; unsigned int
0x1800dcf09  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800dcf0e  mov     dword ptr [rsp+50h], 0
0x1800dcf16  mov     qword ptr [rsp+590h+var_548], 0
0x1800dcf1f  mov     dword ptr [rsp+590h+var_550], edi
0x1800dcf23  mov     qword ptr [rsp+590h+var_558], rbx
0x1800dcf28  lea     rcx, aCsetupplatform_85; "CSetupPlatform::ProcessTelemetry"
0x1800dcf2f  mov     [rsp+590h+var_560], rcx
0x1800dcf34  lea     rcx, aBaseNtsetupSet_34; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1800dcf3b  mov     [rsp+590h+var_568], rcx
0x1800dcf40  mov     dword ptr [rsp+590h+var_570], 4139h
0x1800dcf48  xor     r9d, r9d
0x1800dcf4b  lea     r8, aD_0; "D"
0x1800dcf52  mov     esi, 0C8000h
0x1800dcf57  mov     edx, esi
0x1800dcf59  mov     rcx, rax
0x1800dcf5c  call    cs:__imp_WdsSetupLogMessageW
0x1800dcf62  lea     rcx, [rbp+490h+var_4F0]
0x1800dcf66  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800dcf6c  xor     edi, edi
0x1800dcf6e  test    rax, rax
0x1800dcf71  jz      loc_1800DD016
0x1800dcf77  test    r15, r15
0x1800dcf7a  jz      loc_1800DD016
0x1800dcf80  lea     rcx, [rbp+490h+var_4F0]
0x1800dcf84  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1800dcf8a  mov     rcx, rax
0x1800dcf8d  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1800dcf93  mov     rcx, rax; String1
0x1800dcf96  mov     rdx, r15; String2
0x1800dcf99  call    cs:__imp__wcsicmp
0x1800dcf9f  test    eax, eax
0x1800dcfa1  jz      short loc_1800DD016
0x1800dcfa3  call    cs:__imp_GetLastError
0x1800dcfa9  mov     edi, eax
0x1800dcfab  call    cs:__imp_CurrentIP
0x1800dcfb1  mov     rbx, rax
0x1800dcfb4  lea     rdx, aInputCvIsDiffe; "Input CV is different form existing CV"
0x1800dcfbb  mov     ecx, 3000000h; unsigned int
0x1800dcfc0  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800dcfc5  mov     dword ptr [rsp+50h], 0
0x1800dcfcd  mov     qword ptr [rsp+590h+var_548], 0
0x1800dcfd6  mov     dword ptr [rsp+590h+var_550], edi
0x1800dcfda  mov     qword ptr [rsp+590h+var_558], rbx
0x1800dcfdf  lea     rcx, aCsetupplatform_85; "CSetupPlatform::ProcessTelemetry"
0x1800dcfe6  mov     [rsp+590h+var_560], rcx
0x1800dcfeb  lea     rcx, aBaseNtsetupSet_34; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1800dcff2  mov     [rsp+590h+var_568], rcx
0x1800dcff7  mov     dword ptr [rsp+590h+var_570], 413Fh; unsigned int
0x1800dcfff  xor     r9d, r9d
0x1800dd002  lea     r8, aD_0; "D"
0x1800dd009  mov     edx, esi
0x1800dd00b  mov     rcx, rax
0x1800dd00e  call    cs:__imp_WdsSetupLogMessageW
0x1800dd014  xor     edi, edi
0x1800dd016  test    r14, r14
0x1800dd019  jz      loc_1800DD42E
0x1800dd01f  test    r13d, r13d
0x1800dd022  jz      loc_1800DD42E
0x1800dd028  xor     edx, edx; Val
0x1800dd02a  mov     r8d, 208h; Size
0x1800dd030  lea     rcx, [rbp+490h+var_250]; void *
0x1800dd037  call    memset_0
0x1800dd03c  lea     rdx, aSetupplatformC_0; "SetupPlatform.cfg"
0x1800dd043  lea     rcx, [rbp+490h+var_4B8]
0x1800dd047  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800dd04d  mov     rbx, rax
0x1800dd050  mov     r13, [rbp+490h+var_500]
0x1800dd054  mov     rcx, [r13+28h]
0x1800dd058  add     rcx, 18h
0x1800dd05c  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800dd062  mov     rdx, rbx
0x1800dd065  mov     rcx, rax
0x1800dd068  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1800dd06e  mov     rdx, rax
0x1800dd071  lea     rcx, [rbp+490h+var_510]
0x1800dd075  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800dd07b  nop
0x1800dd07c  lea     rcx, [rbp+490h+var_4B8]
0x1800dd080  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800dd086  lea     rcx, [rbp+490h+var_510]
0x1800dd08a  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1800dd090  mov     rcx, rax
0x1800dd093  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1800dd099  mov     rdx, rax; unsigned __int16 *
0x1800dd09c  lea     r8, [rbp+490h+var_250]; unsigned __int16 *
0x1800dd0a3  mov     rcx, r14; this
0x1800dd0a6  call    ?StopTelemetry@CTelemetry@@QEAAJPEBGPEAGK@Z; CTelemetry::StopTelemetry(ushort const *,ushort *,ulong)
0x1800dd0ab  mov     esi, eax
0x1800dd0ad  test    eax, eax
0x1800dd0af  jns     short loc_1800DD115
0x1800dd0b1  call    cs:__imp_GetLastError
0x1800dd0b7  mov     edi, eax
0x1800dd0b9  call    cs:__imp_CurrentIP
0x1800dd0bf  mov     rbx, rax
0x1800dd0c2  mov     r8d, esi
0x1800dd0c5  lea     rdx, aFailedToStopTe; "Failed to stop telemetry. hr = 0X%x"
0x1800dd0cc  mov     ecx, 2000000h; unsigned int
0x1800dd0d1  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800dd0d6  mov     dword ptr [rsp+50h], 0
0x1800dd0de  mov     qword ptr [rsp+590h+var_548], 0
0x1800dd0e7  mov     dword ptr [rsp+590h+var_550], edi
0x1800dd0eb  mov     qword ptr [rsp+590h+var_558], rbx
0x1800dd0f0  lea     rcx, aCsetupplatform_85; "CSetupPlatform::ProcessTelemetry"
0x1800dd0f7  mov     [rsp+590h+var_560], rcx
0x1800dd0fc  lea     rcx, aBaseNtsetupSet_34; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1800dd103  mov     [rsp+590h+var_568], rcx
0x1800dd108  mov     dword ptr [rsp+590h+var_570], 414Dh
0x1800dd110  jmp     loc_1800DD3F5
0x1800dd115  mov     eax, 7FFFFFFEh
0x1800dd11a  lea     rcx, aDltelMergeEtl; "DlTel-Merge.etl"
0x1800dd121  mov     edx, 104h
0x1800dd126  lea     r8, [rbp+490h+ExistingFileName]
0x1800dd12a  test    rax, rax
0x1800dd12d  jz      short loc_1800DD14E
0x1800dd12f  movzx   r9d, word ptr [rcx]
0x1800dd133  test    r9w, r9w
0x1800dd137  jz      short loc_1800DD14E
0x1800dd139  add     rcx, 2
0x1800dd13d  mov     [r8], r9w
0x1800dd141  add     r8, 2
0x1800dd145  dec     rax
0x1800dd148  sub     rdx, 1
0x1800dd14c  jnz     short loc_1800DD12A
0x1800dd14e  mov     rax, rdx
0x1800dd151  neg     rax
0x1800dd154  sbb     esi, esi
0x1800dd156  not     esi
0x1800dd158  and     esi, 8007007Ah
0x1800dd15e  lea     rcx, [r8-2]
0x1800dd162  test    rdx, rdx
0x1800dd165  cmovnz  rcx, r8
0x1800dd169  mov     [rcx], di
0x1800dd16c  jz      loc_1800DD39C
0x1800dd172  call    ?SPGetPlatformDir@@YAPEAVString@UnBCL@@XZ; SPGetPlatformDir(void)
0x1800dd177  mov     rcx, rax; struct UnBCL::String *
0x1800dd17a  mov     dword ptr [rsp+590h+var_568], edi; int
0x1800dd17e  lea     r9, [rbp+490h+ExistingFileName]; unsigned __int16 *
0x1800dd182  lea     r8, [rbp+490h+var_250]; unsigned __int16 *
0x1800dd189  xor     edx, edx; unsigned __int16 *
0x1800dd18b  call    ?SPMergeEtlFiles@@YAJPEAVString@UnBCL@@PEBG1PEAGKH@Z; SPMergeEtlFiles(UnBCL::String *,ushort const *,ushort const *,ushort *,ulong,int)
0x1800dd190  mov     esi, eax
0x1800dd192  test    eax, eax
0x1800dd194  jns     short loc_1800DD20E
0x1800dd196  call    cs:__imp_GetLastError
0x1800dd19c  mov     edi, eax
0x1800dd19e  call    cs:__imp_CurrentIP
0x1800dd1a4  mov     rbx, rax
0x1800dd1a7  mov     r9d, esi
0x1800dd1aa  lea     r8, [rbp+490h+var_250]
0x1800dd1b1  lea     rdx, aFailedToMergeT_0; "Failed to merge telemetry file: %s. hr "...
0x1800dd1b8  mov     ecx, 2000000h; unsigned int
0x1800dd1bd  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800dd1c2  xor     ecx, ecx
0x1800dd1c4  mov     [rsp+50h], ecx
0x1800dd1c8  mov     qword ptr [rsp+590h+var_548], rcx
0x1800dd1cd  mov     dword ptr [rsp+590h+var_550], edi
0x1800dd1d1  mov     qword ptr [rsp+590h+var_558], rbx
0x1800dd1d6  lea     rcx, aCsetupplatform_85; "CSetupPlatform::ProcessTelemetry"
0x1800dd1dd  mov     [rsp+590h+var_560], rcx
0x1800dd1e2  lea     rcx, aBaseNtsetupSet_34; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1800dd1e9  mov     [rsp+590h+var_568], rcx
0x1800dd1ee  mov     dword ptr [rsp+590h+var_570], 4158h
0x1800dd1f6  xor     r9d, r9d
0x1800dd1f9  lea     r8, aD_0; "D"
0x1800dd200  mov     edx, 0C8000h
0x1800dd205  mov     rcx, rax
0x1800dd208  call    cs:__imp_WdsSetupLogMessageW
0x1800dd20e  movzx   ecx, [rbp+490h+ExistingFileName]
0x1800dd212  call    IsDriveTypeRamDrive
0x1800dd217  test    eax, eax
0x1800dd219  jz      loc_1800DD40D
0x1800dd21f  lea     rcx, [r14+30h]
0x1800dd223  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800dd229  mov     rdx, rax
0x1800dd22c  lea     rcx, [rbp+490h+var_4E0]
0x1800dd230  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800dd236  nop
0x1800dd237  lea     rcx, [rbp+490h+var_4E0]
0x1800dd23b  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800dd241  mov     rcx, rax
0x1800dd244  call    cs:__imp_?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z; UnBCL::Directory::Exists(UnBCL::String const *)
0x1800dd24a  test    eax, eax
0x1800dd24c  jz      loc_1800DD390
0x1800dd252  lea     rdx, [rbp+490h+ExistingFileName]
0x1800dd256  lea     rcx, [rsp+590h+var_530]
0x1800dd25b  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800dd261  nop
0x1800dd262  mov     rcx, rax
0x1800dd265  call    cs:__imp_?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFileName(UnBCL::String const *)
0x1800dd26b  mov     rbx, rax
0x1800dd26e  lea     rcx, [rbp+490h+var_4E0]
0x1800dd272  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800dd278  mov     rdx, rbx
0x1800dd27b  mov     rcx, rax
0x1800dd27e  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1800dd284  mov     rdx, rax
0x1800dd287  lea     rcx, [rbp+490h+var_4D0]
0x1800dd28b  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800dd291  nop
0x1800dd292  lea     rcx, [rsp+590h+var_530]
0x1800dd297  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800dd29d  lea     rcx, [rbp+490h+var_4D0]
0x1800dd2a1  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1800dd2a7  mov     rcx, rax
0x1800dd2aa  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1800dd2b0  mov     rdx, rax; lpNewFileName
0x1800dd2b3  xor     r8d, r8d; bFailIfExists
0x1800dd2b6  lea     rcx, [rbp+490h+ExistingFileName]; lpExistingFileName
  ... truncated ...
```
