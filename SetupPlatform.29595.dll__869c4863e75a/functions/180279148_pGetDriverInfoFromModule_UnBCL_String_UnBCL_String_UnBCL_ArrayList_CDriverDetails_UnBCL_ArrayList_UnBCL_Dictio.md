# pGetDriverInfoFromModule(UnBCL::String *,UnBCL::String *,UnBCL::ArrayList<CDriverDetails *> *,UnBCL::ArrayList<UnBCL::DictionaryEntry<CGlobalPath *,CDriverInstallInfo *> *> *)

- ea: `0x180279148`
- end: `0x1802798e3`
- name: `?pGetDriverInfoFromModule@@YAJPEAVString@UnBCL@@0PEAV?$ArrayList@PEAVCDriverDetails@@@2@PEAV?$ArrayList@PEAV?$DictionaryEntry@PEAVCGlobalPath@@PEAVCDriverInstallInfo@@@UnBCL@@@2@@Z`
- size: `1947`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1802724e8`

## callees

- `0x180057dec`
- `0x1802713f4`
- `0x1802788d8`
- `0x180278e64`
- `0x180279148`
- `0x1802e2078`
- `0x180509010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18027926f`
- `KERNEL32!GetLastError` at `0x18027926f`
- `unbcl!?EndsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x180279632`
- `unbcl!?EndsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x180279632`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x180279658`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x180279658`
- `unbcl!?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802797fe`
- `unbcl!?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18027981f`
- `unbcl!?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802797fe`
- `unbcl!?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18027981f`
- `unbcl!?Remove@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x180279605`
- `unbcl!?Remove@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x18027966a`
- `unbcl!?Remove@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x180279605`
- `unbcl!?Remove@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x18027966a`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18027922a`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18027922a`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1802795e1`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1802795e1`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802791d9`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x180279405`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802791d9`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x180279405`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x180279856`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x180279856`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18027931a`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18027931a`
- `unbcl!?IsPathRooted@Path@UnBCL@@SAHPEBVString@2@@Z` at `0x1802791ab`
- `unbcl!?IsPathRooted@Path@UnBCL@@SAHPEBVString@2@@Z` at `0x1802791ab`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180279260`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180279345`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802795b9`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180279816`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180279837`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180279844`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180279260`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180279345`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802795b9`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180279816`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180279837`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180279844`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802791a1`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802791a1`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802791c1`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802792fe`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802793ac`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802793d0`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802791c1`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802792fe`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802793ac`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802793d0`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802791ff`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180279249`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18027942f`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18027947e`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802794e4`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180279543`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802795a5`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180279687`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802796fd`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18027976c`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802791ff`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180279249`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18027942f`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18027947e`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802794e4`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180279543`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802795a5`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180279687`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802796fd`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18027976c`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802795cb`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802795f2`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027961f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180279641`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027964f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802796c6`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802795cb`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802795f2`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027961f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180279641`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027964f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802796c6`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027920b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180279217`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802794af`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180279515`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180279574`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802796b8`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802796cf`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027973a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027920b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180279217`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802794af`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180279515`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180279574`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802796b8`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802796cf`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027973a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180279255`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802792e9`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18027943a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180279489`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802794ef`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18027954e`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802795b0`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180279692`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180279708`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180279714`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180279777`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18027986b`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180279876`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802798b9`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180279255`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802792e9`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18027943a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180279489`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802794ef`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18027954e`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802795b0`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180279692`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180279708`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180279714`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180279777`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18027986b`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180279876`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802798b9`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802791ee`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180279238`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180279420`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18027946f`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802794d5`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180279534`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180279593`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180279613`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180279677`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802796ee`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18027975d`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18027980b`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18027982c`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802791ee`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180279238`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180279420`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18027946f`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802794d5`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180279534`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180279593`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180279613`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180279677`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802796ee`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18027975d`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18027980b`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18027982c`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802792dd`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802792dd`
- `WDSCORE!CurrentIP` at `0x180279277`
- `WDSCORE!CurrentIP` at `0x180279277`

## string_xrefs

- `0x180279280`: `GetDriverInfoFromModule: Cannot calculate full path for module to examine.`
- `0x180279223`: `%s\System32\Drivers\%s`

## pseudocode

```c

```
