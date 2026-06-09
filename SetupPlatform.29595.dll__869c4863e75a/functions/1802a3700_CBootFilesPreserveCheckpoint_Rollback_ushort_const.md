# CBootFilesPreserveCheckpoint::Rollback(ushort const *)

- ea: `0x1802a3700`
- end: `0x1802a559c`
- name: `?Rollback@CBootFilesPreserveCheckpoint@@UEAAXPEBG@Z`
- size: `7836`
- prototype: `void(CBootFilesPreserveCheckpoint *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `30`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18001413d`
- `0x1800197c0`
- `0x1800447ec`
- `0x180057dec`
- `0x18011a588`
- `0x18011b9c0`
- `0x180129574`
- `0x18029fc74`
- `0x1802a3700`
- `0x1802b5920`
- `0x1802cd800`
- `0x1802d010c`
- `0x1802dacac`
- `0x1802e2078`
- `0x1802fb834`
- `0x180429f40`
- `0x180429f94`
- `0x1804791fc`
- `0x180479248`
- `0x18047942c`
- `0x180479478`
- `0x18047972c`
- `0x1804799e4`
- `0x180479bf4`
- `0x180479e40`
- `0x180479f70`
- `0x18047a1b4`
- `0x18047e04c`
- `0x1804bbfa0`
- `0x180509010`

## import_xrefs

