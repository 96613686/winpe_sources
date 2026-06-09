# SPGetWIMImageInfo(UnBCL::String *,UnBCL::ArrayList<UnBCL::String *> *,ulong,int *,SetupPlatform::IMAGE_TYPE *,ushort * *,ushort * *,ushort * *,ushort * *)

- ea: `0x18029a0fc`
- end: `0x18029ac41`
- name: `?SPGetWIMImageInfo@@YAJPEAVString@UnBCL@@PEAV?$ArrayList@PEAVString@UnBCL@@@2@KPEAHPEAW4IMAGE_TYPE@SetupPlatform@@PEAPEAG444@Z`
- size: `2885`
- prototype: `void __fastcall __noreturn(int, int, int, int, __int64, unsigned __int16 **, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180292878`

## callees

- `0x18001413d`
- `0x180044810`
- `0x180057dec`
- `0x1800b478c`
- `0x18017ca68`
- `0x18017f180`
- `0x18029a0fc`
- `0x18029c980`
- `0x1802d6424`
- `0x1802de3e8`
- `0x180356f34`
- `0x1804bbf62`
- `0x1804bbfa0`
- `0x180509010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18029a4d1`
- `KERNEL32!GetLastError` at `0x18029a4e8`
- `KERNEL32!GetLastError` at `0x18029a508`
- `KERNEL32!GetLastError` at `0x18029a5ad`
- `KERNEL32!GetLastError` at `0x18029a5c3`
- `KERNEL32!GetLastError` at `0x18029a5e3`
- `KERNEL32!GetLastError` at `0x18029a67c`
- `KERNEL32!GetLastError` at `0x18029a692`
- `KERNEL32!GetLastError` at `0x18029a6b2`
- `KERNEL32!GetLastError` at `0x18029a76c`
- `KERNEL32!GetLastError` at `0x18029a789`
- `KERNEL32!GetLastError` at `0x18029a7ad`
- `KERNEL32!GetLastError` at `0x18029a839`
- `KERNEL32!GetLastError` at `0x18029a8cf`
- `KERNEL32!GetLastError` at `0x18029a8e8`
- `KERNEL32!GetLastError` at `0x18029a908`
- `KERNEL32!GetLastError` at `0x18029a9c2`
- `KERNEL32!GetLastError` at `0x18029aa6a`
- `KERNEL32!GetLastError` at `0x18029a4d1`
- `KERNEL32!GetLastError` at `0x18029a4e8`
- `KERNEL32!GetLastError` at `0x18029a508`
- `KERNEL32!GetLastError` at `0x18029a5ad`
- `KERNEL32!GetLastError` at `0x18029a5c3`
- `KERNEL32!GetLastError` at `0x18029a5e3`
- `KERNEL32!GetLastError` at `0x18029a67c`
- `KERNEL32!GetLastError` at `0x18029a692`
- `KERNEL32!GetLastError` at `0x18029a6b2`
- `KERNEL32!GetLastError` at `0x18029a76c`
- `KERNEL32!GetLastError` at `0x18029a789`
- `KERNEL32!GetLastError` at `0x18029a7ad`
- `KERNEL32!GetLastError` at `0x18029a839`
- `KERNEL32!GetLastError` at `0x18029a8cf`
- `KERNEL32!GetLastError` at `0x18029a8e8`
- `KERNEL32!GetLastError` at `0x18029a908`
- `KERNEL32!GetLastError` at `0x18029a9c2`
- `KERNEL32!GetLastError` at `0x18029aa6a`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18029abb4`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18029abb4`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x18029a20f`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x18029a20f`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18029a3ab`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18029a3ab`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x18029a495`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x18029a495`
- `unbcl!?CreateTemporaryDirectory@Directory@UnBCL@@SAPEAVString@2@XZ` at `0x18029a224`
- `unbcl!?CreateTemporaryDirectory@Directory@UnBCL@@SAPEAVString@2@XZ` at `0x18029a224`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18029a39f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18029a39f`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18029a195`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18029a195`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18029a3cb`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18029a3cb`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18029a38e`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18029a38e`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18029a24c`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18029a24c`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18029a2ab`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18029a3d9`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18029a419`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18029a989`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18029abd4`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18029a2ab`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18029a3d9`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18029a419`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18029a989`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18029abd4`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18029a265`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18029a2b4`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18029a31d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18029a3e2`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18029a422`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18029a51c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18029a6c6`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18029a6d2`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18029a992`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18029abdd`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18029a265`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18029a2b4`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18029a31d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18029a3e2`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18029a422`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18029a51c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18029a6c6`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18029a6d2`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18029a992`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18029abdd`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18029a25b`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18029a4a4`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18029ab10`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18029ac0f`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18029a25b`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18029a4a4`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18029ab10`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18029ac0f`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18029a235`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18029a3bc`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18029abc5`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18029a235`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18029a3bc`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18029abc5`
- `WDSCORE!WdsSetupLogMessageW` at `0x18029a57b`
- `WDSCORE!WdsSetupLogMessageW` at `0x18029a64a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18029a73c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18029a816`
- `WDSCORE!WdsSetupLogMessageW` at `0x18029a8a0`
- `WDSCORE!WdsSetupLogMessageW` at `0x18029a96f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18029aa18`
- `WDSCORE!WdsSetupLogMessageW` at `0x18029aad8`
- `WDSCORE!WdsSetupLogMessageW` at `0x18029a57b`
- `WDSCORE!WdsSetupLogMessageW` at `0x18029a64a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18029a73c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18029a816`
- `WDSCORE!WdsSetupLogMessageW` at `0x18029a8a0`
- `WDSCORE!WdsSetupLogMessageW` at `0x18029a96f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18029aa18`
- `WDSCORE!WdsSetupLogMessageW` at `0x18029aad8`
- `WDSCORE!CurrentIP` at `0x18029a510`
- `WDSCORE!CurrentIP` at `0x18029a5eb`
- `WDSCORE!CurrentIP` at `0x18029a6ba`
- `WDSCORE!CurrentIP` at `0x18029a7b5`
- `WDSCORE!CurrentIP` at `0x18029a841`
- `WDSCORE!CurrentIP` at `0x18029a910`
- `WDSCORE!CurrentIP` at `0x18029a9ca`
- `WDSCORE!CurrentIP` at `0x18029aa72`
- `WDSCORE!CurrentIP` at `0x18029a510`
- `WDSCORE!CurrentIP` at `0x18029a5eb`
- `WDSCORE!CurrentIP` at `0x18029a6ba`
- `WDSCORE!CurrentIP` at `0x18029a7b5`
- `WDSCORE!CurrentIP` at `0x18029a841`
- `WDSCORE!CurrentIP` at `0x18029a910`
- `WDSCORE!CurrentIP` at `0x18029a9ca`
- `WDSCORE!CurrentIP` at `0x18029aa72`
- `WIMGAPI!WIMCreateFile` at `0x18029a289`
- `WIMGAPI!WIMCreateFile` at `0x18029a289`
- `WIMGAPI!WIMSetTemporaryPath` at `0x18029a2c0`
- `WIMGAPI!WIMSetTemporaryPath` at `0x18029a2c0`
- `WIMGAPI!WIMSetReferenceFile` at `0x18029a32f`
- `WIMGAPI!WIMSetReferenceFile` at `0x18029a32f`
- `WIMGAPI!WIMLoadImage` at `0x18029ab3b`
- `WIMGAPI!WIMLoadImage` at `0x18029ab3b`
- `WIMGAPI!WIMFindFirstImageFileEx` at `0x18029abf7`
- `WIMGAPI!WIMFindFirstImageFileEx` at `0x18029abf7`
- `WIMGAPI!WIMExtractImagePathByWimHandle` at `0x18029a403`
- `WIMGAPI!WIMExtractImagePathByWimHandle` at `0x18029a403`

## string_xrefs

- `0x18029a5f7`: `SPGetWIMImageInfo: Failed to set temporary WIM path. Error: 0x%08X`
- `0x18029a528`: `SPGetWIMImageInfo: Failed to create WIM handle for %s. Error: 0x%08X`
- `0x18029a3f3`: `\windows\system32\config\SOFTWARE`
- `0x18029a6e2`: `SPGetWIMImageInfo: Failed to set reference path %s for %s. Error: 0x%x`
- `0x18029a9d3`: `SPGetWIMImageInfo: Software hive from temporary location in use; logging process names.`
- `0x18029a91c`: `SPGetWIMImageInfo: Failed to load software hive from temporary location. Error: 0x%08X`

## pseudocode

```c

```
