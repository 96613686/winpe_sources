# OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths(ushort const *,UnBCL::ArrayList<UnBCL::String *> * *)

- ea: `0x18047a9b8`
- end: `0x18047b6ad`
- name: `?GetPageFilePaths@CCrashDumpExtractor@OSRollbackUtils@@KAKPEBGPEAPEAV?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@Z`
- size: `3317`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18047a398`

## callees

- `0x18001413d`
- `0x180044810`
- `0x180057dec`
- `0x18012b26c`
- `0x180131e08`
- `0x180404554`
- `0x18040463c`
- `0x18047a9b8`
- `0x1804bbfa0`
- `0x180509010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18047acec`
- `ADVAPI32!RegOpenKeyExW` at `0x18047acec`
- `ADVAPI32!RegLoadKeyW` at `0x18047ac94`
- `ADVAPI32!RegLoadKeyW` at `0x18047ac94`
- `KERNEL32!GetProcessHeap` at `0x18047afce`
- `KERNEL32!GetProcessHeap` at `0x18047afce`
- `KERNEL32!HeapFree` at `0x18047afdc`
- `KERNEL32!HeapFree` at `0x18047afdc`
- `KERNEL32!GetLastError` at `0x18047add4`
- `KERNEL32!GetLastError` at `0x18047ade5`
- `KERNEL32!GetLastError` at `0x18047af3d`
- `KERNEL32!GetLastError` at `0x18047b053`
- `KERNEL32!GetLastError` at `0x18047b216`
- `KERNEL32!GetLastError` at `0x18047b2ce`
- `KERNEL32!GetLastError` at `0x18047b474`
- `KERNEL32!GetLastError` at `0x18047b526`
- `KERNEL32!GetLastError` at `0x18047b5bf`
- `KERNEL32!GetLastError` at `0x18047b5cb`
- `KERNEL32!GetLastError` at `0x18047add4`
- `KERNEL32!GetLastError` at `0x18047ade5`
- `KERNEL32!GetLastError` at `0x18047af3d`
- `KERNEL32!GetLastError` at `0x18047b053`
- `KERNEL32!GetLastError` at `0x18047b216`
- `KERNEL32!GetLastError` at `0x18047b2ce`
- `KERNEL32!GetLastError` at `0x18047b474`
- `KERNEL32!GetLastError` at `0x18047b526`
- `KERNEL32!GetLastError` at `0x18047b5bf`
- `KERNEL32!GetLastError` at `0x18047b5cb`
- `unbcl!?get_CString@StringBuilder@UnBCL@@QEBAPEBGXZ` at `0x18047af58`
- `unbcl!?get_CString@StringBuilder@UnBCL@@QEBAPEBGXZ` at `0x18047af58`
- `unbcl!?Append@StringBuilder@UnBCL@@QEAAPEAV12@PEBG@Z` at `0x18047aefd`
- `unbcl!?Append@StringBuilder@UnBCL@@QEAAPEAV12@PEBG@Z` at `0x18047af1a`
- `unbcl!?Append@StringBuilder@UnBCL@@QEAAPEAV12@PEBG@Z` at `0x18047af37`
- `unbcl!?Append@StringBuilder@UnBCL@@QEAAPEAV12@PEBG@Z` at `0x18047aefd`
- `unbcl!?Append@StringBuilder@UnBCL@@QEAAPEAV12@PEBG@Z` at `0x18047af1a`
- `unbcl!?Append@StringBuilder@UnBCL@@QEAAPEAV12@PEBG@Z` at `0x18047af37`
- `unbcl!??1StringBuilder@UnBCL@@UEAA@XZ` at `0x18047afc8`
- `unbcl!??1StringBuilder@UnBCL@@UEAA@XZ` at `0x18047afc8`
- `unbcl!??0StringBuilder@UnBCL@@QEAA@XZ` at `0x18047aede`
- `unbcl!??0StringBuilder@UnBCL@@QEAA@XZ` at `0x18047aede`
- `unbcl!?Steal@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x18047b429`
- `unbcl!?Steal@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x18047b429`
- `unbcl!?Split@String@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@PEBG@Z` at `0x18047b2a8`
- `unbcl!?Split@String@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@PEBG@Z` at `0x18047b2a8`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18047abc1`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18047abc1`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18047ad2d`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18047ad2d`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x18047b0e8`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x18047b157`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x18047b0e8`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x18047b157`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x18047ab93`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x18047ab93`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x18047b38b`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x18047b38b`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18047ac3c`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18047b1be`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18047ac3c`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18047b1be`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x18047b411`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x18047b411`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18047aa6a`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18047b34f`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18047aa6a`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18047b34f`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18047aa3a`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18047aa3a`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x18047aa5b`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x18047aa5b`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047b442`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047b442`
- `unbcl!?Substring@String@UnBCL@@QEBAPEAV12@H@Z` at `0x18047b105`
- `unbcl!?Substring@String@UnBCL@@QEBAPEAV12@H@Z` at `0x18047b178`
- `unbcl!?Substring@String@UnBCL@@QEBAPEAV12@H@Z` at `0x18047b105`
- `unbcl!?Substring@String@UnBCL@@QEBAPEAV12@H@Z` at `0x18047b178`
- `unbcl!??0MultiSz@UnBCL@@QEAA@PEBE_KPEAK@Z` at `0x18047aea4`
- `unbcl!??0MultiSz@UnBCL@@QEAA@PEBE_KPEAK@Z` at `0x18047aea4`
- `unbcl!?get_Chars@String@UnBCL@@QEBAAEBGH@Z` at `0x18047abfa`
- `unbcl!?get_Chars@String@UnBCL@@QEBAAEBGH@Z` at `0x18047abfa`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047b198`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047b198`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18047abe1`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18047ac59`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18047ac68`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18047b201`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18047abe1`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18047ac59`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18047ac68`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18047b201`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18047abb7`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18047ac1b`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18047ac2f`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18047b02f`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18047b1b1`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18047abb7`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18047ac1b`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18047ac2f`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18047b02f`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18047b1b1`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18047aa1a`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18047ae79`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18047b013`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18047b36f`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18047aa1a`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18047ae79`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18047b013`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18047b36f`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18047b12a`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18047b1e3`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18047b12a`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18047b1e3`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047abef`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047ac73`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047ada1`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047adf7`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047b06b`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047b0d5`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047b0f7`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047b144`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047b16a`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047b22e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047b298`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047b48b`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047abef`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047ac73`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047ada1`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047adf7`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047b06b`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047b0d5`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047b0f7`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047b144`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047b16a`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047b22e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047b298`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047b48b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047ac7c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047adaa`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047ae00`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047b074`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047b237`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047b2e4`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047b494`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047ac7c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047adaa`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047ae00`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047b074`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047b237`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047b2e4`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047b494`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047acbd`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047b139`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047b1f2`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047b210`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047b3bc`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047b66c`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047b67b`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047acbd`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047b139`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047b1f2`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047b210`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047b3bc`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047b66c`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047b67b`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18047abd2`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18047ac4a`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18047ad3e`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18047b04c`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18047b116`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18047b189`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18047b1cf`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18047abd2`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18047ac4a`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18047ad3e`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18047b04c`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18047b116`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18047b189`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18047b1cf`
- `unbcl!?get_Buffer@MultiSz@UnBCL@@QEBAPEBGXZ` at `0x18047aff2`
- `unbcl!?get_Buffer@MultiSz@UnBCL@@QEBAPEBGXZ` at `0x18047aff2`
- `WDSCORE!WdsSetupLogMessageW` at `0x18047ae64`
- `WDSCORE!WdsSetupLogMessageW` at `0x18047afb9`
- `WDSCORE!WdsSetupLogMessageW` at `0x18047b0ca`
- `WDSCORE!WdsSetupLogMessageW` at `0x18047b28d`
- `WDSCORE!WdsSetupLogMessageW` at `0x18047b341`
- `WDSCORE!WdsSetupLogMessageW` at `0x18047b4f6`
- `WDSCORE!WdsSetupLogMessageW` at `0x18047b590`
- `WDSCORE!WdsSetupLogMessageW` at `0x18047b635`
- `WDSCORE!WdsSetupLogMessageW` at `0x18047ae64`
- `WDSCORE!WdsSetupLogMessageW` at `0x18047afb9`
- `WDSCORE!WdsSetupLogMessageW` at `0x18047b0ca`
- `WDSCORE!WdsSetupLogMessageW` at `0x18047b28d`
- `WDSCORE!WdsSetupLogMessageW` at `0x18047b341`
- `WDSCORE!WdsSetupLogMessageW` at `0x18047b4f6`
- `WDSCORE!WdsSetupLogMessageW` at `0x18047b590`
- `WDSCORE!WdsSetupLogMessageW` at `0x18047b635`
- `WDSCORE!CurrentIP` at `0x18047addc`
- `WDSCORE!CurrentIP` at `0x18047af45`
- `WDSCORE!CurrentIP` at `0x18047b05b`
- `WDSCORE!CurrentIP` at `0x18047b21e`

