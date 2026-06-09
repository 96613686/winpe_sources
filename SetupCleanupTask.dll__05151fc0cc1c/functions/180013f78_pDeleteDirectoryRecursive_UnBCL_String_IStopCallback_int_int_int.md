# pDeleteDirectoryRecursive(UnBCL::String *,IStopCallback *,int *,int *,int *)

- ea: `0x180013f78`
- end: `0x180014b78`
- name: `?pDeleteDirectoryRecursive@@YAXPEAVString@UnBCL@@PEAVIStopCallback@@PEAH22@Z`
- size: `3072`
- prototype: `void __fastcall(struct UnBCL::String *, struct IStopCallback *, int *, int *, int *)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, reparse_path, service_task, installer_update, broker_com_uri`

## callers

- `0x180011214`
- `0x180012600`
- `0x180013f78`

## callees

- `0x18000272c`
- `0x180003c68`
- `0x18000638c`
- `0x18000d054`
- `0x18000d094`
- `0x180013dd8`
- `0x180013f78`
- `0x18002e578`
- `0x1800322d2`
- `0x180032310`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014297`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800148c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014297`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800148c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800142b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800142c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014444`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014541`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001454b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014651`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014666`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014744`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014755`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001482f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800148e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800148f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800142b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800142c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014444`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014541`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001454b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014651`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014666`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014744`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014755`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001482f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800148e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800148f1`
- `unbcl!?ShouldEnumerateReparsePoint@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x1800141a9`
- `unbcl!?ShouldEnumerateReparsePoint@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x1800141a9`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x1800140fd`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x18001411d`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x1800140fd`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x18001411d`
- `unbcl!?SetLiteralStorage@_@UnBCL@@YAXPEAPEBVString@2@PEBG@Z` at `0x180014053`
- `unbcl!?SetLiteralStorage@_@UnBCL@@YAXPEAPEBVString@2@PEBG@Z` at `0x180014053`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1800149b1`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x180014a12`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x180014a75`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x180014ad6`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x180014b37`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1800149b1`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x180014a12`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x180014a75`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x180014ad6`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x180014b37`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18001406f`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180014148`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180014404`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18001406f`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180014148`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180014404`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800141a0`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800142db`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180014380`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18001445d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180014568`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180014678`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800141a0`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800142db`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180014380`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18001445d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180014568`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180014678`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18001408f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180014176`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180014280`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800142f7`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180014479`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18001451d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180014584`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180014617`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180014694`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18001408f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180014176`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180014280`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800142f7`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180014479`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18001451d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180014584`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180014617`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180014694`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180014098`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18001417f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800141e5`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180014289`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180014300`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180014482`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180014526`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18001458d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180014620`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18001469d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180014760`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180014843`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800148b5`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800148fc`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180014098`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18001417f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800141e5`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180014289`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180014300`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180014482`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180014526`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18001458d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180014620`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18001469d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180014760`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180014843`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800148b5`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800148fc`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180014994`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800149f5`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180014a58`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180014ab9`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180014b1a`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180014994`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800149f5`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180014a58`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180014ab9`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180014b1a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180014250`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18001426d`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800143b2`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800143cf`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800144ed`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18001450a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18001471b`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800147e4`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180014250`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18001426d`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800143b2`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800143cf`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800144ed`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18001450a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18001471b`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800147e4`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180014080`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180014159`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180014415`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180014080`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180014159`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180014415`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180014168`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180014424`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180014168`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180014424`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18001413b`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800143f7`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18001413b`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800143f7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180014188`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180014188`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800140ba`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800140a9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800140a9`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180014731`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180014731`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18001462f`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18001462f`
- `WDSCORE!CurrentIP` at `0x1800141d9`
- `WDSCORE!CurrentIP` at `0x1800142be`
- `WDSCORE!CurrentIP` at `0x18001444c`
- `WDSCORE!CurrentIP` at `0x180014555`
- `WDSCORE!CurrentIP` at `0x18001465b`
- `WDSCORE!CurrentIP` at `0x18001474c`
- `WDSCORE!CurrentIP` at `0x180014837`
- `WDSCORE!CurrentIP` at `0x1800148e8`
- `WDSCORE!CurrentIP` at `0x1800141d9`
- `WDSCORE!CurrentIP` at `0x1800142be`
- `WDSCORE!CurrentIP` at `0x18001444c`
- `WDSCORE!CurrentIP` at `0x180014555`
- `WDSCORE!CurrentIP` at `0x18001465b`
- `WDSCORE!CurrentIP` at `0x18001474c`
- `WDSCORE!CurrentIP` at `0x180014837`
- `WDSCORE!CurrentIP` at `0x1800148e8`
- `WDSCORE!WdsSetupLogMessageW` at `0x180014241`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001436a`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800144de`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800145f7`
- `WDSCORE!WdsSetupLogMessageW` at `0x180014707`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800147bf`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001489f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001495b`
- `WDSCORE!WdsSetupLogMessageW` at `0x180014241`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001436a`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800144de`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800145f7`
- `WDSCORE!WdsSetupLogMessageW` at `0x180014707`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800147bf`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001489f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001495b`

## string_xrefs

- `0x1800149c6`: `void __cdecl pDeleteDirectoryRecursive(class UnBCL::String *,class IStopCallback *,int *,int *,int *)`
- `0x180014a27`: `void __cdecl pDeleteDirectoryRecursive(class UnBCL::String *,class IStopCallback *,int *,int *,int *)`
- `0x180014a8a`: `void __cdecl pDeleteDirectoryRecursive(class UnBCL::String *,class IStopCallback *,int *,int *,int *)`
- `0x180014aeb`: `void __cdecl pDeleteDirectoryRecursive(class UnBCL::String *,class IStopCallback *,int *,int *,int *)`
- `0x180014b4c`: `void __cdecl pDeleteDirectoryRecursive(class UnBCL::String *,class IStopCallback *,int *,int *,int *)`
- `0x1800149a7`: `FullDirPath`
- `0x180014b2d`: `PendingDelete`
- `0x180014212`: `pDeleteDirectoryRecursive`
- `0x18001433b`: `pDeleteDirectoryRecursive`
- `0x1800144af`: `pDeleteDirectoryRecursive`
- `0x1800145c8`: `pDeleteDirectoryRecursive`
- `0x1800146d8`: `pDeleteDirectoryRecursive`
- `0x180014790`: `pDeleteDirectoryRecursive`
- `0x180014870`: `pDeleteDirectoryRecursive`
- `0x18001492c`: `pDeleteDirectoryRecursive`
- `0x18001421e`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanupjobs.cpp`
- `0x180014347`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanupjobs.cpp`
- `0x1800144bb`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanupjobs.cpp`
- `0x1800145d4`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanupjobs.cpp`
- `0x1800146e4`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanupjobs.cpp`
- `0x18001479c`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanupjobs.cpp`
- `0x18001487c`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanupjobs.cpp`
- `0x180014938`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanupjobs.cpp`
- `0x1800141ee`: `Interruption requested. Current directory: %s`
- `0x18001484c`: `Interruption requested. Current directory: %s`
- `0x18001430e`: `Failed to delete directory junction: %s. GLE = %d`
- `0x18001459b`: `Failed to delete file: %s. GLE = %d`
- `0x1800146ab`: `Can't register deferred target move: %s. GLE = %d`
- `0x18001476c`: `FindFirstFile returned Invalid file handle for directory: %s, error: %d`
- `0x180014908`: `Failed to delete directory: %s. GLE = %d`

