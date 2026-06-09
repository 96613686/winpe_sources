# CDeploymentBase::PreInitialize(CSetupPlatformInfo *,UnBCL::String *,ushort const *,int,int,int,int)

- ea: `0x1800d39f0`
- end: `0x1800d4cab`
- name: `?PreInitialize@CDeploymentBase@@MEAAJPEAVCSetupPlatformInfo@@PEAVString@UnBCL@@PEBGHHHH@Z`
- size: `4795`
- prototype: `__int64 __fastcall(CDeploymentBase *__hidden this, struct CSetupPlatformInfo *, struct UnBCL::String *, const unsigned __int16 *, int, int, int, int)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800d4cc0`
- `0x1800d9130`

## callees

- `0x18001413d`
- `0x1800197c0`
- `0x180035de8`
- `0x18003d0e8`
- `0x180044754`
- `0x180044820`
- `0x180057dec`
- `0x18005dd24`
- `0x1800ae5fc`
- `0x1800d39f0`
- `0x18029fb60`
- `0x1802c6944`
- `0x1802cff64`
- `0x1802d6bb0`
- `0x1802d9254`
- `0x1803f2ca0`
- `0x1804bbf46`
- `0x180509010`

## import_xrefs

- `msvcrt!iswalpha` at `0x1800d415f`
- `msvcrt!iswalpha` at `0x1800d415f`
- `ADVAPI32!RegGetValueW` at `0x1800d47da`
- `ADVAPI32!RegGetValueW` at `0x1800d47da`
- `ADVAPI32!RegCloseKey` at `0x1800d4b6f`
- `ADVAPI32!RegCloseKey` at `0x1800d4b9d`
- `ADVAPI32!RegCloseKey` at `0x1800d4b6f`
- `ADVAPI32!RegCloseKey` at `0x1800d4b9d`
- `ADVAPI32!RegCreateKeyExW` at `0x1800d4ad1`
- `ADVAPI32!RegCreateKeyExW` at `0x1800d4ad1`
- `KERNEL32!GetLastError` at `0x1800d3ad9`
- `KERNEL32!GetLastError` at `0x1800d405d`
- `KERNEL32!GetLastError` at `0x1800d4220`
- `KERNEL32!GetLastError` at `0x1800d4472`
- `KERNEL32!GetLastError` at `0x1800d459d`
- `KERNEL32!GetLastError` at `0x1800d464e`
- `KERNEL32!GetLastError` at `0x1800d470a`
- `KERNEL32!GetLastError` at `0x1800d4803`
- `KERNEL32!GetLastError` at `0x1800d4883`
- `KERNEL32!GetLastError` at `0x1800d490f`
- `KERNEL32!GetLastError` at `0x1800d4ae2`
- `KERNEL32!GetLastError` at `0x1800d3ad9`
- `KERNEL32!GetLastError` at `0x1800d405d`
- `KERNEL32!GetLastError` at `0x1800d4220`
- `KERNEL32!GetLastError` at `0x1800d4472`
- `KERNEL32!GetLastError` at `0x1800d459d`
- `KERNEL32!GetLastError` at `0x1800d464e`
- `KERNEL32!GetLastError` at `0x1800d470a`
- `KERNEL32!GetLastError` at `0x1800d4803`
- `KERNEL32!GetLastError` at `0x1800d4883`
- `KERNEL32!GetLastError` at `0x1800d490f`
- `KERNEL32!GetLastError` at `0x1800d4ae2`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1800d4414`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1800d4414`
- `unbcl!??0Win32Exception@UnBCL@@QEAA@KPEBG@Z` at `0x1800d4c69`
- `unbcl!??0Win32Exception@UnBCL@@QEAA@KPEBG@Z` at `0x1800d4c69`
- `unbcl!?WithoutLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800d410e`
- `unbcl!?WithoutLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800d410e`
- `unbcl!?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800d40eb`
- `unbcl!?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800d40eb`
- `unbcl!?GetEnvironmentVar@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800d4010`
- `unbcl!?GetEnvironmentVar@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800d4010`
- `unbcl!?IsEnvironmentVarSetTrue@Environment@UnBCL@@SAHPEBVString@2@H@Z` at `0x1800d4630`
- `unbcl!?IsEnvironmentVarSetTrue@Environment@UnBCL@@SAHPEBVString@2@H@Z` at `0x1800d46f0`
- `unbcl!?IsEnvironmentVarSetTrue@Environment@UnBCL@@SAHPEBVString@2@H@Z` at `0x1800d4630`
- `unbcl!?IsEnvironmentVarSetTrue@Environment@UnBCL@@SAHPEBVString@2@H@Z` at `0x1800d46f0`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1800d4bfe`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1800d4bfe`
- `unbcl!?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z` at `0x1800d4527`
- `unbcl!?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z` at `0x1800d4527`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x1800d4356`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x1800d445b`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x1800d4356`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x1800d445b`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800d3b68`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800d3bce`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800d3c31`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800d3c94`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800d3d02`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800d3d68`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800d3db7`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800d3e1a`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800d3e7d`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800d3ee3`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800d42fb`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800d43b5`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800d498e`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800d3b68`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800d3bce`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800d3c31`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800d3c94`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800d3d02`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800d3d68`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800d3db7`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800d3e1a`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800d3e7d`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800d3ee3`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800d42fb`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800d43b5`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800d498e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d3ace`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d3bc2`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d3c25`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d3c88`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d3cf6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d3d5c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d3dab`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d3e0e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d3e71`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d3ed7`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d3fef`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d404e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d40e2`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d4105`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d41e4`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d41fb`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d4207`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d42c5`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d42ef`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d434d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d436c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d43a9`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d4452`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d451e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d4592`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d49d6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d3ace`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d3bc2`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d3c25`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d3c88`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d3cf6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d3d5c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d3dab`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d3e0e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d3e71`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d3ed7`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d3fef`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d404e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d40e2`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d4105`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d41e4`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d41fb`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d4207`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d42c5`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d42ef`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d434d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d436c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d43a9`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d4452`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d451e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d4592`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800d49d6`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d3ba4`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d3c07`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d3c6a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d3cd8`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d3d3b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d3d88`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d3df0`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d3e53`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d3eb9`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d3f1c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d4045`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d431b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d43f2`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d4640`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d4700`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d49ab`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d3ba4`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d3c07`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d3c6a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d3cd8`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d3d3b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d3d88`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d3df0`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d3e53`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d3eb9`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d3f1c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d4045`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d431b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d43f2`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d4640`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d4700`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800d49ab`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d3b5b`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d3bb6`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d3c19`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d3c7c`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d3cea`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d3d50`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d3d9a`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d3e02`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d3e65`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d3ecb`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d3f96`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d4006`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d42e3`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d439d`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d4624`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d46e4`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d497c`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d3b5b`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d3bb6`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d3c19`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d3c7c`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d3cea`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d3d50`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d3d9a`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d3e02`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d3e65`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d3ecb`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d3f96`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d4006`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d42e3`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d439d`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d4624`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d46e4`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800d497c`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800d3f3a`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800d3f7a`