## string_xrefs

- `0x18047ac0c`: `Windows\System32\config\SYSTEM`
- `0x18047ae1c`: `OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths: Could not get %s value from %s: Error %u`
- `0x18047b5df`: `OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths: Failed to get current control set: Error %u`
- `0x18047b53a`: `OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths: Failed to open SYSTEM hive: Error %u`
- `0x18047b4a0`: `OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths: Failed to load offline SYSTEM hive [%s]: Error %u`
- `0x18047b2ed`: `  Resolved path: %s`
- `0x18047b240`: `  Unresolved path: %s`
- `0x18047b07d`: `Examining page file path '%s' extracted from OS`
- `0x18047af6c`: `OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths: Problems parsing MULTI_SZ data from %s:%s`
- `0x18047ad74`: `base\ntsetup\lib\rollback\src\crashdumputils.cpp`
- `0x18047b31b`: `base\ntsetup\lib\rollback\src\crashdumputils.cpp`
- `0x18047b3df`: `base\ntsetup\lib\rollback\src\crashdumputils.cpp`
- `0x18047b4d0`: `base\ntsetup\lib\rollback\src\crashdumputils.cpp`
- `0x18047b56a`: `base\ntsetup\lib\rollback\src\crashdumputils.cpp`
- `0x18047b60f`: `base\ntsetup\lib\rollback\src\crashdumputils.cpp`
- `0x18047ad6d`: `OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths`
- `0x18047b3d8`: `OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths`
- `0x18047b4c4`: `OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths`
- `0x18047b55e`: `OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths`
- `0x18047b603`: `OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths`
- `0x18047aa85`: `$ROLLBACK_OFFLINE_RW$SYSTEM`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
void __fastcall __noreturn OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths(
        const unsigned __int16 *a1,
        __int64 *a2)
{
  const char **v3; // rax
  const char **v4; // rbx
  __int64 v5; // rax
  const struct UnBCL::String *v6; // rax
  struct UnBCL::String *v7; // rax
  UnBCL::String *v8; // rax
  const struct UnBCL::String *v9; // rbx
  const struct UnBCL::String *v10; // rax
  struct UnBCL::String *v11; // rax
  UnBCL::String *v12; // rax
  const WCHAR *CString; // rax
  LSTATUS KeyW; // ebx
  WCHAR *v15; // rbx
  LSTATUS v16; // esi
  unsigned int Dword; // eax
  struct UnBCL::String *v18; // rax
  const char **i; // rbx
  UnBCL::String *v20; // rax
  const unsigned __int16 *v21; // rax
  unsigned __int8 *MultiSz; // rdi
  DWORD v23; // ebx
  __int64 v24; // rcx
  __int64 v25; // rdi
  UnBCL::String *v26; // rax
  const char *v27; // rax
  struct tagLOG_PARTIAL_MSG *v28; // rax
  UnBCL::MultiSz *v29; // rax
  UnBCL::MultiSz *v30; // rbx
  char v31; // al
  DWORD v32; // ebx
  __int64 v33; // rcx
  const char *v34; // rax
  struct tagLOG_PARTIAL_MSG *v35; // rax
  HANDLE ProcessHeap; // rax
  UnBCL::MultiSz *v37; // rax
  const unsigned __int16 *j; // rdi
  UnBCL::String *v39; // rax
  UnBCL::String *v40; // rbx
  DWORD v41; // ebx
  __int64 v42; // rcx
  UnBCL::String *v43; // rax
  const char *v44; // rax
  struct tagLOG_PARTIAL_MSG *v45; // rax
  UnBCL::String *v46; // rax
  UnBCL::String *v47; // rax
  struct UnBCL::String *v48; // rax
  UnBCL::String *v49; // rax
  UnBCL::String *v50; // rax
  struct UnBCL::String *v51; // rax
  const struct UnBCL::String *P; // rbx
  const struct UnBCL::String *v53; // rax
  struct UnBCL::String *v54; // rax
  DWORD v55; // ebx
  __int64 v56; // rcx
  UnBCL::String *v57; // rax
  const char *v58; // rax
  struct tagLOG_PARTIAL_MSG *v59; // rax
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 v62; // rcx
  UnBCL::String *v63; // rsi
  DWORD v64; // ebx
  __int64 v65; // rcx
  const char *v66; // rax
  struct tagLOG_PARTIAL_MSG *v67; // rax
  __int64 v68; // rax
  __int64 v69; // r12
  UnBCL::String *v70; // rax
  UnBCL::String *v71; // rbx
  __int64 v72; // rax
  __int64 v73; // rax
  DWORD LastError; // edi
  __int64 v75; // rsi
  UnBCL::String *v76; // rax
  const char *v77; // rax
  struct tagLOG_PARTIAL_MSG *v78; // rax
  DWORD v79; // edi
  __int64 v80; // rbx
  struct tagLOG_PARTIAL_MSG *v81; // rax
  DWORD v82; // esi
  __int64 v83; // rdi
  struct tagLOG_PARTIAL_MSG *v84; // rax
  const WCHAR *v85; // rbp
  HKEY v86; // rcx
  LSTATUS v87; // esi
  DWORD v88; // edi
  __int64 v89; // rbx
  struct tagLOG_PARTIAL_MSG *v90; // rax
  const WCHAR *v91; // rdx
  __int64 v92; // [rsp+0h] [rbp-2F8h] BYREF
  PHKEY phkResult; // [rsp+20h] [rbp-2D8h]
  __int64 v94; // [rsp+60h] [rbp-298h] BYREF
  unsigned int v95; // [rsp+68h] [rbp-290h] BYREF
  int v96; // [rsp+6Ch] [rbp-28Ch]
  DWORD v97; // [rsp+70h] [rbp-288h]
  _BYTE v98[16]; // [rsp+78h] [rbp-280h] BYREF
  int v99; // [rsp+88h] [rbp-270h]
  const char **v100; // [rsp+90h] [rbp-268h]
  HKEY v101; // [rsp+98h] [rbp-260h] BYREF
  _BYTE v102[24]; // [rsp+A0h] [rbp-258h] BYREF
  UnBCL::MultiSz *v103; // [rsp+B8h] [rbp-240h]
  _QWORD v104[2]; // [rsp+C0h] [rbp-238h] BYREF
  _BYTE v105[16]; // [rsp+D0h] [rbp-228h] BYREF
  _QWORD *pExceptionObject; // [rsp+E0h] [rbp-218h] BYREF
  _QWORD *v107; // [rsp+E8h] [rbp-210h] BYREF
  _QWORD *v108; // [rsp+F0h] [rbp-208h] BYREF
  const unsigned __int16 *v109; // [rsp+F8h] [rbp-200h]
  _QWORD *v110; // [rsp+100h] [rbp-1F8h] BYREF
  __int64 *v111; // [rsp+110h] [rbp-1E8h]
  _BYTE v112[16]; // [rsp+118h] [rbp-1E0h] BYREF
  _BYTE v113[24]; // [rsp+128h] [rbp-1D0h] BYREF
  _BYTE v114[24]; // [rsp+140h] [rbp-1B8h] BYREF
  _BYTE v115[16]; // [rsp+158h] [rbp-1A0h] BYREF
  _BYTE v116[16]; // [rsp+168h] [rbp-190h] BYREF
  _BYTE v117[16]; // [rsp+178h] [rbp-180h] BYREF
  __int64 v118; // [rsp+188h] [rbp-170h]
  _QWORD v119[7]; // [rsp+190h] [rbp-168h] BYREF
  WCHAR SubKey[28]; // [rsp+1C8h] [rbp-130h] BYREF
  __int128 v121; // [rsp+200h] [rbp-F8h] BYREF
  __int64 v122; // [rsp+210h] [rbp-E8h]
  _OWORD v123[2]; // [rsp+218h] [rbp-E0h] BYREF
  int v124; // [rsp+238h] [rbp-C0h]
  _OWORD v125[7]; // [rsp+240h] [rbp-B8h] BYREF
  wchar_t v126; // [rsp+2B0h] [rbp-48h]

  v118 = -2;
  v109 = a1;
  v111 = a2;
  v97 = 0;
  v99 = 0;
  v101 = 0;
  v3 = (const char **)UnBCL::Object::operator new(0xB0u);
  v4 = v3;
  v100 = v3;
  if ( v3 )
  {
    UnBCL::ArrayList<UnBCL::String *>::ArrayList<UnBCL::String *>(v3, 1);
    v4[6] = (const char *)UnBCL::ArrayList<UnBCL::String *>::`local vftable'{for `UnBCL::Object'};
  }
  else
  {
    v4 = 0;
  }
  UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v105, v4);
  v5 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v105);
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 40LL))(v5, 1);
  wcscpy(SubKey, L"$ROLLBACK_OFFLINE_RW$SYSTEM");
  v125[0] = *(_OWORD *)L"ControlSet%03u\\Control\\Session Manager\\Memory Management";
  v125[1] = *(_OWORD *)L"et%03u\\Control\\Session Manager\\Memory Management";
  v125[2] = *(_OWORD *)L"ontrol\\Session Manager\\Memory Management";
  v125[3] = *(_OWORD *)L"ession Manager\\Memory Management";
  v125[4] = *(_OWORD *)L"anager\\Memory Management";
  v125[5] = *(_OWORD *)L"emory Management";
  v125[6] = *(_OWORD *)L"nagement";
  v126 = aControlset03uC_0[56];
  v121 = *(_OWORD *)L"PagingFiles";
  v122 = *(_QWORD *)L"les";
  v123[0] = *(_OWORD *)L"ExistingPageFiles";
  v123[1] = *(_OWORD *)L"PageFiles";
  v124 = *(_DWORD *)L"s";
  v96 = 0;
  UnBCL::Exception::Exception((UnBCL::Exception *)v119);
  v119[0] = &`OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths'::`3'::CXXXXXHandledException::`vftable';
  try
  {
    try
    {
      v6 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v102, L"%WINDIR%");
      v7 = UnBCL::Environment::ExpandEnvironmentVariables(v6);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v117, v7);
      UnBCL::String::~String((UnBCL::String *)v102);
      v8 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v117);
      if ( *UnBCL::String::get_Chars(v8, 0) == *a1 )
      {
        v15 = (WCHAR *)L"SYSTEM";
      }
      else
      {
        v9 = (const struct UnBCL::String *)UnBCL::String::String(
                                             (UnBCL::String *)v113,
                                             L"Windows\\System32\\config\\SYSTEM");
        v10 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v114, a1);
        v11 = UnBCL::Path::Combine(v10, v9);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v98, v11);
        UnBCL::String::~String((UnBCL::String *)v114);
        UnBCL::String::~String((UnBCL::String *)v113);
        v12 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v98);
        CString = UnBCL::String::get_CString(v12);
        KeyW = RegLoadKeyW(HKEY_LOCAL_MACHINE, SubKey, CString);
        v97 = KeyW;
        if ( KeyW )
        {
          LastError = GetLastError();
          v75 = ((__int64 (*)(void))CurrentIP)();
          v76 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v98);
          v77 = (const char *)UnBCL::String::get_CString(v76);
          v78 = ConstructPartialMsgW(
                  0x2000000u,
                  "OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths: Failed to load offline SYSTEM hive [%s]: Error %u",
                  v77,
                  KeyW);
          WdsSetupLogMessageW(
            v78,
            409600,
            L"D",
            0,
            60,
            L"base\\ntsetup\\lib\\rollback\\src\\crashdumputils.cpp",
            L"OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths",
            v75,
            LastError,
            0,
            0);
          v96 = 1;
          pExceptionObject = v119;
          throw (`OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths(ushort const *,UnBCL::ArrayList<UnBCL::String *> * *)'::`3'::CXXXXXHandledException **)&pExceptionObject;
        }
        v99 = 1;
        v15 = SubKey;
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v98);
      }
      v16 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v15, 0, 0x20019u, &v101);
      v97 = v16;
      if ( v16 )
      {
        v79 = GetLastError();
        v80 = ((__int64 (*)(void))CurrentIP)();
        v81 = ConstructPartialMsgW(
                0x2000000u,
                "OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths: Failed to open SYSTEM hive: Error %u",
                v16);
        WdsSetupLogMessageW(
          v81,
          409600,
          L"D",
          0,
          75,
          L"base\\ntsetup\\lib\\rollback\\src\\crashdumputils.cpp",
          L"OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths",
          v80,
          v79,
          0,
          0);
        v96 = 1;
        v107 = v119;
        throw (`OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths(ushort const *,UnBCL::ArrayList<UnBCL::String *> * *)'::`3'::CXXXXXHandledException **)&v107;
      }
      Dword = RegGetDword(v101, L"Select", L"Current");
      if ( !Dword )
      {
        v97 = GetLastError();
        v82 = GetLastError();
        v83 = ((__int64 (*)(void))CurrentIP)();
        v84 = ConstructPartialMsgW(
                0x2000000u,
                "OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths: Failed to get current control set: Error %u",
                v97);
        WdsSetupLogMessageW(
          v84,
          409600,
          L"D",
          0,
          84,
          L"base\\ntsetup\\lib\\rollback\\src\\crashdumputils.cpp",
          L"OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths",
          v83,
          v82,
          0,
          0);
        v96 = 1;
        v108 = v119;
        throw (`OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths(ushort const *,UnBCL::ArrayList<UnBCL::String *> * *)'::`3'::CXXXXXHandledException **)&v108;
      }
      v18 = UnBCL::String::Format((const unsigned __int16 *)v125, Dword);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v112, v18);
      v104[0] = v123;
      v104[1] = &v121;
      for ( i = (const char **)v104; ; i = v100 + 1 )
      {
        v100 = i;
        if ( i == (const char **)v105 )
          break;
        LODWORD(v94) = 0;
        v20 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v112);
        v21 = UnBCL::String::get_CString(v20);
        MultiSz = (unsigned __int8 *)RegGetMultiSz(v101, v21, *i, &v94, (_DWORD)phkResult);
        if ( MultiSz )
        {
          v95 = 0;
          v29 = (UnBCL::MultiSz *)UnBCL::Object::operator new(0x70u);
          v30 = v29;
          v103 = v29;
          if ( v29 )
          {
            LODWORD(phkResult) = 1;
            UnBCL::MultiSz::MultiSz(v29, MultiSz, (unsigned int)v94, &v95);
            *((_QWORD *)v30 + 5) = &UnBCL::MultiSz::`local vftable'{for `UnBCL::Object'};
          }
          else
          {
            v30 = 0;
          }
          UnBCL::SmartPtr<UnBCL::MultiSz>::SmartPtr<UnBCL::MultiSz>(v114, v30);
          if ( v95 )
          {
            UnBCL::StringBuilder::StringBuilder((UnBCL::StringBuilder *)v102);
            v31 = v95;
            if ( (v95 & 1) != 0 )
            {
              UnBCL::StringBuilder::Append((UnBCL::StringBuilder *)v102, L" [Byte Truncated]");
              v31 = v95;
            }
            if ( (v31 & 2) != 0 )
            {
              UnBCL::StringBuilder::Append((UnBCL::StringBuilder *)v102, L" [Missing List Terminator]");
              v31 = v95;
            }
            if ( (v31 & 4) != 0 )
              UnBCL::StringBuilder::Append((UnBCL::StringBuilder *)v102, L" [Missing String Terminator]");
            v32 = GetLastError();
            v94 = CurrentIP(v33);
            v34 = (const char *)UnBCL::StringBuilder::get_CString((UnBCL::StringBuilder *)v102);
            v35 = ConstructPartialMsgW(
                    0x3000000u,
                    "OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths: Problems parsing MULTI_SZ data from %s:%s",
                    *v100,
                    v34);
            WdsSetupLogMessageW(
              v35,
              409600,
              L"D",
              0,
              124,
              L"base\\ntsetup\\lib\\rollback\\src\\crashdumputils.cpp",
              L"OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths",
              v94,
              v32,
              0,
              0);
            UnBCL::StringBuilder::~StringBuilder((UnBCL::StringBuilder *)v102);
          }
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, MultiSz);
          v37 = (UnBCL::MultiSz *)RAII::CAutoCleanupBase<void *>::operator->(v114);
          for ( j = UnBCL::MultiSz::get_Buffer(v37); j && *j; j += v72 + 1 )
          {
            v39 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
            v40 = v39;
            v103 = v39;
            if ( v39 )
            {
              UnBCL::String::String(v39, j);
              *(_QWORD *)v40 = &UnBCL::String::`local vftable';
            }
            else
            {
              v40 = 0;
            }
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v98, v40);
            v41 = GetLastError();
            v94 = CurrentIP(v42);
            v43 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v98);
            v44 = (const char *)UnBCL::String::get_CString(v43);
            v45 = ConstructPartialMsgW(0x4000000u, "Examining page file path '%s' extracted from OS", v44);
            WdsSetupLogMessageW(
              v45,
              409600,
              L"D",
              0,
              135,
              L"base\\ntsetup\\lib\\rollback\\src\\crashdumputils.cpp",
              L"OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths",
              v94,
              v41,
              0,
              0);
            v46 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v98);
            if ( UnBCL::String::StartsWith(v46, L"\\??\\", 1) )
            {
              v47 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v98);
              v48 = UnBCL::String::Substring(v47, 4);
              UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v115, v48);
              UnBCL::SmartPtr<UnBCL::String>::operator=(v98, v115);
              UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v115);
            }
            v49 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v98);
            if ( UnBCL::String::StartsWith(v49, L"?:\\", 1) )
            {
              v50 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v98);
              v51 = UnBCL::String::Substring(v50, 3);
              UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v113, v51);
              P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v113);
              v53 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v102, v109);
              v54 = UnBCL::Path::Combine(v53, P);
              UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v116, v54);
              UnBCL::SmartPtr<UnBCL::String>::operator=(v98, v116);
              UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v116);
              UnBCL::String::~String((UnBCL::String *)v102);
              UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v113);
            }
            v55 = GetLastError();
            v94 = CurrentIP(v56);
            v57 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v98);
            v58 = (const char *)UnBCL::String::get_CString(v57);
            v59 = ConstructPartialMsgW(0x4000000u, "  Unresolved path: %s", v58);
            WdsSetupLogMessageW(
              v59,
              409600,
              L"D",
              0,
              148,
              L"base\\ntsetup\\lib\\rollback\\src\\crashdumputils.cpp",
              L"OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths",
              v94,
              v55,
              0,
              0);
            v60 = UnBCL::SmartPtr<UnBCL::String>::operator->(v98);
            v61 = UnBCL::String::Split(v60, L" ");
            v62 = v61 + 8 + *(int *)(*(_QWORD *)(v61 + 8) + 16LL);
            v63 = *(UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v62 + 24LL))(v62, 0);
            v64 = GetLastError();
            v94 = CurrentIP(v65);
            v66 = (const char *)UnBCL::String::get_CString(v63);
            v67 = ConstructPartialMsgW(0x4000000u, "  Resolved path: %s", v66);
            WdsSetupLogMessageW(
              v67,
              409600,
              L"D",
              0,
              156,
              L"base\\ntsetup\\lib\\rollback\\src\\crashdumputils.cpp",
              L"OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths",
              v94,
              v64,
              0,
              0);
            v68 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v105);
            v69 = v68 + *(int *)(*(_QWORD *)(v68 + 8) + 16LL);
            v94 = *(_QWORD *)(v69 + 8);
            v70 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
            v71 = v70;
            v103 = v70;
            if ( v70 )
            {
              UnBCL::String::String(v70, v63);
              *(_QWORD *)v71 = &UnBCL::String::`local vftable';
            }
            else
            {
              v71 = 0;
            }
            (*(void (__fastcall **)(__int64, UnBCL::String *))(v94 + 40))(v69 + 8, v71);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v98);
            v72 = -1;
            do
              ++v72;
            while ( j[v72] );
          }
          UnBCL::SmartPtr<UnBCL::MultiSz>::~SmartPtr<UnBCL::MultiSz>(v114);
        }
        else
        {
          v23 = GetLastError();
          v25 = CurrentIP(v24);
          LODWORD(v94) = GetLastError();
          v26 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v112);
          v27 = (const char *)UnBCL::String::get_CString(v26);
          v28 = ConstructPartialMsgW(
                  0x3000000u,
                  "OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths: Could not get %s value from %s: Error %u",
                  *v100,
                  v27,
                  v94);
          WdsSetupLogMessageW(
            v28,
            409600,
            L"D",
            0,
            103,
            L"base\\ntsetup\\lib\\rollback\\src\\crashdumputils.cpp",
            L"OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths",
            v25,
            v23,
            0,
            0);
        }
      }
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v112);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v117);
    }
    catch ( ___R0PEAVCXXXXXTemp__3__GetPageFilePaths_CCrashDumpExtractor_OSRollbackUtils__KAKPEBGPEAPEAV__ArrayList_PEAVString_UnBCL___UnBCL___Z__8 )
    {
      OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths_::_1_::catch_22();
      __eh34_caught_type(
        1,
        ___R0PEAVCXXXXXTemp__3__GetPageFilePaths_CCrashDumpExtractor_OSRollbackUtils__KAKPEBGPEAPEAV__ArrayList_PEAVString_UnBCL___UnBCL___Z__8);
    }
    v96 = 1;
    v110 = v119;
    throw (`OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths(ushort const *,UnBCL::ArrayList<UnBCL::String *> * *)'::`3'::CXXXXXHandledException **)&v110;
  }
  catch ( UnBCL::Exception * )
  {
    v91 = (const WCHAR *)&v92;
    v85 = v91;
    v86 = (HKEY)*((_QWORD *)v91 + 19);
    if ( v86 )
      RegCloseKey(v86);
    if ( *((_DWORD *)v85 + 34) )
    {
      v87 = RegUnLoadKeyW(HKEY_LOCAL_MACHINE, v85 + 228);
      if ( v87 )
      {
        v88 = GetLastError();
        v89 = ((__int64 (*)(void))CurrentIP)();
        v90 = ConstructPartialMsgW(
                0x2000000u,
                "OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths: Failed to load offline SYSTEM hive at [%s]: Error %u",
                (const char *)v85 + 456,
                v87);
        WdsSetupLogMessageW(
          v90,
          409600,
          L"D",
          0,
          179,
          L"base\\ntsetup\\lib\\rollback\\src\\crashdumputils.cpp",
          L"OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths",
          v89,
          v88,
          0,
          0);
      }
    }
    if ( !*((_DWORD *)v85 + 27) )
      throw;
    UnBCL::Exception::~Exception((UnBCL::Exception *)v119);
    if ( !v97 )
    {
      v73 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::Steal(v105);
      *v111 = v73;
    }
    UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v105);
  }
}

