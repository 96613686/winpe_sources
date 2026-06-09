# CSetupPlatformCheckpoint::CopyLogFiles(int,ushort,UnBCL::String *,UnBCL::String *,UnBCL::String *)

- ea: `0x1802a1140`
- end: `0x1802a25f9`
- name: `?CopyLogFiles@CSetupPlatformCheckpoint@@IEAAXHGPEAVString@UnBCL@@00@Z`
- size: `5305`
- prototype: `void __usercall(CSetupPlatformCheckpoint *__hidden this@<rcx>, int@<edx>, unsigned __int16@<r8w>, struct UnBCL::String *@<r9>, struct UnBCL::String *, struct UnBCL::String *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1802aa1e0`

## callees

- `0x18001413d`
- `0x1800197c0`
- `0x180057dec`
- `0x1800c2e14`
- `0x180156484`
- `0x18029fc74`
- `0x1802a0158`
- `0x1802a1140`
- `0x18047c5d4`
- `0x18047c9fc`
- `0x180509010`

## import_xrefs

- `msvcrt!iswalpha` at `0x1802a128f`
- `msvcrt!iswalpha` at `0x1802a128f`
- `KERNEL32!GetLastError` at `0x1802a1370`
- `KERNEL32!GetLastError` at `0x1802a154b`
- `KERNEL32!GetLastError` at `0x1802a24a1`
- `KERNEL32!GetLastError` at `0x1802a2521`
- `KERNEL32!GetLastError` at `0x1802a252b`
- `KERNEL32!GetLastError` at `0x1802a1370`
- `KERNEL32!GetLastError` at `0x1802a154b`
- `KERNEL32!GetLastError` at `0x1802a24a1`
- `KERNEL32!GetLastError` at `0x1802a2521`
- `KERNEL32!GetLastError` at `0x1802a252b`
- `KERNEL32!GetFileAttributesW` at `0x1802a15e9`
- `KERNEL32!GetFileAttributesW` at `0x1802a15e9`
- `unbcl!?Exists@File@UnBCL@@SAHPEBVString@2@@Z` at `0x1802a11a8`
- `unbcl!?Exists@File@UnBCL@@SAHPEBVString@2@@Z` at `0x1802a14db`
- `unbcl!?Exists@File@UnBCL@@SAHPEBVString@2@@Z` at `0x1802a11a8`
- `unbcl!?Exists@File@UnBCL@@SAHPEBVString@2@@Z` at `0x1802a14db`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a12dc`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a1331`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a145e`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a1509`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a162f`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a170b`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a1750`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a19e6`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a1a2b`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a1cdc`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a1da9`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a1f0f`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a218e`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a2253`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a2318`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a23dd`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a12dc`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a1331`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a145e`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a1509`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a162f`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a170b`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a1750`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a19e6`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a1a2b`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a1cdc`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a1da9`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a1f0f`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a218e`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a2253`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a2318`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802a23dd`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802a17e1`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802a1805`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802a18b1`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802a18d2`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802a1ab2`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802a1ad6`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802a1b85`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802a1ba9`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802a1dcc`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802a1e06`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802a1e27`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802a1f96`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802a1fb7`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802a2079`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802a209a`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802a17e1`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802a1805`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802a18b1`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802a18d2`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802a1ab2`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802a1ad6`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802a1b85`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802a1ba9`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802a1dcc`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802a1e06`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802a1e27`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802a1f96`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802a1fb7`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802a2079`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x1802a209a`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a147e`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a148f`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a1691`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a16a2`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a1814`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a1825`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a18e1`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a18f2`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a1ae5`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a1af6`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a1bb8`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a1bc9`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a1d38`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a1d49`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a1e36`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a1fc6`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a1fd7`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a20a9`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a20ba`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a21ea`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a21fb`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a22af`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a22c0`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a2374`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a2385`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a2439`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a244a`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a147e`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a148f`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a1691`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a16a2`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a1814`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a1825`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a18e1`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a18f2`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a1ae5`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a1af6`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a1bb8`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a1bc9`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a1d38`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a1d49`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a1e36`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a1fc6`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a1fd7`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a20a9`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a20ba`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a21ea`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a21fb`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a22af`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a22c0`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a2374`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a2385`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a2439`
- `unbcl!??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ` at `0x1802a244a`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802a1663`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802a179a`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802a1a72`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802a1d0d`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802a1f40`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802a21bf`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802a2284`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802a2349`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802a240e`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802a1663`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802a179a`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802a1a72`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802a1d0d`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802a1f40`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802a21bf`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802a2284`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802a2349`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802a240e`
- `unbcl!?get_P@?$SmartPtr@VEncoding@UnBCL@@@UnBCL@@QEBAPEAVEncoding@2@XZ` at `0x1802a11f1`
- `unbcl!?get_P@?$SmartPtr@VEncoding@UnBCL@@@UnBCL@@QEBAPEAVEncoding@2@XZ` at `0x1802a11f1`
- `unbcl!??0StreamReader@UnBCL@@QEAA@PEBVString@1@PEAVEncoding@1@@Z` at `0x1802a1204`
- `unbcl!??0StreamReader@UnBCL@@QEAA@PEBVString@1@PEAVEncoding@1@@Z` at `0x1802a1204`
- `unbcl!??1?$SmartPtr@VEncoding@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802a1412`
- `unbcl!??1?$SmartPtr@VEncoding@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802a1412`
- `unbcl!??0?$SmartPtr@VEncoding@UnBCL@@@UnBCL@@QEAA@PEAVEncoding@1@@Z` at `0x1802a11c7`
- `unbcl!??0?$SmartPtr@VEncoding@UnBCL@@@UnBCL@@QEAA@PEAVEncoding@1@@Z` at `0x1802a11c7`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802a1266`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802a1428`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802a1266`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802a1428`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802a119e`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802a119e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a1683`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a17ba`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a1864`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a1873`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a1882`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a188e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a1931`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a193d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a194c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a195b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a1979`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a1997`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a1a8f`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a1b35`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a1b44`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a1b53`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a1b62`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a1c08`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a1c17`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a1c26`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a1c35`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a1c53`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a1c71`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a1d2a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a1e7a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a1e86`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a1e95`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a1ea4`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a1eb3`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a1ec2`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a1f5d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a2016`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a2022`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802a2031`

## string_xrefs

- `0x1802a254b`: `Rollback folder %s does not exist. Error: 0x%08X`
- `0x1802a25b8`: `Rollback folder not found`
- `0x1802a13b1`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a15b1`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a24e2`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a2574`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802a1381`: `CSetupPlatformCheckpoint::CopyLogFiles: Cannot locate original log folder. Did we even get this far?`
- `0x1802a24b2`: `CSetupPlatformCheckpoint::CopyLogFiles: Invalid parameters.`
- `0x1802a13a5`: `CSetupPlatformCheckpoint::CopyLogFiles`
- `0x1802a15a5`: `CSetupPlatformCheckpoint::CopyLogFiles`
- `0x1802a24d6`: `CSetupPlatformCheckpoint::CopyLogFiles`
- `0x1802a16f4`: `System32\LogFiles\WMI`
- `0x1802a161f`: `ProgramData\Microsoft\Windows\WER\ReportQueue`
- `0x1802a25cd`: `void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class UnBCL::String *,class UnBCL::String *)`
- `0x1802a1581`: `CSetupPlatformCheckpoint::CopyLogFiles: Cannot locate log restore file "%s" or log marker file "%s". Did we even get this far?`
- `0x1802a1a14`: `system32\inetsrv\config`
- `0x1802a1a43`: `applicationHost.config`
- `0x1802a1768`: `service.0.etl`
- `0x1802a223c`: `system32\winevt\logs`
- `0x1802a2177`: `system32\logfiles\scm`
- `0x1802a23c6`: `security\logs`

## pseudocode

```c
// Hidden C++ exception states: #wind=134
void __fastcall CSetupPlatformCheckpoint::CopyLogFiles(
        CSetupPlatformCheckpoint *this,
        __int64 a2,
        unsigned __int16 a3,
        struct UnBCL::String *a4,
        struct UnBCL::String *a5,
        struct UnBCL::String *a6)
{
  UnBCL::String *v6; // r14
  unsigned int v7; // r13d
  OSRollbackService::CCheckpoint *v8; // r12
  RollbackException *v9; // r15
  __int64 Unicode; // rax
  UnBCL::StreamReader *v11; // rbx
  struct UnBCL::Encoding *P; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  UnBCL::String *v15; // rax
  wint_t *CString; // rax
  UnBCL::String *v17; // rax
  UnBCL::String *v18; // rax
  const unsigned __int16 *v19; // rax
  struct UnBCL::String *v20; // rax
  UnBCL::String *v21; // rax
  const unsigned __int16 *v22; // rax
  struct UnBCL::String *v23; // rax
  DWORD LastError; // edi
  __int64 v25; // rbx
  struct tagLOG_PARTIAL_MSG *v26; // rax
  struct UnBCL::String *v27; // rax
  const struct UnBCL::String *v28; // rdi
  const struct UnBCL::String *v29; // rax
  OSRollbackService::CCheckpoint *v30; // rcx
  struct UnBCL::String *v31; // rax
  DWORD v32; // esi
  __int64 v33; // rdi
  const char *v34; // rbx
  const char *v35; // rax
  struct tagLOG_PARTIAL_MSG *v36; // rax
  const WCHAR *v37; // rax
  unsigned int v38; // esi
  unsigned int v39; // ebx
  struct UnBCL::String *v40; // rax
  const struct UnBCL::String *v41; // rax
  struct UnBCL::String *v42; // rax
  const struct UnBCL::String *v43; // rdi
  const struct UnBCL::String *v44; // rax
  OSRollbackService::CCheckpoint *v45; // rcx
  struct UnBCL::String *v46; // rax
  struct UnBCL::String *v47; // rax
  const struct UnBCL::String *v48; // rax
  struct UnBCL::String *v49; // rax
  const struct UnBCL::String *v50; // rax
  const struct UnBCL::String *v51; // rax
  const struct UnBCL::String *v52; // rsi
  const struct UnBCL::String *v53; // rax
  const struct UnBCL::String *v54; // rdx
  const struct UnBCL::String *v55; // rdx
  const struct UnBCL::String *v56; // rsi
  const struct UnBCL::String *v57; // rax
  struct UnBCL::String *v58; // rax
  struct UnBCL::String *v59; // rax
  const struct UnBCL::String *v60; // rax
  struct UnBCL::String *v61; // rax
  const struct UnBCL::String *v62; // rax
  const struct UnBCL::String *v63; // rax
  const struct UnBCL::String *v64; // rsi
  const struct UnBCL::String *v65; // rax
  const struct UnBCL::String *v66; // rdx
  const struct UnBCL::String *v67; // rdx
  const struct UnBCL::String *v68; // rsi
  const struct UnBCL::String *v69; // rax
  struct UnBCL::String *v70; // rax
  const struct UnBCL::String *v71; // rax
  struct UnBCL::String *v72; // rax
  const struct UnBCL::String *v73; // rsi
  const struct UnBCL::String *v74; // rax
  OSRollbackService::CCheckpoint *v75; // rcx
  struct UnBCL::String *v76; // rax
  const struct UnBCL::String *v77; // rax
  const struct UnBCL::String *v78; // rax
  const struct UnBCL::String *v79; // rax
  struct UnBCL::String *v80; // rax
  const struct UnBCL::String *v81; // rax
  struct UnBCL::String *v82; // rax
  const struct UnBCL::String *v83; // rax
  const struct UnBCL::String *v84; // rax
  const struct UnBCL::String *v85; // rsi
  const struct UnBCL::String *v86; // rax
  const struct UnBCL::String *v87; // rdx
  const struct UnBCL::String *v88; // rdx
  const struct UnBCL::String *v89; // rdi
  const struct UnBCL::String *v90; // rax
  struct UnBCL::String *v91; // rax
  const struct UnBCL::String *v92; // rax
  struct UnBCL::String *v93; // rax
  const struct UnBCL::String *v94; // rdi
  const struct UnBCL::String *v95; // rax
  OSRollbackService::CCheckpoint *v96; // rcx
  struct UnBCL::String *v97; // rax
  const struct UnBCL::String *v98; // rax
  struct UnBCL::String *v99; // rax
  const struct UnBCL::String *v100; // rdi
  const struct UnBCL::String *v101; // rax
  OSRollbackService::CCheckpoint *v102; // rcx
  struct UnBCL::String *v103; // rax
  const struct UnBCL::String *v104; // rax
  struct UnBCL::String *v105; // rax
  const struct UnBCL::String *v106; // rdi
  const struct UnBCL::String *v107; // rax
  OSRollbackService::CCheckpoint *v108; // rcx
  struct UnBCL::String *v109; // rax
  const struct UnBCL::String *v110; // rax
  struct UnBCL::String *v111; // rax
  const struct UnBCL::String *v112; // rbx
  const struct UnBCL::String *v113; // rax
  OSRollbackService::CCheckpoint *v114; // rcx
  DWORD v115; // edi
  __int64 v116; // rbx
  struct tagLOG_PARTIAL_MSG *v117; // rax
  DWORD v118; // r12d
  DWORD v119; // edi
  __int64 v120; // rbx
  const char *v121; // rax
  struct tagLOG_PARTIAL_MSG *v122; // rax
  RollbackException *v123; // rax
  struct UnBCL::Exception *v124; // rsi
  DWORD v125; // edi
  __int64 v126; // rbx
  UnBCL::String *v127; // rax
  const char *v128; // rax
  struct tagLOG_PARTIAL_MSG *v129; // rax
  const WCHAR *v130; // rax
  DWORD v131; // r14d
  DWORD v132; // edi
  __int64 v133; // rbx
  const char *v134; // rax
  struct tagLOG_PARTIAL_MSG *v135; // rax
  RollbackException *v136; // rax
  const unsigned __int16 *v137; // r8
  struct UnBCL::Exception *v138; // rsi
  DWORD v139; // edi
  __int64 v140; // rbx
  UnBCL::String *v141; // rax
  const char *v142; // rax
  struct tagLOG_PARTIAL_MSG *v143; // rax
  const WCHAR *v144; // rax
  DWORD v145; // r14d
  DWORD v146; // edi
  __int64 v147; // rbx
  const char *v148; // rax
  struct tagLOG_PARTIAL_MSG *v149; // rax
  RollbackException *v150; // rax
  const unsigned __int16 *v151; // r8
  struct UnBCL::Exception *v152; // rsi
  DWORD v153; // edi
  __int64 v154; // rbx
  UnBCL::String *v155; // rax
  const char *v156; // rax
  struct tagLOG_PARTIAL_MSG *v157; // rax
  const WCHAR *v158; // rax
  DWORD v159; // r14d
  DWORD v160; // edi
  __int64 v161; // rbx
  const char *v162; // rax
  struct tagLOG_PARTIAL_MSG *v163; // rax
  RollbackException *v164; // rax
  const unsigned __int16 *v165; // r8
  struct UnBCL::Exception *v166; // rsi
  DWORD v167; // edi
  __int64 v168; // rbx
  UnBCL::String *v169; // rax
  const char *v170; // rax
  struct tagLOG_PARTIAL_MSG *v171; // rax
  const WCHAR *v172; // rax
  DWORD v173; // r14d
  DWORD v174; // edi
  __int64 v175; // rbx
  const char *v176; // rax
  struct tagLOG_PARTIAL_MSG *v177; // rax
  RollbackException *v178; // rax
  const unsigned __int16 *v179; // r8
  struct UnBCL::Exception *v180; // rsi
  DWORD v181; // edi
  __int64 v182; // rbx
  UnBCL::String *v183; // rax
  const char *v184; // rax
  struct tagLOG_PARTIAL_MSG *v185; // rax
  const WCHAR *v186; // rax
  DWORD v187; // r14d
  DWORD v188; // edi
  __int64 v189; // rbx
  const char *v190; // rax
  struct tagLOG_PARTIAL_MSG *v191; // rax
  RollbackException *v192; // rax
  const unsigned __int16 *v193; // r8
  struct UnBCL::Exception *v194; // rsi
  DWORD v195; // edi
  __int64 v196; // rbx
  UnBCL::String *v197; // rax
  const char *v198; // rax
  struct tagLOG_PARTIAL_MSG *v199; // rax
  const WCHAR *v200; // rax
  DWORD v201; // r14d
  DWORD v202; // edi
  __int64 v203; // rbx
  const char *v204; // rax
  struct tagLOG_PARTIAL_MSG *v205; // rax
  RollbackException *v206; // rax
  const unsigned __int16 *v207; // r8
  struct UnBCL::Exception *v208; // rsi
  DWORD v209; // edi
  __int64 v210; // rbx
  UnBCL::String *v211; // rax
  const char *v212; // rax
  struct tagLOG_PARTIAL_MSG *v213; // rax
  const WCHAR *v214; // rax
  DWORD v215; // r14d
  DWORD v216; // edi
  __int64 v217; // rbx
  const char *v218; // rax
  struct tagLOG_PARTIAL_MSG *v219; // rax
  RollbackException *v220; // rax
  const unsigned __int16 *v221; // r8
  struct UnBCL::Exception *v222; // rsi
  DWORD v223; // edi
  __int64 v224; // rbx
  UnBCL::String *v225; // rax
  const char *v226; // rax
  struct tagLOG_PARTIAL_MSG *v227; // rax
  const WCHAR *v228; // rax
  DWORD v229; // r14d
  DWORD v230; // edi
  __int64 v231; // rbx
  const char *v232; // rax
  struct tagLOG_PARTIAL_MSG *v233; // rax
  RollbackException *v234; // rax
  const unsigned __int16 *v235; // r8
  struct UnBCL::Exception *v236; // rsi
  DWORD v237; // edi
  __int64 v238; // rbx
  UnBCL::String *v239; // rax
  const char *v240; // rax
  struct tagLOG_PARTIAL_MSG *v241; // rax
  const WCHAR *v242; // rax
  DWORD v243; // r14d
  DWORD v244; // edi
  __int64 v245; // rbx
  const char *v246; // rax
  struct tagLOG_PARTIAL_MSG *v247; // rax
  RollbackException *v248; // rax
  const unsigned __int16 *v249; // r8
  struct UnBCL::Exception *v250; // rsi
  DWORD v251; // edi
  __int64 v252; // rbx
  UnBCL::String *v253; // rax
  const char *v254; // rax
  struct tagLOG_PARTIAL_MSG *v255; // rax
  const WCHAR *v256; // rax
  DWORD v257; // r14d
  DWORD v258; // edi
  __int64 v259; // rbx
  const char *v260; // rax
  struct tagLOG_PARTIAL_MSG *v261; // rax
  RollbackException *v262; // rax
  const unsigned __int16 *v263; // r8
  struct UnBCL::Exception *v264; // rsi
  DWORD v265; // edi
  __int64 v266; // rbx
  UnBCL::String *v267; // rax
  const char *v268; // rax
  struct tagLOG_PARTIAL_MSG *v269; // rax
  const WCHAR *v270; // rax
  DWORD v271; // r14d
  DWORD v272; // edi
  __int64 v273; // rbx
  const char *v274; // rax
  struct tagLOG_PARTIAL_MSG *v275; // rax
  RollbackException *v276; // rax
  const unsigned __int16 *v277; // r8
  struct UnBCL::Exception *v278; // rsi
  DWORD v279; // edi
  __int64 v280; // rbx
  UnBCL::String *v281; // rax
  const char *v282; // rax
  struct tagLOG_PARTIAL_MSG *v283; // rax
  const WCHAR *v284; // rax
  DWORD v285; // r14d
  DWORD v286; // edi
  __int64 v287; // rbx
  const char *v288; // rax
  struct tagLOG_PARTIAL_MSG *v289; // rax
  RollbackException *v290; // rax
  const unsigned __int16 *v291; // r8
  unsigned int v292; // [rsp+60h] [rbp-278h] BYREF
  _BYTE v293[16]; // [rsp+68h] [rbp-270h] BYREF
  _BYTE v294[16]; // [rsp+78h] [rbp-260h] BYREF
  UnBCL::Exception *v295; // [rsp+88h] [rbp-250h]
  _BYTE v296[24]; // [rsp+90h] [rbp-248h] BYREF
  void **v297; // [rsp+A8h] [rbp-230h] BYREF
  __int64 v298; // [rsp+B0h] [rbp-228h]
  _BYTE v299[16]; // [rsp+C0h] [rbp-218h] BYREF
  _BYTE v300[24]; // [rsp+D0h] [rbp-208h] BYREF
  _QWORD v301[3]; // [rsp+E8h] [rbp-1F0h] BYREF
  _BYTE v302[24]; // [rsp+100h] [rbp-1D8h] BYREF
  _BYTE v303[24]; // [rsp+118h] [rbp-1C0h] BYREF
  _BYTE v304[24]; // [rsp+130h] [rbp-1A8h] BYREF
  _BYTE v305[16]; // [rsp+148h] [rbp-190h] BYREF
  __int64 v306; // [rsp+158h] [rbp-180h] BYREF
  __int64 v307; // [rsp+160h] [rbp-178h] BYREF
  __int64 v308; // [rsp+168h] [rbp-170h] BYREF
  __int64 v309; // [rsp+170h] [rbp-168h] BYREF
  __int64 v310; // [rsp+178h] [rbp-160h] BYREF
  __int64 v311; // [rsp+180h] [rbp-158h] BYREF
  __int64 v312; // [rsp+188h] [rbp-150h] BYREF
  __int64 v313; // [rsp+190h] [rbp-148h] BYREF
  __int64 v314; // [rsp+198h] [rbp-140h] BYREF
  __int64 v315; // [rsp+1A0h] [rbp-138h] BYREF
  __int64 v316; // [rsp+1A8h] [rbp-130h] BYREF
  __int64 v317; // [rsp+1B0h] [rbp-128h] BYREF
  __int64 v318; // [rsp+1B8h] [rbp-120h] BYREF
  __int64 v319; // [rsp+1C0h] [rbp-118h] BYREF
  __int64 v320; // [rsp+1C8h] [rbp-110h] BYREF
  __int64 v321; // [rsp+1D0h] [rbp-108h] BYREF
  __int64 v322; // [rsp+1D8h] [rbp-100h] BYREF
  __int64 v323; // [rsp+1E0h] [rbp-F8h] BYREF
  __int64 pExceptionObject; // [rsp+1E8h] [rbp-F0h] BYREF
  __int64 v325; // [rsp+1F0h] [rbp-E8h] BYREF
  __int64 v326; // [rsp+1F8h] [rbp-E0h] BYREF
  __int64 v327; // [rsp+200h] [rbp-D8h] BYREF
  __int64 v328; // [rsp+208h] [rbp-D0h] BYREF
  __int64 v329; // [rsp+210h] [rbp-C8h] BYREF
  _BYTE v330[24]; // [rsp+218h] [rbp-C0h] BYREF
  _QWORD v331[2]; // [rsp+230h] [rbp-A8h] BYREF
  struct UnBCL::Exception *v332; // [rsp+240h] [rbp-98h] BYREF
  struct UnBCL::Exception *v333; // [rsp+248h] [rbp-90h] BYREF
  struct UnBCL::Exception *v334; // [rsp+250h] [rbp-88h] BYREF
  struct UnBCL::Exception *v335; // [rsp+258h] [rbp-80h] BYREF
  struct UnBCL::Exception *v336; // [rsp+260h] [rbp-78h] BYREF
  struct UnBCL::Exception *v337; // [rsp+268h] [rbp-70h] BYREF
  struct UnBCL::Exception *v338; // [rsp+270h] [rbp-68h] BYREF
  struct UnBCL::Exception *v339; // [rsp+278h] [rbp-60h] BYREF
  struct UnBCL::Exception *v340; // [rsp+280h] [rbp-58h] BYREF
  struct UnBCL::Exception *v341; // [rsp+288h] [rbp-50h] BYREF
  struct UnBCL::Exception *v342; // [rsp+290h] [rbp-48h] BYREF
  struct UnBCL::Exception *v343; // [rsp+298h] [rbp-40h] BYREF
  unsigned int v345; // [rsp+2E8h] [rbp+10h]