- `msvcrt!wcstoul` at `0x1802a50c0`
- `msvcrt!wcstoul` at `0x1802a50c0`
- `ntdll!RtlNtStatusToDosError` at `0x1802a42ed`
- `ntdll!RtlNtStatusToDosError` at `0x1802a4d65`
- `ntdll!RtlNtStatusToDosError` at `0x1802a42ed`
- `ntdll!RtlNtStatusToDosError` at `0x1802a4d65`
- `KERNEL32!GetLastError` at `0x1802a37c5`
- `KERNEL32!GetLastError` at `0x1802a398c`
- `KERNEL32!GetLastError` at `0x1802a3aed`
- `KERNEL32!GetLastError` at `0x1802a3bac`
- `KERNEL32!GetLastError` at `0x1802a3c0c`
- `KERNEL32!GetLastError` at `0x1802a3dad`
- `KERNEL32!GetLastError` at `0x1802a3e57`
- `KERNEL32!GetLastError` at `0x1802a3ee5`
- `KERNEL32!GetLastError` at `0x1802a3f3b`
- `KERNEL32!GetLastError` at `0x1802a3fa2`
- `KERNEL32!GetLastError` at `0x1802a3fb3`
- `KERNEL32!GetLastError` at `0x1802a40c7`
- `KERNEL32!GetLastError` at `0x1802a4238`
- `KERNEL32!GetLastError` at `0x1802a42fd`
- `KERNEL32!GetLastError` at `0x1802a437e`
- `KERNEL32!GetLastError` at `0x1802a43de`
- `KERNEL32!GetLastError` at `0x1802a4443`
- `KERNEL32!GetLastError` at `0x1802a44b5`
- `KERNEL32!GetLastError` at `0x1802a4512`
- `KERNEL32!GetLastError` at `0x1802a4523`
- `KERNEL32!GetLastError` at `0x1802a46c1`
- `KERNEL32!GetLastError` at `0x1802a4813`
- `KERNEL32!GetLastError` at `0x1802a490a`
- `KERNEL32!GetLastError` at `0x1802a498c`
- `KERNEL32!GetLastError` at `0x1802a4a47`
- `KERNEL32!GetLastError` at `0x1802a4acc`
- `KERNEL32!GetLastError` at `0x1802a4b60`
- `KERNEL32!GetLastError` at `0x1802a4c0a`
- `KERNEL32!GetLastError` at `0x1802a4c99`
- `KERNEL32!GetLastError` at `0x1802a4caa`
- `KERNEL32!GetLastError` at `0x1802a4d77`
- `KERNEL32!GetLastError` at `0x1802a4df5`
- `KERNEL32!GetLastError` at `0x1802a4e55`
- `KERNEL32!GetLastError` at `0x1802a4eaf`
- `KERNEL32!GetLastError` at `0x1802a4f3a`
- `KERNEL32!GetLastError` at `0x1802a4f97`
- `KERNEL32!GetLastError` at `0x1802a4fa8`
- `KERNEL32!GetLastError` at `0x1802a50de`
- `KERNEL32!GetLastError` at `0x1802a5145`
- `KERNEL32!GetLastError` at `0x1802a5241`
- `KERNEL32!GetLastError` at `0x1802a5249`
- `KERNEL32!GetLastError` at `0x1802a536d`
- `KERNEL32!GetLastError` at `0x1802a5375`
- `KERNEL32!GetLastError` at `0x1802a543d`
- `KERNEL32!GetLastError` at `0x1802a544e`
- `KERNEL32!GetLastError` at `0x1802a37c5`
- `KERNEL32!GetLastError` at `0x1802a398c`
- `KERNEL32!GetLastError` at `0x1802a3aed`
- `KERNEL32!GetLastError` at `0x1802a3bac`
- `KERNEL32!GetLastError` at `0x1802a3c0c`
- `KERNEL32!GetLastError` at `0x1802a3dad`
- `KERNEL32!GetLastError` at `0x1802a3e57`
- `KERNEL32!GetLastError` at `0x1802a3ee5`
- `KERNEL32!GetLastError` at `0x1802a3f3b`
- `KERNEL32!GetLastError` at `0x1802a3fa2`
- `KERNEL32!GetLastError` at `0x1802a3fb3`
- `KERNEL32!GetLastError` at `0x1802a40c7`
- `KERNEL32!GetLastError` at `0x1802a4238`
- `KERNEL32!GetLastError` at `0x1802a42fd`
- `KERNEL32!GetLastError` at `0x1802a437e`
- `KERNEL32!GetLastError` at `0x1802a43de`
- `KERNEL32!GetLastError` at `0x1802a4443`
- `KERNEL32!GetLastError` at `0x1802a44b5`
- `KERNEL32!GetLastError` at `0x1802a4512`
- `KERNEL32!GetLastError` at `0x1802a4523`
- `KERNEL32!GetLastError` at `0x1802a46c1`
- `KERNEL32!GetLastError` at `0x1802a4813`
- `KERNEL32!GetLastError` at `0x1802a490a`
- `KERNEL32!GetLastError` at `0x1802a498c`
- `KERNEL32!GetLastError` at `0x1802a4a47`
- `KERNEL32!GetLastError` at `0x1802a4acc`
- `KERNEL32!GetLastError` at `0x1802a4b60`
- `KERNEL32!GetLastError` at `0x1802a4c0a`
- `KERNEL32!GetLastError` at `0x1802a4c99`
- `KERNEL32!GetLastError` at `0x1802a4caa`
- `KERNEL32!GetLastError` at `0x1802a4d77`
- `KERNEL32!GetLastError` at `0x1802a4df5`
- `KERNEL32!GetLastError` at `0x1802a4e55`
- `KERNEL32!GetLastError` at `0x1802a4eaf`
- `KERNEL32!GetLastError` at `0x1802a4f3a`
- `KERNEL32!GetLastError` at `0x1802a4f97`
- `KERNEL32!GetLastError` at `0x1802a4fa8`
- `KERNEL32!GetLastError` at `0x1802a50de`
- `KERNEL32!GetLastError` at `0x1802a5145`
- `KERNEL32!GetLastError` at `0x1802a5241`
- `KERNEL32!GetLastError` at `0x1802a5249`
- `KERNEL32!GetLastError` at `0x1802a536d`
- `KERNEL32!GetLastError` at `0x1802a5375`
- `KERNEL32!GetLastError` at `0x1802a543d`
- `KERNEL32!GetLastError` at `0x1802a544e`
- `KERNEL32!GetFileAttributesW` at `0x1802a375f`
- `KERNEL32!GetFileAttributesW` at `0x1802a502f`
- `KERNEL32!GetFileAttributesW` at `0x1802a375f`
- `KERNEL32!GetFileAttributesW` at `0x1802a502f`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a3896`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a3896`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1802a3785`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1802a3785`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1802a5200`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1802a5200`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802a38da`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802a3930`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802a38da`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802a3930`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1802a3a50`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1802a51aa`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1802a3a50`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1802a51aa`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x1802a40ad`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x1802a47ec`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x1802a40ad`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x1802a47ec`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802a3858`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802a38ce`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802a3aa2`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802a409b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802a417a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802a41ed`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802a45ff`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802a4676`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802a479e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802a47dd`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802a489c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802a48c9`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802a3858`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802a38ce`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802a3aa2`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802a409b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802a417a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802a41ed`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802a45ff`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802a4676`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802a479e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802a47dd`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802a489c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802a48c9`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a38fa`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a3950`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a395f`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a40bd`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a480d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a38fa`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a3950`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a395f`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a40bd`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a480d`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802a38bd`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802a390f`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802a3923`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802a408a`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802a47bb`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802a38bd`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802a390f`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802a3923`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802a408a`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802a47bb`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802a3ca8`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802a51e0`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802a52c1`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802a5319`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802a53ec`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802a3ca8`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802a51e0`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802a52c1`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802a5319`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802a53ec`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802a41d0`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802a4659`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802a41d0`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802a4659`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802a386f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802a3a63`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802a3ac4`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802a3b06`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802a3fc3`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802a4041`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802a413f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802a418d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802a420f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802a4251`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802a4533`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802a45c0`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802a4612`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802a4698`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802a46da`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802a4749`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802a4763`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802a48e8`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802a4bd9`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802a4cba`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802a4fb8`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802a5046`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802a50a3`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802a545e`

## string_xrefs

- `0x1802a4151`: `Rollback`
- `0x1802a3900`: `rollbackinfo.ini`
- `0x1802a39a7`: `%hs: BCD Open failed. Error: 0x%08X`
- `0x1802a4053`: `RollbackExternal`
- `0x1802a37b9`: `SeRestorePrivilege`
- `0x1802a37a6`: `SeBackupPrivilege`
- `0x1802a5260`: `Rollback folder %s does not exist. Error: 0x%08X`
- `0x1802a5391`: `Rollback folder %s does not exist. Error: 0x%08X`
- `0x1802a52d4`: `Rollback folder not found`
- `0x1802a53ff`: `Rollback folder not found`
- `0x1802a37fa`: `CBootFilesPreserveCheckpoint::Rollback`
- `0x1802a4867`: `CBootFilesPreserveCheckpoint::Rollback`
- `0x1802a494c`: `CBootFilesPreserveCheckpoint::Rollback`
- `0x1802a49e0`: `CBootFilesPreserveCheckpoint::Rollback`
- `0x1802a4a82`: `CBootFilesPreserveCheckpoint::Rollback`
- `0x1802a4b1b`: `CBootFilesPreserveCheckpoint::Rollback`
- `0x1802a4b9f`: `CBootFilesPreserveCheckpoint::Rollback`
- `0x1802a4c62`: `CBootFilesPreserveCheckpoint::Rollback`
- `0x1802a4cfe`: `CBootFilesPreserveCheckpoint::Rollback`
- `0x1802a4d36`: `CBootFilesPreserveCheckpoint::Rollback`
- `0x1802a5284`: `CBootFilesPreserveCheckpoint::Rollback`
- `0x1802a5215`: `void __cdecl CBootFilesPreserveCheckpoint::Rollback(const unsigned short *)`
- `0x1802a52ea`: `void __cdecl CBootFilesPreserveCheckpoint::Rollback(const unsigned short *)`
- `0x1802a5341`: `void __cdecl CBootFilesPreserveCheckpoint::Rollback(const unsigned short *)`
- `0x1802a5411`: `void __cdecl CBootFilesPreserveCheckpoint::Rollback(const unsigned short *)`
- `0x1802a3806`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a39d7`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a3b4e`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a3bf3`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a3c50`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a3d38`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a3df8`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a3e41`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a3e9e`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a3f89`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a4013`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a4292`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a433d`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a43c5`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a4422`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a448a`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a44fc`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a457c`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a471b`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a4958`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a49ec`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a4a8e`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a4b27`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a4bab`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a4c6e`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a4d0a`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a4d3d`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a4e3c`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a4e99`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a4f81`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a5001`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a5125`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a518c`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a5290`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a53c1`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a54a7`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a39a0`: `CBootFilesPreserveCheckpoint::Rollback`
- `0x1802a3b18`: `CBootFilesPreserveCheckpoint::Rollback`
- `0x1802a3f4f`: `CBootFilesPreserveCheckpoint::Rollback`
- `0x1802a3fd9`: `CBootFilesPreserveCheckpoint::Rollback`
- `0x1802a37d6`: `CBootFilesPreserveCheckpoint::Rollback: We will preserve the new version of the boot files.`
- `0x1802a532c`: `CBootFilesPreserveCheckpoint: Failed to find setup platform path.`
- `0x1802a4266`: `%hs: Rollback boot entry is: %s`
- `0x1802a4311`: `%hs: We successfully removed rollback boot entry references`
- `0x1802a3fe3`: `%hs: Failed to read the default GUID from file: %s. Error: 0x%08X`
- `0x1802a40db`: `%hs: Not removing rollback boot entry because it was an external rollback`
- `0x1802a3e6e`: `%hs: Failed to read the display list, downlevel OS entry will remain invisible. Error: 0x%08X`
- `0x1802a454c`: `%hs: Failed to read the rollback GUID from file: %s. Error: 0x%08X`
- `0x1802a445a`: `%hs: BCD failed to remove rollback boot entry references. Error: 0x%08X`
- `0x1802a44cc`: `%hs: Failed to convert rollback GUID. Error: 0x%08X`
- `0x1802a4395`: `%hs: BCD failed to remove rollback boot entry. Error: 0x%08X`
- `0x1802a43f2`: `%hs: We successfully removed the rollback boot entry`
- `0x1802a4e0c`: `%hs: BCD failed to remove new OS boot entry. Error: 0x%08X`
- `0x1802a4e69`: `%hs: We successfully removed the new OS boot entry`
- `0x1802a4c37`: `%hs: Failed to delete new OS BCD from BitLocker validation info for %s. hr = 0x%08X`
- `0x1802a4d8b`: `%hs: We successfully removed new OS boot entry references`
- `0x1802a4b74`: `%hs: New OS BCD is added to BitLocker validation info, delete it.`
- `0x1802a5477`: `%hs: Failed to read the boot manager timeout from file: %s. Error: 0x%08X`
- `0x1802a4ec8`: `%hs: BCD failed to remove new OS boot entry references. Error: 0x%08X`
- `0x1802a4fd1`: `%hs: Failed to read the new OS GUID from file: %s. Error: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=31 #try_helpers=1
void __fastcall CBootFilesPreserveCheckpoint::Rollback(CBootFilesPreserveCheckpoint *this, const unsigned __int16 *a2)
{
  DWORD v3; // edi
  __int64 v4; // rbx
  struct tagLOG_PARTIAL_MSG *v5; // rax
  struct UnBCL::String *PlatformDir; // rax
  UnBCL::String *v7; // rax
  unsigned __int16 *CString; // rax
  struct UnBCL::String *v9; // rax
  const struct UnBCL::String *v10; // rbx
  const struct UnBCL::String *P; // rax
  struct UnBCL::String *v12; // rax
  const struct UnBCL::String *v13; // rbx
  const struct UnBCL::String *v14; // rax
  struct UnBCL::String *v15; // rax
  unsigned int v16; // esi
  DWORD v17; // edi
  __int64 v18; // rbx
  struct tagLOG_PARTIAL_MSG *v19; // rax
  UnBCL::String *v20; // rax
  const WCHAR *v21; // rax
  struct UnBCL::String *v22; // rax
  UnBCL::String *v23; // rax
  const unsigned __int16 *v24; // rax
  int v25; // esi
  DWORD v26; // ebx
  __int64 v27; // rdi
  UnBCL::String *v28; // rax
  const char *v29; // rax
  struct tagLOG_PARTIAL_MSG *v30; // rax
  unsigned int v31; // esi
  DWORD v32; // edi
  __int64 v33; // rbx
  struct tagLOG_PARTIAL_MSG *v34; // rax
  DWORD v35; // edi
  __int64 v36; // rbx
  struct tagLOG_PARTIAL_MSG *v37; // rax
  __int64 v38; // rdx
  __int64 v39; // r8
  int IdentityList; // esi
  void *v41; // rax
  __int64 v42; // rdi
  __int64 v43; // rcx
  unsigned int i; // ebx
  _QWORD *Item; // rax
  __int64 v46; // rsi
  void (__fastcall *v47)(__int64, _OWORD *); // r14
  int v48; // esi
  DWORD v49; // edi
  __int64 v50; // rbx
  struct tagLOG_PARTIAL_MSG *v51; // rax
  struct tagLOG_PARTIAL_MSG *v52; // rax
  DWORD v53; // edi
  __int64 v54; // rbx
  struct tagLOG_PARTIAL_MSG *v55; // rax
  DWORD v56; // edi
  __int64 v57; // rbx
  struct tagLOG_PARTIAL_MSG *v58; // rax
  DWORD v59; // edi
  __int64 v60; // rbx
  struct tagLOG_PARTIAL_MSG *v61; // rax
  DWORD v62; // ebx
  __int64 v63; // rdi
  DWORD v64; // esi
  UnBCL::String *v65; // rax
  const char *v66; // rax
  struct tagLOG_PARTIAL_MSG *v67; // rax
  UnBCL::String *v68; // rax
  const WCHAR *v69; // rax
  struct UnBCL::String *v70; // rax
  const struct UnBCL::String *v71; // rbx
  const struct UnBCL::String *v72; // rax
  DWORD v73; // edi
  __int64 v74; // rbx
  struct tagLOG_PARTIAL_MSG *v75; // rax
  UnBCL::String *v76; // rax
  const WCHAR *v77; // rax
  struct UnBCL::String *v78; // rax
  UnBCL::String *v79; // rax
  const WCHAR *v80; // rax
  struct UnBCL::String *v81; // rax
  UnBCL::String *v82; // rax
  const unsigned __int16 *v83; // rax
  int v84; // esi
  DWORD v85; // ebx
  __int64 v86; // rdi
  UnBCL::String *v87; // rax
  const char *v88; // rax
  struct tagLOG_PARTIAL_MSG *v89; // rax
  ULONG v90; // esi
  NTSTATUS v91; // eax
  DWORD v92; // edi
  __int64 v93; // rbx
  struct tagLOG_PARTIAL_MSG *v94; // rax
  unsigned int v95; // esi
  DWORD v96; // edi
  __int64 v97; // rbx
  struct tagLOG_PARTIAL_MSG *v98; // rax
  DWORD v99; // edi
  __int64 v100; // rbx
  struct tagLOG_PARTIAL_MSG *v101; // rax
  DWORD v102; // edi
  __int64 v103; // rbx
  DWORD v104; // ebx
  __int64 v105; // rdi
  DWORD v106; // esi
  UnBCL::String *v107; // rax
  const char *v108; // rax
  UnBCL::String *v109; // rax
  const WCHAR *v110; // rax
  struct UnBCL::String *v111; // rax
  UnBCL::String *v112; // rax
  const WCHAR *v113; // rax
  struct UnBCL::String *v114; // rax
  UnBCL::String *v115; // rax
  const unsigned __int16 *v116; // rax
  int v117; // esi
  DWORD v118; // ebx
  __int64 v119; // rdi
  UnBCL::String *v120; // rax
  const char *v121; // rax
  struct tagLOG_PARTIAL_MSG *v122; // rax
  UnBCL::String *v123; // rax
  const WCHAR *v124; // rbx
  UnBCL::String *v125; // rax
  const WCHAR *v126; // rax
  struct UnBCL::String *v127; // rax
  const wchar_t *v128; // r12
  const struct UnBCL::String *v129; // rbx
  unsigned int v130; // r15d
  char v131; // di
  const struct UnBCL::String *v132; // rax
  DWORD v133; // edi
  __int64 v134; // rbx
  const unsigned __int16 *v135; // r9
  struct tagLOG_PARTIAL_MSG *v136; // rax
  struct UnBCL::String *v137; // rax
  struct UnBCL::String *v138; // rax
  UnBCL::String *v139; // rax
  const unsigned __int16 *v140; // rax
  int IsProtectionActive; // esi
  DWORD v142; // edi
  __int64 v143; // rbx
  struct tagLOG_PARTIAL_MSG *v144; // rax
  int v145; // r14d
  DWORD v146; // edi
  __int64 v147; // rbx
  const wchar_t *v148; // r9
  struct tagLOG_PARTIAL_MSG *v149; // rax
  unsigned int v150; // r8d
  DWORD v151; // edi
  __int64 v152; // rbx
  struct tagLOG_PARTIAL_MSG *v153; // rax
  int v154; // esi
  DWORD v155; // edi
  __int64 v156; // rbx
  struct tagLOG_PARTIAL_MSG *v157; // rax
  DWORD v158; // edi
  __int64 v159; // rbx
  struct tagLOG_PARTIAL_MSG *v160; // rax
  UnBCL::String *v161; // rax
  const unsigned __int16 *v162; // rax
  int updated; // esi
  DWORD v164; // edi
  __int64 v165; // rbx
  const wchar_t *v166; // r9
  struct tagLOG_PARTIAL_MSG *v167; // rax
  DWORD v168; // ebx
  __int64 v169; // rdi
  DWORD v170; // esi
  UnBCL::String *v171; // rax
  const char *v172; // rax
  NTSTATUS v173; // eax
  DWORD v174; // edi
  __int64 v175; // rbx
  struct tagLOG_PARTIAL_MSG *v176; // rax
  unsigned int v177; // esi
  DWORD v178; // edi
  __int64 v179; // rbx
  struct tagLOG_PARTIAL_MSG *v180; // rax
  DWORD v181; // edi
  __int64 v182; // rbx
  DWORD v183; // edi
  __int64 v184; // rbx
  struct tagLOG_PARTIAL_MSG *v185; // rax
  DWORD v186; // ebx
  __int64 v187; // rdi
  DWORD v188; // esi
  UnBCL::String *v189; // rax
  const char *v190; // rax
  struct tagLOG_PARTIAL_MSG *v191; // rax
  UnBCL::String *v192; // rax
  const WCHAR *v193; // rax
  struct UnBCL::String *v194; // rax
  __int64 v195; // rdx
  UnBCL::String *v196; // rax
  const wchar_t *v197; // rax
  unsigned int v198; // esi
  unsigned int v199; // r14d
  DWORD v200; // edi
  __int64 v201; // rbx
  struct tagLOG_PARTIAL_MSG *v202; // rax
  OSRollbackService::CBootFilesRestoreCheckpoint *v203; // rax
  OSRollbackService::CBootFilesRestoreCheckpoint *v204; // rbx
  DWORD LastError; // esi
  DWORD v206; // edi
  __int64 v207; // rbx
  struct tagLOG_PARTIAL_MSG *v208; // rax
  OSRollbackService::CBootFilesRestoreCheckpoint *v209; // rax
  RollbackException *v210; // rax
  OSRollbackService::CBootFilesRestoreCheckpoint *v211; // rax
  DWORD v212; // esi
  DWORD v213; // edi
  __int64 v214; // rbx
  struct tagLOG_PARTIAL_MSG *v215; // rax
  OSRollbackService::CBootFilesRestoreCheckpoint *v216; // rax
  DWORD v217; // ebx
  __int64 v218; // rdi
  DWORD v219; // esi
  UnBCL::String *v220; // rax
  const char *v221; // rax
  DWORD v222; // edi
  __int64 v223; // rbx
  struct tagLOG_PARTIAL_MSG *v224; // rax
  DWORD v225; // edi
  __int64 v226; // rbx
  struct tagLOG_PARTIAL_MSG *v227; // rax
  int v228; // [rsp+20h] [rbp-2B8h]
  int v229; // [rsp+20h] [rbp-2B8h]
  int v230; // [rsp+20h] [rbp-2B8h]
  int v231; // [rsp+20h] [rbp-2B8h]
  __int64 v232; // [rsp+38h] [rbp-2A0h]
  __int64 v233; // [rsp+38h] [rbp-2A0h]
  __int64 v234; // [rsp+38h] [rbp-2A0h]
  __int64 v235; // [rsp+38h] [rbp-2A0h]
  DWORD v236; // [rsp+40h] [rbp-298h]
  DWORD v237; // [rsp+40h] [rbp-298h]
  DWORD v238; // [rsp+40h] [rbp-298h]
  DWORD v239; // [rsp+40h] [rbp-298h]
  wchar_t *EndPtr; // [rsp+60h] [rbp-278h] BYREF
  void *v241; // [rsp+68h] [rbp-270h]
  int v242; // [rsp+70h] [rbp-268h] BYREF
  int v243; // [rsp+74h] [rbp-264h] BYREF
  int v244; // [rsp+78h] [rbp-260h]
  OSRollbackService::CBootFilesRestoreCheckpoint *v245; // [rsp+80h] [rbp-258h]
  _OWORD v246[2]; // [rsp+90h] [rbp-248h] BYREF
  _BYTE v247[16]; // [rsp+B0h] [rbp-228h] BYREF
  LPCWSTR lpFileName; // [rsp+C0h] [rbp-218h]
  _BYTE v249[16]; // [rsp+C8h] [rbp-210h] BYREF
  _BYTE v250[16]; // [rsp+D8h] [rbp-200h] BYREF
  _BYTE v251[16]; // [rsp+E8h] [rbp-1F0h] BYREF
  __int64 v252; // [rsp+F8h] [rbp-1E0h]
  _BYTE v253[16]; // [rsp+108h] [rbp-1D0h] BYREF
  _BYTE v254[16]; // [rsp+118h] [rbp-1C0h] BYREF
  _BYTE v255[16]; // [rsp+128h] [rbp-1B0h] BYREF
  __int64 pExceptionObject; // [rsp+138h] [rbp-1A0h] BYREF
  __int64 v257; // [rsp+140h] [rbp-198h] BYREF
  __int64 v258; // [rsp+148h] [rbp-190h] BYREF
  __int64 v259; // [rsp+150h] [rbp-188h] BYREF
  _QWORD *v260; // [rsp+158h] [rbp-180h] BYREF
  _BYTE v261[16]; // [rsp+160h] [rbp-178h] BYREF
  _BYTE v262[16]; // [rsp+170h] [rbp-168h] BYREF
  __int64 v263; // [rsp+180h] [rbp-158h]
  _QWORD v264[7]; // [rsp+188h] [rbp-150h] BYREF
  _BYTE v265[32]; // [rsp+1C0h] [rbp-118h] BYREF
  struct _GUID v266; // [rsp+1E0h] [rbp-F8h] BYREF
  struct _GUID v267; // [rsp+200h] [rbp-D8h] BYREF
  _BYTE v268[16]; // [rsp+220h] [rbp-B8h] BYREF
  __int64 v269; // [rsp+230h] [rbp-A8h]
  _BYTE v270[64]; // [rsp+250h] [rbp-88h] BYREF
  _BYTE v271[16]; // [rsp+290h] [rbp-48h] BYREF

  v263 = -2;
  lpFileName = a2;
  v245 = this;
  LODWORD(EndPtr) = 0;
  if ( !a2 )
  {
    v203 = (OSRollbackService::CBootFilesRestoreCheckpoint *)UnBCL::Object::operator new(0x38u);
    v204 = v203;
    v245 = v203;
    if ( v203 )
    {
      UnBCL::ArgumentNullException::ArgumentNullException(v203, L"WorkingDir");
      *(_QWORD *)v204 = &UnBCL::ArgumentNullException::`local vftable';
    }
    else
    {
      v204 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v204,
                         "void __cdecl CBootFilesPreserveCheckpoint::Rollback(const unsigned short *)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( GetFileAttributesW(a2) == -1 )
  {
    LastError = GetLastError();
    v206 = GetLastError();
    v207 = CurrentIP();
    v208 = ConstructPartialMsgW(
             0x3000000u,
             "Rollback folder %s does not exist. Error: 0x%08X",
             (const char *)a2,
             LastError);
    WdsSetupLogMessageW(
      v208,
      819200,
      L"D",
      0,
      187,
      L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
      L"CBootFilesPreserveCheckpoint::Rollback",
      v207,
      v206,
      0,
      0);
    v209 = (OSRollbackService::CBootFilesRestoreCheckpoint *)UnBCL::Object::operator new(0x48u);
    v245 = v209;
    if ( v209 )
      v210 = RollbackException::RollbackException(v209, LastError, L"Rollback folder not found");
    else
      v210 = 0;
    v257 = AddStackTraceToException<UnBCL::InvalidOperationException>(
             v210,
             "void __cdecl CBootFilesPreserveCheckpoint::Rollback(const unsigned short *)");
    throw (RollbackException **)&v257;
  }
  v242 = 0;
  v243 = 0;
  v244 = 0;
  UnBCL::Exception::Exception((UnBCL::Exception *)v264);
  v264[0] = &`CBootFilesPreserveCheckpoint::Rollback'::`15'::CXXXXXHandledException::`vftable';
  SPEnablePrivilege(L"SeBackupPrivilege", 1, &v242);
  SPEnablePrivilege(L"SeRestorePrivilege", 1, &v243);
  v3 = GetLastError();
  v4 = CurrentIP();
  v5 = ConstructPartialMsgW(
         0x4000000u,
         "CBootFilesPreserveCheckpoint::Rollback: We will preserve the new version of the boot files.");
  WdsSetupLogMessageW(
    v5,
    819200,
    L"D",
    0,
    200,
    L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
    L"CBootFilesPreserveCheckpoint::Rollback",
    v4,
    v3,
    0,
    0);
  try
  {
    PlatformDir = pGetPlatformDir();
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v255, PlatformDir);
    if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(v255) )
    {
      v211 = (OSRollbackService::CBootFilesRestoreCheckpoint *)UnBCL::Object::operator new(0x48u);
      v245 = v211;
      if ( v211 )
        v211 = RollbackException::RollbackException(
                 v211,
                 3u,
                 L"CBootFilesPreserveCheckpoint: Failed to find setup platform path.");
      v258 = AddStackTraceToException<UnBCL::InvalidOperationException>(
               v211,
               "void __cdecl CBootFilesPreserveCheckpoint::Rollback(const unsigned short *)");
      throw (RollbackException **)&v258;
    }
    v7 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v255);
    CString = (unsigned __int16 *)UnBCL::String::get_CString(v7);
    v9 = UnBCL::String::Format(L"%c:\\%s\\%s", *CString, L"$WINDOWS.~BT", L"Sources");
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v253, v9);
    v10 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v246, L"SetupPlatform.ini");
    P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v253);
    v12 = UnBCL::Path::Combine(P, v10);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v250, v12);
    UnBCL::String::~String((UnBCL::String *)v246);
    v13 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v266, L"rollbackinfo.ini");
    v14 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v267, a2);
    v15 = UnBCL::Path::Combine(v14, v13);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v247, v15);
    UnBCL::String::~String((UnBCL::String *)&v267);
    UnBCL::String::~String((UnBCL::String *)&v266);
    OSRollbackUtils::CBCDManipulator::CBCDManipulator((OSRollbackUtils::CBCDManipulator *)v251);
    v16 = OSRollbackUtils::CBCDManipulator::Open((OSRollbackUtils::CBCDManipulator *)v251, 0);
    if ( v16 )
    {
      v17 = GetLastError();
      v18 = CurrentIP();
      v19 = ConstructPartialMsgW(
              0x3000000u,
              "%hs: BCD Open failed. Error: 0x%08X",
              "CBootFilesPreserveCheckpoint::Rollback",
              v16);
      WdsSetupLogMessageW(
        v19,
        819200,
        L"D",
        0,
        220,
        L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
        L"CBootFilesPreserveCheckpoint::Rollback",
        v18,
        v17,
        0,
        0);
      OSRollbackUtils::CBCDManipulator::~CBCDManipulator((OSRollbackUtils::CBCDManipulator *)v251);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v247);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v250);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v253);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v255);
      UnBCL::Exception::~Exception((UnBCL::Exception *)v264);
      return;
    }
    v20 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v247);
    v21 = UnBCL::String::get_CString(v20);
    v22 = SPReadConfigValue(L"BootEntries", L"DownlevelDefault", v21);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v254, v22);
    if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v254) )
    {
      v266 = 0;
      v23 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v254);
      v24 = UnBCL::String::get_CString(v23);
      v25 = SPGuidFromString(v24, &v266);
      if ( v25 )
      {
        v59 = GetLastError();
        v60 = CurrentIP();
        v61 = ConstructPartialMsgW(
                0x2000000u,
                "%hs: Failed to convert default GUID. Error: 0x%08X",
                "CBootFilesPreserveCheckpoint::Rollback",
                v25);
        WdsSetupLogMessageW(
          v61,
          819200,
          L"D",
          0,
          289,
          L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
          L"CBootFilesPreserveCheckpoint::Rollback",
          v60,
          v59,
          0,
          0);
      }
      else
      {
        v26 = GetLastError();
        v27 = CurrentIP();
        v28 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v254);
        v29 = (const char *)UnBCL::String::get_CString(v28);
        v30 = ConstructPartialMsgW(
                0x4000000u,
                "%hs: Default boot entry is: %s",
                "CBootFilesPreserveCheckpoint::Rollback",
                v29);
        WdsSetupLogMessageW(
          v30,
          819200,
          L"D",
          0,
          232,
          L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
          L"CBootFilesPreserveCheckpoint::Rollback",
          v27,
          v26,
          0,
          0);
        if ( (unsigned int)OSRollbackUtils::CBCDManipulator::DoesBootEntryExists(
                             (OSRollbackUtils::CBCDManipulator *)v251,
                             &v266) )
        {
          v31 = OSRollbackUtils::CBCDManipulator::SetDefaultBootEntry((OSRollbackUtils::CBCDManipulator *)v251, &v266);
          if ( v31 )
          {
            v32 = GetLastError();
            v33 = CurrentIP();
            v34 = ConstructPartialMsgW(
                    0x2000000u,
                    "%hs: BCD failed to set default boot entry. Error: 0x%08X",
                    "CBootFilesPreserveCheckpoint::Rollback",
                    v31);
            WdsSetupLogMessageW(
              v34,
              819200,
              L"D",
              0,
              239,
              L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
              L"CBootFilesPreserveCheckpoint::Rollback",
              v33,
              v32,
              0,
              0);
          }
          else
          {
            v35 = GetLastError();
            v36 = CurrentIP();
            v37 = ConstructPartialMsgW(
                    0x4000000u,
                    "%hs: We successfully set back the default boot entry",
                    "CBootFilesPreserveCheckpoint::Rollback");
            WdsSetupLogMessageW(
              v37,
              819200,
              L"D",
              0,
              243,
              L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
              L"CBootFilesPreserveCheckpoint::Rollback",
              v36,
              v35,
              0,
              0);
            UnBCL::ArrayList<_GUID>::ArrayList<_GUID>(v268);
            IdentityList = OSRollbackUtils::CBCDManipulator::GetIdentityList(v251, v38, v39, v268);
            if ( IdentityList )
            {
              v53 = GetLastError();
              v54 = CurrentIP();
              v55 = ConstructPartialMsgW(
                      0x2000000u,
                      "%hs: Failed to read the display list, downlevel OS entry will remain invisible. Error: 0x%08X",
                      "CBootFilesPreserveCheckpoint::Rollback",
                      IdentityList);
              WdsSetupLogMessageW(
                v55,
                819200,
                L"D",
                0,
                277,
                L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                L"CBootFilesPreserveCheckpoint::Rollback",
                v54,
                v53,
                0,
                0);
            }
            else
            {
              v41 = UnBCL::Object::operator new(0x80u);
              v241 = v41;
              if ( v41 )
                v42 = UnBCL::ArrayList<_GUID>::ArrayList<_GUID>(v41);
              else
                v42 = 0;
              v43 = v42 + *(int *)(*(_QWORD *)(v42 + 8) + 16LL) + 8LL;
              v246[0] = v266;
              (*(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v43 + 40LL))(v43, v246);
              for ( i = 0; (signed int)i < *(_DWORD *)(v269 + 8); ++i )
              {
                Item = (_QWORD *)UnBCL::ArrayList<_GUID>::get_Item(v271, i);
                if ( *Item == *(_QWORD *)&v266.Data1 && Item[1] == *(_QWORD *)v266.Data4 )
                  goto LABEL_25;
                v46 = *(int *)(*(_QWORD *)(v42 + 8) + 16LL);
                v47 = *(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)(v46 + v42 + 8) + 40LL);
                v246[0] = *(_OWORD *)UnBCL::ArrayList<_GUID>::get_Item(v271, i);
                v47(v46 + v42 + 8, v246);
              }
              v48 = OSRollbackUtils::CBCDManipulator::SetIdentityList((OSRollbackUtils::CBCDManipulator *)v251);
              v49 = GetLastError();
              v50 = CurrentIP();
              if ( v48 )
              {
                v51 = ConstructPartialMsgW(
                        0x2000000u,
                        "%hs: Failed to set the new identity list, downlevel OS entry will remain invisible. Error: 0x%08X",
                        "CBootFilesPreserveCheckpoint::Rollback",
                        v48);
                WdsSetupLogMessageW(
                  v51,
                  819200,
                  L"D",
                  0,
                  266,
                  L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                  L"CBootFilesPreserveCheckpoint::Rollback",
                  v50,
                  v49,
                  0,
                  0);
              }
              else
              {
                v52 = ConstructPartialMsgW(
                        0x4000000u,
                        "%hs: Downlevel OS boot entry is now visible",
                        "CBootFilesPreserveCheckpoint::Rollback");
                WdsSetupLogMessageW(
                  v52,
                  819200,
                  L"D",
                  0,
                  271,
                  L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                  L"CBootFilesPreserveCheckpoint::Rollback",
                  v50,
                  v49,
                  0,
                  0);
              }
            }
LABEL_25:
            UnBCL::ArrayList<_GUID>::~ArrayList<_GUID>(v270);
            UnBCL::Object::~Object((UnBCL::Object *)v270);
          }
        }
        else
        {
          v56 = GetLastError();
          v57 = CurrentIP();
          v58 = ConstructPartialMsgW(
                  0x2000000u,
                  "%hs: Default boot entry does not exist.",
                  "CBootFilesPreserveCheckpoint::Rollback");
          WdsSetupLogMessageW(
            v58,
            819200,
            L"D",
            0,
            284,
            L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
            L"CBootFilesPreserveCheckpoint::Rollback",
            v57,
            v56,
            0,
            0);
        }
      }
    }
    else
    {
      v62 = GetLastError();
      v63 = CurrentIP();
      v64 = GetLastError();
      v65 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v247);
      v66 = (const char *)UnBCL::String::get_CString(v65);
      v67 = ConstructPartialMsgW(
              0x3000000u,
              "%hs: Failed to read the default GUID from file: %s. Error: 0x%08X",
              "CBootFilesPreserveCheckpoint::Rollback",
              v66,
              v64);
      WdsSetupLogMessageW(
        v67,
        819200,
        L"D",
        0,
        294,
        L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
        L"CBootFilesPreserveCheckpoint::Rollback",
        v63,
        v62,
        0,
        0);
    }
    v68 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v247);
    v69 = UnBCL::String::get_CString(v68);
    v70 = SPReadConfigValue(L"BootEntries", L"RollbackExternal", v69);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v262, v70);
    v71 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v246, L"Yes");
    v72 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v262);
    LODWORD(v71) = UnBCL::String::Compare(v72, v71, 1);
    UnBCL::String::~String((UnBCL::String *)v246);
    if ( !(_DWORD)v71 )
    {
      v73 = GetLastError();
      v74 = CurrentIP();
      v75 = ConstructPartialMsgW(
              0x4000000u,
              "%hs: Not removing rollback boot entry because it was an external rollback",
              "CBootFilesPreserveCheckpoint::Rollback");
      WdsSetupLogMessageW(
        v75,
        819200,
        L"D",
        0,
        301,
        L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
        L"CBootFilesPreserveCheckpoint::Rollback",
        v74,
        v73,
        0,
        0);
      LODWORD(v241) = 87;
      goto LABEL_47;
    }
    v76 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v247);
    v77 = UnBCL::String::get_CString(v76);
    v78 = SPReadConfigValue(L"BootEntries", L"Rollback", v77);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v266, v78);
    if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(&v266) )
    {
      v79 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v250);
      v80 = UnBCL::String::get_CString(v79);
      v81 = SPReadConfigValue(L"BootEntries", L"SafeOS", v80);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v246, v81);
      UnBCL::SmartPtr<UnBCL::String>::operator=(&v266, v246);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v246);
    }
    if ( UnBCL::SmartPtr<UnBCL::String>::get_P(&v266) )
    {
      v267 = 0;
      v82 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v266);
      v83 = UnBCL::String::get_CString(v82);
      v84 = SPGuidFromString(v83, &v267);
      if ( v84 )
      {
        v102 = GetLastError();
        v103 = CurrentIP();
        v98 = ConstructPartialMsgW(
                0x2000000u,
                "%hs: Failed to convert rollback GUID. Error: 0x%08X",
                "CBootFilesPreserveCheckpoint::Rollback",
                v84);
        v236 = v102;
        v232 = v103;
        v228 = 341;
      }
      else
      {
        v85 = GetLastError();
        v86 = CurrentIP();
        v87 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v266);
        v88 = (const char *)UnBCL::String::get_CString(v87);
        v89 = ConstructPartialMsgW(
                0x4000000u,
                "%hs: Rollback boot entry is: %s",
                "CBootFilesPreserveCheckpoint::Rollback",
                v88);
        WdsSetupLogMessageW(
          v89,
          819200,
          L"D",
          0,
          318,
          L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
          L"CBootFilesPreserveCheckpoint::Rollback",
          v86,
          v85,
          0,
          0);
        if ( !v252 )
        {
          LODWORD(v241) = v84 + 87;
          v90 = v84 + 87;
LABEL_42:
          v99 = GetLastError();
          v100 = CurrentIP();
          v101 = ConstructPartialMsgW(
                   0x2000000u,
                   "%hs: BCD failed to remove rollback boot entry references. Error: 0x%08X",
                   "CBootFilesPreserveCheckpoint::Rollback",
                   v90);
          WdsSetupLogMessageW(
            v101,
            819200,
            L"D",
            0,
            336,
            L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
            L"CBootFilesPreserveCheckpoint::Rollback",
            v100,
            v99,
            0,
            0);
LABEL_46:
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v266);
LABEL_47:
          v109 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v247);
          v110 = UnBCL::String::get_CString(v109);
          v111 = SPReadConfigValue(L"BootEntries", L"NewOS", v110);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v249, v111);
          if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(v249) )
          {
            v112 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v250);
            v113 = UnBCL::String::get_CString(v112);
            v114 = SPReadConfigValue(L"BootEntries", L"NewOS", v113);
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v246, v114);
            UnBCL::SmartPtr<UnBCL::String>::operator=(v249, v246);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v246);
          }
          if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(v249) )
          {
            v186 = GetLastError();
            v187 = CurrentIP();
            v188 = GetLastError();
            v189 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v247);
            v190 = (const char *)UnBCL::String::get_CString(v189);
            v191 = ConstructPartialMsgW(
                     0x3000000u,
                     "%hs: Failed to read the new OS GUID from file: %s. Error: 0x%08X",
                     "CBootFilesPreserveCheckpoint::Rollback",
                     v190,
                     v188);
            WdsSetupLogMessageW(
              v191,
              819200,
              L"D",
              0,
              442,
              L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
              L"CBootFilesPreserveCheckpoint::Rollback",
              v187,
              v186,
              0,
              0);
            goto LABEL_89;
          }
          v266 = 0;
          v115 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v249);
          v116 = UnBCL::String::get_CString(v115);
          v117 = SPGuidFromString(v116, &v266);
          if ( v117 )
          {
            v183 = GetLastError();
            v184 = CurrentIP();
            v185 = ConstructPartialMsgW(
                     0x2000000u,
                     "%hs: Failed to convert default GUID. Error: 0x%08X",
                     "CBootFilesPreserveCheckpoint::Rollback",
                     v117);
            WdsSetupLogMessageW(
              v185,
              819200,
              L"D",
              0,
              437,
              L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
              L"CBootFilesPreserveCheckpoint::Rollback",
              v184,
              v183,
              0,
              0);
            goto LABEL_89;
          }
          v118 = GetLastError();
          v119 = CurrentIP();
          v120 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v249);
          v121 = (const char *)UnBCL::String::get_CString(v120);
          v122 = ConstructPartialMsgW(
                   0x4000000u,
                   "%hs: NewOS boot entry is: %s",
                   "CBootFilesPreserveCheckpoint::Rollback",
                   v121);
          WdsSetupLogMessageW(
            v122,
            819200,
            L"D",
            0,
            363,
            L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
            L"CBootFilesPreserveCheckpoint::Rollback",
            v119,
            v118,
            0,
            0);
          v123 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v250);
          v124 = UnBCL::String::get_CString(v123);
          v125 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v249);
          v126 = UnBCL::String::get_CString(v125);
          v127 = SPReadConfigValue(L"BitLocker.ValidationInfo", v126, v124);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v246, v127);
          v128 = L"True";
          if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v246) )
          {
            v129 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v265, L"True");
            v130 = 1;
            v131 = (unsigned __int8)EndPtr | 1;
            LODWORD(EndPtr) = (unsigned int)EndPtr | 1;
            v132 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v246);
            if ( !UnBCL::String::Compare(v132, v129, 1) )
            {
LABEL_56:
              if ( (v131 & 1) != 0 )
                UnBCL::String::~String((UnBCL::String *)v265);
              v133 = GetLastError();
              v134 = CurrentIP();
              v135 = L"Yes";
              if ( !v130 )
                v135 = L"No";
              v136 = ConstructPartialMsgW(
                       0x4000000u,
                       "%hs: New OS BCD is Layercake: %s",
                       "CBootFilesPreserveCheckpoint::Rollback",
                       (const char *)v135);
              WdsSetupLogMessageW(
                v136,
                819200,
                L"D",
                0,
                368,
                L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                L"CBootFilesPreserveCheckpoint::Rollback",
                v134,
                v133,
                0,
                0);
              v137 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v253);
              v138 = SPGetVolumeNameFromPath(v137, 0, 0);
              UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v267, v138);
              if ( UnBCL::SmartPtr<UnBCL::String>::get_P(&v267) )
              {
                LODWORD(EndPtr) = 0;
                v139 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v267);
                v140 = UnBCL::String::get_CString(v139);
                IsProtectionActive = FveDetectIsProtectionActive(v140, &EndPtr);
                if ( IsProtectionActive >= 0 )
                {
                  v145 = (int)EndPtr;
                }
                else
                {
                  v142 = GetLastError();
                  v143 = CurrentIP();
                  v144 = ConstructPartialMsgW(
                           0x3000000u,
                           "%hs: Failed to check BitLocker protection status. hr = 0x%08X",
                           "CBootFilesPreserveCheckpoint::Rollback",
                           IsProtectionActive);
                  WdsSetupLogMessageW(
                    v144,
                    819200,
                    L"D",
                    0,
                    376,
                    L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                    L"CBootFilesPreserveCheckpoint::Rollback",
                    v143,
                    v142,
                    0,
                    0);
                  v145 = 0;
                  IsProtectionActive = 0;
                }
                v146 = GetLastError();
                v147 = CurrentIP();
                v148 = L"active";
                if ( !v145 )
                  v148 = L"inactive";
                v149 = ConstructPartialMsgW(
                         0x4000000u,
                         "%hs: BitLocker protection is %s",
                         "CBootFilesPreserveCheckpoint::Rollback",
                         (const char *)v148);
                WdsSetupLogMessageW(
                  v149,
                  819200,
                  L"D",
                  0,
                  381,
                  L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                  L"CBootFilesPreserveCheckpoint::Rollback",
                  v147,
                  v146,
                  0,
                  0);
                if ( !v145 )
                  goto LABEL_80;
                LODWORD(EndPtr) = 0;
                if ( OSRollbackUtils::CBCDManipulator::GetBoolElementData(
                       (OSRollbackUtils::CBCDManipulator *)v251,
                       &v266,
                       v150,
                       (int *)&EndPtr) )
                {
                  v151 = GetLastError();
                  v152 = CurrentIP();
                  v153 = ConstructPartialMsgW(
                           0x3000000u,
                           "%hs: Failed to query BCD override for New OS entry. hr = 0x%08X",
                           "CBootFilesPreserveCheckpoint::Rollback",
                           IsProtectionActive);
                  WdsSetupLogMessageW(
                    v153,
                    819200,
                    L"D",
                    0,
                    388,
                    L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                    L"CBootFilesPreserveCheckpoint::Rollback",
                    v152,
                    v151,
                    0,
                    0);
                  v154 = 0;
                }
                else
                {
                  v154 = (int)EndPtr;
                }
                v155 = GetLastError();
                v156 = CurrentIP();
                if ( !v154 )
                  v128 = L"False";
                v157 = ConstructPartialMsgW(
                         0x4000000u,
                         "%hs: New OS BCD override: %s.",
                         "CBootFilesPreserveCheckpoint::Rollback",
                         (const char *)v128);
                WdsSetupLogMessageW(
                  v157,
                  819200,
                  L"D",
                  0,
                  393,
                  L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                  L"CBootFilesPreserveCheckpoint::Rollback",
                  v156,
                  v155,
                  0,
                  0);
                if ( !v154 && !v130 )
                  goto LABEL_80;
                v158 = GetLastError();
                v159 = CurrentIP();
                v160 = ConstructPartialMsgW(
                         0x4000000u,
                         "%hs: New OS BCD is added to BitLocker validation info, delete it.",
                         "CBootFilesPreserveCheckpoint::Rollback");
                WdsSetupLogMessageW(
                  v160,
                  819200,
                  L"D",
                  0,
                  397,
                  L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                  L"CBootFilesPreserveCheckpoint::Rollback",
                  v159,
                  v158,
                  0,
                  0);
                v161 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v267);
                v162 = UnBCL::String::get_CString(v161);
                updated = FveDetectUpdateValidationInfo(v162, 2, &v266, v130);
                if ( updated >= 0 )
                  goto LABEL_80;
                v164 = GetLastError();
                v165 = CurrentIP();
                v166 = L"Layercake";
                if ( !v130 )
                  v166 = L"non-Layercake";
                v167 = ConstructPartialMsgW(
                         0x3000000u,
                         "%hs: Failed to delete new OS BCD from BitLocker validation info for %s. hr = 0x%08X",
                         "CBootFilesPreserveCheckpoint::Rollback",
                         (const char *)v166,
                         updated);
                v237 = v164;
                v233 = v165;
                v229 = 403;
              }
              else
              {
                v168 = GetLastError();
                v169 = CurrentIP();
                v170 = GetLastError();
                v171 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v253);
                v172 = (const char *)UnBCL::String::get_CString(v171);
                v167 = ConstructPartialMsgW(
                         0x2000000u,
                         "%hs: Failed to get the volume name for %s. Error: 0x%08X",
                         "CBootFilesPreserveCheckpoint::Rollback",
                         v172,
                         v170);
                v237 = v168;
                v233 = v169;
                v229 = 412;
              }
              WdsSetupLogMessageW(
                v167,
                819200,
                L"D",
                0,
                v229,
                L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                L"CBootFilesPreserveCheckpoint::Rollback",
                v233,
                v237,
                0,
                0);
LABEL_80:
              if ( !v252
                || (v173 = BcdDeleteObjectReferences(v252, &v266),
                    LODWORD(v241) = RtlNtStatusToDosError(v173),
                    (_DWORD)v241) )
              {
                v181 = GetLastError();
                v182 = CurrentIP();
                v180 = ConstructPartialMsgW(
                         0x2000000u,
                         "%hs: BCD failed to remove new OS boot entry references. Error: 0x%08X",
                         "CBootFilesPreserveCheckpoint::Rollback",
                         (_DWORD)v241);
                v238 = v181;
                v234 = v182;
                v230 = 432;
              }
              else
              {
                v174 = GetLastError();
                v175 = CurrentIP();
                v176 = ConstructPartialMsgW(
                         0x4000000u,
                         "%hs: We successfully removed new OS boot entry references",
                         "CBootFilesPreserveCheckpoint::Rollback");
                WdsSetupLogMessageW(
                  v176,
                  819200,
                  L"D",
                  0,
                  419,
                  L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                  L"CBootFilesPreserveCheckpoint::Rollback",
                  v175,
                  v174,
                  0,
                  0);
                v177 = OSRollbackUtils::CBCDManipulator::RemoveBootEntry(
                         (OSRollbackUtils::CBCDManipulator *)v251,
                         &v266);
                v178 = GetLastError();
                v179 = CurrentIP();
                if ( v177 )
                {
                  v180 = ConstructPartialMsgW(
                           0x2000000u,
                           "%hs: BCD failed to remove new OS boot entry. Error: 0x%08X",
                           "CBootFilesPreserveCheckpoint::Rollback",
                           v177);
                  v238 = v178;
                  v234 = v179;
                  v230 = 423;
                }
                else
                {
                  v180 = ConstructPartialMsgW(
                           0x4000000u,
                           "%hs: We successfully removed the new OS boot entry",
                           "CBootFilesPreserveCheckpoint::Rollback");
                  v238 = v178;
                  v234 = v179;
                  v230 = 427;
                }
              }
              WdsSetupLogMessageW(
                v180,
                819200,
                L"D",
                0,
                v230,
                L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                L"CBootFilesPreserveCheckpoint::Rollback",
                v234,
                v238,
                0,
                0);
              UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v267);
              UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v246);
LABEL_89:
              if ( GetFileAttributesW(lpFileName) != -1 )
              {
                v192 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v250);
                v193 = UnBCL::String::get_CString(v192);
                v194 = SPReadConfigValue(L"BootManager", L"Timeout", v193);
                UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v261, v194);
                if ( (unsigned __int8)UnBCL::operator!=(v261, v195) )
                {
                  EndPtr = 0;
                  v196 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v261);
                  v197 = UnBCL::String::get_CString(v196);
                  v198 = wcstoul(v197, &EndPtr, 10);
                  v199 = OSRollbackUtils::CBCDManipulator::SetTimeout((OSRollbackUtils::CBCDManipulator *)v251, v198);
                  v200 = GetLastError();
                  v201 = CurrentIP();
                  if ( v199 )
                  {
                    v202 = ConstructPartialMsgW(
                             0x2000000u,
                             "%hs: BCD failed to set timeout. Error: 0x%08X",
                             "CBootFilesPreserveCheckpoint::Rollback",
                             v199);
                    v239 = v200;
                    v235 = v201;
                    v231 = 455;
                  }
                  else
                  {
                    v202 = ConstructPartialMsgW(
                             0x4000000u,
                             "%hs: We successfully set back the original timeout of %d",
                             "CBootFilesPreserveCheckpoint::Rollback",
                             v198);
                    v239 = v200;
                    v235 = v201;
                    v231 = 459;
                  }
                }
                else
                {
                  v217 = GetLastError();
                  v218 = CurrentIP();
                  v219 = GetLastError();
                  v220 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v247);
                  v221 = (const char *)UnBCL::String::get_CString(v220);
                  v202 = ConstructPartialMsgW(
                           0x2000000u,
                           "%hs: Failed to read the boot manager timeout from file: %s. Error: 0x%08X",
                           "CBootFilesPreserveCheckpoint::Rollback",
                           v221,
                           v219);
                  v239 = v217;
                  v235 = v218;
                  v231 = 464;
                }
                WdsSetupLogMessageW(
                  v202,
                  819200,
                  L"D",
                  0,
                  v231,
                  L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                  L"CBootFilesPreserveCheckpoint::Rollback",
                  v235,
                  v239,
                  0,
                  0);
                SPCleanupBootEntries();
                OSRollbackService::CBootFilesRestoreCheckpoint::CaptureRollbackData(v245, lpFileName);
                UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v261);
                UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v249);
                UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v262);
                UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v254);
                OSRollbackUtils::CBCDManipulator::~CBCDManipulator((OSRollbackUtils::CBCDManipulator *)v251);
                UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v247);
                UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v250);
                UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v253);
                UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v255);
                v244 = 1;
                v260 = v264;
                throw (`CBootFilesPreserveCheckpoint::Rollback(ushort const *)'::`15'::CXXXXXHandledException **)&v260;
              }
              v212 = GetLastError();
              v213 = GetLastError();
              v214 = CurrentIP();
              v215 = ConstructPartialMsgW(
                       0x3000000u,
                       "Rollback folder %s does not exist. Error: 0x%08X",
                       (const char *)lpFileName,
                       v212);
              WdsSetupLogMessageW(
                v215,
                819200,
                L"D",
                0,
                446,
                L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                L"CBootFilesPreserveCheckpoint::Rollback",
                v214,
                v213,
                0,
                0);
              v216 = (OSRollbackService::CBootFilesRestoreCheckpoint *)UnBCL::Object::operator new(0x48u);
              v245 = v216;
              if ( v216 )
                v216 = RollbackException::RollbackException(v216, v212, L"Rollback folder not found");
              v259 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                       v216,
                       "void __cdecl CBootFilesPreserveCheckpoint::Rollback(const unsigned short *)");
              throw (RollbackException **)&v259;
            }
          }
          else
          {
            v131 = (char)EndPtr;
          }
          v130 = 0;
          goto LABEL_56;
        }
        v91 = BcdDeleteObjectReferences(v252, &v267);
        v90 = RtlNtStatusToDosError(v91);
        if ( v90 )
        {
          LODWORD(v241) = 87;
          goto LABEL_42;
        }
        v92 = GetLastError();
        v93 = CurrentIP();
        v94 = ConstructPartialMsgW(
                0x4000000u,
                "%hs: We successfully removed rollback boot entry references",
                "CBootFilesPreserveCheckpoint::Rollback");
        WdsSetupLogMessageW(
          v94,
          819200,
          L"D",
          0,
          323,
          L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
          L"CBootFilesPreserveCheckpoint::Rollback",
          v93,
          v92,
          0,
          0);
        v95 = OSRollbackUtils::CBCDManipulator::RemoveBootEntry((OSRollbackUtils::CBCDManipulator *)v251, &v267);
        v96 = GetLastError();
        v97 = CurrentIP();
        if ( v95 )
        {
          v98 = ConstructPartialMsgW(
                  0x2000000u,
                  "%hs: BCD failed to remove rollback boot entry. Error: 0x%08X",
                  "CBootFilesPreserveCheckpoint::Rollback",
                  v95);
          v236 = v96;
          v232 = v97;
          v228 = 327;
        }
        else
        {
          v98 = ConstructPartialMsgW(
                  0x4000000u,
                  "%hs: We successfully removed the rollback boot entry",
                  "CBootFilesPreserveCheckpoint::Rollback");
          v236 = v96;
          v232 = v97;
          v228 = 331;
        }
      }
    }
    else
    {
      v104 = GetLastError();
      v105 = CurrentIP();
      v106 = GetLastError();
      v107 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v247);
      v108 = (const char *)UnBCL::String::get_CString(v107);
      v98 = ConstructPartialMsgW(
              0x2000000u,
              "%hs: Failed to read the rollback GUID from file: %s. Error: 0x%08X",
              "CBootFilesPreserveCheckpoint::Rollback",
              v108,
              v106);
      v236 = v104;
      v232 = v105;
      v228 = 346;
    }
    WdsSetupLogMessageW(
      v98,
      819200,
      L"D",
      0,
      v228,
      L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
      L"CBootFilesPreserveCheckpoint::Rollback",
      v232,
      v236,
      0,
      0);
    LODWORD(v241) = 87;
    goto LABEL_46;
  }
  catch ( UnBCL::Exception * )
  {
    if ( v242 )
    {
      v222 = GetLastError();
      v223 = CurrentIP();
      v224 = ConstructPartialMsgW(0x4000000u, "%hs: disable backup privilege", "CBootFilesPreserveCheckpoint::Rollback");
      WdsSetupLogMessageW(
        v224,
        819200,
        L"D",
        0,
        479,
        L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
        L"CBootFilesPreserveCheckpoint::Rollback",
        v223,
        v222,
        0,
        0);
      SPEnablePrivilege(L"SeBackupPrivilege", 0, 0);
    }
    if ( v243 )
    {
      v225 = GetLastError();
      v226 = CurrentIP();
      v227 = ConstructPartialMsgW(
               0x4000000u,
               "%hs: disable restore privilege",
               "CBootFilesPreserveCheckpoint::Rollback");
      WdsSetupLogMessageW(
        v227,
        819200,
        L"D",
        0,
        484,
        L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
        L"CBootFilesPreserveCheckpoint::Rollback",
        v226,
        v225,
        0,
        0);
      SPEnablePrivilege(L"SeRestorePrivilege", 0, 0);
    }
    if ( !v244 )
      throw;
    UnBCL::Exception::~Exception((UnBCL::Exception *)v264);
  }
}