```

## disassembly

```asm
0x18047a9b8  mov     r11, rsp
0x18047a9bb  push    rsi
0x18047a9bc  push    rdi
0x18047a9bd  push    r12
0x18047a9bf  push    r14
0x18047a9c1  push    r15
0x18047a9c3  sub     rsp, 2D0h
0x18047a9ca  mov     qword ptr [r11-170h], 0FFFFFFFFFFFFFFFEh
0x18047a9d5  mov     [r11+18h], rbx
0x18047a9d9  mov     rax, cs:__security_cookie
0x18047a9e0  xor     rax, rsp
0x18047a9e3  mov     [rsp+2F8h+var_38], rax
0x18047a9eb  mov     rdi, rcx
0x18047a9ee  mov     [rsp+2F8h+var_200], rcx
0x18047a9f6  mov     [rsp+2F8h+var_1E8], rdx
0x18047a9fe  xor     r14d, r14d
0x18047aa01  mov     [rsp+2F8h+var_288], r14d
0x18047aa06  mov     [rsp+2F8h+var_270], r14d
0x18047aa0e  mov     [r11-260h], r14
0x18047aa15  mov     ecx, 0B0h
0x18047aa1a  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18047aa20  mov     rbx, rax
0x18047aa23  mov     [rsp+2F8h+var_268], rax
0x18047aa2b  lea     r15d, [r14+1]
0x18047aa2f  test    rax, rax
0x18047aa32  jz      short loc_18047AA4D
0x18047aa34  mov     edx, r15d
0x18047aa37  mov     rcx, rax
0x18047aa3a  call    cs:__imp_??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::ArrayList<UnBCL::String *>::ArrayList<UnBCL::String *>(void)
0x18047aa40  lea     rax, ??_S?$ArrayList@PEAVString@UnBCL@@@UnBCL@@6BObject@1@@; const UnBCL::ArrayList<UnBCL::String *>::`local vftable'{for `UnBCL::Object'}
0x18047aa47  mov     [rbx+30h], rax
0x18047aa4b  jmp     short loc_18047AA50
0x18047aa4d  mov     rbx, r14
0x18047aa50  mov     rdx, rbx
0x18047aa53  lea     rcx, [rsp+2F8h+var_228]
0x18047aa5b  call    cs:__imp_??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(UnBCL::ArrayList<UnBCL::String *> *)
0x18047aa61  nop
0x18047aa62  lea     rcx, [rsp+2F8h+var_228]
0x18047aa6a  call    cs:__imp_??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(void)
0x18047aa70  mov     r8, rax
0x18047aa73  mov     rcx, [rax]
0x18047aa76  mov     rax, [rcx+28h]
0x18047aa7a  mov     edx, r15d
0x18047aa7d  mov     rcx, r8
0x18047aa80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18047aa85  movups  xmm0, xmmword ptr cs:aRollbackOfflin; "$ROLLBACK_OFFLINE_RW$SYSTEM"
0x18047aa8c  movups  xmmword ptr [rsp+2F8h+SubKey], xmm0
0x18047aa94  movups  xmm1, xmmword ptr cs:aRollbackOfflin+10h; "K_OFFLINE_RW$SYSTEM"
0x18047aa9b  movups  [rsp+2F8h+var_120], xmm1
0x18047aaa3  movups  xmm0, xmmword ptr cs:aRollbackOfflin+20h; "E_RW$SYSTEM"
0x18047aaaa  movups  [rsp+2F8h+var_110], xmm0
0x18047aab2  movsd   xmm1, qword ptr cs:aRollbackOfflin+30h; "TEM"
0x18047aaba  movsd   [rsp+2F8h+var_100], xmm1
0x18047aac3  movaps  xmm0, xmmword ptr cs:aControlset03uC_0; "ControlSet%03u\\Control\\Session Manage"...
0x18047aaca  movaps  [rsp+2F8h+var_B8], xmm0
0x18047aad2  movaps  xmm1, xmmword ptr cs:aControlset03uC_0+10h; "et%03u\\Control\\Session Manager\\Memor"...
0x18047aad9  movaps  [rsp+2F8h+var_A8], xmm1
0x18047aae1  movaps  xmm0, xmmword ptr cs:aControlset03uC_0+20h; "ontrol\\Session Manager\\Memory Managem"...
0x18047aae8  movaps  [rsp+2F8h+var_98], xmm0
0x18047aaf0  movaps  xmm1, xmmword ptr cs:aControlset03uC_0+30h; "ession Manager\\Memory Management"
0x18047aaf7  movaps  [rsp+2F8h+var_88], xmm1
0x18047aaff  movaps  xmm0, xmmword ptr cs:aControlset03uC_0+40h; "anager\\Memory Management"
0x18047ab06  movaps  [rsp+2F8h+var_78], xmm0
0x18047ab0e  movaps  xmm1, xmmword ptr cs:aControlset03uC_0+50h; "emory Management"
0x18047ab15  movaps  [rsp+2F8h+var_68], xmm1
0x18047ab1d  movaps  xmm0, xmmword ptr cs:aControlset03uC_0+60h; "nagement"
0x18047ab24  movaps  [rsp+2F8h+var_58], xmm0
0x18047ab2c  movzx   eax, word ptr cs:aControlset03uC_0+70h; ""
0x18047ab33  mov     [rsp+2F8h+var_48], ax
0x18047ab3b  movups  xmm0, xmmword ptr cs:aPagingfiles; "PagingFiles"
0x18047ab42  movups  [rsp+2F8h+var_F8], xmm0
0x18047ab4a  movsd   xmm1, qword ptr cs:aPagingfiles+10h; "les"
0x18047ab52  movsd   [rsp+2F8h+var_E8], xmm1
0x18047ab5b  movups  xmm0, xmmword ptr cs:aExistingpagefi; "ExistingPageFiles"
0x18047ab62  movups  [rsp+2F8h+var_E0], xmm0
0x18047ab6a  movups  xmm1, xmmword ptr cs:aExistingpagefi+10h; "PageFiles"
0x18047ab71  movups  [rsp+2F8h+var_D0], xmm1
0x18047ab79  mov     eax, dword ptr cs:aExistingpagefi+20h; "s"
0x18047ab7f  mov     [rsp+2F8h+var_C0], eax
0x18047ab86  mov     [rsp+2F8h+var_28C], r14d
0x18047ab8b  lea     rcx, [rsp+2F8h+var_168]
0x18047ab93  call    cs:__imp_??0Exception@UnBCL@@QEAA@XZ; UnBCL::Exception::Exception(void)
0x18047ab99  lea     rax, ??_7CXXXXXHandledException@?2??GetPageFilePaths@CCrashDumpExtractor@OSRollbackUtils@@KAKPEBGPEAPEAV?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@Z@6B@; const `OSRollbackUtils::CCrashDumpExtractor::GetPageFilePaths(ushort const *,UnBCL::ArrayList<UnBCL::String *> * *)'::`3'::CXXXXXHandledException::`vftable'
0x18047aba0  mov     [rsp+2F8h+var_168], rax
0x18047aba8  lea     rdx, aWindir_0; "%WINDIR%"
0x18047abaf  lea     rcx, [rsp+2F8h+var_258]
0x18047abb7  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18047abbd  nop
0x18047abbe  mov     rcx, rax
0x18047abc1  call    cs:__imp_?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Environment::ExpandEnvironmentVariables(UnBCL::String const *)
0x18047abc7  mov     rdx, rax
0x18047abca  lea     rcx, [rsp+2F8h+var_180]
0x18047abd2  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18047abd8  nop
0x18047abd9  lea     rcx, [rsp+2F8h+var_258]
0x18047abe1  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18047abe7  lea     rcx, [rsp+2F8h+var_180]
0x18047abef  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18047abf5  xor     edx, edx
0x18047abf7  mov     rcx, rax
0x18047abfa  call    cs:__imp_?get_Chars@String@UnBCL@@QEBAAEBGH@Z; UnBCL::String::get_Chars(int)
0x18047ac00  movzx   ecx, word ptr [rdi]
0x18047ac03  cmp     [rax], cx
0x18047ac06  jz      loc_18047ACC5
0x18047ac0c  lea     rdx, aWindowsSystem3_2; "Windows\\System32\\config\\SYSTEM"
0x18047ac13  lea     rcx, [rsp+2F8h+var_1D0]
0x18047ac1b  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18047ac21  mov     rbx, rax
0x18047ac24  mov     rdx, rdi
0x18047ac27  lea     rcx, [rsp+2F8h+var_1B8]
0x18047ac2f  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18047ac35  nop
0x18047ac36  mov     rdx, rbx
0x18047ac39  mov     rcx, rax
0x18047ac3c  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x18047ac42  mov     rdx, rax
0x18047ac45  lea     rcx, [rsp+2F8h+var_280]
0x18047ac4a  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18047ac50  nop
0x18047ac51  lea     rcx, [rsp+2F8h+var_1B8]
0x18047ac59  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18047ac5f  nop
0x18047ac60  lea     rcx, [rsp+2F8h+var_1D0]
0x18047ac68  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18047ac6e  lea     rcx, [rsp+2F8h+var_280]
0x18047ac73  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18047ac79  mov     rcx, rax
0x18047ac7c  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18047ac82  mov     r8, rax; lpFile
0x18047ac85  lea     rdx, [rsp+2F8h+SubKey]; lpSubKey
0x18047ac8d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18047ac94  call    cs:__imp_RegLoadKeyW
0x18047ac9a  mov     ebx, eax
0x18047ac9c  mov     [rsp+2F8h+var_288], eax
0x18047aca0  test    eax, eax
0x18047aca2  jnz     loc_18047B474
0x18047aca8  mov     [rsp+2F8h+var_270], r15d
0x18047acb0  lea     rbx, [rsp+2F8h+SubKey]
0x18047acb8  lea     rcx, [rsp+2F8h+var_280]
0x18047acbd  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18047acc3  jmp     short loc_18047ACCC
0x18047acc5  lea     rbx, aSystem; "SYSTEM"
0x18047accc  lea     rax, [rsp+2F8h+var_260]
0x18047acd4  mov     [rsp+2F8h+phkResult], rax; phkResult
0x18047acd9  mov     r9d, 20019h; samDesired
0x18047acdf  xor     r8d, r8d; ulOptions
0x18047ace2  mov     rdx, rbx; lpSubKey
0x18047ace5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18047acec  call    cs:__imp_RegOpenKeyExW
0x18047acf2  mov     esi, eax
0x18047acf4  mov     [rsp+2F8h+var_288], eax
0x18047acf8  test    eax, eax
0x18047acfa  jnz     loc_18047B526
0x18047ad00  lea     r8, aCurrent_0; "Current"
0x18047ad07  lea     rdx, aSelect; "Select"
0x18047ad0e  mov     rcx, [rsp+2F8h+var_260]
0x18047ad16  call    RegGetDword
0x18047ad1b  test    eax, eax
0x18047ad1d  jz      loc_18047B5BF
0x18047ad23  mov     edx, eax
0x18047ad25  lea     rcx, [rsp+2F8h+var_B8]
0x18047ad2d  call    cs:__imp_?Format@String@UnBCL@@SAPEAV12@PEBGZZ; UnBCL::String::Format(ushort const *,...)
0x18047ad33  mov     rdx, rax
0x18047ad36  lea     rcx, [rsp+2F8h+var_1E0]
0x18047ad3e  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18047ad44  nop
0x18047ad45  lea     rax, [rsp+2F8h+var_E0]
0x18047ad4d  mov     [rsp+2F8h+var_238], rax
0x18047ad55  lea     rax, [rsp+2F8h+var_F8]
0x18047ad5d  mov     [rsp+2F8h+var_230], rax
0x18047ad65  lea     rbx, [rsp+2F8h+var_238]
0x18047ad6d  lea     r12, aOsrollbackutil_4; "OSRollbackUtils::CCrashDumpExtractor::G"...
0x18047ad74  lea     rsi, aBaseNtsetupLib_6; "base\\ntsetup\\lib\\rollback\\src\\cras"...
0x18047ad7b  lea     rax, [rsp+2F8h+var_228]
0x18047ad83  mov     [rsp+2F8h+var_268], rbx
0x18047ad8b  cmp     rbx, rax
0x18047ad8e  jz      loc_18047B664
0x18047ad94  mov     dword ptr [rsp+2F8h+var_298], r14d
0x18047ad99  lea     rcx, [rsp+2F8h+var_1E0]
0x18047ada1  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18047ada7  mov     rcx, rax
0x18047adaa  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18047adb0  lea     r9, [rsp+2F8h+var_298]
0x18047adb5  mov     r8, [rbx]
0x18047adb8  mov     rdx, rax
0x18047adbb  mov     rcx, [rsp+2F8h+var_260]
0x18047adc3  call    RegGetMultiSz
0x18047adc8  mov     rdi, rax
0x18047adcb  test    rax, rax
0x18047adce  jnz     loc_18047AE6F
0x18047add4  call    cs:__imp_GetLastError
0x18047adda  mov     ebx, eax
0x18047addc  call    cs:__imp_CurrentIP
0x18047ade2  mov     rdi, rax
0x18047ade5  call    cs:__imp_GetLastError
0x18047adeb  mov     dword ptr [rsp+2F8h+var_298], eax
0x18047adef  lea     rcx, [rsp+2F8h+var_1E0]
0x18047adf7  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18047adfd  mov     rcx, rax
0x18047ae00  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18047ae06  mov     ecx, dword ptr [rsp+2F8h+var_298]
0x18047ae0a  mov     dword ptr [rsp+2F8h+phkResult], ecx
0x18047ae0e  mov     r9, rax
0x18047ae11  mov     r8, [rsp+2F8h+var_268]
0x18047ae19  mov     r8, [r8]
0x18047ae1c  lea     rdx, aOsrollbackutil_7; "OSRollbackUtils::CCrashDumpExtractor::G"...
0x18047ae23  mov     ecx, 3000000h; unsigned int
0x18047ae28  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18047ae2d  mov     [rsp+2F8h+var_2A8], r14d
0x18047ae32  mov     [rsp+2F8h+var_2B0], r14
0x18047ae37  mov     [rsp+2F8h+var_2B8], ebx
0x18047ae3b  mov     [rsp+2F8h+var_2C0], rdi
0x18047ae40  mov     [rsp+2F8h+var_2C8], r12
0x18047ae45  mov     [rsp+2F8h+var_2D0], rsi
0x18047ae4a  mov     dword ptr [rsp+2F8h+phkResult], 67h ; 'g'
0x18047ae52  xor     r9d, r9d
0x18047ae55  lea     r8, aD_0; "D"
0x18047ae5c  mov     edx, 64000h
0x18047ae61  mov     rcx, rax
0x18047ae64  call    cs:__imp_WdsSetupLogMessageW
0x18047ae6a  jmp     loc_18047B3F8
0x18047ae6f  mov     [rsp+2F8h+var_290], r14d
0x18047ae74  mov     ecx, 70h ; 'p'
0x18047ae79  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18047ae7f  mov     rbx, rax
0x18047ae82  mov     [rsp+2F8h+var_240], rax
0x18047ae8a  test    rax, rax
0x18047ae8d  jz      short loc_18047AEB7
0x18047ae8f  mov     r8d, dword ptr [rsp+2F8h+var_298]
0x18047ae94  mov     dword ptr [rsp+2F8h+phkResult], r15d
0x18047ae99  lea     r9, [rsp+2F8h+var_290]
0x18047ae9e  mov     rdx, rdi
0x18047aea1  mov     rcx, rax
0x18047aea4  call    cs:__imp_??0MultiSz@UnBCL@@QEAA@PEBE_KPEAK@Z; UnBCL::MultiSz::MultiSz(uchar const *,unsigned __int64,ulong *)
0x18047aeaa  lea     rax, ??_SMultiSz@UnBCL@@6BObject@1@@; const UnBCL::MultiSz::`local vftable'{for `UnBCL::Object'}
0x18047aeb1  mov     [rbx+28h], rax
0x18047aeb5  jmp     short loc_18047AEBA
0x18047aeb7  mov     rbx, r14
0x18047aeba  mov     rdx, rbx
0x18047aebd  lea     rcx, [rsp+2F8h+var_1B8]
0x18047aec5  call    ??0?$SmartPtr@VMultiSz@UnBCL@@@UnBCL@@QEAA@PEAVMultiSz@1@@Z; UnBCL::SmartPtr<UnBCL::MultiSz>::SmartPtr<UnBCL::MultiSz>(UnBCL::MultiSz *)
0x18047aeca  nop
0x18047aecb  cmp     [rsp+2F8h+var_290], r14d
0x18047aed0  jz      loc_18047AFCE
0x18047aed6  lea     rcx, [rsp+2F8h+var_258]
0x18047aede  call    cs:__imp_??0StringBuilder@UnBCL@@QEAA@XZ; UnBCL::StringBuilder::StringBuilder(void)
0x18047aee4  nop
0x18047aee5  mov     eax, [rsp+2F8h+var_290]
0x18047aee9  test    r15b, al
0x18047aeec  jz      short loc_18047AF07
0x18047aeee  lea     rdx, aByteTruncated; " [Byte Truncated]"
0x18047aef5  lea     rcx, [rsp+2F8h+var_258]
0x18047aefd  call    cs:__imp_?Append@StringBuilder@UnBCL@@QEAAPEAV12@PEBG@Z; UnBCL::StringBuilder::Append(ushort const *)
0x18047af03  mov     eax, [rsp+2F8h+var_290]
0x18047af07  test    al, 2
0x18047af09  jz      short loc_18047AF24
0x18047af0b  lea     rdx, aMissingListTer; " [Missing List Terminator]"
0x18047af12  lea     rcx, [rsp+2F8h+var_258]
0x18047af1a  call    cs:__imp_?Append@StringBuilder@UnBCL@@QEAAPEAV12@PEBG@Z; UnBCL::StringBuilder::Append(ushort const *)
0x18047af20  mov     eax, [rsp+2F8h+var_290]
0x18047af24  test    al, 4
0x18047af26  jz      short loc_18047AF3D
0x18047af28  lea     rdx, aMissingStringT; " [Missing String Terminator]"
0x18047af2f  lea     rcx, [rsp+2F8h+var_258]
0x18047af37  call    cs:__imp_?Append@StringBuilder@UnBCL@@QEAAPEAV12@PEBG@Z; UnBCL::StringBuilder::Append(ushort const *)
0x18047af3d  call    cs:__imp_GetLastError
0x18047af43  mov     ebx, eax
0x18047af45  call    cs:__imp_CurrentIP
0x18047af4b  mov     [rsp+2F8h+var_298], rax
0x18047af50  lea     rcx, [rsp+2F8h+var_258]
0x18047af58  call    cs:__imp_?get_CString@StringBuilder@UnBCL@@QEBAPEBGXZ; UnBCL::StringBuilder::get_CString(void)
0x18047af5e  mov     r9, rax
0x18047af61  mov     r8, [rsp+2F8h+var_268]
0x18047af69  mov     r8, [r8]
0x18047af6c  lea     rdx, aOsrollbackutil; "OSRollbackUtils::CCrashDumpExtractor::G"...
0x18047af73  mov     ecx, 3000000h; unsigned int
0x18047af78  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18047af7d  mov     [rsp+2F8h+var_2A8], r14d
0x18047af82  mov     [rsp+2F8h+var_2B0], r14
0x18047af87  mov     [rsp+2F8h+var_2B8], ebx
0x18047af8b  mov     rcx, [rsp+2F8h+var_298]
0x18047af90  mov     [rsp+2F8h+var_2C0], rcx
0x18047af95  mov     [rsp+2F8h+var_2C8], r12
0x18047af9a  mov     [rsp+2F8h+var_2D0], rsi
0x18047af9f  mov     dword ptr [rsp+2F8h+phkResult], 7Ch ; '|'
0x18047afa7  xor     r9d, r9d
0x18047afaa  lea     r8, aD_0; "D"
0x18047afb1  mov     edx, 64000h
0x18047afb6  mov     rcx, rax
0x18047afb9  call    cs:__imp_WdsSetupLogMessageW
0x18047afbf  nop
0x18047afc0  lea     rcx, [rsp+2F8h+var_258]
0x18047afc8  call    cs:__imp_??1StringBuilder@UnBCL@@UEAA@XZ; UnBCL::StringBuilder::~StringBuilder(void)
0x18047afce  call    cs:__imp_GetProcessHeap
0x18047afd4  mov     rcx, rax; hHeap
0x18047afd7  mov     r8, rdi; lpMem
0x18047afda  xor     edx, edx; dwFlags
0x18047afdc  call    cs:__imp_HeapFree
0x18047afe2  lea     rcx, [rsp+2F8h+var_1B8]
0x18047afea  call    ??C?$CAutoCleanupBase@PEAX@RAII@@UEBAQEAXXZ; RAII::CAutoCleanupBase<void *>::operator->(void)
  ... truncated ...
```