  v331[1] = -2;
  v6 = a4;
  v7 = a3;
  v8 = this;
  v9 = 0;
  if ( a4 && a5 )
  {
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v305);
    if ( UnBCL::File::Exists(a5) )
    {
      try
      {
        Unicode = UnBCL::Encoding::GetUnicode();
        UnBCL::SmartPtr<UnBCL::Encoding>::SmartPtr<UnBCL::Encoding>(v296, Unicode);
        v11 = (UnBCL::StreamReader *)UnBCL::Object::operator new(0x128u);
        v301[0] = v11;
        if ( v11 )
        {
          P = (struct UnBCL::Encoding *)UnBCL::SmartPtr<UnBCL::Encoding>::get_P(v296);
          UnBCL::StreamReader::StreamReader(v11, a5, P);
          *((_QWORD *)v11 + 30) = &UnBCL::StreamReader::`local vftable'{for `UnBCL::Object'};
        }
        else
        {
          v11 = 0;
        }
        UnBCL::SmartPtr<UnBCL::StreamReader>::SmartPtr<UnBCL::StreamReader>(&v297, v11);
        v13 = v298 + *(int *)(*(_QWORD *)v298 + 12LL);
        v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v299, v14);
        if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v299) )
        {
          v15 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v299);
          CString = (wint_t *)UnBCL::String::get_CString(v15);
          if ( iswalpha(*CString)
            && (v17 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v299),
                UnBCL::String::get_CString(v17)[1] == 58) )
          {
            v18 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v299);
            v19 = UnBCL::String::get_CString(v18);
            v20 = UnBCL::String::Format(L"%c:\\%s", v7, v19 + 3);
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v301, v20);
            UnBCL::SmartPtr<UnBCL::String>::operator=(v305, v301);
          }
          else
          {
            v21 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v299);
            v22 = UnBCL::String::get_CString(v21);
            v23 = UnBCL::String::Format(L"%c:%s", v7, v22);
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v301, v23);
            UnBCL::SmartPtr<UnBCL::String>::operator=(v305, v301);
          }
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v301);
        }
        else
        {
          LastError = GetLastError();
          v25 = CurrentIP();
          v26 = ConstructPartialMsgW(
                  0x3000000u,
                  "CSetupPlatformCheckpoint::CopyLogFiles: Cannot locate original log folder. Did we even get this far?");
          WdsSetupLogMessageW(
            v26,
            819200,
            L"D",
            0,
            1044,
            L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
            L"CSetupPlatformCheckpoint::CopyLogFiles",
            v25,
            LastError,
            0,
            0);
        }
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v299);
        v297 = &UnBCL::SmartPtr<UnBCL::StreamReader>::`vftable';
        UnBCL::SmartPtr<OC::COptionalComponent>::DeAssign(&v297);
        UnBCL::SmartPtr<UnBCL::Encoding>::~SmartPtr<UnBCL::Encoding>(v296);
      }
      catch ( UnBCL::Exception *v334 )
      {
        v124 = v334;
        pExceptionLogFormat::pExceptionLogFormat(
          (pExceptionLogFormat *)&v292,
          0x2000000u,
          v334,
          "CSetupPlatformCheckpoint::CopyLogFiles: An error occurred while processing the log folder");
        UnBCL::Exception::AddStackTrace(
          v295,
          "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class UnBCL::Stri"
          "ng *,class UnBCL::String *)");
        v125 = GetLastError();
        v126 = CurrentIP();
        v127 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v293);
        v128 = (const char *)UnBCL::String::get_CString(v127);
        v129 = ConstructPartialMsgW(v292, "%s", v128);
        WdsSetupLogMessageW(
          v129,
          819200,
          L"D",
          0,
          1049,
          L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
          L"CSetupPlatformCheckpoint::CopyLogFiles",
          v126,
          v125,
          0,
          0);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v294);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v293);
        v130 = UnBCL::String::get_CString(a4);
        if ( GetFileAttributesW(v130) == -1 )
        {
          v131 = GetLastError();
          v132 = GetLastError();
          v133 = CurrentIP();
          v134 = (const char *)UnBCL::String::get_CString(a4);
          v135 = ConstructPartialMsgW(0x3000000u, "Rollback folder %s does not exist. Error: 0x%08X", v134, v131);
          WdsSetupLogMessageW(
            v135,
            819200,
            L"D",
            0,
            1051,
            L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
            L"CSetupPlatformCheckpoint::CopyLogFiles",
            v133,
            v132,
            0,
            0);
          v136 = (RollbackException *)UnBCL::Object::operator new(0x48u);
          if ( v124 )
          {
            if ( v136 )
              v136 = RollbackException::RollbackException(v136, v124, v137, v131);
            v322 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                     v136,
                     "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class "
                     "UnBCL::String *,class UnBCL::String *)");
            throw (RollbackException **)&v322;
          }
          if ( v136 )
            v136 = RollbackException::RollbackException(v136, v131, L"Rollback folder not found");
          v323 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                   v136,
                   "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class Un"
                   "BCL::String *,class UnBCL::String *)");
          throw (RollbackException **)&v323;
        }
        if ( v124 )
          (**(void (__fastcall ***)(struct UnBCL::Exception *, __int64))v124)(v124, 1);
        v8 = this;
        v6 = a4;
        LOWORD(v7) = a3;
      }
    }
    else if ( UnBCL::File::Exists(a6) )
    {
      v31 = UnBCL::String::Format(L"%c:\\%s\\%s\\%s", v7, L"$WINDOWS.~BT", L"Sources", L"Panther");
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v296, v31);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v305, v296);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v296);
    }
    else
    {
      v32 = GetLastError();
      v33 = CurrentIP();
      v34 = (const char *)UnBCL::String::get_CString(a6);
      v35 = (const char *)UnBCL::String::get_CString(a5);
      v36 = ConstructPartialMsgW(
              0x3000000u,
              "CSetupPlatformCheckpoint::CopyLogFiles: Cannot locate log restore file \"%s\" or log marker file \"%s\". D"
              "id we even get this far?",
              v35,
              v34);
      WdsSetupLogMessageW(
        v36,
        819200,
        L"D",
        0,
        1065,
        L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
        L"CSetupPlatformCheckpoint::CopyLogFiles",
        v33,
        v32,
        0,
        0);
      v37 = UnBCL::String::get_CString(v6);
      if ( GetFileAttributesW(v37) == -1 )
      {
        v118 = GetLastError();
        v119 = GetLastError();
        v120 = CurrentIP();
        v121 = (const char *)UnBCL::String::get_CString(v6);
        v122 = ConstructPartialMsgW(0x3000000u, "Rollback folder %s does not exist. Error: 0x%08X", v121, v118);
        WdsSetupLogMessageW(
          v122,
          819200,
          L"D",
          0,
          1066,
          L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
          L"CSetupPlatformCheckpoint::CopyLogFiles",
          v120,
          v119,
          0,
          0);
        v123 = (RollbackException *)UnBCL::Object::operator new(0x48u);
        if ( v123 )
          v9 = RollbackException::RollbackException(v123, v118, L"Rollback folder not found");
        pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                             v9,
                             "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String "
                             "*,class UnBCL::String *,class UnBCL::String *)");
        throw (RollbackException **)&pExceptionObject;
      }
    }
    if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v305) )
    {
      try
      {
        v38 = (unsigned __int16)v7;
        LODWORD(v301[0]) = (unsigned __int16)v7;
        v39 = (unsigned __int16)v7;
        v345 = (unsigned __int16)v7;
        v27 = UnBCL::String::Format(L"%c:\\%s\\%s", (unsigned __int16)v7, L"WINDOWS", L"Panther");
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v296, v27);
        v28 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator*(v305);
        v29 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator*(v296);
        OSRollbackService::CCheckpoint::MoveOrCopyDirectory(v30, v29, v28);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v296);
      }
      catch ( UnBCL::Exception *v335 )
      {
        v138 = v335;
        pExceptionLogFormat::pExceptionLogFormat(
          (pExceptionLogFormat *)&v292,
          0x2000000u,
          v335,
          "CSetupPlatformCheckpoint::CopyLogFiles: An error occurred while processing the log folder");
        UnBCL::Exception::AddStackTrace(
          v295,
          "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class UnBCL::Stri"
          "ng *,class UnBCL::String *)");
        v139 = GetLastError();
        v140 = CurrentIP();
        v141 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v293);
        v142 = (const char *)UnBCL::String::get_CString(v141);
        v143 = ConstructPartialMsgW(v292, "%s", v142);
        WdsSetupLogMessageW(
          v143,
          819200,
          L"D",
          0,
          1083,
          L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
          L"CSetupPlatformCheckpoint::CopyLogFiles",
          v140,
          v139,
          0,
          0);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v294);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v293);
        v144 = UnBCL::String::get_CString(a4);
        if ( GetFileAttributesW(v144) == -1 )
        {
          v145 = GetLastError();
          v146 = GetLastError();
          v147 = CurrentIP();
          v148 = (const char *)UnBCL::String::get_CString(a4);
          v149 = ConstructPartialMsgW(0x3000000u, "Rollback folder %s does not exist. Error: 0x%08X", v148, v145);
          WdsSetupLogMessageW(
            v149,
            819200,
            L"D",
            0,
            1085,
            L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
            L"CSetupPlatformCheckpoint::CopyLogFiles",
            v147,
            v146,
            0,
            0);
          v150 = (RollbackException *)UnBCL::Object::operator new(0x48u);
          if ( v138 )
          {
            if ( v150 )
              v150 = RollbackException::RollbackException(v150, v138, v151, v145);
            v325 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                     v150,
                     "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class "
                     "UnBCL::String *,class UnBCL::String *)");
            throw (RollbackException **)&v325;
          }
          if ( v150 )
            v150 = RollbackException::RollbackException(v150, v145, L"Rollback folder not found");
          v327 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                   v150,
                   "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class Un"
                   "BCL::String *,class UnBCL::String *)");
          throw (RollbackException **)&v327;
        }
        if ( v138 )
          (**(void (__fastcall ***)(struct UnBCL::Exception *, __int64))v138)(v138, 1);
        v8 = this;
        v6 = a4;
        LOWORD(v7) = a3;
        v38 = v301[0];
        v39 = v301[0];
      }
      try
      {
        v40 = UnBCL::String::Format(L"%c:\\%s", v38, L"ProgramData\\Microsoft\\Windows\\WER\\ReportQueue");
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v297, v40);
        v41 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v300, L"WER\\ReportQueue");
        v42 = UnBCL::Path::Combine(v6, v41);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v296, v42);
        UnBCL::String::~String((UnBCL::String *)v300);
        v43 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator*(v296);
        v44 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator*(&v297);
        OSRollbackService::CCheckpoint::MoveOrCopyDirectory(v45, v44, v43);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v296);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v297);
      }
      catch ( UnBCL::Exception *v336 )
      {
        v152 = v336;
        pExceptionLogFormat::pExceptionLogFormat(
          (pExceptionLogFormat *)&v292,
          0x2000000u,
          v336,
          "CSetupPlatformCheckpoint::CopyLogFiles: An error occurred while processing the WER log folders");
        UnBCL::Exception::AddStackTrace(
          v295,
          "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class UnBCL::Stri"
          "ng *,class UnBCL::String *)");
        v153 = GetLastError();
        v154 = CurrentIP();
        v155 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v293);
        v156 = (const char *)UnBCL::String::get_CString(v155);
        v157 = ConstructPartialMsgW(v292, "%s", v156);
        WdsSetupLogMessageW(
          v157,
          819200,
          L"D",
          0,
          1100,
          L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
          L"CSetupPlatformCheckpoint::CopyLogFiles",
          v154,
          v153,
          0,
          0);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v294);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v293);
        v158 = UnBCL::String::get_CString(a4);
        if ( GetFileAttributesW(v158) == -1 )
        {
          v159 = GetLastError();
          v160 = GetLastError();
          v161 = CurrentIP();
          v162 = (const char *)UnBCL::String::get_CString(a4);
          v163 = ConstructPartialMsgW(0x3000000u, "Rollback folder %s does not exist. Error: 0x%08X", v162, v159);
          WdsSetupLogMessageW(
            v163,
            819200,
            L"D",
            0,
            1102,
            L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
            L"CSetupPlatformCheckpoint::CopyLogFiles",
            v161,
            v160,
            0,
            0);
          v164 = (RollbackException *)UnBCL::Object::operator new(0x48u);
          if ( v152 )
          {
            if ( v164 )
              v164 = RollbackException::RollbackException(v164, v152, v165, v159);
            v320 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                     v164,
                     "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class "
                     "UnBCL::String *,class UnBCL::String *)");
            throw (RollbackException **)&v320;
          }
          if ( v164 )
            v164 = RollbackException::RollbackException(v164, v159, L"Rollback folder not found");
          v328 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                   v164,
                   "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class Un"
                   "BCL::String *,class UnBCL::String *)");
          throw (RollbackException **)&v328;
        }
        if ( v152 )
          (**(void (__fastcall ***)(struct UnBCL::Exception *, __int64))v152)(v152, 1);
        v8 = this;
        v6 = a4;
        LOWORD(v7) = a3;
        v39 = v345;
      }
      try
      {
        v46 = UnBCL::String::Format(L"%c:\\%s\\%s", v39, L"WINDOWS", L"System32\\LogFiles\\WMI");
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v299, v46);
        UnBCL::String::String((UnBCL::String *)v300, L"LwtNetLog.etl");
        v47 = UnBCL::String::Format(L"%c:\\%s\\%s", v39, L"WINDOWS", L"Logs\\NetSetup");
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v296, v47);
        UnBCL::String::String((UnBCL::String *)v302, L"service.0.etl");
        v48 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v330, L"NetLogs");
        v49 = UnBCL::Path::Combine(v6, v48);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v297, v49);
        UnBCL::String::~String((UnBCL::String *)v330);
        v50 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v292, &cchOriginalDestLength);
        UnBCL::String::String((UnBCL::String *)v303, v50);
        v51 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v304, &cchOriginalDestLength);
        UnBCL::String::String((UnBCL::String *)v301, v51);
        v52 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator*(&v297);
        v53 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator*(v299);
        OSRollbackService::CCheckpoint::MoveOrCopyFiles(
          v8,
          v53,
          v52,
          (const struct UnBCL::String *)v300,
          (const struct UnBCL::String *)v301,
          (const struct UnBCL::String *)v303);
        UnBCL::String::~String((UnBCL::String *)v301);
        UnBCL::String::~String((UnBCL::String *)v304);
        UnBCL::String::~String((UnBCL::String *)v303);
        UnBCL::String::~String((UnBCL::String *)&v292);
        v54 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v304, &cchOriginalDestLength);
        UnBCL::String::String((UnBCL::String *)v301, v54);
        v55 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v292, &cchOriginalDestLength);
        UnBCL::String::String((UnBCL::String *)v303, v55);
        v56 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator*(&v297);
        v57 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator*(v296);
        OSRollbackService::CCheckpoint::MoveOrCopyFiles(
          v8,
          v57,
          v56,
          (const struct UnBCL::String *)v302,
          (const struct UnBCL::String *)v303,
          (const struct UnBCL::String *)v301);
        UnBCL::String::~String((UnBCL::String *)v303);
        UnBCL::String::~String((UnBCL::String *)&v292);
        UnBCL::String::~String((UnBCL::String *)v301);
        UnBCL::String::~String((UnBCL::String *)v304);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v297);
        UnBCL::String::~String((UnBCL::String *)v302);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v296);
        UnBCL::String::~String((UnBCL::String *)v300);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v299);
      }
      catch ( UnBCL::Exception *v337 )
      {
        v166 = v337;
        pExceptionLogFormat::pExceptionLogFormat(
          (pExceptionLogFormat *)&v292,
          0x2000000u,
          v337,
          "CSetupPlatformCheckpoint::CopyLogFiles: An error occurred while processing the networking log folders");
        UnBCL::Exception::AddStackTrace(
          v295,
          "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class UnBCL::Stri"
          "ng *,class UnBCL::String *)");
        v167 = GetLastError();
        v168 = CurrentIP();
        v169 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v293);
        v170 = (const char *)UnBCL::String::get_CString(v169);
        v171 = ConstructPartialMsgW(v292, "%s", v170);
        WdsSetupLogMessageW(
          v171,
          819200,
          L"D",
          0,
          1123,
          L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
          L"CSetupPlatformCheckpoint::CopyLogFiles",
          v168,
          v167,
          0,
          0);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v294);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v293);
        v172 = UnBCL::String::get_CString(a4);
        if ( GetFileAttributesW(v172) == -1 )
        {
          v173 = GetLastError();
          v174 = GetLastError();
          v175 = CurrentIP();
          v176 = (const char *)UnBCL::String::get_CString(a4);
          v177 = ConstructPartialMsgW(0x3000000u, "Rollback folder %s does not exist. Error: 0x%08X", v176, v173);
          WdsSetupLogMessageW(
            v177,
            819200,
            L"D",
            0,
            1125,
            L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
            L"CSetupPlatformCheckpoint::CopyLogFiles",
            v175,
            v174,
            0,
            0);
          v178 = (RollbackException *)UnBCL::Object::operator new(0x48u);
          if ( v166 )
          {
            if ( v178 )
              v178 = RollbackException::RollbackException(v178, v166, v179, v173);
            v329 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                     v178,
                     "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class "
                     "UnBCL::String *,class UnBCL::String *)");
            throw (RollbackException **)&v329;
          }
          if ( v178 )
            v178 = RollbackException::RollbackException(v178, v173, L"Rollback folder not found");
          v331[0] = AddStackTraceToException<UnBCL::InvalidOperationException>(
                      v178,
                      "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class"
                      " UnBCL::String *,class UnBCL::String *)");
          throw (RollbackException **)v331;
        }
        if ( v166 )
          (**(void (__fastcall ***)(struct UnBCL::Exception *, __int64))v166)(v166, 1);
        v8 = this;
        v6 = a4;
        LOWORD(v7) = a3;
        v39 = v345;
      }
      try
      {
        v58 = UnBCL::String::Format(L"%c:\\%s", v39, L"WINDOWS");
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v299, v58);
        UnBCL::String::String((UnBCL::String *)v301, L"iis.log");
        v59 = UnBCL::String::Format(L"%c:\\%s\\%s", v39, L"WINDOWS", L"system32\\inetsrv\\config");
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v296, v59);
        UnBCL::String::String((UnBCL::String *)v303, L"applicationHost.config");
        v60 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v292, L"IISLogs");
        v61 = UnBCL::Path::Combine(v6, v60);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v297, v61);
        UnBCL::String::~String((UnBCL::String *)&v292);
        v62 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v330, &cchOriginalDestLength);
        UnBCL::String::String((UnBCL::String *)v302, v62);
        v63 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v304, &cchOriginalDestLength);
        UnBCL::String::String((UnBCL::String *)v300, v63);
        v64 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator*(&v297);
        v65 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator*(v299);
        OSRollbackService::CCheckpoint::MoveOrCopyFiles(
          v8,
          v65,
          v64,
          (const struct UnBCL::String *)v301,
          (const struct UnBCL::String *)v300,
          (const struct UnBCL::String *)v302);
        UnBCL::String::~String((UnBCL::String *)v300);
        UnBCL::String::~String((UnBCL::String *)v304);
        UnBCL::String::~String((UnBCL::String *)v302);
        UnBCL::String::~String((UnBCL::String *)v330);
        v66 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v330, &cchOriginalDestLength);
        UnBCL::String::String((UnBCL::String *)v302, v66);
        v67 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v304, &cchOriginalDestLength);
        UnBCL::String::String((UnBCL::String *)v300, v67);
        v68 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator*(&v297);
        v69 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator*(v296);
        OSRollbackService::CCheckpoint::MoveOrCopyFiles(
          v8,
          v69,
          v68,
          (const struct UnBCL::String *)v303,
          (const struct UnBCL::String *)v300,
          (const struct UnBCL::String *)v302);
        UnBCL::String::~String((UnBCL::String *)v300);
        UnBCL::String::~String((UnBCL::String *)v304);
        UnBCL::String::~String((UnBCL::String *)v302);
        UnBCL::String::~String((UnBCL::String *)v330);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v297);
        UnBCL::String::~String((UnBCL::String *)v303);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v296);
        UnBCL::String::~String((UnBCL::String *)v301);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v299);
      }
      catch ( UnBCL::Exception *v338 )
      {
        v180 = v338;
        pExceptionLogFormat::pExceptionLogFormat(
          (pExceptionLogFormat *)&v292,
          0x2000000u,
          v338,
          "CSetupPlatformCheckpoint::CopyLogFiles: An error occurred while processing the IIS log folders");
        UnBCL::Exception::AddStackTrace(
          v295,
          "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class UnBCL::Stri"
          "ng *,class UnBCL::String *)");
        v181 = GetLastError();
        v182 = CurrentIP();
        v183 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v293);
        v184 = (const char *)UnBCL::String::get_CString(v183);
        v185 = ConstructPartialMsgW(v292, "%s", v184);
        WdsSetupLogMessageW(
          v185,
          819200,
          L"D",
          0,
          1146,
          L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
          L"CSetupPlatformCheckpoint::CopyLogFiles",
          v182,
          v181,
          0,
          0);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v294);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v293);
        v186 = UnBCL::String::get_CString(a4);
        if ( GetFileAttributesW(v186) == -1 )
        {
          v187 = GetLastError();
          v188 = GetLastError();
          v189 = CurrentIP();
          v190 = (const char *)UnBCL::String::get_CString(a4);
          v191 = ConstructPartialMsgW(0x3000000u, "Rollback folder %s does not exist. Error: 0x%08X", v190, v187);
          WdsSetupLogMessageW(
            v191,
            819200,
            L"D",
            0,
            1148,
            L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
            L"CSetupPlatformCheckpoint::CopyLogFiles",
            v189,
            v188,
            0,
            0);
          v192 = (RollbackException *)UnBCL::Object::operator new(0x48u);
          if ( v180 )
          {
            if ( v192 )
              v192 = RollbackException::RollbackException(v192, v180, v193, v187);
            v306 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                     v192,
                     "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class "
                     "UnBCL::String *,class UnBCL::String *)");
            throw (RollbackException **)&v306;
          }
          if ( v192 )
            v192 = RollbackException::RollbackException(v192, v187, L"Rollback folder not found");
          v307 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                   v192,
                   "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class Un"
                   "BCL::String *,class UnBCL::String *)");
          throw (RollbackException **)&v307;
        }
        if ( v180 )
          (**(void (__fastcall ***)(struct UnBCL::Exception *, __int64))v180)(v180, 1);
        v8 = this;
        v6 = a4;
        LOWORD(v7) = a3;
        v39 = v345;
      }
      CSetupPlatformCheckpoint::CopyBootLogFiles(v8, 1, v7, v6);
      try
      {
        v70 = UnBCL::String::Format(L"%c:\\%s\\%s", v39, L"WINDOWS", L"Minidump");
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v297, v70);
        v71 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v292, L"Minidump");
        v72 = UnBCL::Path::Combine(v6, v71);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v296, v72);
        UnBCL::String::~String((UnBCL::String *)&v292);
        v73 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator*(v296);
        v74 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator*(&v297);
        OSRollbackService::CCheckpoint::MoveOrCopyDirectory(v75, v74, v73);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v296);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v297);
      }
      catch ( UnBCL::Exception *v339 )
      {
        v194 = v339;
        pExceptionLogFormat::pExceptionLogFormat(
          (pExceptionLogFormat *)&v292,
          0x2000000u,
          v339,
          "CSetupPlatformCheckpoint::CopyLogFiles: An error occurred while processing the minidump folder");
        UnBCL::Exception::AddStackTrace(
          v295,
          "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class UnBCL::Stri"
          "ng *,class UnBCL::String *)");
        v195 = GetLastError();
        v196 = CurrentIP();
        v197 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v293);
        v198 = (const char *)UnBCL::String::get_CString(v197);
        v199 = ConstructPartialMsgW(v292, "%s", v198);
        WdsSetupLogMessageW(
          v199,
          819200,
          L"D",
          0,
          1168,
          L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
          L"CSetupPlatformCheckpoint::CopyLogFiles",
          v196,
          v195,
          0,
          0);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v294);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v293);
        v200 = UnBCL::String::get_CString(a4);
        if ( GetFileAttributesW(v200) == -1 )
        {
          v201 = GetLastError();
          v202 = GetLastError();
          v203 = CurrentIP();
          v204 = (const char *)UnBCL::String::get_CString(a4);
          v205 = ConstructPartialMsgW(0x3000000u, "Rollback folder %s does not exist. Error: 0x%08X", v204, v201);
          WdsSetupLogMessageW(
            v205,
            819200,
            L"D",
            0,
            1170,
            L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
            L"CSetupPlatformCheckpoint::CopyLogFiles",
            v203,
            v202,
            0,
            0);
          v206 = (RollbackException *)UnBCL::Object::operator new(0x48u);
          if ( v194 )
          {
            if ( v206 )
              v206 = RollbackException::RollbackException(v206, v194, v207, v201);
            v308 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                     v206,
                     "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class "
                     "UnBCL::String *,class UnBCL::String *)");
            throw (RollbackException **)&v308;
          }
          if ( v206 )
            v206 = RollbackException::RollbackException(v206, v201, L"Rollback folder not found");
          v309 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                   v206,
                   "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class Un"
                   "BCL::String *,class UnBCL::String *)");
          throw (RollbackException **)&v309;
        }
        if ( v194 )
          (**(void (__fastcall ***)(struct UnBCL::Exception *, __int64))v194)(v194, 1);
        v8 = this;
        v6 = a4;
        v39 = v345;
      }
      try
      {
        v76 = UnBCL::String::Format(L"%c:\\%s", v39, L"WINDOWS");
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v296, v76);
        UnBCL::String::String((UnBCL::String *)&v297, v6);
        UnBCL::String::String((UnBCL::String *)v303, L"memory.dmp");
        v77 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v304, &cchOriginalDestLength);
        UnBCL::String::String((UnBCL::String *)v302, v77);
        v78 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v292, &cchOriginalDestLength);
        UnBCL::String::String((UnBCL::String *)v300, v78);
        v79 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator*(v296);
        OSRollbackService::CCheckpoint::MoveOrCopyFiles(
          v8,
          v79,
          (const struct UnBCL::String *)&v297,
          (const struct UnBCL::String *)v303,
          (const struct UnBCL::String *)v300,
          (const struct UnBCL::String *)v302);
        UnBCL::String::~String((UnBCL::String *)v300);
        UnBCL::String::~String((UnBCL::String *)&v292);
        UnBCL::String::~String((UnBCL::String *)v302);
        UnBCL::String::~String((UnBCL::String *)v304);
        UnBCL::String::~String((UnBCL::String *)v303);
        UnBCL::String::~String((UnBCL::String *)&v297);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v296);
      }
      catch ( UnBCL::Exception *v340 )
      {
        v208 = v340;
        pExceptionLogFormat::pExceptionLogFormat(
          (pExceptionLogFormat *)&v292,
          0x2000000u,
          v340,
          "CSetupPlatformCheckpoint::CopyLogFiles: An error occurred while processing the memory.dmp file");
        UnBCL::Exception::AddStackTrace(
          v295,
          "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class UnBCL::Stri"
          "ng *,class UnBCL::String *)");
        v209 = GetLastError();
        v210 = CurrentIP();
        v211 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v293);
        v212 = (const char *)UnBCL::String::get_CString(v211);
        v213 = ConstructPartialMsgW(v292, "%s", v212);
        WdsSetupLogMessageW(
          v213,
          819200,
          L"D",
          0,
          1185,
          L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
          L"CSetupPlatformCheckpoint::CopyLogFiles",
          v210,
          v209,
          0,
          0);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v294);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v293);
        v214 = UnBCL::String::get_CString(a4);
        if ( GetFileAttributesW(v214) == -1 )
        {
          v215 = GetLastError();
          v216 = GetLastError();
          v217 = CurrentIP();
          v218 = (const char *)UnBCL::String::get_CString(a4);
          v219 = ConstructPartialMsgW(0x3000000u, "Rollback folder %s does not exist. Error: 0x%08X", v218, v215);
          WdsSetupLogMessageW(
            v219,
            819200,
            L"D",
            0,
            1187,
            L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
            L"CSetupPlatformCheckpoint::CopyLogFiles",
            v217,
            v216,
            0,
            0);
          v220 = (RollbackException *)UnBCL::Object::operator new(0x48u);
          if ( v208 )
          {
            if ( v220 )
              v220 = RollbackException::RollbackException(v220, v208, v221, v215);
            v310 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                     v220,
                     "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class "
                     "UnBCL::String *,class UnBCL::String *)");
            throw (RollbackException **)&v310;
          }
          if ( v220 )
            v220 = RollbackException::RollbackException(v220, v215, L"Rollback folder not found");
          v311 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                   v220,
                   "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class Un"
                   "BCL::String *,class UnBCL::String *)");
          throw (RollbackException **)&v311;
        }
        if ( v208 )
          (**(void (__fastcall ***)(struct UnBCL::Exception *, __int64))v208)(v208, 1);
        v8 = this;
        v6 = a4;
        v39 = v345;
      }
      try
      {
        v80 = UnBCL::String::Format(L"%c:\\%s\\%s", v39, L"WINDOWS", L"inf");
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v299, v80);
        v81 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v292, L"setupapi");
        v82 = UnBCL::Path::Combine(v6, v81);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v297, v82);
        UnBCL::String::~String((UnBCL::String *)&v292);
        UnBCL::String::String((UnBCL::String *)v296, L"setupapi*.log");
        v83 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v304, &cchOriginalDestLength);
        UnBCL::String::String((UnBCL::String *)v302, v83);
        v84 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v292, &cchOriginalDestLength);
        UnBCL::String::String((UnBCL::String *)v300, v84);
        v85 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator*(&v297);
        v86 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator*(v299);
        OSRollbackService::CCheckpoint::MoveOrCopyFiles(
          v8,
          v86,
          v85,
          (const struct UnBCL::String *)v296,
          (const struct UnBCL::String *)v300,
          (const struct UnBCL::String *)v302);
        UnBCL::String::~String((UnBCL::String *)v300);
        UnBCL::String::~String((UnBCL::String *)&v292);
        UnBCL::String::~String((UnBCL::String *)v302);
        UnBCL::String::~String((UnBCL::String *)v304);
        UnBCL::String::String((UnBCL::String *)v303, L"netcfg*.etl");
        v87 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v304, &cchOriginalDestLength);
        UnBCL::String::String((UnBCL::String *)v302, v87);
        v88 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v292, &cchOriginalDestLength);
        UnBCL::String::String((UnBCL::String *)v300, v88);
        v89 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator*(&v297);
        v90 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator*(v299);
        OSRollbackService::CCheckpoint::MoveOrCopyFiles(
          v8,
          v90,
          v89,
          (const struct UnBCL::String *)v303,
          (const struct UnBCL::String *)v300,
          (const struct UnBCL::String *)v302);
        UnBCL::String::~String((UnBCL::String *)v300);
        UnBCL::String::~String((UnBCL::String *)&v292);
        UnBCL::String::~String((UnBCL::String *)v302);
        UnBCL::String::~String((UnBCL::String *)v304);
        UnBCL::String::~String((UnBCL::String *)v303);
        UnBCL::String::~String((UnBCL::String *)v296);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v297);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v299);
      }
      catch ( UnBCL::Exception *v341 )
      {
        v222 = v341;
        pExceptionLogFormat::pExceptionLogFormat(
          (pExceptionLogFormat *)&v292,
          0x2000000u,
          v341,
          "CSetupPlatformCheckpoint::CopyLogFiles: An error occurred while processing the setupapi log folder");
        UnBCL::Exception::AddStackTrace(
          v295,
          "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class UnBCL::Stri"
          "ng *,class UnBCL::String *)");
        v223 = GetLastError();
        v224 = CurrentIP();
        v225 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v293);
        v226 = (const char *)UnBCL::String::get_CString(v225);
        v227 = ConstructPartialMsgW(v292, "%s", v226);
        WdsSetupLogMessageW(
          v227,
          819200,
          L"D",
          0,
          1209,
          L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
          L"CSetupPlatformCheckpoint::CopyLogFiles",
          v224,
          v223,
          0,
          0);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v294);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v293);
        v228 = UnBCL::String::get_CString(a4);
        if ( GetFileAttributesW(v228) == -1 )
        {
          v229 = GetLastError();
          v230 = GetLastError();
          v231 = CurrentIP();
          v232 = (const char *)UnBCL::String::get_CString(a4);
          v233 = ConstructPartialMsgW(0x3000000u, "Rollback folder %s does not exist. Error: 0x%08X", v232, v229);
          WdsSetupLogMessageW(
            v233,
            819200,
            L"D",
            0,
            1211,
            L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
            L"CSetupPlatformCheckpoint::CopyLogFiles",
            v231,
            v230,
            0,
            0);
          v234 = (RollbackException *)UnBCL::Object::operator new(0x48u);
          if ( v222 )
          {
            if ( v234 )
              v234 = RollbackException::RollbackException(v234, v222, v235, v229);
            v312 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                     v234,
                     "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class "
                     "UnBCL::String *,class UnBCL::String *)");
            throw (RollbackException **)&v312;
          }
          if ( v234 )
            v234 = RollbackException::RollbackException(v234, v229, L"Rollback folder not found");
          v313 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                   v234,
                   "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class Un"
                   "BCL::String *,class UnBCL::String *)");
          throw (RollbackException **)&v313;
        }
        if ( v222 )
          (**(void (__fastcall ***)(struct UnBCL::Exception *, __int64))v222)(v222, 1);
        v6 = a4;
        v39 = v345;
      }
      try
      {
        v91 = UnBCL::String::Format(L"%c:\\%s\\%s", v39, L"WINDOWS", L"system32\\logfiles\\scm");
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v297, v91);
        v92 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v292, L"scmlogs");
        v93 = UnBCL::Path::Combine(v6, v92);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v296, v93);
        UnBCL::String::~String((UnBCL::String *)&v292);
        v94 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator*(v296);
        v95 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator*(&v297);
        OSRollbackService::CCheckpoint::MoveOrCopyDirectory(v96, v95, v94);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v296);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v297);
      }
      catch ( UnBCL::Exception *v342 )
      {
        v236 = v342;
        pExceptionLogFormat::pExceptionLogFormat(
          (pExceptionLogFormat *)&v292,
          0x2000000u,
          v342,
          "CSetupPlatformCheckpoint::CopyLogFiles: An error occurred while processing the SCM log folder");
        UnBCL::Exception::AddStackTrace(
          v295,
          "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class UnBCL::Stri"
          "ng *,class UnBCL::String *)");
        v237 = GetLastError();
        v238 = CurrentIP();
        v239 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v293);
        v240 = (const char *)UnBCL::String::get_CString(v239);
        v241 = ConstructPartialMsgW(v292, "%s", v240);
        WdsSetupLogMessageW(
          v241,
          819200,
          L"D",
          0,
          1225,
          L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
          L"CSetupPlatformCheckpoint::CopyLogFiles",
          v238,
          v237,
          0,
          0);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v294);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v293);
        v242 = UnBCL::String::get_CString(a4);
        if ( GetFileAttributesW(v242) == -1 )
        {
          v243 = GetLastError();
          v244 = GetLastError();
          v245 = CurrentIP();
          v246 = (const char *)UnBCL::String::get_CString(a4);
          v247 = ConstructPartialMsgW(0x3000000u, "Rollback folder %s does not exist. Error: 0x%08X", v246, v243);
          WdsSetupLogMessageW(
            v247,
            819200,
            L"D",
            0,
            1227,
            L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
            L"CSetupPlatformCheckpoint::CopyLogFiles",
            v245,
            v244,
            0,
            0);
          v248 = (RollbackException *)UnBCL::Object::operator new(0x48u);
          if ( v236 )
          {
            if ( v248 )
              v248 = RollbackException::RollbackException(v248, v236, v249, v243);
            v314 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                     v248,
                     "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class "
                     "UnBCL::String *,class UnBCL::String *)");
            throw (RollbackException **)&v314;
          }
          if ( v248 )
            v248 = RollbackException::RollbackException(v248, v243, L"Rollback folder not found");
          v315 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                   v248,
                   "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class Un"
                   "BCL::String *,class UnBCL::String *)");
          throw (RollbackException **)&v315;
        }
        if ( v236 )
          (**(void (__fastcall ***)(struct UnBCL::Exception *, __int64))v236)(v236, 1);
        v6 = a4;
        v39 = v345;
      }
      try
      {
        v97 = UnBCL::String::Format(L"%c:\\%s\\%s", v39, L"WINDOWS", L"system32\\winevt\\logs");
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v297, v97);
        v98 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v292, L"evtlogs");
        v99 = UnBCL::Path::Combine(v6, v98);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v296, v99);
        UnBCL::String::~String((UnBCL::String *)&v292);
        v100 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator*(v296);
        v101 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator*(&v297);
        OSRollbackService::CCheckpoint::MoveOrCopyDirectory(v102, v101, v100);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v296);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v297);
      }
      catch ( UnBCL::Exception *v343 )
      {
        v250 = v343;
        pExceptionLogFormat::pExceptionLogFormat(
          (pExceptionLogFormat *)&v292,
          0x2000000u,
          v343,
          "CSetupPlatformCheckpoint::CopyLogFiles: An error occurred while processing the event log folder");
        UnBCL::Exception::AddStackTrace(
          v295,
          "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class UnBCL::Stri"
          "ng *,class UnBCL::String *)");
        v251 = GetLastError();
        v252 = CurrentIP();
        v253 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v293);
        v254 = (const char *)UnBCL::String::get_CString(v253);
        v255 = ConstructPartialMsgW(v292, "%s", v254);
        WdsSetupLogMessageW(
          v255,
          819200,
          L"D",
          0,
          1241,
          L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
          L"CSetupPlatformCheckpoint::CopyLogFiles",
          v252,
          v251,
          0,
          0);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v294);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v293);
        v256 = UnBCL::String::get_CString(a4);
        if ( GetFileAttributesW(v256) == -1 )
        {
          v257 = GetLastError();
          v258 = GetLastError();
          v259 = CurrentIP();
          v260 = (const char *)UnBCL::String::get_CString(a4);
          v261 = ConstructPartialMsgW(0x3000000u, "Rollback folder %s does not exist. Error: 0x%08X", v260, v257);
          WdsSetupLogMessageW(
            v261,
            819200,
            L"D",
            0,
            1243,
            L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
            L"CSetupPlatformCheckpoint::CopyLogFiles",
            v259,
            v258,
            0,
            0);
          v262 = (RollbackException *)UnBCL::Object::operator new(0x48u);
          if ( v250 )
          {
            if ( v262 )
              v262 = RollbackException::RollbackException(v262, v250, v263, v257);
            v316 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                     v262,
                     "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class "
                     "UnBCL::String *,class UnBCL::String *)");
            throw (RollbackException **)&v316;
          }
          if ( v262 )
            v262 = RollbackException::RollbackException(v262, v257, L"Rollback folder not found");
          v317 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                   v262,
                   "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class Un"
                   "BCL::String *,class UnBCL::String *)");
          throw (RollbackException **)&v317;
        }
        if ( v250 )
          (**(void (__fastcall ***)(struct UnBCL::Exception *, __int64))v250)(v250, 1);
        v6 = a4;
        v39 = v345;
      }
      try
      {
        v103 = UnBCL::String::Format(L"%c:\\%s\\%s", v39, L"WINDOWS", L"Logs\\CBS");
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v297, v103);
        v104 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v292, L"CBSLogs");
        v105 = UnBCL::Path::Combine(v6, v104);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v296, v105);
        UnBCL::String::~String((UnBCL::String *)&v292);
        v106 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator*(v296);
        v107 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator*(&v297);
        OSRollbackService::CCheckpoint::MoveOrCopyDirectory(v108, v107, v106);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v296);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v297);
      }
      catch ( UnBCL::Exception *v332 )
      {
        v264 = v332;
        pExceptionLogFormat::pExceptionLogFormat(
          (pExceptionLogFormat *)&v292,
          0x2000000u,
          v332,
          "CSetupPlatformCheckpoint::CopyLogFiles: An error occurred while processing the CBS log folder");
        UnBCL::Exception::AddStackTrace(
          v295,
          "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class UnBCL::Stri"
          "ng *,class UnBCL::String *)");
        v265 = GetLastError();
        v266 = CurrentIP();
        v267 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v293);
        v268 = (const char *)UnBCL::String::get_CString(v267);
        v269 = ConstructPartialMsgW(v292, "%s", v268);
        WdsSetupLogMessageW(
          v269,
          819200,
          L"D",
          0,
          1256,
          L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
          L"CSetupPlatformCheckpoint::CopyLogFiles",
          v266,
          v265,
          0,
          0);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v294);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v293);
        v270 = UnBCL::String::get_CString(a4);
        if ( GetFileAttributesW(v270) == -1 )
        {
          v271 = GetLastError();
          v272 = GetLastError();
          v273 = CurrentIP();
          v274 = (const char *)UnBCL::String::get_CString(a4);
          v275 = ConstructPartialMsgW(0x3000000u, "Rollback folder %s does not exist. Error: 0x%08X", v274, v271);
          WdsSetupLogMessageW(
            v275,
            819200,
            L"D",
            0,
            1258,
            L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
            L"CSetupPlatformCheckpoint::CopyLogFiles",
            v273,
            v272,
            0,
            0);
          v276 = (RollbackException *)UnBCL::Object::operator new(0x48u);
          if ( v264 )
          {
            if ( v276 )
              v276 = RollbackException::RollbackException(v276, v264, v277, v271);
            v318 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                     v276,
                     "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class "
                     "UnBCL::String *,class UnBCL::String *)");
            throw (RollbackException **)&v318;
          }
          if ( v276 )
            v276 = RollbackException::RollbackException(v276, v271, L"Rollback folder not found");
          v319 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                   v276,
                   "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class Un"
                   "BCL::String *,class UnBCL::String *)");
          throw (RollbackException **)&v319;
        }
        if ( v264 )
          (**(void (__fastcall ***)(struct UnBCL::Exception *, __int64))v264)(v264, 1);
        v6 = a4;
        v39 = v345;
      }
      try
      {
        v109 = UnBCL::String::Format(L"%c:\\%s\\%s", v39, L"WINDOWS", L"security\\logs");
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v297, v109);
        v110 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v292, L"SECLogs");
        v111 = UnBCL::Path::Combine(v6, v110);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v296, v111);
        UnBCL::String::~String((UnBCL::String *)&v292);
        v112 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator*(v296);
        v113 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator*(&v297);
        OSRollbackService::CCheckpoint::MoveOrCopyDirectory(v114, v113, v112);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v296);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v297);
      }
      catch ( UnBCL::Exception *v333 )
      {
        v278 = v333;
        pExceptionLogFormat::pExceptionLogFormat(
          (pExceptionLogFormat *)&v292,
          0x2000000u,
          v333,
          "CSetupPlatformCheckpoint::CopyLogFiles: An error occurred while processing the security log folder");
        UnBCL::Exception::AddStackTrace(
          v295,
          "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class UnBCL::Stri"
          "ng *,class UnBCL::String *)");
        v279 = GetLastError();
        v280 = CurrentIP();
        v281 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v293);
        v282 = (const char *)UnBCL::String::get_CString(v281);
        v283 = ConstructPartialMsgW(v292, "%s", v282);
        WdsSetupLogMessageW(
          v283,
          819200,
          L"D",
          0,
          1271,
          L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
          L"CSetupPlatformCheckpoint::CopyLogFiles",
          v280,
          v279,
          0,
          0);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v294);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v293);
        v284 = UnBCL::String::get_CString(a4);
        if ( GetFileAttributesW(v284) == -1 )
        {
          v285 = GetLastError();
          v286 = GetLastError();
          v287 = CurrentIP();
          v288 = (const char *)UnBCL::String::get_CString(a4);
          v289 = ConstructPartialMsgW(0x3000000u, "Rollback folder %s does not exist. Error: 0x%08X", v288, v285);
          WdsSetupLogMessageW(
            v289,
            819200,
            L"D",
            0,
            1273,
            L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
            L"CSetupPlatformCheckpoint::CopyLogFiles",
            v287,
            v286,
            0,
            0);
          v290 = (RollbackException *)UnBCL::Object::operator new(0x48u);
          if ( v278 )
          {
            if ( v290 )
              v290 = RollbackException::RollbackException(v290, v278, v291, v285);
            v326 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                     v290,
                     "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class "
                     "UnBCL::String *,class UnBCL::String *)");
            throw (RollbackException **)&v326;
          }
          if ( v290 )
            v290 = RollbackException::RollbackException(v290, v285, L"Rollback folder not found");
          v321 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                   v290,
                   "void __cdecl CSetupPlatformCheckpoint::CopyLogFiles(int,unsigned short,class UnBCL::String *,class Un"
                   "BCL::String *,class UnBCL::String *)");
          throw (RollbackException **)&v321;
        }
        if ( v278 )
          (**(void (__fastcall ***)(struct UnBCL::Exception *, __int64))v278)(v278, 1);
      }
    }
    else
    {
      CSetupPlatformCheckpoint::CopyBootLogFiles(v8, 1, v7, v6);
    }
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v305);
  }
  else
  {
    v115 = GetLastError();
    v116 = CurrentIP();
    v117 = ConstructPartialMsgW(0x3000000u, "CSetupPlatformCheckpoint::CopyLogFiles: Invalid parameters.");
    WdsSetupLogMessageW(
      v117,
      819200,
      L"D",
      0,
      1015,
      L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
      L"CSetupPlatformCheckpoint::CopyLogFiles",
      v116,
      v115,
      0,
      0);
  }
}

```