## pseudocode

```c
void __fastcall pDeleteDirectoryRecursive(
        struct UnBCL::String *a1,
        struct IStopCallback *a2,
        int *a3,
        int *a4,
        int *a5)
{
  struct IStopCallback *v7; // rbx
  const unsigned __int16 *v9; // r8
  struct UnBCL::String *v10; // rax
  UnBCL::String *v11; // rax
  const WCHAR *CString; // rax
  __int64 v13; // r8
  int v14; // esi
  const struct UnBCL::String *v15; // rax
  struct UnBCL::String *v16; // rax
  UnBCL::String *v17; // rax
  const WCHAR *v18; // rax
  const struct UnBCL::String *v19; // rax
  int v20; // eax
  DWORD v21; // edi
  __int64 v22; // rbx
  const char *v23; // rax
  struct tagLOG_PARTIAL_MSG *v24; // rax
  UnBCL::String *v25; // rax
  const unsigned __int16 *v26; // rax
  const wchar_t *v27; // rax
  UnBCL::String *v28; // rax
  struct tagLOG_PARTIAL_MSG *v29; // rax
  struct UnBCL::String *P; // rax
  _BYTE *v31; // rcx
  const struct UnBCL::String *v32; // rax
  struct UnBCL::String *v33; // rax
  int v34; // eax
  DWORD LastError; // ebx
  __int64 v36; // rdi
  const wchar_t *v37; // rax
  UnBCL::String *v38; // rax
  struct tagLOG_PARTIAL_MSG *v39; // rax
  UnBCL::String *v40; // rax
  const unsigned __int16 *v41; // rax
  const wchar_t *v42; // rax
  UnBCL::String *v43; // rax
  struct tagLOG_PARTIAL_MSG *v44; // rax
  UnBCL::String *v45; // rax
  const WCHAR *v46; // rax
  const wchar_t *v47; // rax
  UnBCL::String *v48; // rax
  struct tagLOG_PARTIAL_MSG *v49; // rax
  DWORD v50; // esi
  __int64 v51; // rdi
  DWORD v52; // ebx
  const char *v53; // rax
  struct tagLOG_PARTIAL_MSG *v54; // rax
  int v55; // eax
  DWORD v56; // edi
  __int64 v57; // rbx
  const char *v58; // rax
  struct tagLOG_PARTIAL_MSG *v59; // rax
  const unsigned __int16 *v60; // rax
  DWORD v61; // esi
  __int64 v62; // rdi
  DWORD v63; // ebx
  const char *v64; // rax
  struct tagLOG_PARTIAL_MSG *v65; // rax
  UnBCL::ArgumentNullException *v66; // rax
  UnBCL::ArgumentNullException *v67; // rbx
  UnBCL::ArgumentNullException *v68; // rax
  UnBCL::ArgumentNullException *v69; // rbx
  UnBCL::ArgumentNullException *v70; // rax
  UnBCL::ArgumentNullException *v71; // rbx
  UnBCL::ArgumentNullException *v72; // rax
  UnBCL::ArgumentNullException *v73; // rbx
  UnBCL::ArgumentNullException *v74; // rax
  UnBCL::ArgumentNullException *v75; // rbx
  DWORD v76; // [rsp+60h] [rbp-398h] BYREF
  DWORD v77; // [rsp+64h] [rbp-394h]
  int v78; // [rsp+68h] [rbp-390h]
  struct IStopCallback *v79; // [rsp+70h] [rbp-388h]
  int *v80; // [rsp+78h] [rbp-380h]
  _BYTE v81[16]; // [rsp+80h] [rbp-378h] BYREF
  _BYTE v82[16]; // [rsp+90h] [rbp-368h] BYREF
  int *v83; // [rsp+A0h] [rbp-358h]
  struct UnBCL::String *v84; // [rsp+A8h] [rbp-350h]
  int *v85; // [rsp+B0h] [rbp-348h]
  int *v86; // [rsp+B8h] [rbp-340h]
  _BYTE v87[24]; // [rsp+C0h] [rbp-338h] BYREF
  __int64 pExceptionObject; // [rsp+D8h] [rbp-320h] BYREF
  __int64 v89; // [rsp+E0h] [rbp-318h] BYREF
  __int64 v90; // [rsp+E8h] [rbp-310h] BYREF
  __int64 v91; // [rsp+F0h] [rbp-308h] BYREF
  __int64 v92; // [rsp+F8h] [rbp-300h] BYREF
  HANDLE hFindFile; // [rsp+100h] [rbp-2F8h]
  struct IStopCallback *v94; // [rsp+108h] [rbp-2F0h]
  _BYTE v95[32]; // [rsp+110h] [rbp-2E8h] BYREF
  _BYTE v96[24]; // [rsp+130h] [rbp-2C8h] BYREF
  _BYTE v97[24]; // [rsp+148h] [rbp-2B0h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+160h] [rbp-298h] BYREF

  v86 = a4;
  v7 = a2;
  v79 = a2;
  v84 = a1;
  v94 = a2;
  v80 = a3;
  v85 = a4;
  v83 = a5;
  if ( !a1 )
  {
    v66 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v67 = v66;
    v80 = (int *)v66;
    if ( v66 )
    {
      UnBCL::ArgumentNullException::ArgumentNullException(v66, L"FullDirPath");
      *(_QWORD *)v67 = &UnBCL::ArgumentNullException::`local vftable';
    }
    else
    {
      v67 = 0;
    }
    pExceptionObject = AddStackTraceToException<SetupCleanupTaskException>(
                         v67,
                         "void __cdecl pDeleteDirectoryRecursive(class UnBCL::String *,class IStopCallback *,int *,int *,int *)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( !a2 )
  {
    v68 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v69 = v68;
    v80 = (int *)v68;
    if ( v68 )
    {
      UnBCL::ArgumentNullException::ArgumentNullException(v68, L"StopCallback");
      *(_QWORD *)v69 = &UnBCL::ArgumentNullException::`local vftable';
    }
    else
    {
      v69 = 0;
    }
    v89 = AddStackTraceToException<SetupCleanupTaskException>(
            v69,
            "void __cdecl pDeleteDirectoryRecursive(class UnBCL::String *,class IStopCallback *,int *,int *,int *)");
    throw (UnBCL::ArgumentNullException **)&v89;
  }
  if ( !a3 )
  {
    v70 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v71 = v70;
    v80 = (int *)v70;
    if ( v70 )
    {
      UnBCL::ArgumentNullException::ArgumentNullException(v70, L"Interrupted");
      *(_QWORD *)v71 = &UnBCL::ArgumentNullException::`local vftable';
    }
    else
    {
      v71 = 0;
    }
    v90 = AddStackTraceToException<SetupCleanupTaskException>(
            v71,
            "void __cdecl pDeleteDirectoryRecursive(class UnBCL::String *,class IStopCallback *,int *,int *,int *)");
    throw (UnBCL::ArgumentNullException **)&v90;
  }
  if ( !a4 )
  {
    v72 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v73 = v72;
    v80 = (int *)v72;
    if ( v72 )
    {
      UnBCL::ArgumentNullException::ArgumentNullException(v72, L"Errors");
      *(_QWORD *)v73 = &UnBCL::ArgumentNullException::`local vftable';
    }
    else
    {
      v73 = 0;
    }
    v91 = AddStackTraceToException<SetupCleanupTaskException>(
            v73,
            "void __cdecl pDeleteDirectoryRecursive(class UnBCL::String *,class IStopCallback *,int *,int *,int *)");
    throw (UnBCL::ArgumentNullException **)&v91;
  }
  if ( !a5 )
  {
    v74 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v75 = v74;
    v80 = (int *)v74;
    if ( v74 )
    {
      UnBCL::ArgumentNullException::ArgumentNullException(v74, L"PendingDelete");
      *(_QWORD *)v75 = &UnBCL::ArgumentNullException::`local vftable';
    }
    else
    {
      v75 = 0;
    }
    v92 = AddStackTraceToException<SetupCleanupTaskException>(
            v75,
            "void __cdecl pDeleteDirectoryRecursive(class UnBCL::String *,class IStopCallback *,int *,int *,int *)");
    throw (UnBCL::ArgumentNullException **)&v92;
  }
  v78 = 0;
  if ( !*a3 )
  {
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    pCheckPathTooLong(a1);
    if ( qword_180052E70 )
    {
      v76 = 0;
      _InterlockedIncrement((volatile signed __int32 *)&v76);
    }
    else
    {
      UnBCL::_::SetLiteralStorage((UnBCL::_ *)&qword_180052E70, (const struct UnBCL::String **)L"*", v9);
    }
    v10 = UnBCL::Path::Combine(a1, (const struct UnBCL::String *)qword_180052E70);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v87, v10);
    v11 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v87);
    CString = UnBCL::String::get_CString(v11);
    hFindFile = FindFirstFileW(CString, &FindFileData);
    MakeGuard<int (*)(void *),void *>(v95, FindClose, hFindFile);
    if ( v13 != -1 )
    {
      v14 = v78;
      while ( 1 )
      {
        if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
        {
          v32 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v97, FindFileData.cFileName);
          v33 = UnBCL::Path::Combine(a1, v32);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v81, v33);
          UnBCL::String::~String((UnBCL::String *)v97);
          v34 = (**(__int64 (__fastcall ***)(struct IStopCallback *))v7)(v7);
          *a3 = v34;
          if ( v34 )
          {
            LastError = GetLastError();
            v36 = CurrentIP();
            if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v81) )
            {
              v38 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v81);
              v37 = UnBCL::String::get_CString(v38);
            }
            else
            {
              v37 = L"(NULL)";
            }
            v39 = ConstructPartialMsgW(0x4000000u, "Interruption requested. Current file: %s", (const char *)v37);
            WdsSetupLogMessageW(
              v39,
              0,
              L"D",
              0,
              170,
              L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
              L"pDeleteDirectoryRecursive",
              v36,
              LastError,
              0,
              0);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v81);
            ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<int (*)(void *),void *>>(v95);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v87);
            return;
          }
          v40 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v81);
          v41 = UnBCL::String::get_CString(v40);
          if ( (unsigned int)DeleteFileEx2(v41, 36) )
            goto LABEL_47;
          v76 = GetLastError();
          v77 = GetLastError();
          v79 = (struct IStopCallback *)CurrentIP();
          if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v81) )
          {
            v43 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v81);
            v42 = UnBCL::String::get_CString(v43);
          }
          else
          {
            v42 = L"(NULL)";
          }
          v44 = ConstructPartialMsgW(0x3000000u, "Failed to delete file: %s. GLE = %d", (const char *)v42, v76);
          WdsSetupLogMessageW(
            v44,
            0,
            L"D",
            0,
            177,
            L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
            L"pDeleteDirectoryRecursive",
            v79,
            v77,
            0,
            0);
          if ( v76 == 5 || v76 == 32 )
          {
            v45 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v81);
            v46 = UnBCL::String::get_CString(v45);
            if ( MoveFileExW(v46, 0, 4u) )
            {
              v14 = 1;
              v78 = 1;
              *v83 = 1;
LABEL_47:
              v31 = v81;
              goto LABEL_48;
            }
            v76 = GetLastError();
            v79 = (struct IStopCallback *)CurrentIP();
            v77 = GetLastError();
            if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v81) )
            {
              v48 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v81);
              v47 = UnBCL::String::get_CString(v48);
            }
            else
            {
              v47 = L"(NULL)";
            }
            v49 = ConstructPartialMsgW(
                    0x3000000u,
                    "Can't register deferred target move: %s. GLE = %d",
                    (const char *)v47,
                    v77);
            WdsSetupLogMessageW(
              v49,
              0,
              L"D",
              0,
              193,
              L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
              L"pDeleteDirectoryRecursive",
              v79,
              v76,
              0,
              0);
          }
          *a4 = 1;
          goto LABEL_47;
        }
        if ( !UnBCL::String::Compare(FindFileData.cFileName, L".", 0)
          || !UnBCL::String::Compare(FindFileData.cFileName, L"..", 0) )
        {
          goto LABEL_49;
        }
        v15 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v96, FindFileData.cFileName);
        v16 = UnBCL::Path::Combine(a1, v15);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v82, v16);
        UnBCL::String::~String((UnBCL::String *)v96);
        v17 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v82);
        v18 = UnBCL::String::get_CString(v17);
        if ( (GetFileAttributesW(v18) & 0x400) == 0
          || (v19 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v82),
              UnBCL::Directory::ShouldEnumerateReparsePoint(v19)) )
        {
          P = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v82);
          pDeleteDirectoryRecursive(P, v7, a3, a4, v83);
          if ( *a3 )
          {
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v82);
            ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<int (*)(void *),void *>>(v95);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v87);
            return;
          }
          goto LABEL_28;
        }
        v20 = (**(__int64 (__fastcall ***)(struct IStopCallback *))v7)(v7);
        *a3 = v20;
        if ( v20 )
        {
          v21 = GetLastError();
          v22 = CurrentIP();
          v23 = (const char *)UnBCL::String::get_CString(a1);
          v24 = ConstructPartialMsgW(0x4000000u, "Interruption requested. Current directory: %s", v23);
          WdsSetupLogMessageW(
            v24,
            0,
            L"D",
            0,
            143,
            L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
            L"pDeleteDirectoryRecursive",
            v22,
            v21,
            0,
            0);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v82);
          ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<int (*)(void *),void *>>(v95);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v87);
          return;
        }
        v25 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v82);
        v26 = UnBCL::String::get_CString(v25);
        if ( !v26 )
          break;
        if ( !(unsigned int)DeleteFileEx2(v26, 32) )
          goto LABEL_22;