## string_xrefs

- `0x1800d3cde`: `Rollback`
- `0x1800d3b19`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800d40b2`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800d426e`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800d44c0`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800d45de`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800d4695`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800d46ce`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800d4bf4`: `BasePath`
- `0x1800d3aea`: `Cannot create an installation ID`
- `0x1800d4c5a`: `Scratch path is not on a local drive`
- `0x1800d4083`: `Scratch directory requested (%s), perfoming validation`
- `0x1800d4246`: `Scratch space %s is on the same volume with the installation.`
- `0x1800d4498`: `Cannot find a suitable directory for the scratch space in %s.`
- `0x1800d45b6`: `Scratch directory %s requested but cannot be used.`
- `0x1800d4729`: `%hs: %s environment variable detected, fail-forward installation is enabled.`
- `0x1800d46d5`: `SP_ENV_FAIL_FORWARD_INSTALL`
- `0x1800d471b`: `SP_ENV_FAIL_FORWARD_INSTALL`
- `0x1800d47c5`: `AllowUninstall`
- `0x1800d4894`: `Rollback not configured correctly, AllowUninstall request will be ignored.`
- `0x1800d4814`: `AllowUninstall value found in the registry, will enable if rollback is active`
- `0x1800d4920`: `DisableShiftF10 request received, will not enable Shift-F10 command prompt hotkey.`
- `0x1800d4a4a`: `SP_INSTALL_INFO`
- `0x1800d4a6a`: `SP_INSTALL_INFO`
- `0x1800d4a63`: `InstallStartTime`

## pseudocode

```c
// Hidden C++ exception states: #wind=53
__int64 __fastcall CDeploymentBase::PreInitialize(
        void **this,
        struct CSetupPlatformInfo *a2,
        struct UnBCL::String *a3,
        const unsigned __int16 *a4,
        int a5,
        int a6,
        int a7,
        int a8)
{
  void **v11; // r15
  struct UnBCL::String *v13; // rax
  DWORD LastError; // edi
  __int64 v15; // rbx
  struct tagLOG_PARTIAL_MSG *v16; // rax
  const struct UnBCL::String *v17; // rax
  struct UnBCL::String *v18; // rax
  const struct UnBCL::String *v19; // rbx
  const struct UnBCL::String *P; // rax
  struct UnBCL::String *v21; // rax
  const struct UnBCL::String *v22; // rbx
  const struct UnBCL::String *v23; // rax
  struct UnBCL::String *v24; // rax
  const struct UnBCL::String *v25; // rbx
  const struct UnBCL::String *v26; // rax
  struct UnBCL::String *v27; // rax
  const struct UnBCL::String *v28; // rbx
  const struct UnBCL::String *v29; // rax
  struct UnBCL::String *v30; // rax
  const struct UnBCL::String *v31; // rbx
  const struct UnBCL::String *v32; // rax
  struct UnBCL::String *v33; // rax
  const struct UnBCL::String *v34; // rbx
  const struct UnBCL::String *v35; // rax
  struct UnBCL::String *v36; // rax
  const struct UnBCL::String *v37; // rbx
  const struct UnBCL::String *v38; // rax
  struct UnBCL::String *v39; // rax
  const struct UnBCL::String *v40; // rbx
  const struct UnBCL::String *v41; // rax
  struct UnBCL::String *v42; // rax
  const struct UnBCL::String *v43; // rbx
  const struct UnBCL::String *v44; // rax
  struct UnBCL::String *v45; // rax
  CSetupPlatformRollback *v46; // rax
  CSetupPlatformRollback *v47; // rdx
  UnBCL::String *v48; // rax
  UnBCL::String *v49; // rbx
  void **v50; // r14
  const struct UnBCL::String *v51; // rax
  struct UnBCL::String *EnvironmentVar; // rax
  DWORD v53; // edi
  __int64 v54; // rbx
  UnBCL::String *v55; // rax
  const char *CString; // rax
  struct tagLOG_PARTIAL_MSG *v57; // rax
  const struct UnBCL::String *v58; // rax
  struct UnBCL::String *FullPath; // rax
  const struct UnBCL::String *v60; // rax
  struct UnBCL::String *v61; // rax
  UnBCL::String *v62; // rax
  wint_t *v63; // rax
  UnBCL::String *v64; // rax
  UnBCL::String *v65; // rax
  struct UnBCL::String *v66; // rbx
  struct UnBCL::String *v67; // rax
  DWORD v68; // edi
  __int64 v69; // rbx
  UnBCL::String *v70; // rax
  const char *v71; // rax
  struct tagLOG_PARTIAL_MSG *v72; // rax
  const struct UnBCL::String *v73; // rbx
  const struct UnBCL::String *v74; // rax
  struct UnBCL::String *v75; // rax
  unsigned int v76; // edi
  const struct UnBCL::String *v77; // rax
  struct UnBCL::String *v78; // rax
  int v79; // edx
  int v80; // r9d
  bool v81; // zf
  const struct UnBCL::String *v82; // rbx
  const struct UnBCL::String *v83; // rax
  struct UnBCL::String *v84; // rax
  UnBCL::String *v85; // rax
  const unsigned __int16 *v86; // rax
  struct UnBCL::String *v87; // rax
  const struct UnBCL::String *v88; // rax
  DWORD v89; // edi
  __int64 v90; // rbx
  UnBCL::String *v91; // rax
  const char *v92; // rax
  struct tagLOG_PARTIAL_MSG *v93; // rax
  const struct UnBCL::String *v94; // rax
  struct UnBCL::DirectoryInfo *Dir; // rax
  DWORD v96; // edi
  __int64 v97; // rbx
  struct tagLOG_PARTIAL_MSG *v98; // rax
  int Key; // r15d
  const struct UnBCL::String *v100; // rax
  int IsEnvironmentVarSetTrue; // ebx
  DWORD v102; // edi
  __int64 v103; // rbx
  struct tagLOG_PARTIAL_MSG *v104; // rax
  const struct UnBCL::String *v105; // rax
  int v106; // ebx
  DWORD v107; // edi
  __int64 v108; // rbx
  struct tagLOG_PARTIAL_MSG *v109; // rax
  DWORD v110; // edi
  __int64 v111; // rbx
  struct tagLOG_PARTIAL_MSG *v112; // rax
  DWORD v113; // edi
  __int64 v114; // rbx
  struct tagLOG_PARTIAL_MSG *v115; // rax
  DWORD v116; // edi
  __int64 v117; // rbx
  struct tagLOG_PARTIAL_MSG *v118; // rax
  const struct UnBCL::String *v119; // rax
  struct UnBCL::String *v120; // rax
  __int64 v121; // rbx
  __int64 v122; // rax
  void *v123; // rdi
  void (__fastcall *v124)(void *, const wchar_t *, const wchar_t *, _QWORD); // rbx
  UnBCL::String *v125; // rax
  const unsigned __int16 *v126; // rax
  unsigned __int64 v127; // rax
  HKEY *phkResult; // rax
  DWORD v129; // edi
  __int64 v130; // rbx
  struct tagLOG_PARTIAL_MSG *v131; // rax
  UnBCL::ArgumentNullException *v132; // rax
  UnBCL::ArgumentNullException *v133; // rbx
  UnBCL::Win32Exception *v134; // rax
  UnBCL::Win32Exception *v135; // rbx
  UnBCL::String *v136; // rax
  const char *v137; // rax
  struct UnBCL::Exception *v138; // rsi
  DWORD v139; // edi
  __int64 v140; // rbx
  UnBCL::String *v141; // rax
  const char *v142; // rax
  struct tagLOG_PARTIAL_MSG *v143; // rax
  UnBCL::String *v144; // rax
  const char *v145; // rax
  struct UnBCL::Exception *v146; // rsi
  DWORD v147; // edi
  __int64 v148; // rbx
  UnBCL::String *v149; // rax
  const char *v150; // rax
  struct tagLOG_PARTIAL_MSG *v151; // rax
  _QWORD v152[2]; // [rsp+60h] [rbp-128h] BYREF
  _BYTE v153[24]; // [rsp+70h] [rbp-118h] BYREF
  DWORD pcbData[4]; // [rsp+88h] [rbp-100h] BYREF
  CSetupPlatformRollback *pvData; // [rsp+98h] [rbp-F0h] BYREF
  void **v156; // [rsp+A0h] [rbp-E8h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp-E0h]
  unsigned int v158; // [rsp+B0h] [rbp-D8h] BYREF
  _BYTE v159[16]; // [rsp+B8h] [rbp-D0h] BYREF
  _BYTE v160[16]; // [rsp+C8h] [rbp-C0h] BYREF
  UnBCL::Exception *v161; // [rsp+D8h] [rbp-B0h]
  void **v162; // [rsp+E0h] [rbp-A8h]
  __int64 pExceptionObject; // [rsp+E8h] [rbp-A0h] BYREF
  __int64 v164; // [rsp+F0h] [rbp-98h] BYREF
  _DWORD *v165; // [rsp+F8h] [rbp-90h]
  _BYTE v166[16]; // [rsp+100h] [rbp-88h] BYREF
  __int64 v167; // [rsp+110h] [rbp-78h]
  struct UnBCL::Exception *v168; // [rsp+118h] [rbp-70h] BYREF
  struct UnBCL::Exception *v169; // [rsp+120h] [rbp-68h] BYREF
  _BYTE v170[24]; // [rsp+128h] [rbp-60h] BYREF
  _BYTE v171[72]; // [rsp+140h] [rbp-48h] BYREF

  v167 = -2;
  v11 = this;
  if ( !a3 )
  {
    v132 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v133 = v132;
    if ( v132 )
    {
      UnBCL::ArgumentNullException::ArgumentNullException(v132, L"BasePath");
      *(_QWORD *)v133 = &UnBCL::ArgumentNullException::`local vftable';
    }
    else
    {
      v133 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v133,
                         "long __cdecl CDeploymentBase::PreInitialize(class CSetupPlatformInfo *,class UnBCL::String *,co"
                         "nst unsigned short *,int,int,int,int)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( (unsigned int)SPIsEventSet(this[69]) )
    return 2147943623LL;
  if ( !a2 )
    a2 = (struct CSetupPlatformInfo *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v11[7] + 5) + 8LL))(*((_QWORD *)v11[7] + 5));
  UnBCL::SmartPtr<CSetupPlatformInfo>::SmartPtr<CSetupPlatformInfo>(v152, a2);
  UnBCL::SmartPtr<UnBCL::ArrayList<CRegCreationData *>>::operator=(v11 + 9, v152);
  v152[0] = &UnBCL::SmartPtr<CSetupPlatformInfo>::`vftable';
  UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(v152);
  v13 = SPGetGuidString();
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v152, v13);
  UnBCL::SmartPtr<UnBCL::String>::operator=(v11 + 15, v152);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v152);
  if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(v11 + 15) )
  {
    LastError = GetLastError();
    v15 = CurrentIP();
    v16 = ConstructPartialMsgW(0x2000000u, "Cannot create an installation ID");
    WdsSetupLogMessageW(
      v16,
      819200,
      L"D",
      0,
      1220,
      L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
      L"CDeploymentBase::PreInitialize",
      v15,
      LastError,
      0,
      0);
    return 2147500037LL;
  }
  v17 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v153, L"$WINDOWS.~BT");
  v18 = UnBCL::Path::Combine(a3, v17);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v152, v18);
  UnBCL::SmartPtr<UnBCL::String>::operator=(v11 + 21, v152);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v152);
  UnBCL::String::~String((UnBCL::String *)v153);
  v19 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v153, L"Work");
  P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v11 + 21);
  v21 = UnBCL::Path::Combine(P, v19);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v152, v21);
  UnBCL::SmartPtr<UnBCL::String>::operator=(v11 + 23, v152);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v152);
  UnBCL::String::~String((UnBCL::String *)v153);
  v22 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v153, L"Store");
  v23 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v11 + 21);
  v24 = UnBCL::Path::Combine(v23, v22);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v152, v24);
  UnBCL::SmartPtr<UnBCL::String>::operator=(v11 + 25, v152);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v152);
  UnBCL::String::~String((UnBCL::String *)v153);
  v25 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v153, L"Sources");
  v26 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v11 + 21);
  v27 = UnBCL::Path::Combine(v26, v25);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v152, v27);
  v162 = v11 + 19;
  UnBCL::SmartPtr<UnBCL::String>::operator=(v11 + 19, v152);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v152);
  UnBCL::String::~String((UnBCL::String *)v153);
  v28 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v153, L"Rollback");
  v29 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v11 + 19);
  v30 = UnBCL::Path::Combine(v29, v28);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v152, v30);
  UnBCL::SmartPtr<UnBCL::String>::operator=(v11 + 39, v152);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v152);
  UnBCL::String::~String((UnBCL::String *)v153);
  v31 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v170, L"Diagnostics");
  v32 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v11 + 19);
  v33 = UnBCL::Path::Combine(v32, v31);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v166, v33);
  UnBCL::String::~String((UnBCL::String *)v170);
  v34 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v153, L"diagnostics.dat");
  v35 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v166);
  v36 = UnBCL::Path::Combine(v35, v34);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v152, v36);
  UnBCL::SmartPtr<UnBCL::String>::operator=(v11 + 29, v152);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v152);
  UnBCL::String::~String((UnBCL::String *)v153);
  v37 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v153, L"SafeOS");
  v38 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v11 + 19);
  v39 = UnBCL::Path::Combine(v38, v37);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v152, v39);
  UnBCL::SmartPtr<UnBCL::String>::operator=(v11 + 31, v152);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v152);
  UnBCL::String::~String((UnBCL::String *)v153);
  v40 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v153, L"Panther");
  v41 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v11 + 19);
  v42 = UnBCL::Path::Combine(v41, v40);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v152, v42);
  UnBCL::SmartPtr<UnBCL::String>::operator=(v11 + 33, v152);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v152);
  UnBCL::String::~String((UnBCL::String *)v153);
  v43 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v153, L"SetupAct.log");
  v44 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v11 + 33);
  v45 = UnBCL::Path::Combine(v44, v43);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v152, v45);
  UnBCL::SmartPtr<UnBCL::String>::operator=(v11 + 35, v152);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v152);
  UnBCL::String::~String((UnBCL::String *)v153);
  v165 = (_DWORD *)v11 + 87;
  if ( *((_DWORD *)v11 + 87) )
  {
    v46 = (CSetupPlatformRollback *)UnBCL::Object::operator new(0x58u);
    pvData = v46;
    if ( v46 )
      v47 = CSetupPlatformRollback::CSetupPlatformRollback(v46);
    else
      v47 = 0;
    (*((void (__fastcall **)(void **, CSetupPlatformRollback *))v11[37] + 4))(v11 + 37, v47);
  }
  if ( a4 )
  {
    v48 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
    v49 = v48;
    pvData = v48;
    if ( v48 )
    {
      UnBCL::String::String(v48, a4);
      *(_QWORD *)v49 = &UnBCL::String::`local vftable';
    }
    else
    {
      v49 = 0;
    }
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v152, v49);
    v50 = v11 + 27;
    UnBCL::SmartPtr<UnBCL::String>::operator=(v11 + 27, v152);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v152);
  }
  else
  {
    v50 = v11 + 27;
  }
  pvData = (CSetupPlatformRollback *)v50;
  if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(v50) )
  {
    v51 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v153, L"SP_ENV_SCRATCH_DRIVE");
    EnvironmentVar = UnBCL::Environment::GetEnvironmentVar(v51);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v152, EnvironmentVar);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v50, v152);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v152);
    UnBCL::String::~String((UnBCL::String *)v153);
  }
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v50) )
  {
    v53 = GetLastError();
    v54 = CurrentIP();
    v55 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v50);
    CString = (const char *)UnBCL::String::get_CString(v55);
    v57 = ConstructPartialMsgW(0x4000000u, "Scratch directory requested (%s), perfoming validation", CString);
    WdsSetupLogMessageW(
      v57,
      819200,
      L"D",
      0,
      1252,
      L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
      L"CDeploymentBase::PreInitialize",
      v54,
      v53,
      0,
      0);
    try
    {
      v58 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v50);
      FullPath = UnBCL::Path::GetFullPath(v58);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v152, FullPath);
      v60 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v152);
      v61 = UnBCL::Path::WithoutLongPrefix(v60);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(pcbData, v61);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v152, pcbData);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(pcbData);
      v62 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v152);
      v63 = (wint_t *)UnBCL::String::get_CString(v62);
      if ( !iswalpha(*v63)
        || (v64 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v152),
            UnBCL::String::get_CString(v64)[1] != 58)
        || (v65 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v152),
            UnBCL::String::get_CString(v65)[2] != 92) )
      {
        v134 = (UnBCL::Win32Exception *)UnBCL::Object::operator new(0x40u);
        v135 = v134;
        *(_QWORD *)pcbData = v134;
        if ( v134 )
        {
          UnBCL::Win32Exception::Win32Exception(v134, 0xA1u, L"Scratch path is not on a local drive");
          *(_QWORD *)v135 = &UnBCL::Win32Exception::`local vftable';
        }
        else
        {
          v135 = 0;
        }
        v164 = AddStackTraceToException<UnBCL::InvalidOperationException>(
                 v135,
                 "long __cdecl CDeploymentBase::PreInitialize(class CSetupPlatformInfo *,class UnBCL::String *,const unsi"
                 "gned short *,int,int,int,int)");
        throw (UnBCL::Win32Exception **)&v164;
      }
      UnBCL::SmartPtr<UnBCL::String>::operator=(v50, v152);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v152);
    }
    catch ( UnBCL::Exception *v168 )
    {
      v136 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(this + 27);
      v137 = (const char *)UnBCL::String::get_CString(v136);
      v138 = v168;
      pExceptionLogFormat::pExceptionLogFormat(
        (pExceptionLogFormat *)&v158,
        0x3000000u,
        v168,
        "Scratch path %s does not seem to be valid.",
        v137);
      UnBCL::Exception::AddStackTrace(
        v161,
        "long __cdecl CDeploymentBase::PreInitialize(class CSetupPlatformInfo *,class UnBCL::String *,const unsigned shor"
        "t *,int,int,int,int)");
      v139 = GetLastError();
      v140 = CurrentIP();
      v141 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v159);
      v142 = (const char *)UnBCL::String::get_CString(v141);
      v143 = ConstructPartialMsgW(v158, "%s", v142);
      WdsSetupLogMessageW(
        v143,
        819200,
        L"D",
        0,
        1268,
        L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
        L"CDeploymentBase::PreInitialize",
        v140,
        v139,
        0,
        0);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v160);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v159);
      if ( v138 )
        (**(void (__fastcall ***)(struct UnBCL::Exception *, __int64))v138)(v138, 1);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v152, 0);
      UnBCL::SmartPtr<UnBCL::String>::operator=(this + 27, v152);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v152);
      v11 = this;
      v50 = (void **)pvData;
    }
  }
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v50) )
  {
    v66 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v162);
    v67 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v50);
    if ( SPArePathsOnSameVolume(v67, v66) )
    {
      v68 = GetLastError();
      v69 = CurrentIP();
      v70 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v50);
      v71 = (const char *)UnBCL::String::get_CString(v70);
      v72 = ConstructPartialMsgW(0x3000000u, "Scratch space %s is on the same volume with the installation.", v71);
      WdsSetupLogMessageW(
        v72,
        819200,
        L"D",
        0,
        1281,
        L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
        L"CDeploymentBase::PreInitialize",
        v69,
        v68,
        0,
        0);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v152, 0);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v50, v152);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v152);
    }
  }
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v50) )
  {
    v73 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v171, L"$WINDOWS.~TMP");
    v74 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v50);
    v75 = UnBCL::Path::Combine(v74, v73);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(pcbData, v75);
    UnBCL::String::~String((UnBCL::String *)v171);
    if ( a5 )
    {
      UnBCL::SmartPtr<UnBCL::String>::operator=(v50, pcbData);
    }
    else
    {
      v76 = 1;
      v77 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(pcbData);
      if ( !UnBCL::Directory::Exists(v77) )
        goto LABEL_86;
      do
      {
        v78 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(pcbData);
        if ( (unsigned int)SPDeleteFolder(v78, v79, 0, v80) )
          break;
        v81 = v76 == -1;
        if ( v76 == -1 )
          goto LABEL_38;
        v82 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v158, L"$WINDOWS(%u).~TMP");
        v83 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v50);
        v84 = UnBCL::Path::Combine(v83, v82);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v152, v84);
        UnBCL::SmartPtr<UnBCL::String>::operator=(pcbData, v152);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v152);
        UnBCL::String::~String((UnBCL::String *)&v158);
        v85 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(pcbData);
        v86 = UnBCL::String::get_CString(v85);
        v87 = UnBCL::String::Format(v86, v76);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v153, v87);
        UnBCL::SmartPtr<UnBCL::String>::operator=(pcbData, v153);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v153);
        ++v76;
        v88 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(pcbData);
      }
      while ( UnBCL::Directory::Exists(v88) );
      v81 = v76 == -1;