## disassembly

```asm
0x1802a1140  mov     rax, rsp
0x1802a1143  mov     [rax+20h], r9
0x1802a1147  mov     [rax+18h], r8w
0x1802a114c  mov     [rax+10h], edx
0x1802a114f  mov     [rax+8], rcx
0x1802a1153  push    rbx
0x1802a1154  push    rsi
0x1802a1155  push    rdi
0x1802a1156  push    r12
0x1802a1158  push    r13
0x1802a115a  push    r14
0x1802a115c  push    r15
0x1802a115e  sub     rsp, 2A0h
0x1802a1165  mov     qword ptr [rax-0A0h], 0FFFFFFFFFFFFFFFEh
0x1802a1170  mov     r14, r9
0x1802a1173  movzx   r13d, r8w
0x1802a1177  mov     r12, rcx
0x1802a117a  xor     r15d, r15d
0x1802a117d  test    r9, r9
0x1802a1180  jz      loc_1802A24A1
0x1802a1186  mov     rdi, [rsp+2D8h+arg_20]
0x1802a118e  test    rdi, rdi
0x1802a1191  jz      loc_1802A24A1
0x1802a1197  lea     rcx, [rax-190h]
0x1802a119e  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x1802a11a4  nop
0x1802a11a5  mov     rcx, rdi
0x1802a11a8  call    cs:__imp_?Exists@File@UnBCL@@SAHPEBVString@2@@Z; UnBCL::File::Exists(UnBCL::String const *)
0x1802a11ae  test    eax, eax
0x1802a11b0  jz      loc_1802A14D3
0x1802a11b6  call    cs:__imp_?GetUnicode@Encoding@UnBCL@@SAPEAV12@XZ; UnBCL::Encoding::GetUnicode(void)
0x1802a11bc  mov     rdx, rax
0x1802a11bf  lea     rcx, [rsp+2D8h+var_248]
0x1802a11c7  call    cs:__imp_??0?$SmartPtr@VEncoding@UnBCL@@@UnBCL@@QEAA@PEAVEncoding@1@@Z; UnBCL::SmartPtr<UnBCL::Encoding>::SmartPtr<UnBCL::Encoding>(UnBCL::Encoding *)
0x1802a11cd  nop
0x1802a11ce  mov     ecx, 128h
0x1802a11d3  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1802a11d9  mov     rbx, rax
0x1802a11dc  mov     [rsp+2D8h+var_1F0], rax
0x1802a11e4  test    rax, rax
0x1802a11e7  jz      short loc_1802A121A
0x1802a11e9  lea     rcx, [rsp+2D8h+var_248]
0x1802a11f1  call    cs:__imp_?get_P@?$SmartPtr@VEncoding@UnBCL@@@UnBCL@@QEBAPEAVEncoding@2@XZ; UnBCL::SmartPtr<UnBCL::Encoding>::get_P(void)
0x1802a11f7  lea     r9d, [r15+1]
0x1802a11fb  mov     r8, rax
0x1802a11fe  mov     rdx, rdi
0x1802a1201  mov     rcx, rbx
0x1802a1204  call    cs:__imp_??0StreamReader@UnBCL@@QEAA@PEBVString@1@PEAVEncoding@1@@Z; UnBCL::StreamReader::StreamReader(UnBCL::String const *,UnBCL::Encoding *)
0x1802a120a  lea     rax, ??_SStreamReader@UnBCL@@6BObject@1@@; const UnBCL::StreamReader::`local vftable'{for `UnBCL::Object'}
0x1802a1211  mov     [rbx+0F0h], rax
0x1802a1218  jmp     short loc_1802A121D
0x1802a121a  mov     rbx, r15
0x1802a121d  mov     rdx, rbx
0x1802a1220  lea     rcx, [rsp+2D8h+var_230]
0x1802a1228  call    ??0?$SmartPtr@VStreamReader@UnBCL@@@UnBCL@@QEAA@PEAVStreamReader@1@@Z; UnBCL::SmartPtr<UnBCL::StreamReader>::SmartPtr<UnBCL::StreamReader>(UnBCL::StreamReader *)
0x1802a122d  nop
0x1802a122e  mov     rdx, [rsp+2D8h+var_228]
0x1802a1236  mov     rax, [rdx]
0x1802a1239  movsxd  rcx, dword ptr [rax+0Ch]
0x1802a123d  add     rcx, rdx
0x1802a1240  mov     rax, [rcx]
0x1802a1243  mov     rax, [rax+10h]
0x1802a1247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802a124c  mov     rdx, rax
0x1802a124f  lea     rcx, [rsp+2D8h+var_218]
0x1802a1257  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802a125d  nop
0x1802a125e  lea     rcx, [rsp+2D8h+var_218]
0x1802a1266  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1802a126c  test    rax, rax
0x1802a126f  jz      loc_1802A1370
0x1802a1275  lea     rcx, [rsp+2D8h+var_218]
0x1802a127d  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802a1283  mov     rcx, rax
0x1802a1286  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802a128c  movzx   ecx, word ptr [rax]; C
0x1802a128f  call    cs:__imp_iswalpha
0x1802a1295  test    eax, eax
0x1802a1297  jz      short loc_1802A130D
0x1802a1299  lea     rcx, [rsp+2D8h+var_218]
0x1802a12a1  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802a12a7  mov     rcx, rax
0x1802a12aa  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802a12b0  cmp     word ptr [rax+2], 3Ah ; ':'
0x1802a12b5  jnz     short loc_1802A130D
0x1802a12b7  lea     rcx, [rsp+2D8h+var_218]
0x1802a12bf  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802a12c5  mov     rcx, rax
0x1802a12c8  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802a12ce  lea     r8, [rax+6]
0x1802a12d2  mov     edx, r13d
0x1802a12d5  lea     rcx, aCS; "%c:\\%s"
0x1802a12dc  call    cs:__imp_?Format@String@UnBCL@@SAPEAV12@PEBGZZ; UnBCL::String::Format(ushort const *,...)
0x1802a12e2  mov     rdx, rax
0x1802a12e5  lea     rcx, [rsp+2D8h+var_1F0]
0x1802a12ed  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802a12f3  nop
0x1802a12f4  lea     rdx, [rsp+2D8h+var_1F0]
0x1802a12fc  lea     rcx, [rsp+2D8h+var_190]
0x1802a1304  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1802a130a  nop
0x1802a130b  jmp     short loc_1802A1360
0x1802a130d  lea     rcx, [rsp+2D8h+var_218]
0x1802a1315  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802a131b  mov     rcx, rax
0x1802a131e  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802a1324  mov     edx, r13d
0x1802a1327  mov     r8, rax
0x1802a132a  lea     rcx, aCS_2; "%c:%s"
0x1802a1331  call    cs:__imp_?Format@String@UnBCL@@SAPEAV12@PEBGZZ; UnBCL::String::Format(ushort const *,...)
0x1802a1337  mov     rdx, rax
0x1802a133a  lea     rcx, [rsp+2D8h+var_1F0]
0x1802a1342  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802a1348  nop
0x1802a1349  lea     rdx, [rsp+2D8h+var_1F0]
0x1802a1351  lea     rcx, [rsp+2D8h+var_190]
0x1802a1359  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1802a135f  nop
0x1802a1360  lea     rcx, [rsp+2D8h+var_1F0]
0x1802a1368  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802a136e  jmp     short loc_1802A13DE
0x1802a1370  call    cs:__imp_GetLastError
0x1802a1376  mov     edi, eax
0x1802a1378  call    cs:__imp_CurrentIP
0x1802a137e  mov     rbx, rax
0x1802a1381  lea     rdx, aCsetupplatform_117; "CSetupPlatformCheckpoint::CopyLogFiles:"...
0x1802a1388  mov     ecx, 3000000h; unsigned int
0x1802a138d  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1802a1392  mov     [rsp+2D8h+var_288], r15d
0x1802a1397  mov     [rsp+2D8h+var_290], r15
0x1802a139c  mov     [rsp+2D8h+var_298], edi
0x1802a13a0  mov     [rsp+2D8h+var_2A0], rbx
0x1802a13a5  lea     rsi, aCsetupplatform_109; "CSetupPlatformCheckpoint::CopyLogFiles"
0x1802a13ac  mov     [rsp+2D8h+var_2A8], rsi
0x1802a13b1  lea     rcx, aBaseNtsetupSet_64; "base\\ntsetup\\setupplatform\\lib\\roll"...
0x1802a13b8  mov     [rsp+2D8h+var_2B0], rcx
0x1802a13bd  mov     dword ptr [rsp+2D8h+var_2B8], 414h
0x1802a13c5  xor     r9d, r9d
0x1802a13c8  lea     r8, aD_0; "D"
0x1802a13cf  mov     edx, 0C8000h
0x1802a13d4  mov     rcx, rax
0x1802a13d7  call    cs:__imp_WdsSetupLogMessageW
0x1802a13dd  nop
0x1802a13de  lea     rcx, [rsp+2D8h+var_218]
0x1802a13e6  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802a13ec  nop
0x1802a13ed  lea     rax, ??_7?$SmartPtr@VStreamReader@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::StreamReader>::`vftable'
0x1802a13f4  mov     [rsp+2D8h+var_230], rax
0x1802a13fc  lea     rcx, [rsp+2D8h+var_230]
0x1802a1404  call    ?DeAssign@?$SmartPtr@VCOptionalComponent@OC@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<OC::COptionalComponent>::DeAssign(void)
0x1802a1409  nop
0x1802a140a  lea     rcx, [rsp+2D8h+var_248]
0x1802a1412  call    cs:__imp_??1?$SmartPtr@VEncoding@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::Encoding>::~SmartPtr<UnBCL::Encoding>(void)
0x1802a1418  nop
0x1802a1419  lea     rdi, aPanther; "Panther"
0x1802a1420  lea     rcx, [rsp+2D8h+var_190]
0x1802a1428  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1802a142e  test    rax, rax
0x1802a1431  jz      loc_1802A247C
0x1802a1437  movzx   esi, r13w
0x1802a143b  mov     dword ptr [rsp+2D8h+var_1F0], esi
0x1802a1442  mov     ebx, esi
0x1802a1444  mov     [rsp+2D8h+arg_8], ebx
0x1802a144b  mov     r9, rdi
0x1802a144e  lea     r8, aWindows_4; "WINDOWS"
0x1802a1455  mov     edx, esi
0x1802a1457  lea     rcx, aCSS; "%c:\\%s\\%s"
0x1802a145e  call    cs:__imp_?Format@String@UnBCL@@SAPEAV12@PEBGZZ; UnBCL::String::Format(ushort const *,...)
0x1802a1464  mov     rdx, rax
0x1802a1467  lea     rcx, [rsp+2D8h+var_248]
0x1802a146f  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802a1475  nop
0x1802a1476  lea     rcx, [rsp+2D8h+var_190]
0x1802a147e  call    cs:__imp_??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator*(void)
0x1802a1484  mov     rdi, rax
0x1802a1487  lea     rcx, [rsp+2D8h+var_248]
0x1802a148f  call    cs:__imp_??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator*(void)
0x1802a1495  mov     r8, rdi; struct UnBCL::String *
0x1802a1498  mov     rdx, rax; struct UnBCL::String *
0x1802a149b  call    ?MoveOrCopyDirectory@CCheckpoint@OSRollbackService@@IEAAHAEBVString@UnBCL@@0@Z; OSRollbackService::CCheckpoint::MoveOrCopyDirectory(UnBCL::String const &,UnBCL::String const &)
0x1802a14a0  nop
0x1802a14a1  lea     rcx, [rsp+2D8h+var_248]
0x1802a14a9  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802a14af  nop
0x1802a14b0  jmp     loc_1802A161F
0x1802a14b5  mov     r12, [rsp+2D8h+arg_0]
0x1802a14bd  mov     r14, [rsp+2D8h+arg_18]
0x1802a14c5  movzx   r13d, [rsp+2D8h+arg_10]
0x1802a14ce  jmp     loc_1802A1419
0x1802a14d3  mov     rcx, [rsp+2D8h+arg_28]
0x1802a14db  call    cs:__imp_?Exists@File@UnBCL@@SAHPEBVString@2@@Z; UnBCL::File::Exists(UnBCL::String const *)
0x1802a14e1  test    eax, eax
0x1802a14e3  jz      short loc_1802A154B
0x1802a14e5  mov     edx, r13d
0x1802a14e8  lea     rdi, aPanther; "Panther"
0x1802a14ef  mov     [rsp+2D8h+var_2B8], rdi
0x1802a14f4  lea     r9, aSources_1; "Sources"
0x1802a14fb  lea     r8, aWindowsBt_1; "$WINDOWS.~BT"
0x1802a1502  lea     rcx, aCSSS; "%c:\\%s\\%s\\%s"
0x1802a1509  call    cs:__imp_?Format@String@UnBCL@@SAPEAV12@PEBGZZ; UnBCL::String::Format(ushort const *,...)
0x1802a150f  mov     rdx, rax
0x1802a1512  lea     rcx, [rsp+2D8h+var_248]
0x1802a151a  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802a1520  nop
0x1802a1521  lea     rdx, [rsp+2D8h+var_248]
0x1802a1529  lea     rcx, [rsp+2D8h+var_190]
0x1802a1531  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1802a1537  nop
0x1802a1538  lea     rcx, [rsp+2D8h+var_248]
0x1802a1540  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802a1546  jmp     loc_1802A1420
0x1802a154b  call    cs:__imp_GetLastError
0x1802a1551  mov     esi, eax
0x1802a1553  call    cs:__imp_CurrentIP
0x1802a1559  mov     rdi, rax
0x1802a155c  mov     rcx, [rsp+2D8h+arg_28]
0x1802a1564  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802a156a  mov     rbx, rax
0x1802a156d  mov     rcx, [rsp+2D8h+arg_20]
0x1802a1575  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802a157b  mov     r9, rbx
0x1802a157e  mov     r8, rax
0x1802a1581  lea     rdx, aCsetupplatform_60; "CSetupPlatformCheckpoint::CopyLogFiles:"...
0x1802a1588  mov     ecx, 3000000h; unsigned int
0x1802a158d  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1802a1592  mov     [rsp+2D8h+var_288], r15d
0x1802a1597  mov     [rsp+2D8h+var_290], r15
0x1802a159c  mov     [rsp+2D8h+var_298], esi
0x1802a15a0  mov     [rsp+2D8h+var_2A0], rdi
0x1802a15a5  lea     rsi, aCsetupplatform_109; "CSetupPlatformCheckpoint::CopyLogFiles"
0x1802a15ac  mov     [rsp+2D8h+var_2A8], rsi
0x1802a15b1  lea     rcx, aBaseNtsetupSet_64; "base\\ntsetup\\setupplatform\\lib\\roll"...
0x1802a15b8  mov     [rsp+2D8h+var_2B0], rcx
0x1802a15bd  mov     dword ptr [rsp+2D8h+var_2B8], 429h
0x1802a15c5  xor     r9d, r9d
0x1802a15c8  lea     r8, aD_0; "D"
0x1802a15cf  mov     edx, 0C8000h
0x1802a15d4  mov     rcx, rax
0x1802a15d7  call    cs:__imp_WdsSetupLogMessageW
0x1802a15dd  mov     rcx, r14
0x1802a15e0  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802a15e6  mov     rcx, rax; lpFileName
0x1802a15e9  call    cs:__imp_GetFileAttributesW
0x1802a15ef  cmp     eax, 0FFFFFFFFh
0x1802a15f2  jz      loc_1802A2521
0x1802a15f8  jmp     loc_1802A1419
0x1802a15fd  mov     r12, [rsp+2D8h+arg_0]
0x1802a1605  mov     r14, [rsp+2D8h+arg_18]
0x1802a160d  movzx   r13d, [rsp+2D8h+arg_10]
0x1802a1616  mov     esi, dword ptr [rsp+2D8h+var_1F0]
0x1802a161d  mov     ebx, esi
0x1802a161f  lea     r8, aProgramdataMic_0; "ProgramData\\Microsoft\\Windows\\WER\\R"...
0x1802a1626  mov     edx, esi
0x1802a1628  lea     rcx, aCS; "%c:\\%s"
0x1802a162f  call    cs:__imp_?Format@String@UnBCL@@SAPEAV12@PEBGZZ; UnBCL::String::Format(ushort const *,...)
0x1802a1635  mov     rdx, rax
0x1802a1638  lea     rcx, [rsp+2D8h+var_230]
0x1802a1640  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802a1646  nop
0x1802a1647  lea     rdx, aWerReportqueue; "WER\\ReportQueue"
0x1802a164e  lea     rcx, [rsp+2D8h+var_208]
0x1802a1656  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1802a165c  nop
0x1802a165d  mov     rdx, rax
0x1802a1660  mov     rcx, r14
0x1802a1663  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1802a1669  mov     rdx, rax
0x1802a166c  lea     rcx, [rsp+2D8h+var_248]
0x1802a1674  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802a167a  nop
0x1802a167b  lea     rcx, [rsp+2D8h+var_208]
0x1802a1683  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1802a1689  lea     rcx, [rsp+2D8h+var_248]
0x1802a1691  call    cs:__imp_??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator*(void)
0x1802a1697  mov     rdi, rax
0x1802a169a  lea     rcx, [rsp+2D8h+var_230]
0x1802a16a2  call    cs:__imp_??D?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAAEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator*(void)
0x1802a16a8  mov     r8, rdi; struct UnBCL::String *
0x1802a16ab  mov     rdx, rax; struct UnBCL::String *
0x1802a16ae  call    ?MoveOrCopyDirectory@CCheckpoint@OSRollbackService@@IEAAHAEBVString@UnBCL@@0@Z; OSRollbackService::CCheckpoint::MoveOrCopyDirectory(UnBCL::String const &,UnBCL::String const &)
0x1802a16b3  nop
0x1802a16b4  lea     rcx, [rsp+2D8h+var_248]
0x1802a16bc  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802a16c2  nop
0x1802a16c3  lea     rcx, [rsp+2D8h+var_230]
0x1802a16cb  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802a16d1  nop
0x1802a16d2  jmp     short loc_1802A16F4
0x1802a16d4  mov     r12, [rsp+2D8h+arg_0]
0x1802a16dc  mov     r14, [rsp+2D8h+arg_18]
0x1802a16e4  movzx   r13d, [rsp+2D8h+arg_10]
0x1802a16ed  mov     ebx, [rsp+2D8h+arg_8]
0x1802a16f4  lea     r9, aSystem32Logfil; "System32\\LogFiles\\WMI"
0x1802a16fb  lea     r8, aWindows_4; "WINDOWS"
0x1802a1702  mov     edx, ebx
0x1802a1704  lea     rcx, aCSS; "%c:\\%s\\%s"
0x1802a170b  call    cs:__imp_?Format@String@UnBCL@@SAPEAV12@PEBGZZ; UnBCL::String::Format(ushort const *,...)
0x1802a1711  mov     rdx, rax
0x1802a1714  lea     rcx, [rsp+2D8h+var_218]
0x1802a171c  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
  ... truncated ...
```