LABEL_28:
        v31 = v82;
LABEL_48:
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v31);
LABEL_49:
        if ( !FindNextFileW(hFindFile, &FindFileData) )
          goto LABEL_52;
      }
      SetLastError(0x57u);
LABEL_22:
      v77 = GetLastError();
      v79 = (struct IStopCallback *)CurrentIP();
      v76 = GetLastError();
      if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v82) )
      {
        v28 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v82);
        v27 = UnBCL::String::get_CString(v28);
      }
      else
      {
        v27 = L"(NULL)";
      }
      v29 = ConstructPartialMsgW(
              0x2000000u,
              "Failed to delete directory junction: %s. GLE = %d",
              (const char *)v27,
              v76);
      WdsSetupLogMessageW(
        v29,
        0,
        L"D",
        0,
        155,
        L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
        L"pDeleteDirectoryRecursive",
        v79,
        v77,
        0,
        0);
      *a4 = 1;
      goto LABEL_28;
    }
    v50 = GetLastError();
    v51 = CurrentIP();
    v52 = GetLastError();
    v53 = (const char *)UnBCL::String::get_CString(a1);
    v54 = ConstructPartialMsgW(
            0x4000000u,
            "FindFirstFile returned Invalid file handle for directory: %s, error: %d",
            v53,
            v52);
    WdsSetupLogMessageW(
      v54,
      0,
      L"D",
      0,
      209,
      L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
      L"pDeleteDirectoryRecursive",
      v51,
      v50,
      0,
      0);
    v7 = v79;
    v14 = v78;
