# CSetupPlatformPrivate::RollbackOnlineCommon(void)

- ea: `0x180267008`
- end: `0x180269206`
- name: `?RollbackOnlineCommon@CSetupPlatformPrivate@@IEAAJXZ`
- size: `8702`
- prototype: `__int64 __fastcall(CSetupPlatformPrivate *__hidden this)`
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18026920c`
- `0x180269adc`

## callees

- `0x180013804`
- `0x180035de8`
- `0x18003d0e8`
- `0x180044810`
- `0x180057dec`
- `0x180267008`
- `0x18026aa40`
- `0x18026b588`
- `0x1802c6944`
- `0x1802dad70`
- `0x1802dff40`
- `0x1802e1864`
- `0x1802e2078`
- `0x1802fa49c`
- `0x18035219c`
- `0x180352658`
- `0x180352abc`
- `0x180372ba4`
- `0x18040c590`
- `0x18042a280`
- `0x1804bbfa0`
- `0x180509010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180267f1b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180267f1b`
- `ntdll!RtlFreeUnicodeString` at `0x180268a04`
- `ntdll!RtlFreeUnicodeString` at `0x180268a04`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1802689c4`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1802689c4`
- `KERNEL32!GetProcessHeap` at `0x180268c5b`
- `KERNEL32!GetProcessHeap` at `0x180268c5b`
- `KERNEL32!HeapFree` at `0x180268c69`
- `KERNEL32!HeapFree` at `0x180268c69`
- `KERNEL32!GetLastError` at `0x180267130`
- `KERNEL32!GetLastError` at `0x180267146`
- `KERNEL32!GetLastError` at `0x18026716a`
- `KERNEL32!GetLastError` at `0x180267236`
- `KERNEL32!GetLastError` at `0x180267324`
- `KERNEL32!GetLastError` at `0x180267335`
- `KERNEL32!GetLastError` at `0x18026738b`
- `KERNEL32!GetLastError` at `0x18026764f`
- `KERNEL32!GetLastError` at `0x18026772e`
- `KERNEL32!GetLastError` at `0x180267740`
- `KERNEL32!GetLastError` at `0x18026782f`
- `KERNEL32!GetLastError` at `0x18026785a`
- `KERNEL32!GetLastError` at `0x1802678b4`
- `KERNEL32!GetLastError` at `0x1802678df`
- `KERNEL32!GetLastError` at `0x1802679a1`
- `KERNEL32!GetLastError` at `0x180267a55`
- `KERNEL32!GetLastError` at `0x180267b37`
- `KERNEL32!GetLastError` at `0x180267c14`
- `KERNEL32!GetLastError` at `0x180267d0f`
- `KERNEL32!GetLastError` at `0x180267dff`
- `KERNEL32!GetLastError` at `0x180267e90`
- `KERNEL32!GetLastError` at `0x18026812e`
- `KERNEL32!GetLastError` at `0x1802681d6`
- `KERNEL32!GetLastError` at `0x18026826b`
- `KERNEL32!GetLastError` at `0x180268300`
- `KERNEL32!GetLastError` at `0x180268395`
- `KERNEL32!GetLastError` at `0x18026842a`
- `KERNEL32!GetLastError` at `0x1802684bf`
- `KERNEL32!GetLastError` at `0x180268622`
- `KERNEL32!GetLastError` at `0x18026868a`
- `KERNEL32!GetLastError` at `0x1802686eb`
- `KERNEL32!GetLastError` at `0x180268793`
- `KERNEL32!GetLastError` at `0x180268a32`
- `KERNEL32!GetLastError` at `0x180268b55`
- `KERNEL32!GetLastError` at `0x180268bdd`
- `KERNEL32!GetLastError` at `0x180268c71`
- `KERNEL32!GetLastError` at `0x18026906f`
- `KERNEL32!GetLastError` at `0x180267130`
- `KERNEL32!GetLastError` at `0x180267146`
- `KERNEL32!GetLastError` at `0x18026716a`
- `KERNEL32!GetLastError` at `0x180267236`
- `KERNEL32!GetLastError` at `0x180267324`
- `KERNEL32!GetLastError` at `0x180267335`
- `KERNEL32!GetLastError` at `0x18026738b`
- `KERNEL32!GetLastError` at `0x18026764f`
- `KERNEL32!GetLastError` at `0x18026772e`
- `KERNEL32!GetLastError` at `0x180267740`
- `KERNEL32!GetLastError` at `0x18026782f`
- `KERNEL32!GetLastError` at `0x18026785a`
- `KERNEL32!GetLastError` at `0x1802678b4`
- `KERNEL32!GetLastError` at `0x1802678df`
- `KERNEL32!GetLastError` at `0x1802679a1`
- `KERNEL32!GetLastError` at `0x180267a55`
- `KERNEL32!GetLastError` at `0x180267b37`
- `KERNEL32!GetLastError` at `0x180267c14`
- `KERNEL32!GetLastError` at `0x180267d0f`
- `KERNEL32!GetLastError` at `0x180267dff`
- `KERNEL32!GetLastError` at `0x180267e90`
- `KERNEL32!GetLastError` at `0x18026812e`
- `KERNEL32!GetLastError` at `0x1802681d6`
- `KERNEL32!GetLastError` at `0x18026826b`
- `KERNEL32!GetLastError` at `0x180268300`
- `KERNEL32!GetLastError` at `0x180268395`
- `KERNEL32!GetLastError` at `0x18026842a`
- `KERNEL32!GetLastError` at `0x1802684bf`
- `KERNEL32!GetLastError` at `0x180268622`
- `KERNEL32!GetLastError` at `0x18026868a`
- `KERNEL32!GetLastError` at `0x1802686eb`
- `KERNEL32!GetLastError` at `0x180268793`
- `KERNEL32!GetLastError` at `0x180268a32`
- `KERNEL32!GetLastError` at `0x180268b55`
- `KERNEL32!GetLastError` at `0x180268bdd`
- `KERNEL32!GetLastError` at `0x180268c71`
- `KERNEL32!GetLastError` at `0x18026906f`
- `KERNEL32!SetFileAttributesW` at `0x180267821`
- `KERNEL32!SetFileAttributesW` at `0x180267821`
- `KERNEL32!GetFileAttributesW` at `0x1802677ed`
- `KERNEL32!GetFileAttributesW` at `0x1802677ed`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@PEBGH@Z` at `0x180268d23`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@PEBGH@Z` at `0x180268d3f`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@PEBGH@Z` at `0x180268d5b`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@PEBGH@Z` at `0x180268d77`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@PEBGH@Z` at `0x180268d23`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@PEBGH@Z` at `0x180268d3f`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@PEBGH@Z` at `0x180268d5b`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@PEBGH@Z` at `0x180268d77`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x180267ad9`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x180267d93`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x180267ad9`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x180267d93`
- `unbcl!?Exists@File@UnBCL@@SAHPEBVString@2@@Z` at `0x18026755b`
- `unbcl!?Exists@File@UnBCL@@SAHPEBVString@2@@Z` at `0x18026896d`
- `unbcl!?Exists@File@UnBCL@@SAHPEBVString@2@@Z` at `0x18026755b`
- `unbcl!?Exists@File@UnBCL@@SAHPEBVString@2@@Z` at `0x18026896d`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x180268d8f`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x180268d8f`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x18026742d`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x180268906`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x180268963`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x18026742d`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x180268906`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x180268963`
- `unbcl!?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z` at `0x180267595`
- `unbcl!?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z` at `0x180267595`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x180267200`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x18026757a`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x180267200`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x18026757a`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180267088`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802670da`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802674b8`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180267504`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180267629`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180267f54`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180268913`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18026902a`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180267088`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802670da`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802674b8`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180267504`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180267629`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180267f54`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180268913`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18026902a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026707c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802670ce`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802671f7`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180267211`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026721d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802672e4`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802672f2`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180267421`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802674ac`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802674f8`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180267552`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180267571`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026758c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802675ee`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026761d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802676eb`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802676f9`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180267a46`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180267b1b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180267cbe`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180267de3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180267f48`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026814b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802681f3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180268288`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026831d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802683b2`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180268447`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802684dc`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026858a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026859b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802685ac`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802685bd`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802687fc`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026880d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026881e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802688f5`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180268952`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180268d0d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180268dd3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180268f91`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026901e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026707c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802670ce`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802671f7`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180267211`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026721d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802672e4`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802672f2`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180267421`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802674ac`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802674f8`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180267552`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180267571`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026758c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802675ee`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026761d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802676eb`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802676f9`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180267a46`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180267b1b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180267cbe`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180267de3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180267f48`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026814b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802681f3`

## string_xrefs

- `0x180267053`: `Rollback`
- `0x180267f21`: `rollbackinfo.ini`
- `0x180268109`: `Comment`
- `0x1802680d1`: `Uninstall`
- `0x180268110`: `Uninstall`
- `0x180268e24`: `SP_ROLLBACK_INFO`
- `0x180268e76`: `SP_ROLLBACK_INFO`
- `0x180268eb4`: `SP_ROLLBACK_INFO`
- `0x180268ef5`: `SP_ROLLBACK_INFO`
- `0x180268f36`: `SP_ROLLBACK_INFO`
- `0x180268fd6`: `SP_ROLLBACK_INFO`
- `0x1802671ab`: `base\ntsetup\setupplatform\lib\private\rollback.cpp`
- `0x1802672a9`: `base\ntsetup\setupplatform\lib\private\rollback.cpp`
- `0x1802676bd`: `base\ntsetup\setupplatform\lib\private\rollback.cpp`
- `0x1802677ba`: `base\ntsetup\setupplatform\lib\private\rollback.cpp`
- `0x18026789e`: `base\ntsetup\setupplatform\lib\private\rollback.cpp`
- `0x18026791d`: `base\ntsetup\setupplatform\lib\private\rollback.cpp`
- `0x18026795e`: `base\ntsetup\setupplatform\lib\private\rollback.cpp`
- `0x180268664`: `base\ntsetup\setupplatform\lib\private\rollback.cpp`
- `0x1802673b6`: `Move was successful, resetting the rollback dir to %s`
- `0x18026733e`: `Error while executing the move/copy/merge. Error: 0x%08X`
- `0x18026719f`: `CSetupPlatformPrivate::RollbackOnlineCommon`
- `0x18026729d`: `CSetupPlatformPrivate::RollbackOnlineCommon`
- `0x180267478`: `CSetupPlatformPrivate::RollbackOnlineCommon`
- `0x1802675be`: `CSetupPlatformPrivate::RollbackOnlineCommon`
- `0x1802677ae`: `CSetupPlatformPrivate::RollbackOnlineCommon`
- `0x180267279`: `Attempting to move/copy/merge %s to %s`
- `0x18026717b`: `CSetupPlatformPrivate::RollbackOnlineCommon: Failed to execute rollback`
- `0x180267b4d`: `CSetupPlatformPrivate::RollbackOnlineCommon: Failed to decode safe OS hash, cannot remove it: 0x%08x`
- `0x180267c2a`: `CSetupPlatformPrivate::RollbackOnlineCommon: Failed to delete safe OS hash: 0x%08x`
- `0x180267782`: `CSetupPlatformPrivate::RollbackOnlineCommon`
- `0x18026786e`: `CSetupPlatformPrivate::RollbackOnlineCommon`
- `0x1802678ed`: `CSetupPlatformPrivate::RollbackOnlineCommon`
- `0x180267789`: `%hs: MoveFile(from "%s" to "%s") failed. Error: 0x%08X`
- `0x1802683dc`: `Current uninstall reason : %s`
- `0x180267ea6`: `CSetupPlatformPrivate::RollbackOnlineCommon: Failed to delete new WinRE hash: 0x%08x`
- `0x180267e15`: `CSetupPlatformPrivate::RollbackOnlineCommon: Failed to decode new WinRE hash, cannot remove it: 0x%08x`
- `0x180268471`: `Current uninstall comment: %s`
- `0x180268c05`: `Failed to convert bootstat.dat file path: %s to NT path`
- `0x180268e1d`: `RollbackDumpType`
- `0x180268b1d`: `RollbackBsdSummary`
- `0x180268a5a`: `Attempt to get BsdSummarize Diagnostic Information for bootstat file: %s`
- `0x18026908c`: `Rollback-Online-Common completed successfully.`
- `0x180268fcf`: `RollbackInitiatedBugCheckBinaryInfo`
- `0x1802690c4`: `Rollback-Online-Common completed with error: 0x%08X`
- `0x180268ead`: `RollbackInitiatedOperation`
- `0x180268e6f`: `RollbackInitiatedPhase`
- `0x180268f2f`: `RollbackInitiatedBugCheckCode`
- `0x180268eee`: `RollbackInitiatedOperationHR`

## pseudocode

```c
// Hidden C++ exception states: #wind=35
__int64 __fastcall CSetupPlatformPrivate::RollbackOnlineCommon(CSetupPlatformPrivate *this)
{
  const struct UnBCL::String *v2; // rbx
  const struct UnBCL::String *P; // rax
  struct UnBCL::String *v4; // rax
  const struct UnBCL::String *v5; // rbx
  const struct UnBCL::String *v6; // rax
  struct UnBCL::String *v7; // rax
  __int64 v8; // rax
  signed int v9; // eax
  bool v10; // sf
  signed int v11; // eax
  DWORD v12; // edi
  __int64 v13; // rbx
  struct tagLOG_PARTIAL_MSG *v14; // rax
  char *v15; // r14
  const struct UnBCL::String *v16; // rax
  struct UnBCL::String *v17; // rbx
  struct UnBCL::String *v18; // rax
  DWORD LastError; // esi
  __int64 v20; // rdi
  UnBCL::String *v21; // rax
  const char *CString; // rbx
  UnBCL::String *v23; // rax
  const char *v24; // rax
  struct tagLOG_PARTIAL_MSG *v25; // rax
  int v26; // eax
  DWORD v27; // edi
  __int64 v28; // rbx
  DWORD v29; // eax
  struct tagLOG_PARTIAL_MSG *v30; // rax
  DWORD v31; // edi
  __int64 v32; // rbx
  UnBCL::String *v33; // rax
  const char *v34; // rax
  struct tagLOG_PARTIAL_MSG *v35; // rax
  UnBCL::String *v36; // rbx
  const struct UnBCL::String *v37; // rax
  const struct UnBCL::String *v38; // rbx
  const struct UnBCL::String *v39; // rax
  struct UnBCL::String *v40; // rax
  const struct UnBCL::String *v41; // rbx
  const struct UnBCL::String *v42; // rax
  struct UnBCL::String *v43; // rax
  const struct UnBCL::String *v44; // rax
  const struct UnBCL::String *v45; // rax
  const struct UnBCL::String *v46; // rax
  struct UnBCL::DirectoryInfo *Dir; // rax
  const struct UnBCL::String *v48; // rbx
  const struct UnBCL::String *v49; // rax
  struct UnBCL::String *v50; // rax
  DWORD v51; // esi
  __int64 v52; // rdi
  UnBCL::String *v53; // rax
  const char *v54; // rbx
  UnBCL::String *v55; // rax
  const char *v56; // rax
  struct tagLOG_PARTIAL_MSG *v57; // rax
  int v58; // eax
  DWORD v59; // r14d
  __int64 v60; // rsi
  DWORD v61; // edi
  UnBCL::String *v62; // rax
  const char *v63; // rbx
  UnBCL::String *v64; // rax
  const char *v65; // rax
  struct tagLOG_PARTIAL_MSG *v66; // rax
  UnBCL::String *v67; // rax
  const WCHAR *v68; // rax
  DWORD FileAttributesW; // ebx
  UnBCL::String *v70; // rax
  const WCHAR *v71; // rax
  DWORD v72; // esi
  __int64 v73; // rdi
  UnBCL::String *v74; // rax
  const char *v75; // rbx
  DWORD v76; // eax
  struct tagLOG_PARTIAL_MSG *v77; // rax
  DWORD v78; // esi
  __int64 v79; // rdi
  UnBCL::String *v80; // rax
  const char *v81; // rbx
  DWORD v82; // eax
  struct tagLOG_PARTIAL_MSG *v83; // rax
  UnBCL::String *v84; // rax
  const WCHAR *v85; // rax
  const unsigned __int16 *v86; // rdx
  DWORD v87; // edi
  __int64 v88; // rbx
  struct tagLOG_PARTIAL_MSG *v89; // rax
  UnBCL::String *v90; // rax
  const WCHAR *v91; // rax
  struct UnBCL::String *v92; // rax
  DWORD v93; // edi
  __int64 v94; // rbx
  UnBCL::String *v95; // rax
  const char *v96; // rax
  struct tagLOG_PARTIAL_MSG *v97; // rax
  UnBCL::String *v98; // rax
  unsigned __int8 *v99; // rbx
  struct UnBCL::String *v100; // rax
  DWORD v101; // edi
  __int64 v102; // rbx
  struct tagLOG_PARTIAL_MSG *v103; // rax
  UnBCL::String *v104; // rax
  DWORD v105; // edi
  __int64 v106; // rbx
  struct tagLOG_PARTIAL_MSG *v107; // rax
  UnBCL::String *v108; // rax
  const WCHAR *v109; // rax
  struct UnBCL::String *v110; // rax
  UnBCL::String *v111; // rbx
  UnBCL::String *v112; // rax
  const unsigned __int16 *v113; // rax
  DWORD v114; // edi
  __int64 v115; // rbx
  UnBCL::String *v116; // rax
  const char *v117; // rax
  struct tagLOG_PARTIAL_MSG *v118; // rax
  UnBCL::String *v119; // rax
  void *v120; // rax
  unsigned __int8 *v121; // rbx
  struct UnBCL::String *v122; // rax
  DWORD v123; // edi
  __int64 v124; // rbx
  struct tagLOG_PARTIAL_MSG *v125; // rax
  DWORD v126; // edi
  __int64 v127; // rbx
  struct tagLOG_PARTIAL_MSG *v128; // rax
  const struct UnBCL::String *v129; // rbx
  const struct UnBCL::String *v130; // rax
  struct UnBCL::String *v131; // rax
  UnBCL::String *v132; // rax
  const WCHAR *v133; // rax
  struct UnBCL::String *v134; // rax
  UnBCL::String *v135; // rax
  const WCHAR *v136; // rax
  struct UnBCL::String *v137; // rax
  UnBCL::String *v138; // rax
  const WCHAR *v139; // rax
  struct UnBCL::String *v140; // rax
  UnBCL::String *v141; // rax
  const WCHAR *v142; // rax
  struct UnBCL::String *v143; // rax
  UnBCL::String *v144; // rax
  const WCHAR *v145; // rax
  struct UnBCL::String *v146; // rax
  UnBCL::String *v147; // rax
  const WCHAR *v148; // rax
  struct UnBCL::String *v149; // rax
  UnBCL::String *v150; // rax
  const WCHAR *v151; // rax
  struct UnBCL::String *v152; // rax
  UnBCL::String *v153; // rax
  const wchar_t *v154; // rax
  const wchar_t *v155; // rdi
  struct tagLOG_PARTIAL_MSG *v156; // rax
  UnBCL::String *v157; // rax
  const wchar_t *v158; // rax
  struct tagLOG_PARTIAL_MSG *v159; // rax
  UnBCL::String *v160; // rax
  const wchar_t *v161; // rax
  struct tagLOG_PARTIAL_MSG *v162; // rax
  UnBCL::String *v163; // rax
  const wchar_t *v164; // rax
  struct tagLOG_PARTIAL_MSG *v165; // rax
  UnBCL::String *v166; // rax
  const wchar_t *v167; // rax
  struct tagLOG_PARTIAL_MSG *v168; // rax
  UnBCL::String *v169; // rax
  const wchar_t *v170; // rax
  struct tagLOG_PARTIAL_MSG *v171; // rax
  UnBCL::String *v172; // rax
  struct tagLOG_PARTIAL_MSG *v173; // rax
  struct UnBCL::String *v174; // rsi
  struct UnBCL::String *v175; // rdi
  struct UnBCL::String *v176; // rbx
  struct UnBCL::String *v177; // rax
  __int64 v178; // rbx
  struct tagLOG_PARTIAL_MSG *v179; // rax
  __int64 v180; // rbx
  struct tagLOG_PARTIAL_MSG *v181; // rax
  DWORD v182; // edi
  __int64 v183; // rbx
  struct tagLOG_PARTIAL_MSG *v184; // rax
  DWORD v185; // edi
  __int64 v186; // rbx
  struct tagLOG_PARTIAL_MSG *v187; // rax
  __int64 v188; // rdi
  __int64 v189; // rbx
  __int64 v190; // rax
  unsigned int v191; // eax
  const struct UnBCL::String *v192; // rbx
  const struct UnBCL::String *v193; // rax
  const struct UnBCL::String *v194; // rax
  struct UnBCL::String *v195; // rax
  LPVOID v196; // rdi
  const struct UnBCL::String *v197; // rax
  const struct UnBCL::String *v198; // rax
  UnBCL::String *v199; // rax
  const unsigned __int16 *v200; // rax
  int v201; // eax
  int v202; // ebx
  DWORD v203; // edi
  __int64 v204; // rbx
  UnBCL::String *v205; // rax
  const char *v206; // rax
  struct tagLOG_PARTIAL_MSG *v207; // rax
  CSetupPlatformPrivate *v208; // rbx
  __int64 v209; // rdi
  void (__fastcall *v210)(__int64, const wchar_t *, _QWORD, const unsigned __int16 *); // rbx
  const unsigned __int16 *v211; // rax
  DWORD v212; // edi
  __int64 v213; // rbx
  UnBCL::String *v214; // rax
  const char *v215; // rax
  struct tagLOG_PARTIAL_MSG *v216; // rax
  DWORD v217; // edi
  __int64 v218; // rbx
  UnBCL::String *v219; // rax
  const char *v220; // rax
  struct tagLOG_PARTIAL_MSG *v221; // rax
  void *v222; // rbx
  HANDLE ProcessHeap; // rax
  DWORD v224; // edi
  __int64 v225; // rbx
  UnBCL::String *v226; // rax
  const char *v227; // rax
  struct tagLOG_PARTIAL_MSG *v228; // rax
  const struct UnBCL::String *v229; // rdi
  __int64 v230; // rdx
  int v231; // eax
  UnBCL::String *v232; // rax
  const unsigned __int16 *v233; // rax
  CSetupPlatformPrivate *v234; // rbx
  __int64 v235; // rdi
  void (__fastcall *v236)(__int64, const wchar_t *, const wchar_t *, const unsigned __int16 *); // rbx
  UnBCL::String *v237; // rax
  const unsigned __int16 *v238; // rax
  char *v239; // rbx
  _QWORD *v240; // rax
  __int64 v241; // rax
  __int64 v242; // rdx
  __int64 v243; // r10
  _QWORD *v244; // rax
  __int64 v245; // rax
  __int64 v246; // rdx
  __int64 v247; // r10
  __int64 v248; // rax
  __int64 v249; // rax
  UnBCL::String *v250; // rax
  const WCHAR *v251; // rax
  struct UnBCL::String *v252; // rax
  __int64 v253; // rdi
  void (__fastcall *v254)(__int64, const wchar_t *, const wchar_t *, const unsigned __int16 *); // rbx
  UnBCL::String *v255; // rax
  const unsigned __int16 *v256; // rax
  const struct UnBCL::String *v257; // rbx
  const struct UnBCL::String *v258; // rax
  struct UnBCL::String *v259; // rax
  UnBCL::String *v260; // rax
  unsigned __int16 *v261; // rax
  DWORD v262; // edi
  __int64 v263; // rbx
  struct tagLOG_PARTIAL_MSG *v264; // rax
  UnBCL::String *v266; // rax
  const char *v267; // rax
  struct UnBCL::Exception *v268; // rsi
  DWORD v269; // edi
  __int64 v270; // rbx
  UnBCL::String *v271; // rax
  const char *v272; // rax
  struct tagLOG_PARTIAL_MSG *v273; // rax
  int v274; // [rsp+20h] [rbp-248h]
  int v275; // [rsp+20h] [rbp-248h]
  int *v276; // [rsp+38h] [rbp-230h]
  int *v277; // [rsp+38h] [rbp-230h]
  DWORD v278; // [rsp+40h] [rbp-228h]
  DWORD v279; // [rsp+40h] [rbp-228h]
  unsigned int v280; // [rsp+60h] [rbp-208h]
  int v281; // [rsp+60h] [rbp-208h]
  int v282; // [rsp+60h] [rbp-208h]
  int v283; // [rsp+60h] [rbp-208h]
  DWORD v284; // [rsp+60h] [rbp-208h]
  DWORD v285; // [rsp+60h] [rbp-208h]
  DWORD v286; // [rsp+60h] [rbp-208h]
  DWORD v287; // [rsp+60h] [rbp-208h]
  DWORD v288; // [rsp+60h] [rbp-208h]
  DWORD v289; // [rsp+60h] [rbp-208h]
  DWORD v290; // [rsp+60h] [rbp-208h]
  unsigned int v291; // [rsp+60h] [rbp-208h]
  UnBCL::String *v292; // [rsp+60h] [rbp-208h]
  signed int v293; // [rsp+68h] [rbp-200h]
  LPVOID lpMem; // [rsp+70h] [rbp-1F8h] BYREF
  void **v295; // [rsp+78h] [rbp-1F0h] BYREF
  void *v296; // [rsp+80h] [rbp-1E8h]
  CSetupPlatformPrivate *v297; // [rsp+88h] [rbp-1E0h] BYREF
  unsigned int v298; // [rsp+90h] [rbp-1D8h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+98h] [rbp-1D0h] BYREF
  unsigned int v300; // [rsp+B0h] [rbp-1B8h] BYREF
  unsigned int v301; // [rsp+B4h] [rbp-1B4h] BYREF
  int v302; // [rsp+B8h] [rbp-1B0h] BYREF
  int v303; // [rsp+BCh] [rbp-1ACh] BYREF
  CSetupPlatformPrivate *v304; // [rsp+C0h] [rbp-1A8h]
  struct UnBCL::String *v305; // [rsp+C8h] [rbp-1A0h] BYREF
  _BYTE v306[16]; // [rsp+D0h] [rbp-198h] BYREF
  _BYTE v307[16]; // [rsp+E0h] [rbp-188h] BYREF
  _BYTE v308[16]; // [rsp+F0h] [rbp-178h] BYREF
  _BYTE v309[16]; // [rsp+100h] [rbp-168h] BYREF
  _BYTE v310[16]; // [rsp+110h] [rbp-158h] BYREF
  _BYTE v311[24]; // [rsp+120h] [rbp-148h] BYREF
  _BYTE v312[16]; // [rsp+138h] [rbp-130h] BYREF
  _BYTE v313[16]; // [rsp+148h] [rbp-120h] BYREF
  _BYTE v314[16]; // [rsp+158h] [rbp-110h] BYREF
  _BYTE v315[16]; // [rsp+168h] [rbp-100h] BYREF
  _BYTE v316[16]; // [rsp+178h] [rbp-F0h] BYREF
  _BYTE v317[16]; // [rsp+188h] [rbp-E0h] BYREF
  _BYTE v318[16]; // [rsp+198h] [rbp-D0h] BYREF
  _BYTE v319[24]; // [rsp+1A8h] [rbp-C0h] BYREF
  _QWORD v320[5]; // [rsp+1C0h] [rbp-A8h]
  struct UnBCL::Exception *v321; // [rsp+1E8h] [rbp-80h] BYREF
  _BYTE v322[48]; // [rsp+1F0h] [rbp-78h] BYREF
  WCHAR FileName[12]; // [rsp+220h] [rbp-48h] BYREF

  v320[4] = -2;
  v304 = this;
  v297 = this;
  v2 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&UnicodeString, L"Rollback");
  v305 = (CSetupPlatformPrivate *)((char *)this + 208);
  P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 208);
  v4 = UnBCL::Path::Combine(P, v2);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v310, v4);
  UnBCL::String::~String((UnBCL::String *)&UnicodeString);
  v5 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v319, L"bootstat");
  v6 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v310);
  v7 = UnBCL::Path::Combine(v6, v5);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v309, v7);
  UnBCL::String::~String((UnBCL::String *)v319);
  v8 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 8LL))((char *)this + 176);
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8) )
  {
    v293 = 0;
    v15 = (char *)this + 368;
    lpMem = (char *)this + 368;
    v16 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 368);
    if ( UnBCL::Directory::Exists(v16) )
    {
      v17 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 208);
      v18 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 368);
      if ( !SPArePathsOnSameVolume(v18, v17) )
      {
        LastError = GetLastError();
        v20 = CurrentIP();
        v21 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v310);
        CString = (const char *)UnBCL::String::get_CString(v21);
        v23 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v15);
        v24 = (const char *)UnBCL::String::get_CString(v23);
        v25 = ConstructPartialMsgW(0x4000000u, "Attempting to move/copy/merge %s to %s", v24, CString);
        WdsSetupLogMessageW(
          v25,
          819200,
          L"D",
          0,
          997,
          L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
          L"CSetupPlatformPrivate::RollbackOnlineCommon",
          v20,
          LastError,
          0,
          0);
        LODWORD(CString) = UnBCL::SmartPtr<UnBCL::String>::get_P(v310);
        v26 = UnBCL::SmartPtr<UnBCL::String>::get_P(lpMem);
        if ( (unsigned int)SPMoveFileWithShortName(v26, (_DWORD)CString, 0, 0, 1, 1, 0, 0) )
        {
          v31 = GetLastError();
          v32 = CurrentIP();
          v33 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v310);
          v34 = (const char *)UnBCL::String::get_CString(v33);
          v35 = ConstructPartialMsgW(0x4000000u, "Move was successful, resetting the rollback dir to %s", v34);
          WdsSetupLogMessageW(
            v35,
            819200,
            L"D",
            0,
            1005,
            L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
            L"CSetupPlatformPrivate::RollbackOnlineCommon",
            v32,
            v31,
            0,
            0);
          v36 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
          *(_QWORD *)FileName = v36;
          if ( v36 )
          {
            v37 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v310);
            UnBCL::String::String(v36, v37);
            *(_QWORD *)v36 = &UnBCL::String::`local vftable';
          }
          else
          {
            v36 = 0;
          }
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&UnicodeString, v36);
          UnBCL::SmartPtr<UnBCL::String>::operator=(lpMem, &UnicodeString);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&UnicodeString);
        }
        else
        {
          v27 = GetLastError();
          v28 = CurrentIP();
          v29 = GetLastError();
          v30 = ConstructPartialMsgW(0x3000000u, "Error while executing the move/copy/merge. Error: 0x%08X", v29);
          WdsSetupLogMessageW(
            v30,
            819200,
            L"D",
            0,
            1000,
            L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
            L"CSetupPlatformPrivate::RollbackOnlineCommon",
            v28,
            v27,
            0,
            0);
        }
      }
    }
    v38 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v311, L"SafeOS");
    v39 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v305);
    v40 = UnBCL::Path::Combine(v39, v38);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v295, v40);
    UnBCL::String::~String((UnBCL::String *)v311);
    v41 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)FileName, L"bootstat.dat");
    v42 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(&v295);
    v43 = UnBCL::Path::Combine(v42, v41);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&UnicodeString, v43);
    UnBCL::SmartPtr<UnBCL::String>::operator=(&v295, &UnicodeString);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&UnicodeString);
    UnBCL::String::~String((UnBCL::String *)FileName);
    v44 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(&v295);
    if ( UnBCL::File::Exists(v44) )
    {
      v45 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v309);
      if ( !UnBCL::Directory::Exists(v45) )
      {
        try
        {
          v46 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v309);
          Dir = UnBCL::Directory::CreateDir(v46);
          UnBCL::SmartPtr<UnBCL::DirectoryInfo>::SmartPtr<UnBCL::DirectoryInfo>(&UnicodeString, Dir);
          UnBCL::SmartPtr<UnBCL::DirectoryInfo>::~SmartPtr<UnBCL::DirectoryInfo>(&UnicodeString);
        }
        catch ( UnBCL::Exception *v321 )
        {
          v266 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v309);
          v267 = (const char *)UnBCL::String::get_CString(v266);
          v268 = v321;
          pExceptionLogFormat::pExceptionLogFormat(
            (pExceptionLogFormat *)v322,
            0x3000000u,
            v321,
            "Cannot create WinPE boot logging directory %s.",
            v267);
          UnBCL::Exception::AddStackTrace(
            *(UnBCL::Exception **)&v322[40],
            "long __cdecl CSetupPlatformPrivate::RollbackOnlineCommon(void)");
          v269 = GetLastError();
          v270 = CurrentIP();
          v271 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v322[8]);
          v272 = (const char *)UnBCL::String::get_CString(v271);
          v273 = ConstructPartialMsgW(*(unsigned int *)v322, "%s", v272);
          WdsSetupLogMessageW(
            v273,
            819200,
            L"D",
            0,
            1028,
            L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
            L"CSetupPlatformPrivate::RollbackOnlineCommon",
            v270,
            v269,
            0,
            0);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v322[24]);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v322[8]);
          if ( v268 )
            (**(void (__fastcall ***)(struct UnBCL::Exception *, __int64))v268)(v268, 1);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&UnicodeString, 0);
          UnBCL::SmartPtr<UnBCL::String>::operator=(&v295, &UnicodeString);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&UnicodeString);
          v293 = 0;
          v304 = v297;
        }
      }
      if ( UnBCL::SmartPtr<UnBCL::String>::get_P(&v295) )
      {
        v48 = (const struct UnBCL::String *)UnBCL::String::String(
                                              (UnBCL::String *)&UnicodeString,
                                              L"bootstat-SafeOS.dat");
        v49 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v309);
        v50 = UnBCL::Path::Combine(v49, v48);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(FileName, v50);
        UnBCL::String::~String((UnBCL::String *)&UnicodeString);
        v51 = GetLastError();
        v52 = CurrentIP();
        v53 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(FileName);
        v54 = (const char *)UnBCL::String::get_CString(v53);
        v55 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v295);
        v56 = (const char *)UnBCL::String::get_CString(v55);
        v57 = ConstructPartialMsgW(0x4000000u, "Moving %s to %s", v56, v54);
        WdsSetupLogMessageW(
          v57,
          819200,
          L"D",
          0,
          1036,
          L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
          L"CSetupPlatformPrivate::RollbackOnlineCommon",
          v52,
          v51,
          0,
          0);
        LODWORD(v54) = UnBCL::SmartPtr<UnBCL::String>::get_P(FileName);
        v58 = UnBCL::SmartPtr<UnBCL::String>::get_P(&v295);
        if ( (unsigned int)SPMoveFileWithShortName(v58, (_DWORD)v54, 0, 0, 1, 1, 0, 1) )
        {
          v67 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(FileName);
          v68 = UnBCL::String::get_CString(v67);
          FileAttributesW = GetFileAttributesW(v68);
          if ( FileAttributesW == -1 )
          {
            v78 = GetLastError();
            v79 = CurrentIP();
            v80 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(FileName);
            v81 = (const char *)UnBCL::String::get_CString(v80);
            v82 = GetLastError();
            v83 = ConstructPartialMsgW(
                    0x2000000u,
                    "%hs: failed to get attributes (error %u) from %s",
                    "CSetupPlatformPrivate::RollbackOnlineCommon",
                    v82,
                    v81);
            WdsSetupLogMessageW(
              v83,
              819200,
              L"D",
              0,
              1071,
              L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
              L"CSetupPlatformPrivate::RollbackOnlineCommon",
              v79,
              v78,
              0,
              0);
          }
          else
          {
            v280 = FileAttributesW & 0xFFFFFFF9;
            v70 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(FileName);
            v71 = UnBCL::String::get_CString(v70);
            if ( !SetFileAttributesW(v71, FileAttributesW & 0xFFFFFFF9) )
            {
              v72 = GetLastError();
              v73 = CurrentIP();
              v74 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(FileName);
              v75 = (const char *)UnBCL::String::get_CString(v74);
              v76 = GetLastError();
              v77 = ConstructPartialMsgW(
                      0x2000000u,
                      "%hs: Failed to set attributes 0x%08x (error %u) on %s",
                      "CSetupPlatformPrivate::RollbackOnlineCommon",
                      v280,
                      v76,
                      v75);
              WdsSetupLogMessageW(
                v77,
                819200,
                L"D",
                0,
                1062,
                L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
                L"CSetupPlatformPrivate::RollbackOnlineCommon",
                v73,
                v72,
                0,
                0);
            }
          }
        }
        else
        {
          v59 = GetLastError();
          v60 = CurrentIP();
          v61 = GetLastError();
          v62 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(FileName);
          v63 = (const char *)UnBCL::String::get_CString(v62);
          v64 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v295);
          v65 = (const char *)UnBCL::String::get_CString(v64);
          v66 = ConstructPartialMsgW(
                  0x2000000u,
                  "%hs: MoveFile(from \"%s\" to \"%s\") failed. Error: 0x%08X",
                  "CSetupPlatformPrivate::RollbackOnlineCommon",
                  v65,
                  v63,
                  v61);
          WdsSetupLogMessageW(
            v66,
            819200,
            L"D",
            0,
            1046,
            L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
            L"CSetupPlatformPrivate::RollbackOnlineCommon",
            v60,
            v59,
            0,
            0);
        }
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(FileName);
      }
    }
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v295);
  }
  else
  {
    v9 = GetLastError();
    v10 = v9 < 0;
    if ( v9 > 0 )
      v10 = 1;
    if ( v10 )
    {
      v11 = GetLastError();
      v293 = v11;
      if ( v11 > 0 )
        v293 = (unsigned __int16)v11 | 0x80070000;
    }
    else
    {
      v293 = -2147467259;
    }
    v12 = GetLastError();
    v13 = CurrentIP();
    v14 = ConstructPartialMsgW(0x2000000u, "CSetupPlatformPrivate::RollbackOnlineCommon: Failed to execute rollback");
    WdsSetupLogMessageW(
      v14,
      819200,
      L"D",
      0,
      985,
      L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
      L"CSetupPlatformPrivate::RollbackOnlineCommon",
      v13,
      v12,
      0,
      0);
  }
  v297 = (CSetupPlatformPrivate *)((char *)v304 + 24);
  v84 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)v304 + 24);
  v85 = UnBCL::String::get_CString(v84);
  v281 = SPProcessBitlockerOnDrives(v85, v86, 1);
  if ( v281 < 0 )
  {
    v87 = GetLastError();
    v88 = CurrentIP();
    v89 = ConstructPartialMsgW(0x2000000u, "Failed to enable bitlocker on some drives. Result: 0x%08X", v281);
    WdsSetupLogMessageW(
      v89,
      819200,
      L"D",
      0,
      1084,
      L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
      L"CSetupPlatformPrivate::RollbackOnlineCommon",
      v88,
      v87,
      0,
      0);
  }
  v90 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v297);
  v91 = UnBCL::String::get_CString(v90);
  v92 = SPReadConfigValue(L"BitLocker", L"SafeOSHash", v91);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v308, v92);
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v308) )
  {
    v93 = GetLastError();
    v94 = CurrentIP();
    v95 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v308);
    v96 = (const char *)UnBCL::String::get_CString(v95);
    v97 = ConstructPartialMsgW(0x4000000u, "Deleting safe OS BitLocker hash %s", v96);
    WdsSetupLogMessageW(
      v97,
      819200,
      L"D",
      0,
      1093,
      L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
      L"CSetupPlatformPrivate::RollbackOnlineCommon",
      v94,
      v93,
      0,
      0);
    v98 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v308);
    lpMem = (LPVOID)(unsigned int)(UnBCL::String::get_Length(v98) / 2);
    v296 = operator new[]((unsigned __int64)lpMem);
    v295 = &Mig::CAutoDeleteArray<unsigned char>::`vftable';
    v99 = (unsigned __int8 *)RAII::CAutoCleanupBase<void *>::operator->(&v295);
    v100 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v308);
    v282 = SPHexDecode(v100, v99, (unsigned int)lpMem);
    if ( v282 < 0 )
    {
      v101 = GetLastError();
      v102 = CurrentIP();
      v103 = ConstructPartialMsgW(
               0x3000000u,
               "CSetupPlatformPrivate::RollbackOnlineCommon: Failed to decode safe OS hash, cannot remove it: 0x%08x",
               v282);
      WdsSetupLogMessageW(
        v103,
        819200,
        L"D",
        0,
        1101,
        L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
        L"CSetupPlatformPrivate::RollbackOnlineCommon",
        v102,
        v101,
        0,
        0);
    }
    wcscpy(FileName, L"\\\\.\\?:");
    v104 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v305);
    FileName[4] = *UnBCL::String::get_CString(v104);
    ((void (__fastcall *)(void ***))v295[3])(&v295);
    v293 = FveRemoveTrustedWimData(FileName);
    if ( v293 < 0 )
    {
      v105 = GetLastError();
      v106 = CurrentIP();
      v107 = ConstructPartialMsgW(
               0x3000000u,
               "CSetupPlatformPrivate::RollbackOnlineCommon: Failed to delete safe OS hash: 0x%08x",
               v293);
      WdsSetupLogMessageW(
        v107,
        819200,
        L"D",
        0,
        1111,
        L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
        L"CSetupPlatformPrivate::RollbackOnlineCommon",
        v106,
        v105,
        0,
        0);
      v293 = 0;
    }
    v108 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v297);
    v109 = UnBCL::String::get_CString(v108);
    v110 = SPReadConfigValue(L"BitLocker", L"WinREHash", v109);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&UnicodeString, v110);
    if ( UnBCL::SmartPtr<UnBCL::String>::get_P(&UnicodeString) )
    {
      v111 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v308);
      v112 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&UnicodeString);
      v113 = UnBCL::String::get_CString(v112);
      if ( UnBCL::String::CompareTo(v111, v113, 1) )
      {
        v114 = GetLastError();
        v115 = CurrentIP();
        v116 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&UnicodeString);
        v117 = (const char *)UnBCL::String::get_CString(v116);
        v118 = ConstructPartialMsgW(0x4000000u, "Deleting new WinRE BitLocker hash %s", v117);
        WdsSetupLogMessageW(
          v118,
          819200,
          L"D",
          0,
          1118,
          L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
          L"CSetupPlatformPrivate::RollbackOnlineCommon",
          v115,
          v114,
          0,
          0);
        v119 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&UnicodeString);
        lpMem = (LPVOID)(unsigned int)(UnBCL::String::get_Length(v119) / 2);
        v120 = operator new[]((unsigned __int64)lpMem);
        ((void (__fastcall *)(void ***, void *))v295[4])(&v295, v120);
        v121 = (unsigned __int8 *)((__int64 (__fastcall *)(void ***))v295[3])(&v295);
        v122 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(&UnicodeString);
        v283 = SPHexDecode(v122, v121, (unsigned int)lpMem);
        if ( v283 < 0 )
        {
          v123 = GetLastError();
          v124 = CurrentIP();
          v125 = ConstructPartialMsgW(
                   0x3000000u,
                   "CSetupPlatformPrivate::RollbackOnlineCommon: Failed to decode new WinRE hash, cannot remove it: 0x%08x",
                   v283);
          WdsSetupLogMessageW(
            v125,
            819200,
            L"D",
            0,
            1125,
            L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
            L"CSetupPlatformPrivate::RollbackOnlineCommon",
            v124,
            v123,
            0,
            0);
        }
        ((void (__fastcall *)(void ***))v295[3])(&v295);
        v293 = FveRemoveTrustedWimData(FileName);
        if ( v293 < 0 )
        {
          v126 = GetLastError();
          v127 = CurrentIP();
          v128 = ConstructPartialMsgW(
                   0x3000000u,
                   "CSetupPlatformPrivate::RollbackOnlineCommon: Failed to delete new WinRE hash: 0x%08x",
                   v293);
          WdsSetupLogMessageW(
            v128,
            819200,
            L"D",
            0,
            1132,
            L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
            L"CSetupPlatformPrivate::RollbackOnlineCommon",
            v127,
            v126,
            0,
            0);
          v293 = 0;
        }
      }
    }
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&UnicodeString);
    v295 = &Mig::CAutoDeleteArray<unsigned char>::`vftable';
    if ( v296 )
      operator delete[](v296);
  }
  v129 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v311, L"rollbackinfo.ini");
  v130 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v304 + 368);
  v131 = UnBCL::Path::Combine(v130, v129);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v306, v131);
  UnBCL::String::~String((UnBCL::String *)v311);
  v132 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v306);
  v133 = UnBCL::String::get_CString(v132);
  v134 = SPReadConfigValue(L"Flow", L"CurrentPhase", v133);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v317, v134);
  v135 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v306);
  v136 = UnBCL::String::get_CString(v135);
  v137 = SPReadConfigValue(L"Flow", L"CurrentOperation", v136);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v316, v137);
  v138 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v306);
  v139 = UnBCL::String::get_CString(v138);
  v140 = SPReadConfigValue(L"Flow", L"OperationResult", v139);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v315, v140);
  v141 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v306);
  v142 = UnBCL::String::get_CString(v141);
  v143 = SPReadConfigValue(L"Bugcheck", L"Code", v142);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v314, v143);
  v144 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v306);
  v145 = UnBCL::String::get_CString(v144);
  v146 = SPReadConfigValue(L"Bugcheck", L"DumpType", v145);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v307, v146);
  v147 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v297);
  v148 = UnBCL::String::get_CString(v147);
  v149 = SPReadConfigValue(L"Uninstall", L"Reason", v148);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v313, v149);
  v150 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v297);
  v151 = UnBCL::String::get_CString(v150);
  v152 = SPReadConfigValue(L"Uninstall", L"Comment", v151);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v312, v152);
  v284 = GetLastError();
  lpMem = (LPVOID)CurrentIP();
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v317) )
  {
    v153 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v317);
    v154 = UnBCL::String::get_CString(v153);
    v155 = L"NULL";
  }
  else
  {
    v155 = L"NULL";
    v154 = L"NULL";
  }
  v156 = ConstructPartialMsgW(0x4000000u, "Current phase string     : %s", (const char *)v154);
  WdsSetupLogMessageW(
    v156,
    819200,
    L"D",
    0,
    1148,
    L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
    L"CSetupPlatformPrivate::RollbackOnlineCommon",
    lpMem,
    v284,
    0,
    0);
  v285 = GetLastError();
  lpMem = (LPVOID)CurrentIP();
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v316) )
  {
    v157 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v316);
    v158 = UnBCL::String::get_CString(v157);
  }
  else
  {
    v158 = L"NULL";
  }
  v159 = ConstructPartialMsgW(0x4000000u, "Current op string        : %s", (const char *)v158);
  WdsSetupLogMessageW(
    v159,
    819200,
    L"D",
    0,
    1149,
    L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
    L"CSetupPlatformPrivate::RollbackOnlineCommon",
    lpMem,
    v285,
    0,
    0);
  v286 = GetLastError();
  lpMem = (LPVOID)CurrentIP();
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v315) )
  {
    v160 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v315);
    v161 = UnBCL::String::get_CString(v160);
  }
  else
  {
    v161 = L"NULL";
  }
  v162 = ConstructPartialMsgW(0x4000000u, "Current result string    : %s", (const char *)v161);
  WdsSetupLogMessageW(
    v162,
    819200,
    L"D",
    0,
    1150,
    L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
    L"CSetupPlatformPrivate::RollbackOnlineCommon",
    lpMem,
    v286,
    0,
    0);
  v287 = GetLastError();
  lpMem = (LPVOID)CurrentIP();
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v314) )
  {
    v163 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v314);
    v164 = UnBCL::String::get_CString(v163);
  }
  else
  {
    v164 = L"NULL";
  }
  v165 = ConstructPartialMsgW(0x4000000u, "Current bugcheck string  : %s", (const char *)v164);
  WdsSetupLogMessageW(
    v165,
    819200,
    L"D",
    0,
    1151,
    L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
    L"CSetupPlatformPrivate::RollbackOnlineCommon",
    lpMem,
    v287,
    0,
    0);
  v288 = GetLastError();
  lpMem = (LPVOID)CurrentIP();
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v313) )
  {
    v166 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v313);
    v167 = UnBCL::String::get_CString(v166);
  }
  else
  {
    v167 = L"NULL";
  }
  v168 = ConstructPartialMsgW(0x4000000u, "Current uninstall reason : %s", (const char *)v167);
  WdsSetupLogMessageW(
    v168,
    819200,
    L"D",
    0,
    1152,
    L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
    L"CSetupPlatformPrivate::RollbackOnlineCommon",
    lpMem,
    v288,
    0,
    0);
  v289 = GetLastError();
  lpMem = (LPVOID)CurrentIP();
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v312) )
  {
    v169 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v312);
    v170 = UnBCL::String::get_CString(v169);
  }
  else
  {
    v170 = L"NULL";
  }
  v171 = ConstructPartialMsgW(0x4000000u, "Current uninstall comment: %s", (const char *)v170);
  WdsSetupLogMessageW(
    v171,
    819200,
    L"D",
    0,
    1153,
    L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
    L"CSetupPlatformPrivate::RollbackOnlineCommon",
    lpMem,
    v289,
    0,
    0);
  v290 = GetLastError();
  lpMem = (LPVOID)CurrentIP();
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v307) )
  {
    v172 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v307);
    v155 = UnBCL::String::get_CString(v172);
  }
  v173 = ConstructPartialMsgW(0x4000000u, "Dump type : %s", (const char *)v155);
  WdsSetupLogMessageW(
    v173,
    819200,
    L"D",
    0,
    1154,
    L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
    L"CSetupPlatformPrivate::RollbackOnlineCommon",
    lpMem,
    v290,
    0,
    0);
  v300 = 0;
  v301 = 0;
  LODWORD(v297) = 0;
  v302 = 0;
  v303 = 0;
  v298 = 0;
  v174 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v314);
  v175 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v315);
  v176 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v316);
  v177 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v317);
  SPGetExternalPhaseAndOp(
    v177,
    v176,
    v175,
    v174,
    (enum SetupPlatform::SP_EXECUTION_PHASE *)&v300,
    (enum SetupPlatform::SP_EXECUTION_OPERATION *)&v301,
    (enum OP_OPERATION_ID *)&v297,
    &v302,
    &v303,
    &v298);
  LODWORD(v175) = GetLastError();
  v178 = CurrentIP();
  v179 = ConstructPartialMsgW(0x4000000u, "Current phase : %u", v300);
  WdsSetupLogMessageW(
    v179,
    819200,
    L"D",
    0,
    1173,
    L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
    L"CSetupPlatformPrivate::RollbackOnlineCommon",
    v178,
    (_DWORD)v175,
    0,
    0);
  LODWORD(v175) = GetLastError();
  v180 = CurrentIP();
  v181 = ConstructPartialMsgW(0x4000000u, "Current op    : %u", v301);
  WdsSetupLogMessageW(
    v181,
    819200,
    L"D",
    0,
    1174,
    L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
    L"CSetupPlatformPrivate::RollbackOnlineCommon",
    v180,
    (_DWORD)v175,
    0,
    0);
  v182 = GetLastError();
  v183 = CurrentIP();
  if ( v302 )
  {
    v184 = ConstructPartialMsgW(0x4000000u, "Current result: 0x%08X", v303);
    v278 = v182;
    v276 = (int *)v183;
    v274 = 1177;
  }
  else
  {
    v184 = ConstructPartialMsgW(0x4000000u, "Current result: Unknown");
    v278 = v182;
    v276 = (int *)v183;
    v274 = 1181;
  }
  WdsSetupLogMessageW(
    v184,
    819200,
    L"D",
    0,
    v274,
    L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
    L"CSetupPlatformPrivate::RollbackOnlineCommon",
    v276,
    v278,
    0,
    0);
  if ( v298 )
  {
    v185 = GetLastError();
    v186 = CurrentIP();
    v187 = ConstructPartialMsgW(0x4000000u, "Bugcheck code : 0x%08X", v298);
    WdsSetupLogMessageW(
      v187,
      819200,
      L"D",
      0,
      1185,
      L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
      L"CSetupPlatformPrivate::RollbackOnlineCommon",
      v186,
      v185,
      0,
      0);
  }
  v188 = UnBCL::SmartPtr<UnBCL::String>::get_P(v306);
  v189 = UnBCL::SmartPtr<UnBCL::String>::get_P(v312);
  v190 = UnBCL::SmartPtr<UnBCL::String>::get_P(v313);
  pRegisterFailureData(
    v300,
    v301,
    (int)v297,
    v302,
    v303,
    (UnBCL::String *)v190,
    (UnBCL::String *)v189,
    (UnBCL::String *)v188);
  v320[0] = L"bootstat-NewOS.dat";
  v320[1] = L"bootstat-SafeOS.dat";
  v320[2] = L"bootstat-PCAT.dat";
  v320[3] = L"bootstat-BootMgr.dat";
  v191 = 0;
  v291 = 0;
  do
  {
    memset(v322, 0, 44);
    v305 = 0;
    *(_QWORD *)FileName = v320[v191];
    v192 = (const struct UnBCL::String *)UnBCL::String::String(
                                           (UnBCL::String *)v319,
                                           *(const unsigned __int16 **)FileName);
    v193 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v309);
    v194 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v311, v193);
    v195 = UnBCL::Path::Combine(v194, v192);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v295, v195);
    UnBCL::String::~String((UnBCL::String *)v311);
    UnBCL::String::~String((UnBCL::String *)v319);
    v196 = 0;
    lpMem = 0;
    v197 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(&v295);
    v198 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&UnicodeString, v197);
    LODWORD(v192) = UnBCL::File::Exists(v198);
    UnBCL::String::~String((UnBCL::String *)&UnicodeString);
    if ( (_DWORD)v192 )
    {
      v199 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v295);
      v200 = UnBCL::String::get_CString(v199);
      UnicodeString = 0;
      if ( !v200 )
        goto LABEL_84;
      v201 = RtlDosPathNameToNtPathName_U_WithStatus(v200, &UnicodeString, 0, 0);
      v202 = 0;
      if ( v201 < 0 )
        v202 = v201 | 0x10000000;
      if ( v202 >= 0 )
      {
        v202 = StrAllocatingPrintf(&lpMem, L"%wZ", &UnicodeString);
        v196 = lpMem;
      }
      RtlFreeUnicodeString(&UnicodeString);
      if ( v202 >= 0 )
      {
        LODWORD(v297) = BsdSummarize(v196, v322);
        if ( (int)v297 < 0 )
        {
          v212 = GetLastError();
          v213 = CurrentIP();
          LODWORD(v297) = (unsigned int)v297 | 0x10000000;
          v214 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v295);
          v215 = (const char *)UnBCL::String::get_CString(v214);
          v216 = ConstructPartialMsgW(
                   0x3000000u,
                   " Call to BsdSummarize for bootstat file %s failed with error: 0x%08x",
                   v215,
                   (_DWORD)v297);
          WdsSetupLogMessageW(
            v216,
            819200,
            L"D",
            0,
            1240,
            L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
            L"CSetupPlatformPrivate::RollbackOnlineCommon",
            v213,
            v212,
            0,
            0);
          v293 = 0;
        }
        else
        {
          v203 = GetLastError();
          v204 = CurrentIP();
          v205 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v295);
          v206 = (const char *)UnBCL::String::get_CString(v205);
          v207 = ConstructPartialMsgW(
                   0x4000000u,
                   "Attempt to get BsdSummarize Diagnostic Information for bootstat file: %s",
                   v206);
          WdsSetupLogMessageW(
            v207,
            819200,
            L"D",
            0,
            1227,
            L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
            L"CSetupPlatformPrivate::RollbackOnlineCommon",
            v204,
            v203,
            0,
            0);
          if ( (int)pGetBootStatSummaryString((struct _BSD_SUMMARY *)v322, &v305) >= 0 )
          {
            v208 = v304;
            if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)v304 + 24) + 24LL))((char *)v304 + 192) )
            {
              v209 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)v208 + 24) + 8LL))((char *)v208 + 192);
              v210 = *(void (__fastcall **)(__int64, const wchar_t *, _QWORD, const unsigned __int16 *))(*(_QWORD *)v209 + 16LL);
              v211 = UnBCL::String::get_CString(v305);
              v210(v209, L"RollbackBsdSummary", *(_QWORD *)FileName, v211);
            }
            if ( v305 )
              (**(void (__fastcall ***)(struct UnBCL::String *, __int64))v305)(v305, 1);
          }
        }
      }
      else
      {
LABEL_84:
        v217 = GetLastError();
        v218 = CurrentIP();
        v219 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v295);
        v220 = (const char *)UnBCL::String::get_CString(v219);
        v221 = ConstructPartialMsgW(0x3000000u, "Failed to convert bootstat.dat file path: %s to NT path", v220);
        WdsSetupLogMessageW(
          v221,
          819200,
          L"D",
          0,
          1246,
          L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
          L"CSetupPlatformPrivate::RollbackOnlineCommon",
          v218,
          v217,
          0,
          0);
      }
      v222 = lpMem;
      if ( lpMem )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v222);
      }
    }
    else
    {
      v224 = GetLastError();
      v225 = CurrentIP();
      v226 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v295);
      v227 = (const char *)UnBCL::String::get_CString(v226);
      v228 = ConstructPartialMsgW(0x3000000u, "Bootstat.dat file: %s does not exist", v227);
      WdsSetupLogMessageW(
        v228,
        819200,
        L"D",
        0,
        1252,
        L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
        L"CSetupPlatformPrivate::RollbackOnlineCommon",
        v225,
        v224,
        0,
        0);
    }
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v295);
    v191 = v291 + 1;
    v291 = v191;
  }
  while ( v191 < 4 );
  v229 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v307);
  if ( UnBCL::String::Compare(v229, L"ActiveDump", 1) )
  {
    if ( UnBCL::String::Compare(v229, L"FullDump", 1) )
    {
      if ( UnBCL::String::Compare(v229, L"KernelDump", 1) )
      {
        v231 = UnBCL::String::Compare(v229, L"MiniDump", 1);
        v230 = 4;
        if ( v231 )
          v230 = 1;
      }
      else
      {
        v230 = 7;
      }
    }
    else
    {
      v230 = 6;
    }
  }
  else
  {
    v230 = 5;
  }
  v232 = UnBCL::String::Format(L"%d", v230);
  v292 = v232;
  if ( v232 )
  {
    v233 = UnBCL::String::get_CString(v232);
    v234 = v304;
    CDiagnosticsHelper::SetWatsonBucketingParam((CSetupPlatformPrivate *)((char *)v304 + 40), 3u, v233);
  }
  else
  {
    v234 = v304;
  }
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v307) )
  {
    *(_QWORD *)FileName = (char *)v234 + 192;
    v235 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)v234 + 24) + 8LL))((char *)v234 + 192);
    v236 = *(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, const unsigned __int16 *))(*(_QWORD *)v235 + 16LL);
    v237 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v307);
    v238 = UnBCL::String::get_CString(v237);
    v236(v235, L"SP_ROLLBACK_INFO", L"RollbackDumpType", v238);
    v239 = *(char **)FileName;
  }
  else
  {
    v239 = (char *)v234 + 192;
  }
  v240 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v239 + 8LL))(v239);
  v241 = SPGetPhaseStr(v300, *v240);
  (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64))(v242 + 16))(
    v243,
    L"SP_ROLLBACK_INFO",
    L"RollbackInitiatedPhase",
    v241);
  v244 = (_QWORD *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v239 + 8LL))(v239);
  v245 = SPGetOperationStr(v301, *v244);
  (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64))(v246 + 16))(
    v247,
    L"SP_ROLLBACK_INFO",
    L"RollbackInitiatedOperation",
    v245);
  if ( v302 )
  {
    v248 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v239 + 8LL))(v239);
    (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, _QWORD))(*(_QWORD *)v248 + 24LL))(
      v248,
      L"SP_ROLLBACK_INFO",
      L"RollbackInitiatedOperationHR",
      (unsigned int)v303);
  }
  if ( v298 )
  {
    v249 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v239 + 8LL))(v239);
    (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, _QWORD))(*(_QWORD *)v249 + 24LL))(
      v249,
      L"SP_ROLLBACK_INFO",
      L"RollbackInitiatedBugCheckCode",
      v298);
  }
  else
  {
    v250 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v306);
    v251 = UnBCL::String::get_CString(v250);
    v252 = SPReadConfigValue(L"Bugcheck", L"BinaryInfo", v251);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&UnicodeString, v252);
    if ( UnBCL::SmartPtr<UnBCL::String>::get_P(&UnicodeString) )
    {
      v253 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v239 + 8LL))(v239);
      v254 = *(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, const unsigned __int16 *))(*(_QWORD *)v253 + 16LL);
      v255 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&UnicodeString);
      v256 = UnBCL::String::get_CString(v255);
      v254(v253, L"SP_ROLLBACK_INFO", L"RollbackInitiatedBugCheckBinaryInfo", v256);
    }
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&UnicodeString);
  }
  v257 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v311, L"$WINDOWS.~BT");
  v258 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v304 + 224);
  v259 = UnBCL::Path::Combine(v258, v257);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v318, v259);
  UnBCL::String::~String((UnBCL::String *)v311);
  v260 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v318);
  v261 = (unsigned __int16 *)UnBCL::String::get_CString(v260);
  SPDeleteTempPageFileForCrashDumpCapsule(*v261);
  v262 = GetLastError();
  v263 = CurrentIP();
  if ( v293 < 0 )
  {
    v264 = ConstructPartialMsgW(0x4000000u, "Rollback-Online-Common completed with error: 0x%08X", v293);
    v279 = v262;
    v277 = (int *)v263;
    v275 = 1300;
  }
  else
  {
    v264 = ConstructPartialMsgW(0x4000000u, "Rollback-Online-Common completed successfully.");
    v279 = v262;
    v277 = (int *)v263;
    v275 = 1296;
  }
  WdsSetupLogMessageW(
    v264,
    819200,
    L"D",
    0,
    v275,
    L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
    L"CSetupPlatformPrivate::RollbackOnlineCommon",
    v277,
    v279,
    0,
    0);
  if ( v292 )
    (**(void (__fastcall ***)(UnBCL::String *, __int64))v292)(v292, 1);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v318);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v312);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v313);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v307);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v314);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v315);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v316);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v317);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v306);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v308);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v309);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v310);
  return (unsigned int)v293;
}

```

