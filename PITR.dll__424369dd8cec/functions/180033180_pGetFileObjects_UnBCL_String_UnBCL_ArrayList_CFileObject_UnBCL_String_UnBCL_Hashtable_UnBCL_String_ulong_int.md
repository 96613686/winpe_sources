# pGetFileObjects(UnBCL::String *,UnBCL::ArrayList<CFileObject *> *,UnBCL::String *,UnBCL::Hashtable<UnBCL::String *,ulong> *,int)

- ea: `0x180033180`
- end: `0x1800339d0`
- name: `?pGetFileObjects@@YAJPEAVString@UnBCL@@PEAV?$ArrayList@PEAVCFileObject@@@2@0PEAV?$Hashtable@PEAVString@UnBCL@@K@2@H@Z`
- size: `2128`
- prototype: `__int64 __fastcall(const struct UnBCL::String *, __int64, const struct UnBCL::String *, __int64, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003275c`
- `0x180032ae4`

## callees

- `0x180009e04`
- `0x180025298`
- `0x180033180`
- `0x180035edc`
- `0x1800362ec`
- `0x1800502c2`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180033597`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180033597`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800335cb`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800335cb`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180033992`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180033992`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003326b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003326b`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003382c`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003382c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003327b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033608`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003361c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033638`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003383f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003386f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800338df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003327b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033608`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003361c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033638`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003383f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003386f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800338df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800336c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800336c2`
- `WDSCORE!CurrentIP` at `0x180033641`
- `WDSCORE!CurrentIP` at `0x180033877`
- `WDSCORE!CurrentIP` at `0x1800338e7`
- `WDSCORE!CurrentIP` at `0x180033641`
- `WDSCORE!CurrentIP` at `0x180033877`
- `WDSCORE!CurrentIP` at `0x1800338e7`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800336b6`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003395c`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800336b6`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003395c`
- `unbcl!?Steal@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x18003375e`
- `unbcl!?Steal@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x18003375e`
- `unbcl!?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x180033524`
- `unbcl!?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x180033551`
- `unbcl!?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x180033524`
- `unbcl!?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x180033551`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180033315`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180033473`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18003374b`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180033315`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180033473`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18003374b`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180033209`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180033331`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180033492`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180033209`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180033331`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180033492`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180033248`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180033248`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18003325b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18003356d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180033657`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18003388d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800338fd`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18003325b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18003356d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180033657`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18003388d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800338fd`
- `unbcl!?ToLower@String@UnBCL@@QEBAPEAV12@XZ` at `0x1800333b8`
- `unbcl!?ToLower@String@UnBCL@@QEBAPEAV12@XZ` at `0x1800333ea`
- `unbcl!?ToLower@String@UnBCL@@QEBAPEAV12@XZ` at `0x1800333b8`
- `unbcl!?ToLower@String@UnBCL@@QEBAPEAV12@XZ` at `0x1800333ea`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x1800332cc`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x1800332eb`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x1800332cc`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x1800332eb`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180033216`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18003337e`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800334c5`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180033216`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18003337e`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800334c5`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x180033519`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x180033519`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800337ed`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180033967`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800337ed`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180033967`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180033533`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180033533`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180033223`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18003334c`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180033362`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18003338b`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800333c5`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800333f7`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800334ae`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800334d2`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180033223`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18003334c`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180033362`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18003338b`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800333c5`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800333f7`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800334ae`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800334d2`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1800331f7`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1800331f7`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18003323d`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800333a5`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180033411`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18003344d`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180033458`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180033463`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800337f8`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180033803`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18003380e`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180033972`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18003397d`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180033988`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18003399d`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18003323d`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800333a5`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180033411`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18003344d`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180033458`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180033463`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800337f8`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180033803`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18003380e`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180033972`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18003397d`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180033988`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18003399d`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x18003376b`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x180033778`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x180033785`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x18003376b`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x180033778`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x180033785`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180033232`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18003339a`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800333d4`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180033406`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180033232`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18003339a`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800333d4`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180033406`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180033252`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800333af`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800333e1`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180033564`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18003364e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180033884`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800338f4`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180033252`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800333af`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800333e1`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180033564`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18003364e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180033884`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800338f4`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180033372`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18003342c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800334b9`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180033504`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18003370b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180033372`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18003342c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800334b9`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180033504`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18003370b`