LABEL_52:
    ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<int (*)(void *),void *>>(v95);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v87);
    v55 = (**(__int64 (__fastcall ***)(struct IStopCallback *))v7)(v7);
    *a3 = v55;
    if ( v55 )
    {
      v56 = GetLastError();
      v57 = CurrentIP();
      v58 = (const char *)UnBCL::String::get_CString(a1);
      v59 = ConstructPartialMsgW(0x4000000u, "Interruption requested. Current directory: %s", v58);
      WdsSetupLogMessageW(
        v59,
        0,
        L"D",
        0,
        224,
        L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
        L"pDeleteDirectoryRecursive",
        v57,
        v56,
        0,
        0);
      return;
    }
    if ( !v14 )
    {
      v60 = UnBCL::String::get_CString(a1);
      if ( v60 )
      {
        if ( (unsigned int)DeleteFileEx2(v60, 32) )
          return;
      }
      else
      {
        SetLastError(0x57u);
      }
      v61 = GetLastError();
      v62 = CurrentIP();
      v63 = GetLastError();
      v64 = (const char *)UnBCL::String::get_CString(a1);
      v65 = ConstructPartialMsgW(0x2000000u, "Failed to delete directory: %s. GLE = %d", v64, v63);
      WdsSetupLogMessageW(
        v65,
        0,
        L"D",
        0,
        234,
        L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
        L"pDeleteDirectoryRecursive",
        v62,
        v61,
        0,
        0);
      *v86 = 1;
    }
  }
}