## disassembly

```asm
0x180267008  mov     r11, rsp
0x18026700b  push    rdi
0x18026700c  push    r12
0x18026700e  push    r13
0x180267010  push    r14
0x180267012  push    r15
0x180267014  sub     rsp, 240h
0x18026701b  mov     qword ptr [r11-88h], 0FFFFFFFFFFFFFFFEh
0x180267026  mov     [r11+10h], rbx
0x18026702a  mov     [r11+18h], rsi
0x18026702e  mov     rax, cs:__security_cookie
0x180267035  xor     rax, rsp
0x180267038  mov     [rsp+268h+var_30], rax
0x180267040  mov     rsi, rcx
0x180267043  mov     [rsp+268h+var_1A8], rcx
0x18026704b  mov     [rsp+268h+var_1E0], rcx
0x180267053  lea     rdx, aRollback; "Rollback"
0x18026705a  lea     rcx, [r11-1D0h]
0x180267061  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180267067  mov     rbx, rax
0x18026706a  lea     r12, [rsi+0D0h]
0x180267071  mov     [rsp+268h+var_1A0], r12
0x180267079  mov     rcx, r12
0x18026707c  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180267082  mov     rdx, rbx
0x180267085  mov     rcx, rax
0x180267088  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x18026708e  mov     rdx, rax
0x180267091  lea     rcx, [rsp+268h+var_158]
0x180267099  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18026709f  nop
0x1802670a0  lea     rcx, [rsp+268h+UnicodeString]
0x1802670a8  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1802670ae  lea     rdx, aBootstat; "bootstat"
0x1802670b5  lea     rcx, [rsp+268h+var_C0]
0x1802670bd  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1802670c3  mov     rbx, rax
0x1802670c6  lea     rcx, [rsp+268h+var_158]
0x1802670ce  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1802670d4  mov     rdx, rbx
0x1802670d7  mov     rcx, rax
0x1802670da  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1802670e0  mov     rdx, rax
0x1802670e3  lea     rcx, [rsp+268h+var_168]
0x1802670eb  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802670f1  nop
0x1802670f2  lea     rcx, [rsp+268h+var_C0]
0x1802670fa  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180267100  lea     rcx, [rsi+0B0h]
0x180267107  mov     rax, [rcx]
0x18026710a  mov     rax, [rax+8]
0x18026710e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180267113  mov     rdx, rax
0x180267116  mov     rcx, [rax]
0x180267119  mov     rax, [rcx+10h]
0x18026711d  mov     rcx, rdx
0x180267120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180267125  xor     r15d, r15d
0x180267128  test    eax, eax
0x18026712a  jnz     loc_1802671E3
0x180267130  call    cs:__imp_GetLastError
0x180267136  test    eax, eax
0x180267138  jle     short loc_180267144
0x18026713a  movzx   eax, ax
0x18026713d  or      eax, 80070000h
0x180267142  test    eax, eax
0x180267144  jns     short loc_180267162
0x180267146  call    cs:__imp_GetLastError
0x18026714c  mov     [rsp+268h+var_200], eax
0x180267150  test    eax, eax
0x180267152  jle     short loc_18026716A
0x180267154  movzx   eax, ax
0x180267157  or      eax, 80070000h
0x18026715c  mov     [rsp+268h+var_200], eax
0x180267160  jmp     short loc_18026716A
0x180267162  mov     [rsp+268h+var_200], 80004005h
0x18026716a  call    cs:__imp_GetLastError
0x180267170  mov     edi, eax
0x180267172  call    cs:__imp_CurrentIP
0x180267178  mov     rbx, rax
0x18026717b  lea     rdx, aCsetupplatform_254; "CSetupPlatformPrivate::RollbackOnlineCo"...
0x180267182  mov     ecx, 2000000h; unsigned int
0x180267187  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18026718c  mov     [rsp+268h+var_218], r15d
0x180267191  mov     [rsp+268h+var_220], r15
0x180267196  mov     dword ptr [rsp+268h+var_228], edi
0x18026719a  mov     [rsp+268h+var_230], rbx
0x18026719f  lea     r14, aCsetupplatform_245; "CSetupPlatformPrivate::RollbackOnlineCo"...
0x1802671a6  mov     [rsp+268h+var_238], r14
0x1802671ab  lea     rsi, aBaseNtsetupSet_35; "base\\ntsetup\\setupplatform\\lib\\priv"...
0x1802671b2  mov     [rsp+268h+var_240], rsi
0x1802671b7  mov     dword ptr [rsp+268h+var_248], 3D9h
0x1802671bf  xor     r9d, r9d
0x1802671c2  lea     r12, aD_0; "D"
0x1802671c9  mov     r8, r12
0x1802671cc  mov     r13d, 0C8000h
0x1802671d2  mov     edx, r13d
0x1802671d5  mov     rcx, rax
0x1802671d8  call    cs:__imp_WdsSetupLogMessageW
0x1802671de  jmp     loc_180267965
0x1802671e3  mov     [rsp+268h+var_200], r15d
0x1802671e8  lea     r14, [rsi+170h]
0x1802671ef  mov     [rsp+268h+lpMem], r14
0x1802671f4  mov     rcx, r14
0x1802671f7  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1802671fd  mov     rcx, rax
0x180267200  call    cs:__imp_?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z; UnBCL::Directory::Exists(UnBCL::String const *)
0x180267206  test    eax, eax
0x180267208  jz      loc_180267478
0x18026720e  mov     rcx, r12
0x180267211  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180267217  mov     rbx, rax
0x18026721a  mov     rcx, r14
0x18026721d  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180267223  mov     rdx, rbx; struct UnBCL::String *
0x180267226  mov     rcx, rax; struct UnBCL::String *
0x180267229  call    ?SPArePathsOnSameVolume@@YAHPEAVString@UnBCL@@0@Z; SPArePathsOnSameVolume(UnBCL::String *,UnBCL::String *)
0x18026722e  test    eax, eax
0x180267230  jnz     loc_180267478
0x180267236  call    cs:__imp_GetLastError
0x18026723c  mov     esi, eax
0x18026723e  call    cs:__imp_CurrentIP
0x180267244  mov     rdi, rax
0x180267247  lea     rcx, [rsp+268h+var_158]
0x18026724f  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180267255  mov     rcx, rax
0x180267258  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18026725e  mov     rbx, rax
0x180267261  mov     rcx, r14
0x180267264  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18026726a  mov     rcx, rax
0x18026726d  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180267273  mov     r9, rbx
0x180267276  mov     r8, rax
0x180267279  lea     rdx, aAttemptingToMo_0; "Attempting to move/copy/merge %s to %s"
0x180267280  mov     ecx, 4000000h; unsigned int
0x180267285  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18026728a  mov     [rsp+268h+var_218], r15d
0x18026728f  mov     [rsp+268h+var_220], r15
0x180267294  mov     dword ptr [rsp+268h+var_228], esi
0x180267298  mov     [rsp+268h+var_230], rdi
0x18026729d  lea     r14, aCsetupplatform_245; "CSetupPlatformPrivate::RollbackOnlineCo"...
0x1802672a4  mov     [rsp+268h+var_238], r14
0x1802672a9  lea     rsi, aBaseNtsetupSet_35; "base\\ntsetup\\setupplatform\\lib\\priv"...
0x1802672b0  mov     [rsp+268h+var_240], rsi
0x1802672b5  mov     dword ptr [rsp+268h+var_248], 3E5h
0x1802672bd  xor     r9d, r9d
0x1802672c0  lea     r12, aD_0; "D"
0x1802672c7  mov     r8, r12
0x1802672ca  mov     r13d, 0C8000h
0x1802672d0  mov     edx, r13d
0x1802672d3  mov     rcx, rax
0x1802672d6  call    cs:__imp_WdsSetupLogMessageW
0x1802672dc  lea     rcx, [rsp+268h+var_158]
0x1802672e4  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1802672ea  mov     rbx, rax
0x1802672ed  mov     rcx, [rsp+268h+lpMem]
0x1802672f2  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1802672f8  mov     dword ptr [rsp+268h+var_230], r15d
0x1802672fd  mov     dword ptr [rsp+268h+var_238], r15d
0x180267302  mov     ecx, 1
0x180267307  mov     dword ptr [rsp+268h+var_240], ecx
0x18026730b  mov     dword ptr [rsp+268h+var_248], ecx
0x18026730f  xor     r9d, r9d
0x180267312  xor     r8d, r8d
0x180267315  mov     rdx, rbx
0x180267318  mov     rcx, rax
0x18026731b  call    ?SPMoveFileWithShortName@@YAHPEAVString@UnBCL@@00PEAV?$ArrayList@PEAVString@UnBCL@@@2@HHHH@Z; SPMoveFileWithShortName(UnBCL::String *,UnBCL::String *,UnBCL::String *,UnBCL::ArrayList<UnBCL::String *> *,int,int,int,int)
0x180267320  test    eax, eax
0x180267322  jnz     short loc_18026738B
0x180267324  call    cs:__imp_GetLastError
0x18026732a  mov     edi, eax
0x18026732c  call    cs:__imp_CurrentIP
0x180267332  mov     rbx, rax
0x180267335  call    cs:__imp_GetLastError
0x18026733b  mov     r8d, eax
0x18026733e  lea     rdx, aErrorWhileExec; "Error while executing the move/copy/mer"...
0x180267345  mov     ecx, 3000000h; unsigned int
0x18026734a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18026734f  mov     [rsp+268h+var_218], r15d
0x180267354  mov     [rsp+268h+var_220], r15
0x180267359  mov     dword ptr [rsp+268h+var_228], edi
0x18026735d  mov     [rsp+268h+var_230], rbx
0x180267362  mov     [rsp+268h+var_238], r14
0x180267367  mov     [rsp+268h+var_240], rsi
0x18026736c  mov     dword ptr [rsp+268h+var_248], 3E8h
0x180267374  xor     r9d, r9d
0x180267377  mov     r8, r12
0x18026737a  mov     edx, r13d
0x18026737d  mov     rcx, rax
0x180267380  call    cs:__imp_WdsSetupLogMessageW
0x180267386  jmp     loc_18026748C
0x18026738b  call    cs:__imp_GetLastError
0x180267391  mov     edi, eax
0x180267393  call    cs:__imp_CurrentIP
0x180267399  mov     rbx, rax
0x18026739c  lea     rcx, [rsp+268h+var_158]
0x1802673a4  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802673aa  mov     rcx, rax
0x1802673ad  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802673b3  mov     r8, rax
0x1802673b6  lea     rdx, aMoveWasSuccess; "Move was successful, resetting the roll"...
0x1802673bd  mov     ecx, 4000000h; unsigned int
0x1802673c2  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1802673c7  mov     [rsp+268h+var_218], r15d
0x1802673cc  mov     [rsp+268h+var_220], r15
0x1802673d1  mov     dword ptr [rsp+268h+var_228], edi
0x1802673d5  mov     [rsp+268h+var_230], rbx
0x1802673da  mov     [rsp+268h+var_238], r14
0x1802673df  mov     [rsp+268h+var_240], rsi
0x1802673e4  mov     dword ptr [rsp+268h+var_248], 3EDh
0x1802673ec  xor     r9d, r9d
0x1802673ef  mov     r8, r12
0x1802673f2  mov     edx, r13d
0x1802673f5  mov     rcx, rax
0x1802673f8  call    cs:__imp_WdsSetupLogMessageW
0x1802673fe  mov     ecx, 18h
0x180267403  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180267409  mov     rbx, rax
0x18026740c  mov     qword ptr [rsp+268h+FileName], rax
0x180267414  test    rax, rax
0x180267417  jz      short loc_18026743F
0x180267419  lea     rcx, [rsp+268h+var_158]
0x180267421  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180267427  mov     rdx, rax
0x18026742a  mov     rcx, rbx
0x18026742d  call    cs:__imp_??0String@UnBCL@@QEAA@PEBV01@@Z; UnBCL::String::String(UnBCL::String const *)
0x180267433  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x18026743a  mov     [rbx], rax
0x18026743d  jmp     short loc_180267442
0x18026743f  mov     rbx, r15
0x180267442  mov     rdx, rbx
0x180267445  lea     rcx, [rsp+268h+UnicodeString]
0x18026744d  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180267453  nop
0x180267454  lea     rdx, [rsp+268h+UnicodeString]
0x18026745c  mov     rcx, [rsp+268h+lpMem]
0x180267461  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180267467  nop
0x180267468  lea     rcx, [rsp+268h+UnicodeString]
0x180267470  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180267476  jmp     short loc_18026748C
0x180267478  lea     r14, aCsetupplatform_245; "CSetupPlatformPrivate::RollbackOnlineCo"...
0x18026747f  lea     r12, aD_0; "D"
0x180267486  mov     r13d, 0C8000h
0x18026748c  lea     rdx, aSafeos; "SafeOS"
0x180267493  lea     rcx, [rsp+268h+var_148]
0x18026749b  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1802674a1  mov     rbx, rax
0x1802674a4  mov     rcx, [rsp+268h+var_1A0]
0x1802674ac  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1802674b2  mov     rdx, rbx
0x1802674b5  mov     rcx, rax
0x1802674b8  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1802674be  mov     rdx, rax
0x1802674c1  lea     rcx, [rsp+268h+var_1F0]
0x1802674c6  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802674cc  nop
0x1802674cd  lea     rcx, [rsp+268h+var_148]
0x1802674d5  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1802674db  lea     rdx, aBootstatDat; "bootstat.dat"
0x1802674e2  lea     rcx, [rsp+268h+FileName]
0x1802674ea  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1802674f0  mov     rbx, rax
0x1802674f3  lea     rcx, [rsp+268h+var_1F0]
0x1802674f8  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1802674fe  mov     rdx, rbx
0x180267501  mov     rcx, rax
0x180267504  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x18026750a  mov     rdx, rax
0x18026750d  lea     rcx, [rsp+268h+UnicodeString]
0x180267515  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18026751b  nop
0x18026751c  lea     rdx, [rsp+268h+UnicodeString]
0x180267524  lea     rcx, [rsp+268h+var_1F0]
0x180267529  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x18026752f  nop
0x180267530  lea     rcx, [rsp+268h+UnicodeString]
0x180267538  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18026753e  nop
0x18026753f  lea     rcx, [rsp+268h+FileName]
0x180267547  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18026754d  lea     rcx, [rsp+268h+var_1F0]
0x180267552  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180267558  mov     rcx, rax
0x18026755b  call    cs:__imp_?Exists@File@UnBCL@@SAHPEBVString@2@@Z; UnBCL::File::Exists(UnBCL::String const *)
0x180267561  test    eax, eax
0x180267563  jz      loc_180267953
0x180267569  lea     rcx, [rsp+268h+var_168]
0x180267571  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180267577  mov     rcx, rax
0x18026757a  call    cs:__imp_?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z; UnBCL::Directory::Exists(UnBCL::String const *)
0x180267580  test    eax, eax
0x180267582  jnz     short loc_1802675E9
0x180267584  lea     rcx, [rsp+268h+var_168]
0x18026758c  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180267592  mov     rcx, rax
0x180267595  call    cs:__imp_?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z; UnBCL::Directory::CreateDir(UnBCL::String const *)
0x18026759b  mov     rdx, rax
0x18026759e  lea     rcx, [rsp+268h+UnicodeString]
  ... truncated ...
```
