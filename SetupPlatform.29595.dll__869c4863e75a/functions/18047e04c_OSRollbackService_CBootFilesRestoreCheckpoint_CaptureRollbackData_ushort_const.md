# OSRollbackService::CBootFilesRestoreCheckpoint::CaptureRollbackData(ushort const *)

- ea: `0x18047e04c`
- end: `0x18047ec60`
- name: `?CaptureRollbackData@CBootFilesRestoreCheckpoint@OSRollbackService@@IEAAXPEBG@Z`
- size: `3092`
- prototype: `void __fastcall(OSRollbackService::CBootFilesRestoreCheckpoint *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, reparse_path, service_task, installer_update, broker_com_uri`

## callers

- `0x1802a3700`

## callees

- `0x18001413d`
- `0x1800197c0`
- `0x180057dec`
- `0x1804058b0`
- `0x180405958`
- `0x180406480`
- `0x1804068a4`
- `0x18047a238`
- `0x18047a318`
- `0x18047a398`
- `0x18047c9fc`
- `0x18047e04c`
- `0x180482270`
- `0x180482e7c`
- `0x18048c4c0`
- `0x18048c770`
- `0x180509010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18047e1cb`
- `KERNEL32!GetProcessHeap` at `0x18047e283`
- `KERNEL32!GetProcessHeap` at `0x18047e3c9`
- `KERNEL32!GetProcessHeap` at `0x18047e5a5`
- `KERNEL32!GetProcessHeap` at `0x18047e5da`
- `KERNEL32!GetProcessHeap` at `0x18047e5f8`
- `KERNEL32!GetProcessHeap` at `0x18047e1cb`
- `KERNEL32!GetProcessHeap` at `0x18047e283`
- `KERNEL32!GetProcessHeap` at `0x18047e3c9`
- `KERNEL32!GetProcessHeap` at `0x18047e5a5`
- `KERNEL32!GetProcessHeap` at `0x18047e5da`
- `KERNEL32!GetProcessHeap` at `0x18047e5f8`
- `KERNEL32!HeapAlloc` at `0x18047e1db`
- `KERNEL32!HeapAlloc` at `0x18047e1db`
- `KERNEL32!HeapFree` at `0x18047e291`
- `KERNEL32!HeapFree` at `0x18047e3d7`
- `KERNEL32!HeapFree` at `0x18047e5b3`
- `KERNEL32!HeapFree` at `0x18047e5e8`
- `KERNEL32!HeapFree` at `0x18047e606`
- `KERNEL32!HeapFree` at `0x18047e291`
- `KERNEL32!HeapFree` at `0x18047e3d7`
- `KERNEL32!HeapFree` at `0x18047e5b3`
- `KERNEL32!HeapFree` at `0x18047e5e8`
- `KERNEL32!HeapFree` at `0x18047e606`
- `KERNEL32!GetLastError` at `0x18047e102`
- `KERNEL32!GetLastError` at `0x18047e1ec`
- `KERNEL32!GetLastError` at `0x18047e202`
- `KERNEL32!GetLastError` at `0x18047e33c`
- `KERNEL32!GetLastError` at `0x18047e441`
- `KERNEL32!GetLastError` at `0x18047e457`
- `KERNEL32!GetLastError` at `0x18047e491`
- `KERNEL32!GetLastError` at `0x18047e51e`
- `KERNEL32!GetLastError` at `0x18047e610`
- `KERNEL32!GetLastError` at `0x18047e743`
- `KERNEL32!GetLastError` at `0x18047e750`
- `KERNEL32!GetLastError` at `0x18047e94e`
- `KERNEL32!GetLastError` at `0x18047ea8f`
- `KERNEL32!GetLastError` at `0x18047eb25`
- `KERNEL32!GetLastError` at `0x18047e102`
- `KERNEL32!GetLastError` at `0x18047e1ec`
- `KERNEL32!GetLastError` at `0x18047e202`
- `KERNEL32!GetLastError` at `0x18047e33c`
- `KERNEL32!GetLastError` at `0x18047e441`
- `KERNEL32!GetLastError` at `0x18047e457`
- `KERNEL32!GetLastError` at `0x18047e491`
- `KERNEL32!GetLastError` at `0x18047e51e`
- `KERNEL32!GetLastError` at `0x18047e610`
- `KERNEL32!GetLastError` at `0x18047e743`
- `KERNEL32!GetLastError` at `0x18047e750`
- `KERNEL32!GetLastError` at `0x18047e94e`
- `KERNEL32!GetLastError` at `0x18047ea8f`
- `KERNEL32!GetLastError` at `0x18047eb25`
- `KERNEL32!CreateDirectoryW` at `0x18047e735`
- `KERNEL32!CreateDirectoryW` at `0x18047e735`
- `unbcl!?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18047e094`
- `unbcl!?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18047e0b5`
- `unbcl!?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18047e094`
- `unbcl!?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18047e0b5`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18047e6a5`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18047e709`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18047e7ee`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18047e822`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18047e8c8`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18047e917`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18047e6a5`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18047e709`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18047e7ee`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18047e822`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18047e8c8`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18047e917`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x18047e9fe`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x18047ea1e`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x18047e9fe`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x18047ea1e`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x18047ea29`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x18047ea36`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x18047ea29`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x18047ea36`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18047ec21`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x18047ec21`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047e0ac`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047e0ac`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18047ea67`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18047ea72`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18047ea7e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18047ea89`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18047ebab`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18047ebe3`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18047ea67`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18047ea72`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18047ea7e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18047ea89`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18047ebab`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18047ebe3`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18047e089`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18047e8e7`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18047e9ef`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18047ea10`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18047e089`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18047e8e7`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18047e9ef`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18047ea10`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18047ec02`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18047ec02`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18047e6c4`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18047e6c4`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047e0cf`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047e118`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047e721`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047e765`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047e7d2`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047e806`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047e83b`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047e85e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047e8ac`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047e8ff`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047e92f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047e963`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047e979`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047eb3a`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047e0cf`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047e118`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047e721`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047e765`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047e7d2`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047e806`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047e83b`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047e85e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047e8ac`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047e8ff`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047e92f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047e963`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047e979`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047eb3a`
- `unbcl!?Nullify@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV12@XZ` at `0x18047e68e`
- `unbcl!?Nullify@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV12@XZ` at `0x18047e68e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047e0d8`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047e121`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047e72a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047e76e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047e7db`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047e80f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047e844`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047e867`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047e8b5`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047e8f2`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047e908`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047e938`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047e96c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047e982`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047eb43`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047e0d8`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047e121`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047e72a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047e76e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047e7db`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047e80f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047e844`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047e867`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047e8b5`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047e8f2`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047e908`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047e938`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047e96c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047e982`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047eb43`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047e6d0`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047e896`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047e8a1`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047eba0`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047ebb6`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047ebc1`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047ebcd`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047ebd8`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047e6d0`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047e896`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047e8a1`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047eba0`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047ebb6`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047ebc1`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047ebcd`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047ebd8`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18047e0a1`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18047e0c3`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18047e6b3`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18047e716`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18047e7fb`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18047e830`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18047e8d5`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18047e924`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18047e0a1`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18047e0c3`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18047e6b3`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18047e716`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18047e7fb`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18047e830`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18047e8d5`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18047e924`
- `WDSCORE!WdsSetupLogMessageW` at `0x18047e173`
- `WDSCORE!WdsSetupLogMessageW` at `0x18047e3aa`

## string_xrefs

- `0x18047e153`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x18047e654`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x18047e7a0`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x18047e9be`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x18047eacd`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x18047eb0f`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x18047eb75`: `base\ntsetup\lib\rollback\src\common_checkpoints.cpp`
- `0x18047e624`: `OSRollbackService::CBootFilesRestoreCheckpoint::CaptureRollbackData: Failed to find BT drive; hr = 0x%X`
- `0x18047e12a`: `OSRollbackService::CBootFilesRestoreCheckpoint::CaptureRollbackData: Directory %s does not exist; looking for BT drive volume`
- `0x18047e0e6`: `OSRollbackService::CBootFilesRestoreCheckpoint::CaptureRollbackData`
- `0x18047e648`: `OSRollbackService::CBootFilesRestoreCheckpoint::CaptureRollbackData`
- `0x18047e6e3`: `OSRollbackService::CBootFilesRestoreCheckpoint::CaptureRollbackData`
- `0x18047e9b2`: `OSRollbackService::CBootFilesRestoreCheckpoint::CaptureRollbackData`
- `0x18047e777`: `OSRollbackService::CBootFilesRestoreCheckpoint::CaptureRollbackData: Failed to create WinPE rollback directory: %s`
- `0x18047ec36`: `void __cdecl OSRollbackService::CBootFilesRestoreCheckpoint::CaptureRollbackData(const unsigned short *)`
- `0x18047eb4c`: `OSRollbackService::CBootFilesRestoreCheckpoint::CaptureRollbackData:No crash dump files found: %s.`
- `0x18047eae6`: `OSRollbackService::CBootFilesRestoreCheckpoint::CaptureRollbackData: successfully recovered WinPE memory crash dump file`
- `0x18047eaa4`: `OSRollbackService::CBootFilesRestoreCheckpoint::CaptureRollbackData: Failed to recover WinPE memory crash dump files`
- `0x18047e98e`: `OSRollbackService::CBootFilesRestoreCheckpoint::CaptureRollbackData: Found crash dump file (memory.dmp) in %s; attempting to copy to %s`
- `0x18047e378`: `OSRollbackUtils::VolumeTracking::FindVolume`
- `0x18047e4db`: `OSRollbackUtils::VolumeTracking::FindVolume`
- `0x18047e564`: `OSRollbackUtils::VolumeTracking::FindVolume`
- `0x18047e384`: `base\ntsetup\lib\rollback\src\volumetracking.cpp`
- `0x18047e4e7`: `base\ntsetup\lib\rollback\src\volumetracking.cpp`
- `0x18047e570`: `base\ntsetup\lib\rollback\src\volumetracking.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
void __fastcall OSRollbackService::CBootFilesRestoreCheckpoint::CaptureRollbackData(
        OSRollbackService::CBootFilesRestoreCheckpoint *this,
        const unsigned __int16 *a2)
{
  OSRollbackService::CCheckpoint *v2; // r14
  struct UnBCL::String *ParentPath; // rax
  const struct UnBCL::String *P; // rax
  struct UnBCL::String *v5; // rax
  UnBCL::String *v6; // rax
  const unsigned __int16 *CString; // rax
  DWORD LastError; // edi
  __int64 v9; // rbx
  UnBCL::String *v10; // rax
  const char *v11; // rax
  struct tagLOG_PARTIAL_MSG *v12; // rax
  unsigned __int16 *v13; // r15
  unsigned int v14; // r12d
  signed int VolumeReference; // esi
  __int64 v16; // r8
  void *v17; // r13
  HANDLE ProcessHeap; // rax
  _QWORD *v19; // rbx
  _QWORD *v20; // r14
  signed int v21; // eax
  bool v22; // sf
  signed int v23; // eax
  HANDLE v24; // rax
  unsigned int v25; // edx
  DWORD v26; // edi
  __int64 v27; // rbx
  struct tagLOG_PARTIAL_MSG *v28; // rax
  void (__fastcall *v29)(_QWORD); // rax
  HANDLE v30; // rax
  unsigned __int16 DriveLetter; // ax
  signed int v32; // eax
  bool v33; // sf
  signed int v34; // eax
  int v35; // eax
  signed int v36; // r14d
  DWORD v37; // edi
  __int64 v38; // rbx
  struct tagLOG_PARTIAL_MSG *v39; // rax
  DWORD v40; // edi
  __int64 v41; // rbx
  struct tagLOG_PARTIAL_MSG *v42; // rax
  HANDLE v43; // rax
  void *v44; // rbx
  HANDLE v45; // rax
  HANDLE v46; // rax
  DWORD v47; // edi
  __int64 v48; // rbx
  struct tagLOG_PARTIAL_MSG *v49; // rax
  struct UnBCL::String *v50; // rax
  struct UnBCL::String *v51; // rax
  UnBCL::String *v52; // rax
  const WCHAR *v53; // rax
  DWORD v54; // edi
  __int64 v55; // rbx
  UnBCL::String *v56; // rax
  const char *v57; // rax
  struct tagLOG_PARTIAL_MSG *v58; // rax
  UnBCL::String *v59; // rax
  const unsigned __int16 *v60; // rax
  struct UnBCL::String *v61; // rax
  UnBCL::String *v62; // rax
  const unsigned __int16 *v63; // rax
  struct UnBCL::String *v64; // rax
  UnBCL::String *v65; // rax
  const unsigned __int16 *v66; // rax
  UnBCL::String *v67; // rax
  const unsigned __int16 *v68; // rax
  int *v69; // r9
  UnBCL::String *v70; // rax
  const unsigned __int16 *v71; // rax
  struct UnBCL::String *v72; // rax
  const unsigned __int16 *v73; // rbx
  UnBCL::String *v74; // rax
  const unsigned __int16 *v75; // rax
  struct UnBCL::String *v76; // rax
  UnBCL::String *v77; // rax
  const unsigned __int16 *v78; // rax
  DWORD v79; // esi
  __int64 v80; // rdi
  UnBCL::String *v81; // rax
  const char *v82; // rbx
  UnBCL::String *v83; // rax
  const char *v84; // rax
  struct tagLOG_PARTIAL_MSG *v85; // rax
  const struct UnBCL::String *v86; // rax
  const struct UnBCL::String *v87; // rax
  const struct UnBCL::String *v88; // rbx
  const struct UnBCL::String *v89; // rax
  DWORD v90; // edi
  __int64 v91; // rax
  bool v92; // zf
  __int64 v93; // rbx
  struct tagLOG_PARTIAL_MSG *v94; // rax
  struct tagLOG_PARTIAL_MSG *v95; // rax
  DWORD v96; // edi
  __int64 v97; // rbx
  UnBCL::String *v98; // rax
  const char *v99; // rax
  struct tagLOG_PARTIAL_MSG *v100; // rax
  _QWORD *v101; // rax
  _QWORD *v102; // rbx
  LPVOID lpMem[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v104[16]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v105[16]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v106[16]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v107[16]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v108[24]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v109[16]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v110[24]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v111; // [rsp+F8h] [rbp-8h]
  _BYTE v112[24]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v113[48]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v114[88]; // [rsp+148h] [rbp+48h] BYREF
  const unsigned __int16 *pExceptionObject; // [rsp+1B8h] [rbp+B8h] BYREF
  LPVOID v117; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int16 *v118; // [rsp+1C8h] [rbp+C8h] BYREF

  pExceptionObject = a2;
  v111 = -2;
  v2 = this;
  if ( !a2 )
  {
    v101 = UnBCL::Object::operator new(0x38u);
    v102 = v101;
    v117 = v101;
    if ( v101 )
    {
      UnBCL::ArgumentNullException::ArgumentNullException((UnBCL::ArgumentNullException *)v101, L"pWorkingDir");
      *v102 = &UnBCL::ArgumentNullException::`local vftable';
    }
    else
    {
      v102 = 0;
    }
    pExceptionObject = (const unsigned __int16 *)AddStackTraceToException<UnBCL::InvalidOperationException>(
                                                   v102,
                                                   "void __cdecl OSRollbackService::CBootFilesRestoreCheckpoint::CaptureR"
                                                   "ollbackData(const unsigned short *)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  UnBCL::String::String((UnBCL::String *)v112, a2);
  ParentPath = UnBCL::Path::GetParentPath((const struct UnBCL::String *)v112);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v109, ParentPath);
  P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v109);
  v5 = UnBCL::Path::GetParentPath(P);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v104, v5);
  v6 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v104);
  CString = UnBCL::String::get_CString(v6);
  if ( !(unsigned int)DirectoryExists(CString) )
  {
    LastError = GetLastError();
    v9 = CurrentIP();
    v10 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v104);
    v11 = (const char *)UnBCL::String::get_CString(v10);
    v12 = ConstructPartialMsgW(
            0x4000000u,
            "OSRollbackService::CBootFilesRestoreCheckpoint::CaptureRollbackData: Directory %s does not exist; looking fo"
            "r BT drive volume",
            v11);
    WdsSetupLogMessageW(
      v12,
      409600,
      L"D",
      0,
      1130,
      L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
      L"OSRollbackService::CBootFilesRestoreCheckpoint::CaptureRollbackData",
      v9,
      LastError,
      0,
      0);
    v13 = 0;
    v118 = 0;
    *(_OWORD *)lpMem = 0;
    LOWORD(v14) = 0;
    v117 = 0;
    VolumeReference = BuildPathHr(pExceptionObject, L"TrackedVolumes.ini", &v117);
    v17 = v117;
    if ( VolumeReference < 0 )
      goto LABEL_51;
    if ( v117 )
    {
      ProcessHeap = GetProcessHeap();
      v19 = HeapAlloc(ProcessHeap, 8u, 0x38u);
      if ( !v19 )
      {
        v20 = 0;
        v21 = GetLastError();
        v22 = v21 < 0;
        if ( v21 > 0 )
          v22 = 1;
        if ( !v22 )
        {
          VolumeReference = -2147467259;
          goto LABEL_19;
        }
        v23 = GetLastError();
        VolumeReference = v23;
        if ( v23 > 0 )
          VolumeReference = (unsigned __int16)v23 | 0x80070000;
        if ( VolumeReference < 0 )
        {
LABEL_19:
          if ( VolumeReference < 0 )
            goto LABEL_51;
          LODWORD(v117) = 0;
          VolumeReference = StpGetVolumeReference(v20, L"$Setup_BTFolderVolume$", v16, lpMem, &v117);
          if ( VolumeReference >= 0 )
          {
            if ( (_DWORD)v117 )
            {
              if ( LODWORD(lpMem[1]) == 4 )
              {
                if ( (unsigned __int16)(LOWORD(lpMem[0]) - 97) <= 0x19u
                  || (unsigned __int16)(LOWORD(lpMem[0]) - 65) <= 0x19u )
                {
                  goto LABEL_33;
                }
              }
              else if ( LODWORD(lpMem[1]) == 3 && lpMem[0]
                     || LODWORD(lpMem[1]) == 2 && lpMem[0]
                     || LODWORD(lpMem[1]) == 1 && lpMem[0] )
              {
                goto LABEL_33;
              }
            }
            VolumeReference = -2147023728;
            v26 = GetLastError();
            v27 = CurrentIP();
            v28 = ConstructPartialMsgW(
                    0x200013Cu,
                    "FindVolume: Unable to find volume marked as [%s]",
                    (const char *)L"$Setup_BTFolderVolume$");
            WdsSetupLogMessageW(
              v28,
              409600,
              L"D",
              0,
              157,
              L"base\\ntsetup\\lib\\rollback\\src\\volumetracking.cpp",
              L"OSRollbackUtils::VolumeTracking::FindVolume",
              v27,
              v26,
              0,
              0);
          }
LABEL_33:
          if ( v20 )
          {
            v29 = (void (__fastcall *)(_QWORD))v20[5];
            if ( v29 )
              v29(v20[6]);
            v30 = GetProcessHeap();
            HeapFree(v30, 0, v20);
          }
          if ( VolumeReference >= 0 )
          {
            VolumeReference = PrepareVolumeAccessPath((struct _VOLUME_REFERENCE *)lpMem, v25, &v118);
            v13 = v118;
            if ( VolumeReference >= 0 )
            {
              if ( (unsigned __int16)ExtractDriveLetter(v118) >= 0x61u
                && (DriveLetter = ExtractDriveLetter(v13), DriveLetter <= 0x7Au)
                || (unsigned __int16)ExtractDriveLetter(v13) >= 0x41u
                && (DriveLetter = ExtractDriveLetter(v13), DriveLetter <= 0x5Au) )
              {
                LOWORD(v14) = DriveLetter;
              }
              else
              {
                v32 = GetLastError();
                v33 = v32 < 0;
                if ( v32 > 0 )
                  v33 = 1;
                if ( v33 )
                {
                  v34 = GetLastError();
                  VolumeReference = v34;
                  if ( v34 > 0 )
                    VolumeReference = (unsigned __int16)v34 | 0x80070000;
                }
                else
                {
                  VolumeReference = -2147467259;
                }
                LOWORD(v14) = 0;
              }
            }
          }
LABEL_51:
          v35 = ReleaseVolumeAccessPath(v13);
          v36 = v35;
          if ( VolumeReference >= 0 )
          {
            if ( v35 >= 0 )
            {
              v37 = GetLastError();
              v38 = CurrentIP();
              v14 = (unsigned __int16)v14;
              v39 = ConstructPartialMsgW(
                      0x4000000u,
                      "FindVolume: Successfully found [%s] on drive [%c:]",
                      (const char *)L"$Setup_BTFolderVolume$",
                      (unsigned __int16)v14);
              WdsSetupLogMessageW(
                v39,
                409600,
                L"D",
                0,
                188,
                L"base\\ntsetup\\lib\\rollback\\src\\volumetracking.cpp",
                L"OSRollbackUtils::VolumeTracking::FindVolume",
                v38,
                v37,
                0,
                0);
              VolumeReference = v36;
LABEL_56:
              if ( v13 )
              {
                v43 = GetProcessHeap();
                HeapFree(v43, 0, v13);
              }
              if ( LODWORD(lpMem[1]) == 1 || (unsigned int)(LODWORD(lpMem[1]) - 2) <= 1 )
              {
                v44 = lpMem[0];
                if ( lpMem[0] )
                {
                  v45 = GetProcessHeap();
                  HeapFree(v45, 0, v44);
                }
              }
              if ( v17 )
              {
                v46 = GetProcessHeap();
                HeapFree(v46, 0, v17);
              }
              if ( VolumeReference >= 0 )
              {
                UnBCL::SmartPtr<UnBCL::String>::Nullify(v104);
                v50 = UnBCL::String::Format(L"%c:\\%s", v14, L"$windows.~bt");
                UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(lpMem, v50);
                UnBCL::SmartPtr<UnBCL::String>::operator=(v104, lpMem);
                UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(lpMem);
              }
              else
              {
                v47 = GetLastError();
                v48 = CurrentIP();
                v49 = ConstructPartialMsgW(
                        0x2000000u,
                        "OSRollbackService::CBootFilesRestoreCheckpoint::CaptureRollbackData: Failed to find BT drive; hr = 0x%X",
                        VolumeReference);
                WdsSetupLogMessageW(
                  v49,
                  409600,
                  L"D",
                  0,
                  1138,
                  L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
                  L"OSRollbackService::CBootFilesRestoreCheckpoint::CaptureRollbackData",
                  v48,
                  v47,
                  0,
                  0);
              }
              v2 = this;
              goto LABEL_68;
            }
            VolumeReference = v35;
          }
          v40 = GetLastError();
          v41 = CurrentIP();
          v42 = ConstructPartialMsgW(
                  0x2000225u,
                  "FindVolume: Failed while looking for [%s]; hr = 0x%X.",
                  (const char *)L"$Setup_BTFolderVolume$",
                  VolumeReference);
          WdsSetupLogMessageW(
            v42,
            409600,
            L"D",
            0,
            195,
            L"base\\ntsetup\\lib\\rollback\\src\\volumetracking.cpp",
            L"OSRollbackUtils::VolumeTracking::FindVolume",
            v41,
            v40,
            0,
            0);
          v14 = (unsigned __int16)v14;
          goto LABEL_56;
        }
      }
      VolumeReference = IniStoreOpen(v17, v19 + 6);
      if ( VolumeReference >= 0 )
      {
        *v19 = IniStoreReadValue;
        v19[1] = IniStoreWriteValue;
        v19[2] = IniStoreDeleteItem;
        v19[3] = IniStoreEnumSubkeys;
        v19[4] = IniStoreFree;
        v19[5] = IniStoreClose;
        v20 = v19;
        goto LABEL_19;
      }
      if ( v19 )
      {
        v24 = GetProcessHeap();
        HeapFree(v24, 0, v19);
      }
    }
    else
    {
      VolumeReference = -2147024809;
    }
    v20 = 0;
    goto LABEL_19;
  }
LABEL_68:
  v51 = UnBCL::String::Format(L"%s\\%s", pExceptionObject, L"WinPE");
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v105, v51);
  v52 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v105);
  v53 = UnBCL::String::get_CString(v52);
  if ( !CreateDirectoryW(v53, 0) && GetLastError() != 183 )
  {
    v54 = GetLastError();
    v55 = CurrentIP();
    v56 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v105);
    v57 = (const char *)UnBCL::String::get_CString(v56);
    v58 = ConstructPartialMsgW(
            0x2000000u,
            "OSRollbackService::CBootFilesRestoreCheckpoint::CaptureRollbackData: Failed to create WinPE rollback directory: %s",
            v57);
    WdsSetupLogMessageW(
      v58,
      409600,
      L"D",
      0,
      1155,
      L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
      L"OSRollbackService::CBootFilesRestoreCheckpoint::CaptureRollbackData",
      v55,
      v54,
      0,
      0);
  }
  v59 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v104);
  v60 = UnBCL::String::get_CString(v59);
  v61 = UnBCL::String::Format(L"%s\\%s", v60, L"pagefile.sys");
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v108, v61);
  v62 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v105);
  v63 = UnBCL::String::get_CString(v62);
  v64 = UnBCL::String::Format(L"%s\\%s", v63, L"winpemem.dmp");
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(lpMem, v64);
  v65 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v108);
  v66 = UnBCL::String::get_CString(v65);
  OSRollbackUtils::CCrashDumpExtractor::CCrashDumpExtractor((OSRollbackUtils::CCrashDumpExtractor *)v113, 0, v66);
  v67 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(lpMem);
  v68 = UnBCL::String::get_CString(v67);
  OSRollbackUtils::CCrashDumpExtractor::Extract((OSRollbackUtils::CCrashDumpExtractor *)v113, v68, 0, v69, 0, 0);
  OSRollbackUtils::CCrashDumpExtractor::~CCrashDumpExtractor((OSRollbackUtils::CCrashDumpExtractor *)v113);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(lpMem);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v108);
  v70 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v104);
  v71 = UnBCL::String::get_CString(v70);
  v72 = UnBCL::String::Format(L"%s\\%s", v71, L"windows");
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v106, v72);
  UnBCL::String::String((UnBCL::String *)v110, L"memory.dmp");
  v73 = UnBCL::String::get_CString((UnBCL::String *)v110);
  v74 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v106);
  v75 = UnBCL::String::get_CString(v74);
  v76 = UnBCL::String::Format(L"%s\\%s", v75, v73);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v107, v76);
  v77 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v107);
  v78 = UnBCL::String::get_CString(v77);
  if ( (unsigned int)FileExists(v78) )
  {
    v79 = GetLastError();
    v80 = CurrentIP();
    v81 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v105);
    v82 = (const char *)UnBCL::String::get_CString(v81);
    v83 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v106);
    v84 = (const char *)UnBCL::String::get_CString(v83);
    v85 = ConstructPartialMsgW(
            0x4000000u,
            "OSRollbackService::CBootFilesRestoreCheckpoint::CaptureRollbackData: Found crash dump file (memory.dmp) in %"
            "s; attempting to copy to %s",
            v84,
            v82);
    WdsSetupLogMessageW(
      v85,
      409600,
      L"D",
      0,
      1181,
      L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
      L"OSRollbackService::CBootFilesRestoreCheckpoint::CaptureRollbackData",
      v80,
      v79,
      0,
      0);
    v86 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v113, &cchOriginalDestLength);
    UnBCL::String::String((UnBCL::String *)lpMem, v86);
    v87 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v114, &cchOriginalDestLength);
    UnBCL::String::String((UnBCL::String *)v108, v87);
    v88 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator*(v105);
    v89 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator*(v106);
    LODWORD(v88) = OSRollbackService::CCheckpoint::MoveOrCopyFiles(
                     v2,
                     v89,
                     v88,
                     (const struct UnBCL::String *)v110,
                     (const struct UnBCL::String *)v108,
                     (const struct UnBCL::String *)lpMem);
    UnBCL::String::~String((UnBCL::String *)v108);
    UnBCL::String::~String((UnBCL::String *)v114);
    UnBCL::String::~String((UnBCL::String *)lpMem);
    UnBCL::String::~String((UnBCL::String *)v113);
    v90 = GetLastError();
    v91 = CurrentIP();
    v92 = (_DWORD)v88 == 0;
    v93 = v91;
    if ( v92 )
    {
      v94 = ConstructPartialMsgW(
              0x2000244u,
              "OSRollbackService::CBootFilesRestoreCheckpoint::CaptureRollbackData: Failed to recover WinPE memory crash dump files");
      WdsSetupLogMessageW(
        v94,
        409600,
        L"D",
        0,
        1186,
        L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
        L"OSRollbackService::CBootFilesRestoreCheckpoint::CaptureRollbackData",
        v93,
        v90,
        0,
        0);
    }
    else
    {
      v95 = ConstructPartialMsgW(
              0x4000000u,
              "OSRollbackService::CBootFilesRestoreCheckpoint::CaptureRollbackData: successfully recovered WinPE memory crash dump file");
      WdsSetupLogMessageW(
        v95,
        409600,
        L"D",
        0,
        1190,
        L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
        L"OSRollbackService::CBootFilesRestoreCheckpoint::CaptureRollbackData",
        v93,
        v90,
        0,
        0);
    }
  }
  else
  {
    v96 = GetLastError();
    v97 = CurrentIP();
    v98 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v107);
    v99 = (const char *)UnBCL::String::get_CString(v98);
    v100 = ConstructPartialMsgW(
             0x4000000u,
             "OSRollbackService::CBootFilesRestoreCheckpoint::CaptureRollbackData:No crash dump files found: %s.",
             v99);
    WdsSetupLogMessageW(
      v100,
      409600,
      L"D",
      0,
      1195,
      L"base\\ntsetup\\lib\\rollback\\src\\common_checkpoints.cpp",
      L"OSRollbackService::CBootFilesRestoreCheckpoint::CaptureRollbackData",
      v97,
      v96,
      0,
      0);
  }
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v107);
  UnBCL::String::~String((UnBCL::String *)v110);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v106);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v105);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v104);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v109);
  UnBCL::String::~String((UnBCL::String *)v112);
}

```

## disassembly

```asm
0x18047e04c  mov     [rsp-8+pExceptionObject], rdx
0x18047e051  mov     [rsp-8+arg_0], rcx
0x18047e056  push    rbp
0x18047e057  push    rbx
0x18047e058  push    rsi
0x18047e059  push    rdi
0x18047e05a  push    r12
0x18047e05c  push    r13
0x18047e05e  push    r14
0x18047e060  push    r15
0x18047e062  lea     rbp, [rsp-68h]
0x18047e067  sub     rsp, 168h
0x18047e06e  mov     [rbp+0A0h+var_A8], 0FFFFFFFFFFFFFFFEh
0x18047e076  mov     r14, rcx
0x18047e079  xor     r15d, r15d
0x18047e07c  test    rdx, rdx
0x18047e07f  jz      loc_18047EBFD
0x18047e085  lea     rcx, [rbp+0A0h+var_A0]
0x18047e089  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18047e08f  nop
0x18047e090  lea     rcx, [rbp+0A0h+var_A0]
0x18047e094  call    cs:__imp_?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetParentPath(UnBCL::String const *)
0x18047e09a  mov     rdx, rax
0x18047e09d  lea     rcx, [rbp+0A0h+var_D0]
0x18047e0a1  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18047e0a7  nop
0x18047e0a8  lea     rcx, [rbp+0A0h+var_D0]
0x18047e0ac  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18047e0b2  mov     rcx, rax
0x18047e0b5  call    cs:__imp_?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetParentPath(UnBCL::String const *)
0x18047e0bb  mov     rdx, rax
0x18047e0be  lea     rcx, [rsp+1A0h+var_128]
0x18047e0c3  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18047e0c9  nop
0x18047e0ca  lea     rcx, [rsp+1A0h+var_128]
0x18047e0cf  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18047e0d5  mov     rcx, rax
0x18047e0d8  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18047e0de  mov     rcx, rax
0x18047e0e1  call    DirectoryExists
0x18047e0e6  lea     rsi, aOsrollbackserv_20; "OSRollbackService::CBootFilesRestoreChe"...
0x18047e0ed  lea     r12, aD_0; "D"
0x18047e0f4  mov     r13d, 64000h
0x18047e0fa  test    eax, eax
0x18047e0fc  jnz     loc_18047E6F1
0x18047e102  call    cs:__imp_GetLastError
0x18047e108  mov     edi, eax
0x18047e10a  call    cs:__imp_CurrentIP
0x18047e110  mov     rbx, rax
0x18047e113  lea     rcx, [rsp+1A0h+var_128]
0x18047e118  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18047e11e  mov     rcx, rax
0x18047e121  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18047e127  mov     r8, rax
0x18047e12a  lea     rdx, aOsrollbackserv_3; "OSRollbackService::CBootFilesRestoreChe"...
0x18047e131  mov     ecx, 4000000h; unsigned int
0x18047e136  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18047e13b  mov     [rsp+1A0h+var_150], r15d
0x18047e140  mov     [rsp+1A0h+var_158], r15
0x18047e145  mov     [rsp+1A0h+var_160], edi
0x18047e149  mov     [rsp+1A0h+var_168], rbx
0x18047e14e  mov     [rsp+1A0h+var_170], rsi
0x18047e153  lea     rcx, aBaseNtsetupLib; "base\\ntsetup\\lib\\rollback\\src\\comm"...
0x18047e15a  mov     [rsp+1A0h+var_178], rcx
0x18047e15f  mov     dword ptr [rsp+1A0h+var_180], 46Ah
0x18047e167  xor     r9d, r9d
0x18047e16a  mov     r8, r12
0x18047e16d  mov     edx, r13d
0x18047e170  mov     rcx, rax
0x18047e173  call    cs:__imp_WdsSetupLogMessageW
0x18047e179  xor     edi, edi
0x18047e17b  mov     r15d, edi
0x18047e17e  mov     [rbp+0A0h+arg_18], rdi
0x18047e185  xorps   xmm0, xmm0
0x18047e188  movups  xmmword ptr [rsp+1A0h+lpMem], xmm0
0x18047e18d  mov     r12d, edi
0x18047e190  mov     [rbp+0A0h+arg_10], rdi
0x18047e197  lea     r8, [rbp+0A0h+arg_10]
0x18047e19e  lea     rdx, aTrackedvolumes; "TrackedVolumes.ini"
0x18047e1a5  mov     rcx, [rbp+0A0h+pExceptionObject]
0x18047e1ac  call    BuildPathHr
0x18047e1b1  mov     esi, eax
0x18047e1b3  mov     r13, [rbp+0A0h+arg_10]
0x18047e1ba  test    eax, eax
0x18047e1bc  js      loc_18047E476
0x18047e1c2  test    r13, r13
0x18047e1c5  jz      loc_18047E299
0x18047e1cb  call    cs:__imp_GetProcessHeap
0x18047e1d1  mov     rcx, rax; hHeap
0x18047e1d4  lea     edx, [rdi+8]; dwFlags
0x18047e1d7  lea     r8d, [rdi+38h]; dwBytes
0x18047e1db  call    cs:__imp_HeapAlloc
0x18047e1e1  mov     rbx, rax
0x18047e1e4  test    rax, rax
0x18047e1e7  jnz     short loc_18047E21F
0x18047e1e9  mov     r14d, edi
0x18047e1ec  call    cs:__imp_GetLastError
0x18047e1f2  test    eax, eax
0x18047e1f4  jle     short loc_18047E200
0x18047e1f6  movzx   eax, ax
0x18047e1f9  or      eax, 80070000h
0x18047e1fe  test    eax, eax
0x18047e200  jns     short loc_18047E277
0x18047e202  call    cs:__imp_GetLastError
0x18047e208  mov     esi, eax
0x18047e20a  test    eax, eax
0x18047e20c  jle     short loc_18047E217
0x18047e20e  movzx   esi, ax
0x18047e211  or      esi, 80070000h
0x18047e217  test    esi, esi
0x18047e219  js      loc_18047E2A1
0x18047e21f  lea     rdx, [rbx+30h]
0x18047e223  mov     rcx, r13
0x18047e226  call    IniStoreOpen
0x18047e22b  mov     esi, eax
0x18047e22d  test    eax, eax
0x18047e22f  js      short loc_18047E27E
0x18047e231  lea     rax, IniStoreReadValue
0x18047e238  mov     [rbx], rax
0x18047e23b  lea     rax, IniStoreWriteValue
0x18047e242  mov     [rbx+8], rax
0x18047e246  lea     rax, IniStoreDeleteItem
0x18047e24d  mov     [rbx+10h], rax
0x18047e251  lea     rax, IniStoreEnumSubkeys
0x18047e258  mov     [rbx+18h], rax
0x18047e25c  lea     rax, IniStoreFree
0x18047e263  mov     [rbx+20h], rax
0x18047e267  lea     rax, IniStoreClose
0x18047e26e  mov     [rbx+28h], rax
0x18047e272  mov     r14, rbx
0x18047e275  jmp     short loc_18047E2A1
0x18047e277  mov     esi, 80004005h
0x18047e27c  jmp     short loc_18047E2A1
0x18047e27e  test    rbx, rbx
0x18047e281  jz      short loc_18047E29E
0x18047e283  call    cs:__imp_GetProcessHeap
0x18047e289  mov     rcx, rax; hHeap
0x18047e28c  mov     r8, rbx; lpMem
0x18047e28f  xor     edx, edx; dwFlags
0x18047e291  call    cs:__imp_HeapFree
0x18047e297  jmp     short loc_18047E29E
0x18047e299  mov     esi, 80070057h
0x18047e29e  mov     r14, rdi
0x18047e2a1  test    esi, esi
0x18047e2a3  js      loc_18047E476
0x18047e2a9  mov     dword ptr [rbp+0A0h+arg_10], edi
0x18047e2af  lea     rax, [rbp+0A0h+arg_10]
0x18047e2b6  mov     [rsp+1A0h+var_180], rax
0x18047e2bb  lea     r9, [rsp+1A0h+lpMem]
0x18047e2c0  lea     rdx, aSetupBtfolderv; "$Setup_BTFolderVolume$"
0x18047e2c7  mov     rcx, r14
0x18047e2ca  call    ?StpGetVolumeReference@@YAJPEAU_LOCATION_STATE@@PEBGW4_VOLUME_REFERENCE_TYPE@@PEAU_VOLUME_REFERENCE@@PEAH@Z; StpGetVolumeReference(_LOCATION_STATE *,ushort const *,_VOLUME_REFERENCE_TYPE,_VOLUME_REFERENCE *,int *)
0x18047e2cf  mov     esi, eax
0x18047e2d1  test    eax, eax
0x18047e2d3  js      loc_18047E3B2
0x18047e2d9  cmp     dword ptr [rbp+0A0h+arg_10], edi
0x18047e2df  jz      short loc_18047E337
0x18047e2e1  mov     eax, dword ptr [rsp+1A0h+lpMem+8]
0x18047e2e5  cmp     eax, 4
0x18047e2e8  jnz     short loc_18047E30B
0x18047e2ea  movzx   ecx, word ptr [rsp+1A0h+lpMem]
0x18047e2ef  lea     eax, [rcx-61h]
0x18047e2f2  cmp     ax, 19h
0x18047e2f6  jbe     loc_18047E3B2
0x18047e2fc  sub     cx, 41h ; 'A'
0x18047e300  cmp     cx, 19h
0x18047e304  ja      short loc_18047E337
0x18047e306  jmp     loc_18047E3B2
0x18047e30b  cmp     eax, 3
0x18047e30e  jnz     short loc_18047E31B
0x18047e310  cmp     [rsp+1A0h+lpMem], rdi
0x18047e315  jnz     loc_18047E3B2
0x18047e31b  cmp     eax, 2
0x18047e31e  jnz     short loc_18047E32B
0x18047e320  cmp     [rsp+1A0h+lpMem], rdi
0x18047e325  jnz     loc_18047E3B2
0x18047e32b  cmp     eax, 1
0x18047e32e  jnz     short loc_18047E337
0x18047e330  cmp     [rsp+1A0h+lpMem], rdi
0x18047e335  jnz     short loc_18047E3B2
0x18047e337  mov     esi, 80070490h
0x18047e33c  call    cs:__imp_GetLastError
0x18047e342  mov     edi, eax
0x18047e344  call    cs:__imp_CurrentIP
0x18047e34a  mov     rbx, rax
0x18047e34d  lea     r8, aSetupBtfolderv; "$Setup_BTFolderVolume$"
0x18047e354  lea     rdx, aFindvolumeUnab; "FindVolume: Unable to find volume marke"...
0x18047e35b  mov     ecx, 200013Ch; unsigned int
0x18047e360  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18047e365  mov     [rsp+1A0h+var_150], r12d
0x18047e36a  mov     [rsp+1A0h+var_158], r12
0x18047e36f  mov     [rsp+1A0h+var_160], edi
0x18047e373  mov     [rsp+1A0h+var_168], rbx
0x18047e378  lea     rcx, aOsrollbackutil_8; "OSRollbackUtils::VolumeTracking::FindVo"...
0x18047e37f  mov     [rsp+1A0h+var_170], rcx
0x18047e384  lea     rcx, aBaseNtsetupLib_4; "base\\ntsetup\\lib\\rollback\\src\\volu"...
0x18047e38b  mov     [rsp+1A0h+var_178], rcx
0x18047e390  mov     dword ptr [rsp+1A0h+var_180], 9Dh
0x18047e398  xor     r9d, r9d
0x18047e39b  lea     r8, aD_0; "D"
0x18047e3a2  mov     edx, 64000h
0x18047e3a7  mov     rcx, rax
0x18047e3aa  call    cs:__imp_WdsSetupLogMessageW
0x18047e3b0  xor     edi, edi
0x18047e3b2  test    r14, r14
0x18047e3b5  jz      short loc_18047E3DD
0x18047e3b7  mov     rax, [r14+28h]
0x18047e3bb  test    rax, rax
0x18047e3be  jz      short loc_18047E3C9
0x18047e3c0  mov     rcx, [r14+30h]
0x18047e3c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18047e3c9  call    cs:__imp_GetProcessHeap
0x18047e3cf  mov     rcx, rax; hHeap
0x18047e3d2  mov     r8, r14; lpMem
0x18047e3d5  xor     edx, edx; dwFlags
0x18047e3d7  call    cs:__imp_HeapFree
0x18047e3dd  test    esi, esi
0x18047e3df  js      loc_18047E476
0x18047e3e5  lea     r8, [rbp+0A0h+arg_18]; unsigned __int16 **
0x18047e3ec  lea     rcx, [rsp+1A0h+lpMem]; struct _VOLUME_REFERENCE *
0x18047e3f1  call    ?PrepareVolumeAccessPath@@YAJPEAU_VOLUME_REFERENCE@@KPEAPEAG@Z; PrepareVolumeAccessPath(_VOLUME_REFERENCE *,ulong,ushort * *)
0x18047e3f6  mov     esi, eax
0x18047e3f8  mov     r15, [rbp+0A0h+arg_18]
0x18047e3ff  test    eax, eax
0x18047e401  js      short loc_18047E476
0x18047e403  mov     rcx, r15
0x18047e406  call    ExtractDriveLetter
0x18047e40b  cmp     ax, 61h ; 'a'
0x18047e40f  jb      short loc_18047E425
0x18047e411  mov     rcx, r15
0x18047e414  call    ExtractDriveLetter
0x18047e419  cmp     ax, 7Ah ; 'z'
0x18047e41d  ja      short loc_18047E425
0x18047e41f  movzx   r12d, ax
0x18047e423  jmp     short loc_18047E476
0x18047e425  mov     rcx, r15
0x18047e428  call    ExtractDriveLetter
0x18047e42d  cmp     ax, 41h ; 'A'
0x18047e431  jb      short loc_18047E441
0x18047e433  mov     rcx, r15
0x18047e436  call    ExtractDriveLetter
0x18047e43b  cmp     ax, 5Ah ; 'Z'
0x18047e43f  jbe     short loc_18047E41F
0x18047e441  call    cs:__imp_GetLastError
0x18047e447  test    eax, eax
0x18047e449  jle     short loc_18047E455
0x18047e44b  movzx   eax, ax
0x18047e44e  or      eax, 80070000h
0x18047e453  test    eax, eax
0x18047e455  jns     short loc_18047E46E
0x18047e457  call    cs:__imp_GetLastError
0x18047e45d  mov     esi, eax
0x18047e45f  test    eax, eax
0x18047e461  jle     short loc_18047E473
0x18047e463  movzx   esi, ax
0x18047e466  or      esi, 80070000h
0x18047e46c  jmp     short loc_18047E473
0x18047e46e  mov     esi, 80004005h
0x18047e473  mov     r12d, edi
0x18047e476  mov     rcx, r15; unsigned __int16 *
0x18047e479  call    ?ReleaseVolumeAccessPath@@YAJPEBG@Z; ReleaseVolumeAccessPath(ushort const *)
0x18047e47e  mov     r14d, eax
0x18047e481  test    esi, esi
0x18047e483  js      loc_18047E51E
0x18047e489  test    eax, eax
0x18047e48b  js      loc_18047E51B
0x18047e491  call    cs:__imp_GetLastError
0x18047e497  mov     edi, eax
0x18047e499  call    cs:__imp_CurrentIP
0x18047e49f  mov     rbx, rax
0x18047e4a2  movzx   r12d, r12w
0x18047e4a6  mov     r9d, r12d
0x18047e4a9  lea     r8, aSetupBtfolderv; "$Setup_BTFolderVolume$"
0x18047e4b0  lea     rdx, aFindvolumeSucc; "FindVolume: Successfully found [%s] on "...
0x18047e4b7  mov     ecx, 4000000h; unsigned int
0x18047e4bc  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18047e4c1  mov     [rsp+1A0h+var_150], 0
0x18047e4c9  mov     [rsp+1A0h+var_158], 0
0x18047e4d2  mov     [rsp+1A0h+var_160], edi
0x18047e4d6  mov     [rsp+1A0h+var_168], rbx
0x18047e4db  lea     rcx, aOsrollbackutil_8; "OSRollbackUtils::VolumeTracking::FindVo"...
0x18047e4e2  mov     [rsp+1A0h+var_170], rcx
0x18047e4e7  lea     rcx, aBaseNtsetupLib_4; "base\\ntsetup\\lib\\rollback\\src\\volu"...
0x18047e4ee  mov     [rsp+1A0h+var_178], rcx
0x18047e4f3  mov     dword ptr [rsp+1A0h+var_180], 0BCh
0x18047e4fb  xor     r9d, r9d
0x18047e4fe  lea     r8, aD_0; "D"
0x18047e505  mov     edx, 64000h
0x18047e50a  mov     rcx, rax
0x18047e50d  call    cs:__imp_WdsSetupLogMessageW
0x18047e513  mov     esi, r14d
0x18047e516  jmp     loc_18047E5A0
0x18047e51b  mov     esi, r14d
0x18047e51e  call    cs:__imp_GetLastError
0x18047e524  mov     edi, eax
0x18047e526  call    cs:__imp_CurrentIP
0x18047e52c  mov     rbx, rax
0x18047e52f  mov     r9d, esi
0x18047e532  lea     r8, aSetupBtfolderv; "$Setup_BTFolderVolume$"
0x18047e539  lea     rdx, aFindvolumeFail; "FindVolume: Failed while looking for [%"...
  ... truncated ...
```