```

## disassembly

```asm
0x180013f78  push    rbx
0x180013f7a  push    rsi
0x180013f7b  push    rdi
0x180013f7c  push    r12
0x180013f7e  push    r14
0x180013f80  push    r15
0x180013f82  sub     rsp, 3C8h
0x180013f89  mov     rax, cs:__security_cookie
0x180013f90  xor     rax, rsp
0x180013f93  mov     [rsp+3F8h+var_48], rax
0x180013f9b  mov     rdi, r9
0x180013f9e  mov     [rsp+3F8h+var_340], r9
0x180013fa6  mov     r12, r8
0x180013fa9  mov     rbx, rdx
0x180013fac  mov     [rsp+3F8h+var_388], rdx
0x180013fb1  mov     r15, rcx
0x180013fb4  mov     [rsp+3F8h+var_350], rcx
0x180013fbc  mov     [rsp+3F8h+var_2F0], rdx
0x180013fc4  mov     [rsp+3F8h+var_380], r8
0x180013fc9  mov     [rsp+3F8h+var_348], r9
0x180013fd1  mov     rax, [rsp+3F8h+arg_20]
0x180013fd9  mov     [rsp+3F8h+var_358], rax
0x180013fe1  xor     r14d, r14d
0x180013fe4  test    rcx, rcx
0x180013fe7  jz      loc_180014990
0x180013fed  test    rbx, rbx
0x180013ff0  jz      loc_1800149F2
0x180013ff6  test    r12, r12
0x180013ff9  jz      loc_180014A53
0x180013fff  test    rdi, rdi
0x180014002  jz      loc_180014AB6
0x180014008  test    rax, rax
0x18001400b  jz      loc_180014B17
0x180014011  mov     [rsp+3F8h+var_390], r14d
0x180014016  cmp     [r8], r14d
0x180014019  jnz     loc_18001496F
0x18001401f  xor     edx, edx; Val
0x180014021  mov     r8d, 250h; Size
0x180014027  lea     rcx, [rsp+3F8h+FindFileData]; void *
0x18001402f  call    memset_0
0x180014034  mov     rcx, r15; struct UnBCL::String *
0x180014037  call    ?pCheckPathTooLong@@YAXPEBVString@UnBCL@@@Z; pCheckPathTooLong(UnBCL::String const *)
0x18001403c  cmp     cs:qword_180052E70, r14
0x180014043  jnz     short loc_18001405B
0x180014045  lea     rdx, asc_18003D8D4; "*"
0x18001404c  lea     rcx, qword_180052E70
0x180014053  call    cs:__imp_?SetLiteralStorage@_@UnBCL@@YAXPEAPEBVString@2@PEBG@Z; UnBCL::_::SetLiteralStorage(UnBCL::String const * *,ushort const *)
0x180014059  jmp     short loc_180014065
0x18001405b  mov     [rsp+3F8h+var_398], r14d
0x180014060  lock inc [rsp+3F8h+var_398]
0x180014065  mov     rdx, cs:qword_180052E70
0x18001406c  mov     rcx, r15
0x18001406f  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x180014075  mov     rdx, rax
0x180014078  lea     rcx, [rsp+3F8h+var_338]
0x180014080  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180014086  nop
0x180014087  lea     rcx, [rsp+3F8h+var_338]
0x18001408f  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180014095  mov     rcx, rax
0x180014098  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18001409e  mov     rcx, rax; lpFileName
0x1800140a1  lea     rdx, [rsp+3F8h+FindFileData]; lpFindFileData
0x1800140a9  call    cs:__imp_FindFirstFileW
0x1800140af  mov     r8, rax
0x1800140b2  mov     [rsp+3F8h+hFindFile], rax
0x1800140ba  mov     rdx, cs:__imp_FindClose
0x1800140c1  lea     rcx, [rsp+3F8h+var_2E8]
0x1800140c9  call    ??$MakeGuard@P6AHPEAX@ZPEAX@@YA?AV?$ScopeGuardImpl1@P6AHPEAX@ZPEAX@@P6AHPEAX@Z0@Z; MakeGuard<int (*)(void *),void *>(int (*)(void *),void *)
0x1800140ce  nop
0x1800140cf  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1800140d3  jz      loc_180014744
0x1800140d9  mov     esi, [rsp+3F8h+var_390]
0x1800140dd  test    byte ptr [rsp+3F8h+FindFileData.dwFileAttributes], 10h
0x1800140e5  jz      loc_1800143E7
0x1800140eb  xor     r8d, r8d
0x1800140ee  lea     rdx, asc_18003D8D8; "."
0x1800140f5  lea     rcx, [rsp+3F8h+FindFileData.cFileName]
0x1800140fd  call    cs:__imp_?Compare@String@UnBCL@@SAHPEBG0H@Z; UnBCL::String::Compare(ushort const *,ushort const *,int)
0x180014103  test    eax, eax
0x180014105  jz      loc_180014721
0x18001410b  xor     r8d, r8d
0x18001410e  lea     rdx, asc_18003D8DC; ".."
0x180014115  lea     rcx, [rsp+3F8h+FindFileData.cFileName]
0x18001411d  call    cs:__imp_?Compare@String@UnBCL@@SAHPEBG0H@Z; UnBCL::String::Compare(ushort const *,ushort const *,int)
0x180014123  test    eax, eax
0x180014125  jz      loc_180014721
0x18001412b  lea     rdx, [rsp+3F8h+FindFileData.cFileName]
0x180014133  lea     rcx, [rsp+3F8h+var_2C8]
0x18001413b  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180014141  nop
0x180014142  mov     rdx, rax
0x180014145  mov     rcx, r15
0x180014148  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x18001414e  mov     rdx, rax
0x180014151  lea     rcx, [rsp+3F8h+var_368]
0x180014159  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18001415f  nop
0x180014160  lea     rcx, [rsp+3F8h+var_2C8]
0x180014168  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18001416e  lea     rcx, [rsp+3F8h+var_368]
0x180014176  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18001417c  mov     rcx, rax
0x18001417f  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180014185  mov     rcx, rax; lpFileName
0x180014188  call    cs:__imp_GetFileAttributesW
0x18001418e  bt      eax, 0Ah
0x180014192  jnb     loc_180014378
0x180014198  lea     rcx, [rsp+3F8h+var_368]
0x1800141a0  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800141a6  mov     rcx, rax
0x1800141a9  call    cs:__imp_?ShouldEnumerateReparsePoint@Directory@UnBCL@@SAHPEBVString@2@@Z; UnBCL::Directory::ShouldEnumerateReparsePoint(UnBCL::String const *)
0x1800141af  test    eax, eax
0x1800141b1  jnz     loc_180014378
0x1800141b7  mov     rax, [rbx]
0x1800141ba  mov     rcx, rbx
0x1800141bd  mov     rax, [rax]
0x1800141c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141c5  mov     [r12], eax
0x1800141c9  test    eax, eax
0x1800141cb  jz      loc_180014278
0x1800141d1  call    cs:__imp_GetLastError
0x1800141d7  mov     edi, eax
0x1800141d9  call    cs:__imp_CurrentIP
0x1800141df  mov     rbx, rax
0x1800141e2  mov     rcx, r15
0x1800141e5  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1800141eb  mov     r8, rax
0x1800141ee  lea     rdx, aInterruptionRe; "Interruption requested. Current directo"...
0x1800141f5  mov     ecx, 4000000h; unsigned int
0x1800141fa  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800141ff  mov     [rsp+3F8h+var_3A8], r14d
0x180014204  mov     [rsp+3F8h+var_3B0], r14
0x180014209  mov     [rsp+3F8h+var_3B8], edi
0x18001420d  mov     [rsp+3F8h+var_3C0], rbx
0x180014212  lea     rcx, aPdeletedirecto; "pDeleteDirectoryRecursive"
0x180014219  mov     [rsp+3F8h+var_3C8], rcx
0x18001421e  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupclean"...
0x180014225  mov     [rsp+3F8h+var_3D0], rcx
0x18001422a  mov     dword ptr [rsp+3F8h+var_3D8], 8Fh
0x180014232  xor     r9d, r9d
0x180014235  lea     r8, aD_0; "D"
0x18001423c  xor     edx, edx
0x18001423e  mov     rcx, rax
0x180014241  call    cs:__imp_WdsSetupLogMessageW
0x180014247  nop
0x180014248  lea     rcx, [rsp+3F8h+var_368]
0x180014250  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180014256  nop
0x180014257  lea     rcx, [rsp+3F8h+var_2E8]
0x18001425f  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AHPEAX@ZPEAX@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AHPEAX@ZPEAX@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<int (*)(void *),void *>>(ScopeGuardImpl1<int (*)(void *),void *> &)
0x180014264  nop
0x180014265  lea     rcx, [rsp+3F8h+var_338]
0x18001426d  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180014273  jmp     loc_18001496F
0x180014278  lea     rcx, [rsp+3F8h+var_368]
0x180014280  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180014286  mov     rcx, rax
0x180014289  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18001428f  test    rax, rax
0x180014292  jnz     short loc_18001429F
0x180014294  lea     ecx, [rax+57h]; dwErrCode
0x180014297  call    cs:__imp_SetLastError
0x18001429d  jmp     short loc_1800142B4
0x18001429f  mov     edx, 20h ; ' '
0x1800142a4  mov     rcx, rax
0x1800142a7  call    DeleteFileEx2
0x1800142ac  test    eax, eax
0x1800142ae  jnz     loc_1800143DA
0x1800142b4  call    cs:__imp_GetLastError
0x1800142ba  mov     [rsp+3F8h+var_394], eax
0x1800142be  call    cs:__imp_CurrentIP
0x1800142c4  mov     [rsp+3F8h+var_388], rax
0x1800142c9  call    cs:__imp_GetLastError
0x1800142cf  mov     [rsp+3F8h+var_398], eax
0x1800142d3  lea     rcx, [rsp+3F8h+var_368]
0x1800142db  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800142e1  test    rax, rax
0x1800142e4  jnz     short loc_1800142EF
0x1800142e6  lea     rax, aNull; "(NULL)"
0x1800142ed  jmp     short loc_180014306
0x1800142ef  lea     rcx, [rsp+3F8h+var_368]
0x1800142f7  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1800142fd  mov     rcx, rax
0x180014300  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180014306  mov     r9d, [rsp+3F8h+var_398]
0x18001430b  mov     r8, rax
0x18001430e  lea     rdx, aFailedToDelete_8; "Failed to delete directory junction: %s"...
0x180014315  mov     ecx, 2000000h; unsigned int
0x18001431a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18001431f  mov     [rsp+3F8h+var_3A8], r14d
0x180014324  mov     [rsp+3F8h+var_3B0], r14
0x180014329  mov     ecx, [rsp+3F8h+var_394]
0x18001432d  mov     [rsp+3F8h+var_3B8], ecx
0x180014331  mov     rcx, [rsp+3F8h+var_388]
0x180014336  mov     [rsp+3F8h+var_3C0], rcx
0x18001433b  lea     rcx, aPdeletedirecto; "pDeleteDirectoryRecursive"
0x180014342  mov     [rsp+3F8h+var_3C8], rcx
0x180014347  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupclean"...
0x18001434e  mov     [rsp+3F8h+var_3D0], rcx
0x180014353  mov     dword ptr [rsp+3F8h+var_3D8], 9Bh
0x18001435b  xor     r9d, r9d
0x18001435e  lea     r8, aD_0; "D"
0x180014365  xor     edx, edx
0x180014367  mov     rcx, rax
0x18001436a  call    cs:__imp_WdsSetupLogMessageW
0x180014370  mov     dword ptr [rdi], 1
0x180014376  jmp     short loc_1800143DA
0x180014378  lea     rcx, [rsp+3F8h+var_368]
0x180014380  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180014386  mov     rcx, rax; struct UnBCL::String *
0x180014389  mov     rax, [rsp+3F8h+var_358]
0x180014391  mov     [rsp+3F8h+var_3D8], rax; int *
0x180014396  mov     r9, rdi; int *
0x180014399  mov     r8, r12; int *
0x18001439c  mov     rdx, rbx; struct IStopCallback *
0x18001439f  call    ?pDeleteDirectoryRecursive@@YAXPEAVString@UnBCL@@PEAVIStopCallback@@PEAH22@Z; pDeleteDirectoryRecursive(UnBCL::String *,IStopCallback *,int *,int *,int *)
0x1800143a4  cmp     [r12], r14d
0x1800143a8  jz      short loc_1800143DA
0x1800143aa  lea     rcx, [rsp+3F8h+var_368]
0x1800143b2  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800143b8  nop
0x1800143b9  lea     rcx, [rsp+3F8h+var_2E8]
0x1800143c1  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AHPEAX@ZPEAX@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AHPEAX@ZPEAX@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<int (*)(void *),void *>>(ScopeGuardImpl1<int (*)(void *),void *> &)
0x1800143c6  nop
0x1800143c7  lea     rcx, [rsp+3F8h+var_338]
0x1800143cf  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800143d5  jmp     loc_18001496F
0x1800143da  lea     rcx, [rsp+3F8h+var_368]
0x1800143e2  jmp     loc_18001471B
0x1800143e7  lea     rdx, [rsp+3F8h+FindFileData.cFileName]
0x1800143ef  lea     rcx, [rsp+3F8h+var_2B0]
0x1800143f7  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800143fd  nop
0x1800143fe  mov     rdx, rax
0x180014401  mov     rcx, r15
0x180014404  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x18001440a  mov     rdx, rax
0x18001440d  lea     rcx, [rsp+3F8h+var_378]
0x180014415  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18001441b  nop
0x18001441c  lea     rcx, [rsp+3F8h+var_2B0]
0x180014424  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18001442a  mov     rax, [rbx]
0x18001442d  mov     rcx, rbx
0x180014430  mov     rax, [rax]
0x180014433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014438  mov     [r12], eax
0x18001443c  test    eax, eax
0x18001443e  jz      loc_180014515
0x180014444  call    cs:__imp_GetLastError
0x18001444a  mov     ebx, eax
0x18001444c  call    cs:__imp_CurrentIP
0x180014452  mov     rdi, rax
0x180014455  lea     rcx, [rsp+3F8h+var_378]
0x18001445d  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180014463  test    rax, rax
0x180014466  jnz     short loc_180014471
0x180014468  lea     rax, aNull; "(NULL)"
0x18001446f  jmp     short loc_180014488
0x180014471  lea     rcx, [rsp+3F8h+var_378]
0x180014479  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18001447f  mov     rcx, rax
0x180014482  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180014488  mov     r8, rax
0x18001448b  lea     rdx, aInterruptionRe_0; "Interruption requested. Current file: %"...
0x180014492  mov     ecx, 4000000h; unsigned int
0x180014497  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18001449c  mov     [rsp+3F8h+var_3A8], r14d
0x1800144a1  mov     [rsp+3F8h+var_3B0], r14
0x1800144a6  mov     [rsp+3F8h+var_3B8], ebx
0x1800144aa  mov     [rsp+3F8h+var_3C0], rdi
0x1800144af  lea     rcx, aPdeletedirecto; "pDeleteDirectoryRecursive"
0x1800144b6  mov     [rsp+3F8h+var_3C8], rcx
0x1800144bb  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupclean"...
0x1800144c2  mov     [rsp+3F8h+var_3D0], rcx
0x1800144c7  mov     dword ptr [rsp+3F8h+var_3D8], 0AAh
0x1800144cf  xor     r9d, r9d
0x1800144d2  lea     r8, aD_0; "D"
0x1800144d9  xor     edx, edx
0x1800144db  mov     rcx, rax
0x1800144de  call    cs:__imp_WdsSetupLogMessageW
0x1800144e4  nop
0x1800144e5  lea     rcx, [rsp+3F8h+var_378]
0x1800144ed  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800144f3  nop
0x1800144f4  lea     rcx, [rsp+3F8h+var_2E8]
0x1800144fc  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AHPEAX@ZPEAX@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AHPEAX@ZPEAX@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<int (*)(void *),void *>>(ScopeGuardImpl1<int (*)(void *),void *> &)
0x180014501  nop
0x180014502  lea     rcx, [rsp+3F8h+var_338]
0x18001450a  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180014510  jmp     loc_18001496F
0x180014515  lea     rcx, [rsp+3F8h+var_378]
0x18001451d  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180014523  mov     rcx, rax
0x180014526  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18001452c  mov     edx, 24h ; '$'
0x180014531  mov     rcx, rax
0x180014534  call    DeleteFileEx2
0x180014539  test    eax, eax
  ... truncated ...
```
