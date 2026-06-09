# CImageInfoSet::CreateFromWDSServer(ushort const *,tagWDS_CLI_CRED *,CImageInfoSet * *)

- ea: `0x180297410`
- end: `0x180297e46`
- name: `?CreateFromWDSServer@CImageInfoSet@@SAJPEBGPEAUtagWDS_CLI_CRED@@PEAPEAV1@@Z`
- size: `2614`
- prototype: `void __fastcall __noreturn(PWSTR pwszServer, PWDS_CLI_CRED pCred, struct CImageInfoSet **)`
- caller_count: `2`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x1800c03c0`
- `0x1800cc290`

## callees

- `0x18001413d`
- `0x18002cab4`
- `0x180044810`
- `0x180057dec`
- `0x1800ae494`
- `0x1800b3888`
- `0x18010f584`
- `0x18010f5c8`
- `0x18028f7c0`
- `0x180290b2c`
- `0x18029206c`
- `0x180292878`
- `0x180297410`
- `0x18029acd0`
- `0x180509010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18029761e`
- `KERNEL32!GetLastError` at `0x1802977ca`
- `KERNEL32!GetLastError` at `0x18029784b`
- `KERNEL32!GetLastError` at `0x1802979c2`
- `KERNEL32!GetLastError` at `0x180297bf3`
- `KERNEL32!GetLastError` at `0x180297c8f`
- `KERNEL32!GetLastError` at `0x180297d2b`
- `KERNEL32!GetLastError` at `0x180297d93`
- `KERNEL32!GetLastError` at `0x18029761e`
- `KERNEL32!GetLastError` at `0x1802977ca`
- `KERNEL32!GetLastError` at `0x18029784b`
- `KERNEL32!GetLastError` at `0x1802979c2`
- `KERNEL32!GetLastError` at `0x180297bf3`
- `KERNEL32!GetLastError` at `0x180297c8f`
- `KERNEL32!GetLastError` at `0x180297d2b`
- `KERNEL32!GetLastError` at `0x180297d93`
- `MPR!WNetAddConnection2W` at `0x18029760a`
- `MPR!WNetAddConnection2W` at `0x18029760a`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802979ad`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802979ad`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG00@Z` at `0x1802974e1`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG00@Z` at `0x180297581`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG00@Z` at `0x1802974e1`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG00@Z` at `0x180297581`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x180297450`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x180297450`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x180297bd3`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x180297bd3`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180297960`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180297982`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x1802979d8`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180297960`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180297982`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x1802979d8`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180297911`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180297911`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x180297932`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x180297932`
- `unbcl!??4?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180297946`
- `unbcl!??4?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180297946`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180297955`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180297b10`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180297b52`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180297bb1`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180297955`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180297b10`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180297b52`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180297bb1`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802978d9`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802978d9`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG000@Z` at `0x1802978bc`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG000@Z` at `0x1802978bc`
- `unbcl!?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x180297a88`
- `unbcl!?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x180297a88`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180297a99`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180297a99`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802974be`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802974be`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18029752d`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18029752d`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180297511`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802976be`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802976f4`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802978f3`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180297511`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802976be`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802976f4`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802978f3`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180297503`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18029755e`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180297503`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18029755e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802975c7`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802975e6`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802975c7`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802975e6`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802975d0`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802975ef`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802979fe`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802975d0`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802975ef`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802979fe`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18029756a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18029769b`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802976aa`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180297b1f`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180297b61`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180297bc0`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18029756a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18029769b`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802976aa`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180297b1f`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180297b61`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180297bc0`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802974ef`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18029754a`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180297592`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802978cd`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802974ef`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18029754a`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180297592`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802978cd`
- `WDSCORE!WdsSetupLogMessageW` at `0x180297684`
- `WDSCORE!WdsSetupLogMessageW` at `0x180297a5a`
- `WDSCORE!WdsSetupLogMessageW` at `0x180297c5d`
- `WDSCORE!WdsSetupLogMessageW` at `0x180297cf8`
- `WDSCORE!WdsSetupLogMessageW` at `0x180297d8d`
- `WDSCORE!WdsSetupLogMessageW` at `0x180297df5`
- `WDSCORE!WdsSetupLogMessageW` at `0x180297684`
- `WDSCORE!WdsSetupLogMessageW` at `0x180297a5a`
- `WDSCORE!WdsSetupLogMessageW` at `0x180297c5d`
- `WDSCORE!WdsSetupLogMessageW` at `0x180297cf8`
- `WDSCORE!WdsSetupLogMessageW` at `0x180297d8d`
- `WDSCORE!WdsSetupLogMessageW` at `0x180297df5`
- `WDSCORE!CurrentIP` at `0x180297626`
- `WDSCORE!CurrentIP` at `0x1802977d2`
- `WDSCORE!CurrentIP` at `0x180297853`
- `WDSCORE!CurrentIP` at `0x1802979ca`
- `WDSCORE!CurrentIP` at `0x180297bfc`
- `WDSCORE!CurrentIP` at `0x180297c97`
- `WDSCORE!CurrentIP` at `0x180297d33`
- `WDSCORE!CurrentIP` at `0x180297d9b`
- `WDSCORE!CurrentIP` at `0x180297626`
- `WDSCORE!CurrentIP` at `0x1802977d2`
- `WDSCORE!CurrentIP` at `0x180297853`
- `WDSCORE!CurrentIP` at `0x1802979ca`
- `WDSCORE!CurrentIP` at `0x180297bfc`
- `WDSCORE!CurrentIP` at `0x180297c97`
- `WDSCORE!CurrentIP` at `0x180297d33`
- `WDSCORE!CurrentIP` at `0x180297d9b`
- `WDSCLIENTAPI!WdsCliGetWimImageReferenceFile` at `0x180297837`
- `WDSCLIENTAPI!WdsCliGetWimImageReferenceFile` at `0x180297837`
- `WDSCLIENTAPI!WdsCliFindFirstImage` at `0x18029775b`
- `WDSCLIENTAPI!WdsCliFindFirstImage` at `0x18029775b`
- `WDSCLIENTAPI!WdsCliAuthorizeSession` at `0x180297495`
- `WDSCLIENTAPI!WdsCliAuthorizeSession` at `0x180297495`
- `WDSCLIENTAPI!WdsCliCreateSession` at `0x180297472`
- `WDSCLIENTAPI!WdsCliCreateSession` at `0x180297472`
- `WDSCLIENTAPI!WdsCliGetImagePath` at `0x180297789`
- `WDSCLIENTAPI!WdsCliGetImagePath` at `0x180297789`
- `WDSCLIENTAPI!WdsCliFindNextImage` at `0x180297b2f`
- `WDSCLIENTAPI!WdsCliFindNextImage` at `0x180297b2f`
- `WDSCLIENTAPI!WdsCliGetImageNamespace` at `0x1802977b6`
- `WDSCLIENTAPI!WdsCliGetImageNamespace` at `0x1802977b6`

## string_xrefs

- `0x180297c0b`: `Cannot create WDS client session to server %s. Error: 0x%08X`
- `0x180297655`: `CImageInfoSet::CreateFromWDSServer`
- `0x18029768c`: `CImageInfoSet::CreateFromWDSServer`
- `0x1802976b2`: `CImageInfoSet::CreateFromWDSServer`
- `0x180297ae7`: `CImageInfoSet::CreateFromWDSServer`
- `0x180297c2e`: `CImageInfoSet::CreateFromWDSServer`
- `0x180297cc9`: `CImageInfoSet::CreateFromWDSServer`
- `0x180297d42`: `Failed to retrieve image path for image on server %s. Error: 0x%08X`

## pseudocode

```c

```