```

## disassembly

```asm
0x1802a3700  mov     rax, rsp
0x1802a3703  push    rdi
0x1802a3704  push    r12
0x1802a3706  push    r13
0x1802a3708  push    r14
0x1802a370a  push    r15
0x1802a370c  sub     rsp, 2B0h
0x1802a3713  mov     qword ptr [rax-158h], 0FFFFFFFFFFFFFFFEh
0x1802a371e  mov     [rax+18h], rbx
0x1802a3722  mov     [rax+20h], rsi
0x1802a3726  mov     rax, cs:__security_cookie
0x1802a372d  xor     rax, rsp
0x1802a3730  mov     [rsp+2D8h+var_38], rax
0x1802a3738  mov     r13, rdx
0x1802a373b  mov     [rsp+2D8h+lpFileName], rdx
0x1802a3743  mov     [rsp+2D8h+var_258], rcx
0x1802a374b  xor     r14d, r14d
0x1802a374e  mov     dword ptr [rsp+2D8h+EndPtr], r14d
0x1802a3753  test    rdx, rdx
0x1802a3756  jz      loc_1802A51DD
0x1802a375c  mov     rcx, r13; lpFileName
0x1802a375f  call    cs:__imp_GetFileAttributesW
0x1802a3765  cmp     eax, 0FFFFFFFFh
0x1802a3768  jz      loc_1802A5241
0x1802a376e  mov     [rsp+2D8h+var_268], r14d
0x1802a3773  mov     [rsp+2D8h+var_264], r14d
0x1802a3778  mov     [rsp+2D8h+var_260], r14d
0x1802a377d  lea     rcx, [rsp+2D8h+var_150]
0x1802a3785  call    cs:__imp_??0Exception@UnBCL@@QEAA@XZ; UnBCL::Exception::Exception(void)
0x1802a378b  lea     rax, ??_7CXXXXXHandledException@?P@??Rollback@CBootFilesPreserveCheckpoint@@UEAAXPEBG@Z@6B@; const `CBootFilesPreserveCheckpoint::Rollback(ushort const *)'::`15'::CXXXXXHandledException::`vftable'
0x1802a3792  mov     [rsp+2D8h+var_150], rax
0x1802a379a  lea     r8, [rsp+2D8h+var_268]; int *
0x1802a379f  mov     ebx, 1
0x1802a37a4  mov     edx, ebx; int
0x1802a37a6  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x1802a37ad  call    ?SPEnablePrivilege@@YAHPEBGHPEAH@Z; SPEnablePrivilege(ushort const *,int,int *)
0x1802a37b2  lea     r8, [rsp+2D8h+var_264]; int *
0x1802a37b7  mov     edx, ebx; int
0x1802a37b9  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x1802a37c0  call    ?SPEnablePrivilege@@YAHPEBGHPEAH@Z; SPEnablePrivilege(ushort const *,int,int *)
0x1802a37c5  call    cs:__imp_GetLastError
0x1802a37cb  mov     edi, eax
0x1802a37cd  call    cs:__imp_CurrentIP
0x1802a37d3  mov     rbx, rax
0x1802a37d6  lea     rdx, aCbootfilespres; "CBootFilesPreserveCheckpoint::Rollback:"...
0x1802a37dd  mov     ecx, 4000000h; unsigned int
0x1802a37e2  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1802a37e7  mov     [rsp+2D8h+var_288], r14d
0x1802a37ec  mov     [rsp+2D8h+var_290], r14
0x1802a37f1  mov     [rsp+2D8h+var_298], edi
0x1802a37f5  mov     [rsp+2D8h+var_2A0], rbx
0x1802a37fa  lea     r15, aCbootfilespres_0; "CBootFilesPreserveCheckpoint::Rollback"
0x1802a3801  mov     [rsp+2D8h+var_2A8], r15
0x1802a3806  lea     rcx, aBaseNtsetupSet_64; "base\\ntsetup\\setupplatform\\lib\\roll"...
0x1802a380d  mov     [rsp+2D8h+var_2B0], rcx
0x1802a3812  mov     [rsp+2D8h+var_2B8], 0C8h
0x1802a381a  xor     r9d, r9d
0x1802a381d  lea     r14, aD_0; "D"
0x1802a3824  mov     r8, r14
0x1802a3827  mov     r12d, 0C8000h
0x1802a382d  mov     edx, r12d
0x1802a3830  mov     rcx, rax
0x1802a3833  call    cs:__imp_WdsSetupLogMessageW
0x1802a3839  call    ?pGetPlatformDir@@YAPEAVString@UnBCL@@XZ; pGetPlatformDir(void)
0x1802a383e  mov     rdx, rax
0x1802a3841  lea     rcx, [rsp+2D8h+var_1B0]
0x1802a3849  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802a384f  nop
0x1802a3850  lea     rcx, [rsp+2D8h+var_1B0]
0x1802a3858  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1802a385e  test    rax, rax
0x1802a3861  jz      loc_1802A5316
0x1802a3867  lea     rcx, [rsp+2D8h+var_1B0]
0x1802a386f  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802a3875  mov     rcx, rax
0x1802a3878  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802a387e  movzx   edx, word ptr [rax]
0x1802a3881  lea     r9, aSources_1; "Sources"
0x1802a3888  lea     r8, aWindowsBt_1; "$WINDOWS.~BT"
0x1802a388f  lea     rcx, aCSS; "%c:\\%s\\%s"
0x1802a3896  call    cs:__imp_?Format@String@UnBCL@@SAPEAV12@PEBGZZ; UnBCL::String::Format(ushort const *,...)
0x1802a389c  mov     rdx, rax
0x1802a389f  lea     rcx, [rsp+2D8h+var_1D0]
0x1802a38a7  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802a38ad  nop
0x1802a38ae  lea     rdx, aSetupplatformI; "SetupPlatform.ini"
0x1802a38b5  lea     rcx, [rsp+2D8h+var_248]
0x1802a38bd  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1802a38c3  mov     rbx, rax
0x1802a38c6  lea     rcx, [rsp+2D8h+var_1D0]
0x1802a38ce  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1802a38d4  mov     rdx, rbx
0x1802a38d7  mov     rcx, rax
0x1802a38da  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1802a38e0  mov     rdx, rax
0x1802a38e3  lea     rcx, [rsp+2D8h+var_200]
0x1802a38eb  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802a38f1  nop
0x1802a38f2  lea     rcx, [rsp+2D8h+var_248]
0x1802a38fa  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1802a3900  lea     rdx, aRollbackinfoIn; "rollbackinfo.ini"
0x1802a3907  lea     rcx, [rsp+2D8h+var_F8]
0x1802a390f  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1802a3915  mov     rbx, rax
0x1802a3918  mov     rdx, r13
0x1802a391b  lea     rcx, [rsp+2D8h+var_D8]
0x1802a3923  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1802a3929  nop
0x1802a392a  mov     rdx, rbx
0x1802a392d  mov     rcx, rax
0x1802a3930  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1802a3936  mov     rdx, rax
0x1802a3939  lea     rcx, [rsp+2D8h+var_228]
0x1802a3941  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802a3947  nop
0x1802a3948  lea     rcx, [rsp+2D8h+var_D8]
0x1802a3950  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1802a3956  nop
0x1802a3957  lea     rcx, [rsp+2D8h+var_F8]
0x1802a395f  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1802a3965  lea     rcx, [rsp+2D8h+var_1F0]; this
0x1802a396d  call    ??0CBCDManipulator@OSRollbackUtils@@QEAA@XZ; OSRollbackUtils::CBCDManipulator::CBCDManipulator(void)
0x1802a3972  nop
0x1802a3973  xor     edx, edx; unsigned __int16 *
0x1802a3975  lea     rcx, [rsp+2D8h+var_1F0]; this
0x1802a397d  call    ?Open@CBCDManipulator@OSRollbackUtils@@QEAAKPEBG@Z; OSRollbackUtils::CBCDManipulator::Open(ushort const *)
0x1802a3982  mov     esi, eax
0x1802a3984  test    eax, eax
0x1802a3986  jz      loc_1802A3A5B
0x1802a398c  call    cs:__imp_GetLastError
0x1802a3992  mov     edi, eax
0x1802a3994  call    cs:__imp_CurrentIP
0x1802a399a  mov     rbx, rax
0x1802a399d  mov     r9d, esi
0x1802a39a0  lea     r8, aCbootfilespres_2; "CBootFilesPreserveCheckpoint::Rollback"
0x1802a39a7  lea     rdx, aHsBcdOpenFaile_0; "%hs: BCD Open failed. Error: 0x%08X"
0x1802a39ae  mov     ecx, 3000000h; unsigned int
0x1802a39b3  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1802a39b8  mov     [rsp+2D8h+var_288], 0
0x1802a39c0  mov     [rsp+2D8h+var_290], 0
0x1802a39c9  mov     [rsp+2D8h+var_298], edi
0x1802a39cd  mov     [rsp+2D8h+var_2A0], rbx
0x1802a39d2  mov     [rsp+2D8h+var_2A8], r15
0x1802a39d7  lea     rcx, aBaseNtsetupSet_64; "base\\ntsetup\\setupplatform\\lib\\roll"...
0x1802a39de  mov     [rsp+2D8h+var_2B0], rcx
0x1802a39e3  mov     [rsp+2D8h+var_2B8], 0DCh
0x1802a39eb  xor     r9d, r9d
0x1802a39ee  mov     r8, r14
0x1802a39f1  mov     edx, r12d
0x1802a39f4  mov     rcx, rax
0x1802a39f7  call    cs:__imp_WdsSetupLogMessageW
0x1802a39fd  nop
0x1802a39fe  lea     rcx, [rsp+2D8h+var_1F0]; this
0x1802a3a06  call    ??1CBCDManipulator@OSRollbackUtils@@UEAA@XZ; OSRollbackUtils::CBCDManipulator::~CBCDManipulator(void)
0x1802a3a0b  nop
0x1802a3a0c  lea     rcx, [rsp+2D8h+var_228]
0x1802a3a14  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802a3a1a  nop
0x1802a3a1b  lea     rcx, [rsp+2D8h+var_200]
0x1802a3a23  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802a3a29  nop
0x1802a3a2a  lea     rcx, [rsp+2D8h+var_1D0]
0x1802a3a32  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802a3a38  nop
0x1802a3a39  lea     rcx, [rsp+2D8h+var_1B0]
0x1802a3a41  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802a3a47  nop
0x1802a3a48  lea     rcx, [rsp+2D8h+var_150]
0x1802a3a50  call    cs:__imp_??1Exception@UnBCL@@UEAA@XZ; UnBCL::Exception::~Exception(void)
0x1802a3a56  jmp     loc_1802A51B0
0x1802a3a5b  lea     rcx, [rsp+2D8h+var_228]
0x1802a3a63  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802a3a69  mov     rcx, rax
0x1802a3a6c  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802a3a72  mov     r8, rax; lpFileName
0x1802a3a75  lea     rdx, aDownleveldefau; "DownlevelDefault"
0x1802a3a7c  lea     rcx, aBootentries; "BootEntries"
0x1802a3a83  call    ?SPReadConfigValue@@YAPEAVString@UnBCL@@PEBG00@Z; SPReadConfigValue(ushort const *,ushort const *,ushort const *)
0x1802a3a88  mov     rdx, rax
0x1802a3a8b  lea     rcx, [rsp+2D8h+var_1C0]
0x1802a3a93  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802a3a99  nop
0x1802a3a9a  lea     rcx, [rsp+2D8h+var_1C0]
0x1802a3aa2  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1802a3aa8  test    rax, rax
0x1802a3aab  jz      loc_1802A3FA2
0x1802a3ab1  xorps   xmm0, xmm0
0x1802a3ab4  movups  xmmword ptr [rsp+2D8h+var_F8.Data1], xmm0
0x1802a3abc  lea     rcx, [rsp+2D8h+var_1C0]
0x1802a3ac4  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802a3aca  mov     rcx, rax
0x1802a3acd  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802a3ad3  lea     rdx, [rsp+2D8h+var_F8]; struct _GUID *
0x1802a3adb  mov     rcx, rax; unsigned __int16 *
0x1802a3ade  call    ?SPGuidFromString@@YAJPEBGPEAU_GUID@@@Z; SPGuidFromString(ushort const *,_GUID *)
0x1802a3ae3  mov     esi, eax
0x1802a3ae5  test    eax, eax
0x1802a3ae7  jnz     loc_1802A3F3B
0x1802a3aed  call    cs:__imp_GetLastError
0x1802a3af3  mov     ebx, eax
0x1802a3af5  call    cs:__imp_CurrentIP
0x1802a3afb  mov     rdi, rax
0x1802a3afe  lea     rcx, [rsp+2D8h+var_1C0]
0x1802a3b06  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802a3b0c  mov     rcx, rax
0x1802a3b0f  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802a3b15  mov     r9, rax
0x1802a3b18  lea     r13, aCbootfilespres_2; "CBootFilesPreserveCheckpoint::Rollback"
0x1802a3b1f  mov     r8, r13
0x1802a3b22  lea     rdx, aHsDefaultBootE; "%hs: Default boot entry is: %s"
0x1802a3b29  mov     ecx, 4000000h; unsigned int
0x1802a3b2e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1802a3b33  mov     [rsp+2D8h+var_288], esi
0x1802a3b37  mov     [rsp+2D8h+var_290], 0
0x1802a3b40  mov     [rsp+2D8h+var_298], ebx
0x1802a3b44  mov     [rsp+2D8h+var_2A0], rdi
0x1802a3b49  mov     [rsp+2D8h+var_2A8], r15
0x1802a3b4e  lea     rsi, aBaseNtsetupSet_64; "base\\ntsetup\\setupplatform\\lib\\roll"...
0x1802a3b55  mov     [rsp+2D8h+var_2B0], rsi
0x1802a3b5a  mov     [rsp+2D8h+var_2B8], 0E8h
0x1802a3b62  xor     r9d, r9d
0x1802a3b65  mov     r8, r14
0x1802a3b68  mov     edx, r12d
0x1802a3b6b  mov     rcx, rax
0x1802a3b6e  call    cs:__imp_WdsSetupLogMessageW
0x1802a3b74  lea     rdx, [rsp+2D8h+var_F8]; struct _GUID *
0x1802a3b7c  lea     rcx, [rsp+2D8h+var_1F0]; this
0x1802a3b84  call    ?DoesBootEntryExists@CBCDManipulator@OSRollbackUtils@@QEAAHAEBU_GUID@@@Z; OSRollbackUtils::CBCDManipulator::DoesBootEntryExists(_GUID const &)
0x1802a3b89  test    eax, eax
0x1802a3b8b  jz      loc_1802A3EE5
0x1802a3b91  lea     rdx, [rsp+2D8h+var_F8]; struct _GUID *
0x1802a3b99  lea     rcx, [rsp+2D8h+var_1F0]; this
0x1802a3ba1  call    ?SetDefaultBootEntry@CBCDManipulator@OSRollbackUtils@@QEAAKAEBU_GUID@@@Z; OSRollbackUtils::CBCDManipulator::SetDefaultBootEntry(_GUID const &)
0x1802a3ba6  mov     esi, eax
0x1802a3ba8  test    eax, eax
0x1802a3baa  jz      short loc_1802A3C0C
0x1802a3bac  call    cs:__imp_GetLastError
0x1802a3bb2  mov     edi, eax
0x1802a3bb4  call    cs:__imp_CurrentIP
0x1802a3bba  mov     rbx, rax
0x1802a3bbd  mov     r9d, esi
0x1802a3bc0  mov     r8, r13
0x1802a3bc3  lea     rdx, aHsBcdFailedToS_8; "%hs: BCD failed to set default boot ent"...
0x1802a3bca  mov     ecx, 2000000h; unsigned int
0x1802a3bcf  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1802a3bd4  mov     [rsp+2D8h+var_288], 0
0x1802a3bdc  mov     [rsp+2D8h+var_290], 0
0x1802a3be5  mov     [rsp+2D8h+var_298], edi
0x1802a3be9  mov     [rsp+2D8h+var_2A0], rbx
0x1802a3bee  mov     [rsp+2D8h+var_2A8], r15
0x1802a3bf3  lea     rsi, aBaseNtsetupSet_64; "base\\ntsetup\\setupplatform\\lib\\roll"...
0x1802a3bfa  mov     [rsp+2D8h+var_2B0], rsi
0x1802a3bff  mov     [rsp+2D8h+var_2B8], 0EFh
0x1802a3c07  jmp     loc_1802A4027
0x1802a3c0c  call    cs:__imp_GetLastError
0x1802a3c12  mov     edi, eax
0x1802a3c14  call    cs:__imp_CurrentIP
0x1802a3c1a  mov     rbx, rax
0x1802a3c1d  mov     r8, r13
0x1802a3c20  lea     rdx, aHsWeSuccessful_2; "%hs: We successfully set back the defau"...
0x1802a3c27  mov     ecx, 4000000h; unsigned int
0x1802a3c2c  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1802a3c31  mov     [rsp+2D8h+var_288], 0
0x1802a3c39  mov     [rsp+2D8h+var_290], 0
0x1802a3c42  mov     [rsp+2D8h+var_298], edi
0x1802a3c46  mov     [rsp+2D8h+var_2A0], rbx
0x1802a3c4b  mov     [rsp+2D8h+var_2A8], r15
0x1802a3c50  lea     rcx, aBaseNtsetupSet_64; "base\\ntsetup\\setupplatform\\lib\\roll"...
0x1802a3c57  mov     [rsp+2D8h+var_2B0], rcx
0x1802a3c5c  mov     [rsp+2D8h+var_2B8], 0F3h
0x1802a3c64  xor     r9d, r9d
0x1802a3c67  mov     r8, r14
0x1802a3c6a  mov     edx, r12d
0x1802a3c6d  mov     rcx, rax
0x1802a3c70  call    cs:__imp_WdsSetupLogMessageW
0x1802a3c76  lea     rcx, [rsp+2D8h+var_B8]
0x1802a3c7e  call    ??0?$ArrayList@U_GUID@@@UnBCL@@QEAA@XZ; UnBCL::ArrayList<_GUID>::ArrayList<_GUID>(void)
0x1802a3c83  nop
0x1802a3c84  lea     r9, [rsp+2D8h+var_B8]
0x1802a3c8c  lea     rcx, [rsp+2D8h+var_1F0]
0x1802a3c94  call    ?GetIdentityList@CBCDManipulator@OSRollbackUtils@@QEAAKAEBU_GUID@@KAEAV?$ArrayList@U_GUID@@@UnBCL@@@Z; OSRollbackUtils::CBCDManipulator::GetIdentityList(_GUID const &,ulong,UnBCL::ArrayList<_GUID> &)
0x1802a3c99  mov     esi, eax
0x1802a3c9b  test    eax, eax
0x1802a3c9d  jnz     loc_1802A3E57
0x1802a3ca3  mov     ecx, 80h
0x1802a3ca8  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1802a3cae  mov     [rsp+2D8h+var_270], rax
0x1802a3cb3  test    rax, rax
0x1802a3cb6  jz      short loc_1802A3CC5
0x1802a3cb8  mov     rcx, rax
0x1802a3cbb  call    ??0?$ArrayList@U_GUID@@@UnBCL@@QEAA@XZ; UnBCL::ArrayList<_GUID>::ArrayList<_GUID>(void)
0x1802a3cc0  mov     rdi, rax
0x1802a3cc3  jmp     short loc_1802A3CC7
0x1802a3cc5  xor     edi, edi
0x1802a3cc7  mov     rax, [rdi+8]
0x1802a3ccb  movsxd  rcx, dword ptr [rax+10h]
0x1802a3ccf  add     rcx, 8
0x1802a3cd3  add     rcx, rdi
0x1802a3cd6  movaps  xmm0, xmmword ptr [rsp+2D8h+var_F8.Data1]
0x1802a3cde  movdqa  [rsp+2D8h+var_248], xmm0
  ... truncated ...
```