LABEL_38:
      if ( v81 )
      {
        v89 = GetLastError();
        v90 = CurrentIP();
        v91 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v50);
        v92 = (const char *)UnBCL::String::get_CString(v91);
        v93 = ConstructPartialMsgW(0x3000000u, "Cannot find a suitable directory for the scratch space in %s.", v92);
        WdsSetupLogMessageW(
          v93,
          819200,
          L"D",
          0,
          1304,
          L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
          L"CDeploymentBase::PreInitialize",
          v90,
          v89,
          0,
          0);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v153, 0);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v50, v153);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v153);
      }
      else
      {
LABEL_86:
        try
        {
          v94 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(pcbData);
          Dir = UnBCL::Directory::CreateDir(v94);
          UnBCL::SmartPtr<UnBCL::DirectoryInfo>::SmartPtr<UnBCL::DirectoryInfo>(v153, Dir);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v50, pcbData);
          UnBCL::SmartPtr<UnBCL::DirectoryInfo>::~SmartPtr<UnBCL::DirectoryInfo>(v153);
        }
        catch ( UnBCL::Exception *v169 )
        {
          v144 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(pcbData);
          v145 = (const char *)UnBCL::String::get_CString(v144);
          v146 = v169;
          pExceptionLogFormat::pExceptionLogFormat(
            (pExceptionLogFormat *)&v158,
            0x3000000u,
            v169,
            "Cannot create proposed scratch directory %s.",
            v145);
          UnBCL::Exception::AddStackTrace(
            v161,
            "long __cdecl CDeploymentBase::PreInitialize(class CSetupPlatformInfo *,class UnBCL::String *,const unsigned "
            "short *,int,int,int,int)");
          v147 = GetLastError();
          v148 = CurrentIP();
          v149 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v159);
          v150 = (const char *)UnBCL::String::get_CString(v149);
          v151 = ConstructPartialMsgW(v158, "%s", v150);
          WdsSetupLogMessageW(
            v151,
            819200,
            L"D",
            0,
            1322,
            L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
            L"CDeploymentBase::PreInitialize",
            v148,
            v147,
            0,
            0);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v160);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v159);
          if ( v146 )
            (**(void (__fastcall ***)(struct UnBCL::Exception *, __int64))v146)(v146, 1);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v153, 0);
          UnBCL::SmartPtr<UnBCL::String>::operator=(this + 27, v153);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v153);
          v11 = this;
          v50 = (void **)pvData;
        }
      }
    }
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(pcbData);
  }
  if ( a4 && !UnBCL::SmartPtr<UnBCL::String>::get_P(v50) )
  {
    v96 = GetLastError();
    v97 = CurrentIP();
    v98 = ConstructPartialMsgW(0x2000000u, "Scratch directory %s requested but cannot be used.", (const char *)a4);
    WdsSetupLogMessageW(
      v98,
      819200,
      L"D",
      0,
      1332,
      L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
      L"CDeploymentBase::PreInitialize",
      v97,
      v96,
      0,
      0);
    Key = -2147023264;
LABEL_63:
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v166);
    return (unsigned int)Key;
  }
  v100 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v158, L"SP_ENV_VERBOSE_LOGGING");
  IsEnvironmentVarSetTrue = UnBCL::Environment::IsEnvironmentVarSetTrue(v100, 0);
  UnBCL::String::~String((UnBCL::String *)&v158);
  if ( IsEnvironmentVarSetTrue )
  {
    v102 = GetLastError();
    v103 = CurrentIP();
    v104 = ConstructPartialMsgW(
             0x4000000u,
             "%hs: %s environment variable detected, verbose logging is enabled.",
             "CDeploymentBase::PreInitialize",
             (const char *)L"SP_ENV_VERBOSE_LOGGING");
    WdsSetupLogMessageW(
      v104,
      819200,
      L"D",
      0,
      1344,
      L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
      L"CDeploymentBase::PreInitialize",
      v103,
      v102,
      0,
      0);
    *((_DWORD *)v11 + 132) = 1;
  }
  v105 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v158, L"SP_ENV_FAIL_FORWARD_INSTALL");
  v106 = UnBCL::Environment::IsEnvironmentVarSetTrue(v105, 0);
  UnBCL::String::~String((UnBCL::String *)&v158);
  if ( v106 )
  {
    v107 = GetLastError();
    v108 = CurrentIP();
    v109 = ConstructPartialMsgW(
             0x4000000u,
             "%hs: %s environment variable detected, fail-forward installation is enabled.",
             "CDeploymentBase::PreInitialize",
             (const char *)L"SP_ENV_FAIL_FORWARD_INSTALL");
    WdsSetupLogMessageW(
      v109,
      819200,
      L"D",
      0,
      1357,
      L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
      L"CDeploymentBase::PreInitialize",
      v108,
      v107,
      0,
      0);
    *((_DWORD *)v11 + 114) = 1;
  }
  if ( !*((_DWORD *)v11 + 94) )
  {
    LODWORD(pvData) = 0;
    pcbData[0] = 4;
    if ( !RegGetValueW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup", L"AllowUninstall", 0x18u, 0, &pvData, pcbData)
      && pcbData[0] == 4
      && (_DWORD)pvData )
    {
      v110 = GetLastError();
      v111 = CurrentIP();
      v112 = ConstructPartialMsgW(
               0x4000000u,
               "AllowUninstall value found in the registry, will enable if rollback is active");
      WdsSetupLogMessageW(
        v112,
        819200,
        L"D",
        0,
        1379,
        L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
        L"CDeploymentBase::PreInitialize",
        v111,
        v110,
        0,
        0);
      if ( *v165 && *((_DWORD *)v11 + 89) )
      {
        *((_DWORD *)v11 + 94) = 1;
      }
      else
      {
        v113 = GetLastError();
        v114 = CurrentIP();
        v115 = ConstructPartialMsgW(
                 0x3000000u,
                 "Rollback not configured correctly, AllowUninstall request will be ignored.");
        WdsSetupLogMessageW(
          v115,
          819200,
          L"D",
          0,
          1386,
          L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
          L"CDeploymentBase::PreInitialize",
          v114,
          v113,
          0,
          0);
      }
    }
  }
  *((_DWORD *)v11 + 133) = a6;
  *((_DWORD *)v11 + 134) = a7;
  *((_DWORD *)v11 + 135) = a8;
  if ( a8 )
  {
    v116 = GetLastError();
    v117 = CurrentIP();
    v118 = ConstructPartialMsgW(
             0x4000000u,
             "DisableShiftF10 request received, will not enable Shift-F10 command prompt hotkey.");
    WdsSetupLogMessageW(
      v118,
      819200,
      L"D",
      0,
      1397,
      L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
      L"CDeploymentBase::PreInitialize",
      v117,
      v116,
      0,
      0);
  }
  v119 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)&v158, L"WINDOWS\\Panther");
  v120 = UnBCL::Path::Combine(a3, v119);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v152, v120);
  UnBCL::String::~String((UnBCL::String *)&v158);
  v121 = _RTDynamicCast_0(v11[12], 0, &ITelemetry `RTTI Type Descriptor', &CTelemetry `RTTI Type Descriptor', 0);
  v122 = UnBCL::SmartPtr<UnBCL::String>::get_P(v152);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v153, v122);
  UnBCL::SmartPtr<UnBCL::String>::operator=(v121 + 48, v153);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v153);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v152);
  v123 = v11[12];
  v124 = *(void (__fastcall **)(void *, const wchar_t *, const wchar_t *, _QWORD))(*(_QWORD *)v123 + 24LL);
  v125 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v162);
  v126 = UnBCL::String::get_CString(v125);
  v127 = SPGetTotalDiskSpace(v126);
  v124(v123, L"SP_INSTALL_INFO", L"OSPartitionSize", (unsigned int)(v127 >> 20));
  (*(void (__fastcall **)(void *, const wchar_t *, const wchar_t *))(*(_QWORD *)v11[12] + 32LL))(
    v11[12],
    L"SP_INSTALL_INFO",
    L"InstallStartTime");
  v156 = &RAII::CAutoCleanup<HKEY__ *>::`vftable';
  hKey = 0;
  phkResult = (HKEY *)RAII::CAutoCleanupBase<VdsVolumePathEnumerator *>::operator&(&v156);
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup\\DeploymentInProgress", 0, 0, 1u, 0x20006u, 0, phkResult, 0);
  if ( Key )
  {
    v129 = GetLastError();
    v130 = CurrentIP();
    v131 = ConstructPartialMsgW(
             0x2000000u,
             "CDeploymentBase::PreInitialize: Error creating the DeploymentInProgress key. Error: 0x%08X",
             Key);
    WdsSetupLogMessageW(
      v131,
      819200,
      L"D",
      0,
      1430,
      L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
      L"CDeploymentBase::PreInitialize",
      v130,
      v129,
      0,
      0);
    if ( Key > 0 )
      Key = (unsigned __int16)Key | 0x80070000;
    v156 = &RAII::CAutoCleanup<HKEY__ *>::`vftable';
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    goto LABEL_63;
  }
  if ( hKey )
    RegCloseKey(hKey);
  hKey = 0;
  v156 = &RAII::CAutoCleanup<HKEY__ *>::`vftable';
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v166);
  return 0;
}

```