## string_xrefs

- `0x180033693`: `base\diagnosis\srt\pitr\dll\src\restore.cpp`
- `0x1800338c9`: `base\diagnosis\srt\pitr\dll\src\restore.cpp`
- `0x180033939`: `base\diagnosis\srt\pitr\dll\src\restore.cpp`
- `0x180033909`: `Failed to get ACL for %s. Error: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=2
__int64 __fastcall pGetFileObjects(
        const struct UnBCL::String *a1,
        __int64 a2,
        const struct UnBCL::String *a3,
        __int64 a4,
        int a5)
{
  __int64 v5; // r14
  const struct UnBCL::String *v6; // r15
  __int64 v7; // rsi
  const struct UnBCL::String *v8; // rdi
  signed int SecurityInfoStr; // r12d
  const struct UnBCL::String *v10; // rax
  struct UnBCL::String *v11; // rax
  UnBCL::String *v12; // rax
  const WCHAR *CString; // rax
  signed int LastError; // ecx
  char dwFileAttributes; // al
  UnBCL::String *v16; // rax
  UnBCL::String *v17; // rbx
  const struct UnBCL::String *P; // rax
  struct UnBCL::String *v19; // rax
  UnBCL::String *v20; // rax
  struct UnBCL::String *v21; // rax
  _BYTE *v22; // rcx
  UnBCL::String *v23; // rax
  struct UnBCL::String *v24; // rax
  __int64 v25; // rdi
  unsigned int (__fastcall *v26)(__int64, __int64); // rbx
  __int64 v27; // rax
  UnBCL::String *v28; // rax
  UnBCL::String *v29; // rbx
  const struct UnBCL::String *v30; // rax
  struct UnBCL::String *v31; // rax
  __int64 FileHardlinks; // rax
  UnBCL::String *v33; // rax
  __int64 v34; // rax
  UnBCL::String *v35; // rax
  const WCHAR *v36; // rax
  HANDLE FileW; // r15
  __int64 ftCreationTime; // rbx
  __int64 ftLastWriteTime; // rdi
  signed int v40; // eax
  bool v41; // sf
  signed int v42; // eax
  DWORD v43; // r14d
  __int64 v44; // rsi
  UnBCL::String *v45; // rax
  const char *v46; // rax
  struct tagLOG_PARTIAL_MSG *v47; // rax
  struct UnBCL::String *v48; // rax
  __int64 v49; // r15
  int v50; // r14d
  int v51; // esi
  int v52; // eax
  __int64 v53; // rax
  signed int v54; // eax
  bool v55; // sf
  signed int v56; // eax
  DWORD v57; // edi
  __int64 v58; // rbx
  UnBCL::String *v59; // rax
  const char *v60; // rax
  struct tagLOG_PARTIAL_MSG *v61; // rax
  DWORD v62; // edi
  __int64 v63; // rbx
  UnBCL::String *v64; // rax
  const char *v65; // rax
  struct tagLOG_PARTIAL_MSG *v66; // rax
  int v68; // [rsp+58h] [rbp-A8h]
  DWORD v69; // [rsp+60h] [rbp-A0h]
  __int64 v70; // [rsp+68h] [rbp-98h]
  DWORD v71; // [rsp+70h] [rbp-90h]
  struct UnBCL::String *v73; // [rsp+80h] [rbp-80h] BYREF
  __int64 v74; // [rsp+88h] [rbp-78h]
  HANDLE hFindFile; // [rsp+90h] [rbp-70h]
  void *v76; // [rsp+98h] [rbp-68h]
  __int64 v77; // [rsp+A0h] [rbp-60h]
  void (__fastcall *v78)(__int64, __int64); // [rsp+A8h] [rbp-58h]
  __int64 v79; // [rsp+B0h] [rbp-50h]
  const struct UnBCL::String *v80; // [rsp+B8h] [rbp-48h]
  _BYTE v81[24]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v82[16]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v83[16]; // [rsp+E8h] [rbp-18h] BYREF
  UnBCL::String *v84; // [rsp+F8h] [rbp-8h]
  UnBCL::String *v85; // [rsp+100h] [rbp+0h]
  _BYTE v86[16]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v87[16]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v88[16]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v89[16]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v90[16]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v91[16]; // [rsp+158h] [rbp+58h] BYREF
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+168h] [rbp+68h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+1A0h] [rbp+A0h] BYREF

  v5 = a4;
  v79 = a4;
  v6 = a3;
  v80 = a3;
  v7 = a2;
  v74 = a2;
  v8 = a1;
  if ( !a1 || !a2 )
    return 2147942487LL;
  SecurityInfoStr = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v91);
  v10 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v81, L"*");
  v11 = UnBCL::Path::Combine(v8, v10);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v89, v11);
  UnBCL::SmartPtr<UnBCL::String>::operator=(v91, v89);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v89);
  UnBCL::String::~String((UnBCL::String *)v81);
  v12 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v91);
  CString = UnBCL::String::get_CString(v12);
  hFindFile = FindFirstFileW(CString, &FindFileData);
  if ( hFindFile == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( (unsigned int)(LastError - 2) > 1 )
    {
      if ( LastError > 0 )
        SecurityInfoStr = (unsigned __int16)LastError | 0x80070000;
      else
        SecurityInfoStr = LastError;
    }
    goto LABEL_63;
  }
  while ( 1 )
  {
    dwFileAttributes = FindFileData.dwFileAttributes;
    if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
    {
      if ( !UnBCL::String::Compare(FindFileData.cFileName, L".", 0)
        || !UnBCL::String::Compare(FindFileData.cFileName, L"..", 0) )
      {
        goto LABEL_52;
      }
      dwFileAttributes = FindFileData.dwFileAttributes;
    }
    if ( !a5 || (dwFileAttributes & 0x10) != 0 )
      break;
LABEL_52:
    if ( !FindNextFileW(hFindFile, &FindFileData) )
      goto LABEL_63;
  }
  v16 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
  v17 = v16;
  v84 = v16;
  if ( v16 )
  {
    UnBCL::String::String(v16, FindFileData.cFileName);
    *(_QWORD *)v17 = &UnBCL::String::`local vftable';
  }
  else
  {
    v17 = 0;
  }
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v87, v17);
  if ( v5 )
  {
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v90, 0);
    if ( v6 )
    {
      P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v87);
      v19 = UnBCL::Path::Combine(v6, P);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v82, v19);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v90, v82);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v82);
      v20 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v90);
      v21 = UnBCL::String::ToLower(v20);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v83, v21);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v90, v83);
      v22 = v83;
    }
    else
    {
      v23 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v87);
      v24 = UnBCL::String::ToLower(v23);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v81, v24);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v90, v81);
      v22 = v81;
    }
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v22);
    v25 = *(int *)(*(_QWORD *)(v5 + 8) + 16LL);
    v26 = *(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)(v25 + v5 + 8) + 64LL);
    v27 = UnBCL::SmartPtr<UnBCL::String>::get_P(v90);
    if ( v26(v5 + v25 + 8, v27) )
    {
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v90);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v87);
LABEL_51:
      v8 = a1;
      goto LABEL_52;
    }
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v90);
    v8 = a1;
  }
  v28 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
  v29 = v28;
  v85 = v28;
  if ( v28 )
  {
    UnBCL::String::String(v28, FindFileData.cAlternateFileName);
    *(_QWORD *)v29 = &UnBCL::String::`local vftable';
  }
  else
  {
    v29 = 0;
  }
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v89, v29);
  v30 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v87);
  v31 = UnBCL::Path::Combine(v8, v30);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v86, v31);
  v71 = (FindFileData.dwFileAttributes & 0x400) != 0 ? FindFileData.dwReserved0 : 0;
  if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
  {
    FileHardlinks = 0;
  }
  else
  {
    v33 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v86);
    FileHardlinks = GetFileHardlinks(v33);
  }
  UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v88, FileHardlinks);
  if ( UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::get_P(v88) )
  {
    v34 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v88);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 88LL))(v34);
  }
  v70 = 0;
  if ( !UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::get_P(v88) )
  {
    v69 = FindFileData.dwFileAttributes;
    ftCreationTime = (__int64)FindFileData.ftCreationTime;
    ftLastWriteTime = (__int64)FindFileData.ftLastWriteTime;
    v70 = __PAIR64__(FindFileData.nFileSizeHigh, FindFileData.nFileSizeLow);
LABEL_46:
    v73 = 0;
    v48 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v86);
    SecurityInfoStr = GetSecurityInfoStr(v48, &v73);
    if ( SecurityInfoStr < 0 )
    {
      v62 = GetLastError();
      v63 = CurrentIP();
      v64 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v86);
      v65 = (const char *)UnBCL::String::get_CString(v64);
      v66 = ConstructPartialMsgW(0x2000000, "Failed to get ACL for %s. Error: 0x%08X", v65, SecurityInfoStr);
      WdsSetupLogMessageW(
        v66,
        0,
        L"D",
        0,
        515,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
        L"pGetFileObjects",
        v63,
        v62,
        0,
        0);
      goto LABEL_62;
    }
    v77 = v7 + *(int *)(*(_QWORD *)(v7 + 8) + 16LL) + 8LL;
    v78 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v77 + 40LL);
    v76 = UnBCL::Object::operator new(0x90u);
    if ( v76 )
    {
      v49 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::Steal(v88);
      v50 = UnBCL::SmartPtr<UnBCL::String>::Steal(v89);
      v51 = UnBCL::SmartPtr<UnBCL::String>::Steal(v87);
      v52 = UnBCL::SmartPtr<UnBCL::String>::Steal(v86);
      v53 = CFileObject::CFileObject(
              (_DWORD)v76,
              v52,
              v51,
              v50,
              v49,
              v69,
              v71,
              ftCreationTime,
              ftLastWriteTime,
              v70,
              (__int64)v73,
              v68);
      v7 = v74;
    }
    else
    {
      v53 = 0;
    }
    v78(v77, v53);
    UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v88);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v86);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v89);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v87);
    v5 = v79;
    v6 = v80;
    goto LABEL_51;
  }
  v35 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v86);
  v36 = UnBCL::String::get_CString(v35);
  FileW = CreateFileW(v36, 0x80u, 7u, 0, 3u, 0x2200000u, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    memset(&FileInformation, 0, sizeof(FileInformation));
    if ( GetFileInformationByHandle(FileW, &FileInformation) )
    {
      v69 = FileInformation.dwFileAttributes;
      ftCreationTime = (__int64)FileInformation.ftCreationTime;
      ftLastWriteTime = (__int64)FileInformation.ftLastWriteTime;
      v70 = __PAIR64__(FileInformation.nFileSizeHigh, FileInformation.nFileSizeLow);
    }
    else
    {
      v69 = 0;
      ftCreationTime = 0;
      ftLastWriteTime = 0;
      v40 = GetLastError();
      v41 = v40 < 0;
      if ( v40 > 0 )
        v41 = 1;
      if ( v41 )
      {
        v42 = GetLastError();
        SecurityInfoStr = v42;
        if ( v42 > 0 )
          SecurityInfoStr = (unsigned __int16)v42 | 0x80070000;
      }
      else
      {
        SecurityInfoStr = -2147467259;
      }
      v43 = GetLastError();
      v44 = CurrentIP();
      v45 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v86);
      v46 = (const char *)UnBCL::String::get_CString(v45);
      v47 = ConstructPartialMsgW(
              0x2000000,
              "Failed to get file information (2) for %s. Error: 0x%08X",
              v46,
              SecurityInfoStr);
      WdsSetupLogMessageW(
        v47,
        0,
        L"D",
        0,
        493,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
        L"pGetFileObjects",
        v44,
        v43,
        0,
        0);
    }
    CloseHandle(FileW);
    if ( SecurityInfoStr < 0 )
      goto LABEL_62;
    v7 = v74;
    goto LABEL_46;
  }
  v54 = GetLastError();
  v55 = v54 < 0;
  if ( v54 > 0 )
    v55 = 1;
  if ( v55 )
  {
    v56 = GetLastError();
    SecurityInfoStr = v56;
    if ( v56 > 0 )
      SecurityInfoStr = (unsigned __int16)v56 | 0x80070000;
  }
  else
  {
    SecurityInfoStr = -2147467259;
  }
  v57 = GetLastError();
  v58 = CurrentIP();
  v59 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v86);
  v60 = (const char *)UnBCL::String::get_CString(v59);
  v61 = ConstructPartialMsgW(0x2000000, "Failed to get file information for %s. Error: 0x%08X", v60, SecurityInfoStr);
  WdsSetupLogMessageW(
    v61,
    0,
    L"D",
    0,
    476,
    L"base\\diagnosis\\srt\\pitr\\dll\\src\\restore.cpp",
    L"pGetFileObjects",
    v58,
    v57,
    0,
    0);
LABEL_62:
  UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v88);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v86);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v89);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v87);
LABEL_63:
  FindClose(hFindFile);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v91);
  return (unsigned int)SecurityInfoStr;
}

```

## disassembly

```asm
0x180033180  push    rbp
0x180033182  push    rbx
0x180033183  push    rsi
0x180033184  push    rdi
0x180033185  push    r12
0x180033187  push    r13
0x180033189  push    r14
0x18003318b  push    r15
0x18003318d  lea     rbp, [rsp-308h]
0x180033195  sub     rsp, 408h
0x18003319c  mov     rax, cs:__security_cookie
0x1800331a3  xor     rax, rsp
0x1800331a6  mov     [rbp+340h+var_50], rax
0x1800331ad  mov     r14, r9
0x1800331b0  mov     [rbp+340h+var_390], r9
0x1800331b4  mov     r15, r8
0x1800331b7  mov     [rbp+340h+var_388], r8
0x1800331bb  mov     rsi, rdx
0x1800331be  mov     [rbp+340h+var_3B8], rdx
0x1800331c2  mov     rdi, rcx
0x1800331c5  mov     [rsp+440h+var_3C8], rcx
0x1800331ca  test    rcx, rcx
0x1800331cd  jz      loc_1800339A8
0x1800331d3  test    rdx, rdx
0x1800331d6  jz      loc_1800339A8
0x1800331dc  xor     r12d, r12d
0x1800331df  xor     edx, edx; Val
0x1800331e1  mov     r8d, 250h; Size
0x1800331e7  lea     rcx, [rbp+340h+FindFileData]; void *
0x1800331ee  call    memset_0
0x1800331f3  lea     rcx, [rbp+340h+var_2E8]
0x1800331f7  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x1800331fd  nop
0x1800331fe  lea     rdx, asc_180061A1C; "*"
0x180033205  lea     rcx, [rbp+340h+var_380]
0x180033209  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18003320f  nop
0x180033210  mov     rdx, rax
0x180033213  mov     rcx, rdi
0x180033216  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x18003321c  mov     rdx, rax
0x18003321f  lea     rcx, [rbp+340h+var_308]
0x180033223  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180033229  nop
0x18003322a  lea     rdx, [rbp+340h+var_308]
0x18003322e  lea     rcx, [rbp+340h+var_2E8]
0x180033232  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180033238  nop
0x180033239  lea     rcx, [rbp+340h+var_308]
0x18003323d  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180033243  nop
0x180033244  lea     rcx, [rbp+340h+var_380]
0x180033248  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18003324e  lea     rcx, [rbp+340h+var_2E8]
0x180033252  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180033258  mov     rcx, rax
0x18003325b  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180033261  mov     rcx, rax; lpFileName
0x180033264  lea     rdx, [rbp+340h+FindFileData]; lpFindFileData
0x18003326b  call    cs:__imp_FindFirstFileW
0x180033271  mov     [rbp+340h+hFindFile], rax
0x180033275  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180033279  jnz     short loc_1800332AB
0x18003327b  call    cs:__imp_GetLastError
0x180033281  mov     ecx, eax
0x180033283  add     eax, 0FFFFFFFEh
0x180033286  cmp     eax, 1
0x180033289  jbe     loc_18003398E
0x18003328f  test    ecx, ecx
0x180033291  jg      short loc_18003329B
0x180033293  mov     r12d, ecx
0x180033296  jmp     loc_18003398E
0x18003329b  movzx   r12d, cx
0x18003329f  or      r12d, 80070000h
0x1800332a6  jmp     loc_18003398E
0x1800332ab  mov     r13d, 80070000h
0x1800332b1  mov     eax, [rbp+340h+FindFileData.dwFileAttributes]
0x1800332b7  test    al, 10h
0x1800332b9  jz      short loc_1800332FF
0x1800332bb  xor     r8d, r8d
0x1800332be  lea     rdx, String1; "."
0x1800332c5  lea     rcx, [rbp+340h+FindFileData.cFileName]
0x1800332cc  call    cs:__imp_?Compare@String@UnBCL@@SAHPEBG0H@Z; UnBCL::String::Compare(ushort const *,ushort const *,int)
0x1800332d2  test    eax, eax
0x1800332d4  jz      loc_180033821
0x1800332da  xor     r8d, r8d
0x1800332dd  lea     rdx, asc_180061A20; ".."
0x1800332e4  lea     rcx, [rbp+340h+FindFileData.cFileName]
0x1800332eb  call    cs:__imp_?Compare@String@UnBCL@@SAHPEBG0H@Z; UnBCL::String::Compare(ushort const *,ushort const *,int)
0x1800332f1  test    eax, eax
0x1800332f3  jz      loc_180033821
0x1800332f9  mov     eax, [rbp+340h+FindFileData.dwFileAttributes]
0x1800332ff  cmp     [rbp+340h+arg_20], 0
0x180033306  jz      short loc_180033310
0x180033308  test    al, 10h
0x18003330a  jz      loc_180033821
0x180033310  mov     ecx, 18h
0x180033315  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18003331b  mov     rbx, rax
0x18003331e  mov     [rbp+340h+var_348], rax
0x180033322  test    rax, rax
0x180033325  jz      short loc_180033343
0x180033327  lea     rdx, [rbp+340h+FindFileData.cFileName]
0x18003332e  mov     rcx, rax
0x180033331  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180033337  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x18003333e  mov     [rbx], rax
0x180033341  jmp     short loc_180033345
0x180033343  xor     ebx, ebx
0x180033345  mov     rdx, rbx
0x180033348  lea     rcx, [rbp+340h+var_328]
0x18003334c  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180033352  nop
0x180033353  test    r14, r14
0x180033356  jz      loc_18003346E
0x18003335c  xor     edx, edx
0x18003335e  lea     rcx, [rbp+340h+var_2F8]
0x180033362  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180033368  nop
0x180033369  lea     rcx, [rbp+340h+var_328]
0x18003336d  test    r15, r15
0x180033370  jz      short loc_1800333E1
0x180033372  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180033378  mov     rdx, rax
0x18003337b  mov     rcx, r15
0x18003337e  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x180033384  mov     rdx, rax
0x180033387  lea     rcx, [rbp+340h+var_368]
0x18003338b  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180033391  nop
0x180033392  lea     rdx, [rbp+340h+var_368]
0x180033396  lea     rcx, [rbp+340h+var_2F8]
0x18003339a  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1800333a0  nop
0x1800333a1  lea     rcx, [rbp+340h+var_368]
0x1800333a5  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800333ab  lea     rcx, [rbp+340h+var_2F8]
0x1800333af  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1800333b5  mov     rcx, rax
0x1800333b8  call    cs:__imp_?ToLower@String@UnBCL@@QEBAPEAV12@XZ; UnBCL::String::ToLower(void)
0x1800333be  mov     rdx, rax
0x1800333c1  lea     rcx, [rbp+340h+var_358]
0x1800333c5  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800333cb  nop
0x1800333cc  lea     rdx, [rbp+340h+var_358]
0x1800333d0  lea     rcx, [rbp+340h+var_2F8]
0x1800333d4  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1800333da  nop
0x1800333db  lea     rcx, [rbp+340h+var_358]
0x1800333df  jmp     short loc_180033411
0x1800333e1  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1800333e7  mov     rcx, rax
0x1800333ea  call    cs:__imp_?ToLower@String@UnBCL@@QEBAPEAV12@XZ; UnBCL::String::ToLower(void)
0x1800333f0  mov     rdx, rax
0x1800333f3  lea     rcx, [rbp+340h+var_380]
0x1800333f7  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800333fd  nop
0x1800333fe  lea     rdx, [rbp+340h+var_380]
0x180033402  lea     rcx, [rbp+340h+var_2F8]
0x180033406  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x18003340c  nop
0x18003340d  lea     rcx, [rbp+340h+var_380]
0x180033411  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180033417  mov     rax, [r14+8]
0x18003341b  movsxd  rdi, dword ptr [rax+10h]
0x18003341f  mov     rax, [rdi+r14+8]
0x180033424  mov     rbx, [rax+40h]
0x180033428  lea     rcx, [rbp+340h+var_2F8]
0x18003342c  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180033432  mov     rdx, rax
0x180033435  lea     rcx, [rdi+8]
0x180033439  add     rcx, r14
0x18003343c  mov     rax, rbx
0x18003343f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033444  nop
0x180033445  lea     rcx, [rbp+340h+var_2F8]
0x180033449  test    eax, eax
0x18003344b  jz      short loc_180033463
0x18003344d  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180033453  nop
0x180033454  lea     rcx, [rbp+340h+var_328]
0x180033458  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18003345e  jmp     loc_18003381C
0x180033463  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180033469  mov     rdi, [rsp+440h+var_3C8]
0x18003346e  mov     ecx, 18h
0x180033473  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180033479  mov     rbx, rax
0x18003347c  mov     [rbp+340h+var_340], rax
0x180033480  xor     r14d, r14d
0x180033483  test    rax, rax
0x180033486  jz      short loc_1800334A4
0x180033488  lea     rdx, [rbp+340h+FindFileData.cAlternateFileName]
0x18003348f  mov     rcx, rax
0x180033492  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180033498  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x18003349f  mov     [rbx], rax
0x1800334a2  jmp     short loc_1800334A7
0x1800334a4  mov     rbx, r14
0x1800334a7  mov     rdx, rbx
0x1800334aa  lea     rcx, [rbp+340h+var_308]
0x1800334ae  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800334b4  nop
0x1800334b5  lea     rcx, [rbp+340h+var_328]
0x1800334b9  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800334bf  mov     rdx, rax
0x1800334c2  mov     rcx, rdi
0x1800334c5  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1800334cb  mov     rdx, rax
0x1800334ce  lea     rcx, [rbp+340h+var_338]
0x1800334d2  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800334d8  nop
0x1800334d9  mov     eax, [rbp+340h+FindFileData.dwFileAttributes]
0x1800334df  and     eax, 400h
0x1800334e4  neg     eax
0x1800334e6  sbb     eax, eax
0x1800334e8  and     eax, [rbp+340h+FindFileData.dwReserved0]
0x1800334ee  mov     [rsp+440h+var_3D0], eax
0x1800334f2  test    byte ptr [rbp+340h+FindFileData.dwFileAttributes], 10h
0x1800334f9  jz      short loc_180033500
0x1800334fb  mov     rax, r14
0x1800334fe  jmp     short loc_180033512
0x180033500  lea     rcx, [rbp+340h+var_338]
0x180033504  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18003350a  mov     rcx, rax
0x18003350d  call    ?GetFileHardlinks@@YAPEAV?$ArrayList@PEAVString@UnBCL@@@UnBCL@@PEAVString@2@@Z; GetFileHardlinks(UnBCL::String *)
0x180033512  mov     rdx, rax
0x180033515  lea     rcx, [rbp+340h+var_318]
0x180033519  call    cs:__imp_??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(UnBCL::ArrayList<UnBCL::String *> *)
0x18003351f  nop
0x180033520  lea     rcx, [rbp+340h+var_318]
0x180033524  call    cs:__imp_?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::get_P(void)
0x18003352a  test    rax, rax
0x18003352d  jz      short loc_180033548
0x18003352f  lea     rcx, [rbp+340h+var_318]
0x180033533  call    cs:__imp_??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(void)
0x180033539  mov     rcx, rax
0x18003353c  mov     rax, [rax]
0x18003353f  mov     rax, [rax+58h]
0x180033543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033548  mov     [rsp+440h+var_3D8], r14
0x18003354d  lea     rcx, [rbp+340h+var_318]
0x180033551  call    cs:__imp_?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::get_P(void)
0x180033557  test    rax, rax
0x18003355a  jz      loc_1800336D7
0x180033560  lea     rcx, [rbp+340h+var_338]
0x180033564  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18003356a  mov     rcx, rax
0x18003356d  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180033573  mov     rcx, rax; lpFileName
0x180033576  mov     [rsp+440h+hTemplateFile], r14; hTemplateFile
0x18003357b  mov     [rsp+440h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180033583  mov     [rsp+440h+dwCreationDisposition], 3; dwCreationDisposition
0x18003358b  xor     r9d, r9d; lpSecurityAttributes
0x18003358e  mov     edx, 80h; dwDesiredAccess
0x180033593  lea     r8d, [r9+7]; dwShareMode
0x180033597  call    cs:__imp_CreateFileW
0x18003359d  mov     r15, rax
0x1800335a0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800335a4  jz      loc_18003383F
0x1800335aa  xorps   xmm0, xmm0
0x1800335ad  xor     eax, eax
0x1800335af  movups  xmmword ptr [rbp+340h+FileInformation.dwFileAttributes], xmm0
0x1800335b3  movups  xmmword ptr [rbp+340h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x1800335b7  movups  xmmword ptr [rbp+340h+FileInformation.nFileSizeHigh], xmm0
0x1800335be  mov     [rbp+340h+FileInformation.nFileIndexLow], eax
0x1800335c4  lea     rdx, [rbp+340h+FileInformation]; lpFileInformation
0x1800335c8  mov     rcx, r15; hFile
0x1800335cb  call    cs:__imp_GetFileInformationByHandle
0x1800335d1  test    eax, eax
0x1800335d3  jz      short loc_1800335FD
0x1800335d5  mov     esi, [rbp+340h+FileInformation.dwFileAttributes]
0x1800335d8  mov     [rsp+440h+var_3E0], esi
0x1800335dc  mov     rbx, qword ptr [rbp+340h+FileInformation.ftCreationTime.dwLowDateTime]
0x1800335e0  mov     rdi, qword ptr [rbp+340h+FileInformation.ftLastWriteTime.dwLowDateTime]
0x1800335e4  mov     eax, [rbp+340h+FileInformation.nFileSizeLow]
0x1800335ea  mov     dword ptr [rsp+440h+var_3D8], eax
0x1800335ee  mov     eax, [rbp+340h+FileInformation.nFileSizeHigh]
0x1800335f4  mov     dword ptr [rsp+440h+var_3D8+4], eax
0x1800335f8  jmp     loc_1800336BF
0x1800335fd  mov     [rsp+440h+var_3E0], r14d
0x180033602  mov     rbx, r14
0x180033605  mov     rdi, r14
0x180033608  call    cs:__imp_GetLastError
0x18003360e  test    eax, eax
0x180033610  jle     short loc_18003361A
0x180033612  movzx   eax, ax
0x180033615  or      eax, r13d
0x180033618  test    eax, eax
0x18003361a  jns     short loc_180033632
0x18003361c  call    cs:__imp_GetLastError
0x180033622  mov     r12d, eax
0x180033625  test    eax, eax
0x180033627  jle     short loc_180033638
0x180033629  movzx   r12d, ax
0x18003362d  or      r12d, r13d
0x180033630  jmp     short loc_180033638
0x180033632  mov     r12d, 80004005h
0x180033638  call    cs:__imp_GetLastError
0x18003363e  mov     r14d, eax
  ... truncated ...
```