## disassembly

```asm
0x1800d39f0  mov     rax, rsp
0x1800d39f3  mov     [rax+20h], r9
0x1800d39f7  mov     [rax+18h], r8
0x1800d39fb  mov     [rax+8], rcx
0x1800d39ff  push    rsi
0x1800d3a00  push    rdi
0x1800d3a01  push    r13
0x1800d3a03  push    r14
0x1800d3a05  push    r15
0x1800d3a07  sub     rsp, 160h
0x1800d3a0e  mov     qword ptr [rax-78h], 0FFFFFFFFFFFFFFFEh
0x1800d3a16  mov     [rax+10h], rbx
0x1800d3a1a  mov     r14, r9
0x1800d3a1d  mov     rdi, r8
0x1800d3a20  mov     rbx, rdx
0x1800d3a23  mov     r15, rcx
0x1800d3a26  xor     esi, esi
0x1800d3a28  test    r8, r8
0x1800d3a2b  jz      loc_1800D4BDB
0x1800d3a31  mov     rcx, [rcx+228h]; void *
0x1800d3a38  call    ?SPIsEventSet@@YAHPEAX@Z; SPIsEventSet(void *)
0x1800d3a3d  test    eax, eax
0x1800d3a3f  jz      short loc_1800D3A4B
0x1800d3a41  mov     eax, 800704C7h
0x1800d3a46  jmp     loc_1800D4BC3
0x1800d3a4b  test    rbx, rbx
0x1800d3a4e  jnz     short loc_1800D3A67
0x1800d3a50  mov     rax, [r15+38h]
0x1800d3a54  mov     rcx, [rax+28h]
0x1800d3a58  mov     rax, [rcx]
0x1800d3a5b  mov     rax, [rax+8]
0x1800d3a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3a64  mov     rbx, rax
0x1800d3a67  mov     rdx, rbx
0x1800d3a6a  lea     rcx, [rsp+188h+var_128]
0x1800d3a6f  call    ??0?$SmartPtr@VCSetupPlatformInfo@@@UnBCL@@QEAA@PEAVCSetupPlatformInfo@@@Z; UnBCL::SmartPtr<CSetupPlatformInfo>::SmartPtr<CSetupPlatformInfo>(CSetupPlatformInfo *)
0x1800d3a74  nop
0x1800d3a75  lea     rcx, [r15+48h]
0x1800d3a79  lea     rdx, [rsp+188h+var_128]
0x1800d3a7e  call    ??4?$SmartPtr@V?$ArrayList@PEAVCRegCreationData@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::ArrayList<CRegCreationData *>>::operator=(UnBCL::SmartPtr<UnBCL::ArrayList<CRegCreationData *>> const &)
0x1800d3a83  nop
0x1800d3a84  lea     rax, ??_7?$SmartPtr@VCSetupPlatformInfo@@@UnBCL@@6B@; const UnBCL::SmartPtr<CSetupPlatformInfo>::`vftable'
0x1800d3a8b  mov     [rsp+188h+var_128], rax
0x1800d3a90  lea     rcx, [rsp+188h+var_128]
0x1800d3a95  call    ?DeAssign@?$SmartPtr@V?$Hashtable@KPEAUIVdsVDisk@@@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::Hashtable<ulong,IVdsVDisk *>>::DeAssign(void)
0x1800d3a9a  nop
0x1800d3a9b  call    ?SPGetGuidString@@YAPEAVString@UnBCL@@XZ; SPGetGuidString(void)
0x1800d3aa0  mov     rdx, rax
0x1800d3aa3  lea     rcx, [rsp+188h+var_128]
0x1800d3aa8  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800d3aae  nop
0x1800d3aaf  lea     rdx, [rsp+188h+var_128]
0x1800d3ab4  lea     rcx, [r15+78h]
0x1800d3ab8  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1800d3abe  nop
0x1800d3abf  lea     rcx, [rsp+188h+var_128]
0x1800d3ac4  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800d3aca  lea     rcx, [r15+78h]
0x1800d3ace  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800d3ad4  test    rax, rax
0x1800d3ad7  jnz     short loc_1800D3B4F
0x1800d3ad9  call    cs:__imp_GetLastError
0x1800d3adf  mov     edi, eax
0x1800d3ae1  call    cs:__imp_CurrentIP
0x1800d3ae7  mov     rbx, rax
0x1800d3aea  lea     rdx, aCannotCreateAn; "Cannot create an installation ID"
0x1800d3af1  mov     ecx, 2000000h; unsigned int
0x1800d3af6  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800d3afb  mov     [rsp+188h+var_138], esi
0x1800d3aff  mov     [rsp+188h+var_140], rsi
0x1800d3b04  mov     dword ptr [rsp+188h+lpdwDisposition], edi
0x1800d3b08  mov     [rsp+188h+phkResult], rbx
0x1800d3b0d  lea     r13, aCdeploymentbas_3; "CDeploymentBase::PreInitialize"
0x1800d3b14  mov     [rsp+188h+pcbData], r13
0x1800d3b19  lea     rcx, aBaseNtsetupSet_34; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1800d3b20  mov     [rsp+188h+pvData], rcx
0x1800d3b25  mov     dword ptr [rsp+188h+pdwType], 4C4h
0x1800d3b2d  xor     r9d, r9d
0x1800d3b30  lea     r8, aD_0; "D"
0x1800d3b37  mov     edx, 0C8000h
0x1800d3b3c  mov     rcx, rax
0x1800d3b3f  call    cs:__imp_WdsSetupLogMessageW
0x1800d3b45  mov     eax, 80004005h
0x1800d3b4a  jmp     loc_1800D4BC3
0x1800d3b4f  lea     rdx, aWindowsBt_1; "$WINDOWS.~BT"
0x1800d3b56  lea     rcx, [rsp+188h+var_118]
0x1800d3b5b  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800d3b61  nop
0x1800d3b62  mov     rdx, rax
0x1800d3b65  mov     rcx, rdi
0x1800d3b68  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1800d3b6e  mov     rdx, rax
0x1800d3b71  lea     rcx, [rsp+188h+var_128]
0x1800d3b76  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800d3b7c  nop
0x1800d3b7d  lea     rdi, [r15+0A8h]
0x1800d3b84  lea     rdx, [rsp+188h+var_128]
0x1800d3b89  mov     rcx, rdi
0x1800d3b8c  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1800d3b92  nop
0x1800d3b93  lea     rcx, [rsp+188h+var_128]
0x1800d3b98  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800d3b9e  nop
0x1800d3b9f  lea     rcx, [rsp+188h+var_118]
0x1800d3ba4  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800d3baa  lea     rdx, aWork; "Work"
0x1800d3bb1  lea     rcx, [rsp+188h+var_118]
0x1800d3bb6  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800d3bbc  mov     rbx, rax
0x1800d3bbf  mov     rcx, rdi
0x1800d3bc2  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800d3bc8  mov     rdx, rbx
0x1800d3bcb  mov     rcx, rax
0x1800d3bce  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1800d3bd4  mov     rdx, rax
0x1800d3bd7  lea     rcx, [rsp+188h+var_128]
0x1800d3bdc  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800d3be2  nop
0x1800d3be3  lea     rcx, [r15+0B8h]
0x1800d3bea  lea     rdx, [rsp+188h+var_128]
0x1800d3bef  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1800d3bf5  nop
0x1800d3bf6  lea     rcx, [rsp+188h+var_128]
0x1800d3bfb  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800d3c01  nop
0x1800d3c02  lea     rcx, [rsp+188h+var_118]
0x1800d3c07  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800d3c0d  lea     rdx, aStore; "Store"
0x1800d3c14  lea     rcx, [rsp+188h+var_118]
0x1800d3c19  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800d3c1f  mov     rbx, rax
0x1800d3c22  mov     rcx, rdi
0x1800d3c25  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800d3c2b  mov     rdx, rbx
0x1800d3c2e  mov     rcx, rax
0x1800d3c31  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1800d3c37  mov     rdx, rax
0x1800d3c3a  lea     rcx, [rsp+188h+var_128]
0x1800d3c3f  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800d3c45  nop
0x1800d3c46  lea     rcx, [r15+0C8h]
0x1800d3c4d  lea     rdx, [rsp+188h+var_128]
0x1800d3c52  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1800d3c58  nop
0x1800d3c59  lea     rcx, [rsp+188h+var_128]
0x1800d3c5e  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800d3c64  nop
0x1800d3c65  lea     rcx, [rsp+188h+var_118]
0x1800d3c6a  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800d3c70  lea     rdx, aSources_1; "Sources"
0x1800d3c77  lea     rcx, [rsp+188h+var_118]
0x1800d3c7c  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800d3c82  mov     rbx, rax
0x1800d3c85  mov     rcx, rdi
0x1800d3c88  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800d3c8e  mov     rdx, rbx
0x1800d3c91  mov     rcx, rax
0x1800d3c94  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1800d3c9a  mov     rdx, rax
0x1800d3c9d  lea     rcx, [rsp+188h+var_128]
0x1800d3ca2  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800d3ca8  nop
0x1800d3ca9  lea     rdi, [r15+98h]
0x1800d3cb0  mov     [rsp+188h+var_A8], rdi
0x1800d3cb8  lea     rdx, [rsp+188h+var_128]
0x1800d3cbd  mov     rcx, rdi
0x1800d3cc0  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1800d3cc6  nop
0x1800d3cc7  lea     rcx, [rsp+188h+var_128]
0x1800d3ccc  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800d3cd2  nop
0x1800d3cd3  lea     rcx, [rsp+188h+var_118]
0x1800d3cd8  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800d3cde  lea     rdx, aRollback; "Rollback"
0x1800d3ce5  lea     rcx, [rsp+188h+var_118]
0x1800d3cea  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800d3cf0  mov     rbx, rax
0x1800d3cf3  mov     rcx, rdi
0x1800d3cf6  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800d3cfc  mov     rdx, rbx
0x1800d3cff  mov     rcx, rax
0x1800d3d02  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1800d3d08  mov     rdx, rax
0x1800d3d0b  lea     rcx, [rsp+188h+var_128]
0x1800d3d10  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800d3d16  nop
0x1800d3d17  lea     rcx, [r15+138h]
0x1800d3d1e  lea     rdx, [rsp+188h+var_128]
0x1800d3d23  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1800d3d29  nop
0x1800d3d2a  lea     rcx, [rsp+188h+var_128]
0x1800d3d2f  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800d3d35  nop
0x1800d3d36  lea     rcx, [rsp+188h+var_118]
0x1800d3d3b  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800d3d41  lea     rdx, aDiagnostics; "Diagnostics"
0x1800d3d48  lea     rcx, [rsp+188h+var_60]
0x1800d3d50  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800d3d56  mov     rbx, rax
0x1800d3d59  mov     rcx, rdi
0x1800d3d5c  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800d3d62  mov     rdx, rbx
0x1800d3d65  mov     rcx, rax
0x1800d3d68  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1800d3d6e  mov     rdx, rax
0x1800d3d71  lea     rcx, [rsp+188h+var_88]
0x1800d3d79  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800d3d7f  nop
0x1800d3d80  lea     rcx, [rsp+188h+var_60]
0x1800d3d88  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800d3d8e  lea     rdx, aDiagnosticsDat; "diagnostics.dat"
0x1800d3d95  lea     rcx, [rsp+188h+var_118]
0x1800d3d9a  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800d3da0  mov     rbx, rax
0x1800d3da3  lea     rcx, [rsp+188h+var_88]
0x1800d3dab  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800d3db1  mov     rdx, rbx
0x1800d3db4  mov     rcx, rax
0x1800d3db7  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1800d3dbd  mov     rdx, rax
0x1800d3dc0  lea     rcx, [rsp+188h+var_128]
0x1800d3dc5  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800d3dcb  nop
0x1800d3dcc  lea     rcx, [r15+0E8h]
0x1800d3dd3  lea     rdx, [rsp+188h+var_128]
0x1800d3dd8  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1800d3dde  nop
0x1800d3ddf  lea     rcx, [rsp+188h+var_128]
0x1800d3de4  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800d3dea  nop
0x1800d3deb  lea     rcx, [rsp+188h+var_118]
0x1800d3df0  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800d3df6  lea     rdx, aSafeos; "SafeOS"
0x1800d3dfd  lea     rcx, [rsp+188h+var_118]
0x1800d3e02  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800d3e08  mov     rbx, rax
0x1800d3e0b  mov     rcx, rdi
0x1800d3e0e  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800d3e14  mov     rdx, rbx
0x1800d3e17  mov     rcx, rax
0x1800d3e1a  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1800d3e20  mov     rdx, rax
0x1800d3e23  lea     rcx, [rsp+188h+var_128]
0x1800d3e28  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800d3e2e  nop
0x1800d3e2f  lea     rcx, [r15+0F8h]
0x1800d3e36  lea     rdx, [rsp+188h+var_128]
0x1800d3e3b  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1800d3e41  nop
0x1800d3e42  lea     rcx, [rsp+188h+var_128]
0x1800d3e47  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800d3e4d  nop
0x1800d3e4e  lea     rcx, [rsp+188h+var_118]
0x1800d3e53  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800d3e59  lea     rdx, aPanther; "Panther"
0x1800d3e60  lea     rcx, [rsp+188h+var_118]
0x1800d3e65  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800d3e6b  mov     rbx, rax
0x1800d3e6e  mov     rcx, rdi
0x1800d3e71  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800d3e77  mov     rdx, rbx
0x1800d3e7a  mov     rcx, rax
0x1800d3e7d  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1800d3e83  mov     rdx, rax
0x1800d3e86  lea     rcx, [rsp+188h+var_128]
0x1800d3e8b  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800d3e91  nop
0x1800d3e92  lea     rdi, [r15+108h]
0x1800d3e99  lea     rdx, [rsp+188h+var_128]
0x1800d3e9e  mov     rcx, rdi
0x1800d3ea1  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1800d3ea7  nop
0x1800d3ea8  lea     rcx, [rsp+188h+var_128]
0x1800d3ead  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800d3eb3  nop
0x1800d3eb4  lea     rcx, [rsp+188h+var_118]
0x1800d3eb9  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800d3ebf  lea     rdx, aSetupactLog_0; "SetupAct.log"
0x1800d3ec6  lea     rcx, [rsp+188h+var_118]
0x1800d3ecb  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800d3ed1  mov     rbx, rax
0x1800d3ed4  mov     rcx, rdi
0x1800d3ed7  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800d3edd  mov     rdx, rbx
0x1800d3ee0  mov     rcx, rax
0x1800d3ee3  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1800d3ee9  mov     rdx, rax
0x1800d3eec  lea     rcx, [rsp+188h+var_128]
0x1800d3ef1  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800d3ef7  nop
0x1800d3ef8  lea     rcx, [r15+118h]
0x1800d3eff  lea     rdx, [rsp+188h+var_128]
0x1800d3f04  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1800d3f0a  nop
0x1800d3f0b  lea     rcx, [rsp+188h+var_128]
0x1800d3f10  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800d3f16  nop
0x1800d3f17  lea     rcx, [rsp+188h+var_118]
0x1800d3f1c  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800d3f22  lea     rax, [r15+15Ch]
  ... truncated ...
```
