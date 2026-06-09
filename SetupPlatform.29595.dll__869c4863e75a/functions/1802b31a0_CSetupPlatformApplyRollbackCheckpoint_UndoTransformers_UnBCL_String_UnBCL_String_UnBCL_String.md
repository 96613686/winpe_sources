# CSetupPlatformApplyRollbackCheckpoint::UndoTransformers(UnBCL::String *,UnBCL::String *,UnBCL::String *)

- ea: `0x1802b31a0`
- end: `0x1802b54a4`
- name: `?UndoTransformers@CSetupPlatformApplyRollbackCheckpoint@@IEAAJPEAVString@UnBCL@@00@Z`
- size: `8964`
- prototype: `__int64 __fastcall(CSetupPlatformApplyRollbackCheckpoint *__hidden this, struct UnBCL::String *, struct UnBCL::String *, struct UnBCL::String *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1802a6aa0`

## callees

- `0x18001413d`
- `0x1800447ec`
- `0x180044810`
- `0x180057dec`
- `0x18005dd24`
- `0x18012a5c0`
- `0x18012b0fc`
- `0x1801556c4`
- `0x1802b31a0`
- `0x1802d8598`
- `0x1802db0f8`
- `0x1802e2078`
- `0x180509010`

## import_xrefs

- `ADVAPI32!RegLoadKeyW` at `0x1802b4a84`
- `ADVAPI32!RegLoadKeyW` at `0x1802b4c86`
- `ADVAPI32!RegLoadKeyW` at `0x1802b4a84`
- `ADVAPI32!RegLoadKeyW` at `0x1802b4c86`
- `ADVAPI32!RegUnLoadKeyW` at `0x1802b51ee`
- `ADVAPI32!RegUnLoadKeyW` at `0x1802b52ad`
- `ADVAPI32!RegUnLoadKeyW` at `0x1802b51ee`
- `ADVAPI32!RegUnLoadKeyW` at `0x1802b52ad`
- `KERNEL32!GetLastError` at `0x1802b3276`
- `KERNEL32!GetLastError` at `0x1802b337a`
- `KERNEL32!GetLastError` at `0x1802b3717`
- `KERNEL32!GetLastError` at `0x1802b3a7f`
- `KERNEL32!GetLastError` at `0x1802b3b97`
- `KERNEL32!GetLastError` at `0x1802b3c82`
- `KERNEL32!GetLastError` at `0x1802b3d7b`
- `KERNEL32!GetLastError` at `0x1802b3e42`
- `KERNEL32!GetLastError` at `0x1802b3f28`
- `KERNEL32!GetLastError` at `0x1802b3fd7`
- `KERNEL32!GetLastError` at `0x1802b402f`
- `KERNEL32!GetLastError` at `0x1802b40d1`
- `KERNEL32!GetLastError` at `0x1802b4144`
- `KERNEL32!GetLastError` at `0x1802b42d4`
- `KERNEL32!GetLastError` at `0x1802b43ee`
- `KERNEL32!GetLastError` at `0x1802b4546`
- `KERNEL32!GetLastError` at `0x1802b45d7`
- `KERNEL32!GetLastError` at `0x1802b4666`
- `KERNEL32!GetLastError` at `0x1802b46f2`
- `KERNEL32!GetLastError` at `0x1802b477f`
- `KERNEL32!GetLastError` at `0x1802b4809`
- `KERNEL32!GetLastError` at `0x1802b4af3`
- `KERNEL32!GetLastError` at `0x1802b4cf5`
- `KERNEL32!GetLastError` at `0x1802b4db9`
- `KERNEL32!GetLastError` at `0x1802b4e11`
- `KERNEL32!GetLastError` at `0x1802b4e9f`
- `KERNEL32!GetLastError` at `0x1802b4f34`
- `KERNEL32!GetLastError` at `0x1802b4fc9`
- `KERNEL32!GetLastError` at `0x1802b504c`
- `KERNEL32!GetLastError` at `0x1802b51f8`
- `KERNEL32!GetLastError` at `0x1802b52b7`
- `KERNEL32!GetLastError` at `0x1802b5336`
- `KERNEL32!GetLastError` at `0x1802b3276`
- `KERNEL32!GetLastError` at `0x1802b337a`
- `KERNEL32!GetLastError` at `0x1802b3717`
- `KERNEL32!GetLastError` at `0x1802b3a7f`
- `KERNEL32!GetLastError` at `0x1802b3b97`
- `KERNEL32!GetLastError` at `0x1802b3c82`
- `KERNEL32!GetLastError` at `0x1802b3d7b`
- `KERNEL32!GetLastError` at `0x1802b3e42`
- `KERNEL32!GetLastError` at `0x1802b3f28`
- `KERNEL32!GetLastError` at `0x1802b3fd7`
- `KERNEL32!GetLastError` at `0x1802b402f`
- `KERNEL32!GetLastError` at `0x1802b40d1`
- `KERNEL32!GetLastError` at `0x1802b4144`
- `KERNEL32!GetLastError` at `0x1802b42d4`
- `KERNEL32!GetLastError` at `0x1802b43ee`
- `KERNEL32!GetLastError` at `0x1802b4546`
- `KERNEL32!GetLastError` at `0x1802b45d7`
- `KERNEL32!GetLastError` at `0x1802b4666`
- `KERNEL32!GetLastError` at `0x1802b46f2`
- `KERNEL32!GetLastError` at `0x1802b477f`
- `KERNEL32!GetLastError` at `0x1802b4809`
- `KERNEL32!GetLastError` at `0x1802b4af3`
- `KERNEL32!GetLastError` at `0x1802b4cf5`
- `KERNEL32!GetLastError` at `0x1802b4db9`
- `KERNEL32!GetLastError` at `0x1802b4e11`
- `KERNEL32!GetLastError` at `0x1802b4e9f`
- `KERNEL32!GetLastError` at `0x1802b4f34`
- `KERNEL32!GetLastError` at `0x1802b4fc9`
- `KERNEL32!GetLastError` at `0x1802b504c`
- `KERNEL32!GetLastError` at `0x1802b51f8`
- `KERNEL32!GetLastError` at `0x1802b52b7`
- `KERNEL32!GetLastError` at `0x1802b5336`
- `ole32!CoInitializeSecurity` at `0x1802b3b86`
- `ole32!CoInitializeSecurity` at `0x1802b3b86`
- `ole32!CoSetProxyBlanket` at `0x1802b3d6a`
- `ole32!CoSetProxyBlanket` at `0x1802b3d6a`
- `ServicingCommon!CbsOfflineSetLogFile` at `0x1802b3c6b`
- `ServicingCommon!CbsOfflineSetLogFile` at `0x1802b3c6b`
- `ServicingCommon!CbsCreateOfflineSessionFromStackInImage` at `0x1802b3d1d`
- `ServicingCommon!CbsCreateOfflineSessionFromStackInImage` at `0x1802b3d1d`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x1802b34db`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x1802b350b`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x1802b3843`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x1802b3873`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x1802b34db`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x1802b350b`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x1802b3843`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x1802b3873`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802b44d4`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802b44f9`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802b44d4`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802b44f9`
- `unbcl!??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z` at `0x1802b3445`
- `unbcl!??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z` at `0x1802b37c8`
- `unbcl!??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z` at `0x1802b3445`
- `unbcl!??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z` at `0x1802b37c8`
- `unbcl!?Substring@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x1802b355d`
- `unbcl!?Substring@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x1802b38c5`
- `unbcl!?Substring@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x1802b355d`
- `unbcl!?Substring@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x1802b38c5`
- `unbcl!?Insert@String@UnBCL@@QEBAPEAV12@HPEBG@Z` at `0x1802b362d`
- `unbcl!?Insert@String@UnBCL@@QEBAPEAV12@HPEBG@Z` at `0x1802b3995`
- `unbcl!?Insert@String@UnBCL@@QEBAPEAV12@HPEBG@Z` at `0x1802b362d`
- `unbcl!?Insert@String@UnBCL@@QEBAPEAV12@HPEBG@Z` at `0x1802b3995`
- `unbcl!?get_Build@Version@UnBCL@@QEBAHXZ` at `0x1802b404a`
- `unbcl!?get_Build@Version@UnBCL@@QEBAHXZ` at `0x1802b41ca`
- `unbcl!?get_Build@Version@UnBCL@@QEBAHXZ` at `0x1802b404a`
- `unbcl!?get_Build@Version@UnBCL@@QEBAHXZ` at `0x1802b41ca`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x1802b4945`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x1802b4945`
- `unbcl!?get_Minor@Version@UnBCL@@QEBAHXZ` at `0x1802b405c`
- `unbcl!?get_Minor@Version@UnBCL@@QEBAHXZ` at `0x1802b41dd`
- `unbcl!?get_Minor@Version@UnBCL@@QEBAHXZ` at `0x1802b405c`
- `unbcl!?get_Minor@Version@UnBCL@@QEBAHXZ` at `0x1802b41dd`
- `unbcl!?get_Major@Version@UnBCL@@QEBAHXZ` at `0x1802b406c`
- `unbcl!?get_Major@Version@UnBCL@@QEBAHXZ` at `0x1802b41f0`
- `unbcl!?get_Major@Version@UnBCL@@QEBAHXZ` at `0x1802b406c`
- `unbcl!?get_Major@Version@UnBCL@@QEBAHXZ` at `0x1802b41f0`
- `unbcl!?Exists@File@UnBCL@@SAHPEBVString@2@@Z` at `0x1802b3266`
- `unbcl!?Exists@File@UnBCL@@SAHPEBVString@2@@Z` at `0x1802b3266`
- `unbcl!?Remove@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x1802b3587`
- `unbcl!?Remove@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x1802b35b6`
- `unbcl!?Remove@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x1802b38ef`
- `unbcl!?Remove@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x1802b391e`
- `unbcl!?Remove@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x1802b3587`
- `unbcl!?Remove@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x1802b35b6`
- `unbcl!?Remove@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x1802b38ef`
- `unbcl!?Remove@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x1802b391e`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802b4ab1`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802b4c0b`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802b4cb3`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802b4ab1`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802b4c0b`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802b4cb3`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1802b3b25`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1802b3f13`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1802b3b25`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1802b3f13`
- `unbcl!?get_P@?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@2@XZ` at `0x1802b34a3`
- `unbcl!?get_P@?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@2@XZ` at `0x1802b3826`
- `unbcl!?get_P@?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@2@XZ` at `0x1802b34a3`
- `unbcl!?get_P@?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@2@XZ` at `0x1802b3826`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802b31ed`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802b322f`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802b3c2b`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802b499c`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802b4bc4`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802b31ed`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802b322f`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802b3c2b`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802b499c`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802b4bc4`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1802b446f`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1802b44a8`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1802b446f`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1802b44a8`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x1802b36b2`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x1802b36c3`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x1802b3a1a`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x1802b3a2b`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x1802b36b2`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x1802b36c3`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x1802b3a1a`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x1802b3a2b`
- `unbcl!??0Version@UnBCL@@QEAA@PEBG@Z` at `0x1802b3fd0`
- `unbcl!??0Version@UnBCL@@QEAA@PEBG@Z` at `0x1802b3fd0`
- `unbcl!??_DVersion@UnBCL@@QEAAXXZ` at `0x1802b5430`
- `unbcl!??_DVersion@UnBCL@@QEAAXXZ` at `0x1802b5430`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802b325d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802b336b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802b4210`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802b325d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802b336b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802b4210`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802b48e2`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802b48f1`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802b4900`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802b490f`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802b48e2`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802b48f1`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802b4900`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802b490f`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802b320d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802b324f`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802b3c4b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802b49bc`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802b4be4`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802b320d`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802b324f`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802b3c4b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802b49bc`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802b4be4`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802b31e0`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802b3222`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802b3c19`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802b498f`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802b49fa`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802b4bb2`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802b31e0`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802b3222`

## string_xrefs

- `0x1802b3bb0`: `Failed to initialize COM security. Will use CoSetProxyBlanket instead. hr = 0x%08X`
- `0x1802b32d0`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802b33d4`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802b34b0`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802b4487`: `base\ntsetup\setupplatform\lib\rollback\rollback.cpp`
- `0x1802b4560`: `Failed to initialize COM. hr = 0x%08X`
- `0x1802b32c4`: `CSetupPlatformApplyRollbackCheckpoint::UndoTransformers`
- `0x1802b33c8`: `CSetupPlatformApplyRollbackCheckpoint::UndoTransformers`
- `0x1802b34a9`: `CSetupPlatformApplyRollbackCheckpoint::UndoTransformers`
- `0x1802b4480`: `CSetupPlatformApplyRollbackCheckpoint::UndoTransformers`
- `0x1802b3213`: `TransformersRollback.ini`
- `0x1802b45f0`: `Failed to create offline CBS session. hr = 0x%08X`
- `0x1802b40f8`: `    Windows directory: %s`
- `0x1802b4795`: `Failed to create the transformer executor. hr = 0x%08X`
- `0x1802b4407`: `Call to Transformer Uninstall failed. Error: 0x%08X`
- `0x1802b432b`: `Calling transformer Uninstall for %s, manifest %s`
- `0x1802b5228`: `Failed to unload %s, this is most likely a registry leak from the transformer layer`
- `0x1802b52e7`: `Failed to unload %s, this is most likely a registry leak from the transformer layer`
- `0x1802b5350`: `Failure while calling Transformer Commit. Error: 0x%08X`
- `0x1802b4e50`: `    User SID: %s`
- `0x1802b4dca`: `Calling Transformer Commit with parameters:`
- `0x1802b53a4`: `Transformer Commit succeeded`

## pseudocode

```c
// Hidden C++ exception states: #wind=46
__int64 __fastcall CSetupPlatformApplyRollbackCheckpoint::UndoTransformers(
        CSetupPlatformApplyRollbackCheckpoint *this,
        struct UnBCL::String *a2,
        struct UnBCL::String *a3,
        struct UnBCL::String *a4)
{
  UnBCL::String *v5; // rdi
  const struct UnBCL::String *v6; // rdx
  struct UnBCL::String *v7; // rax
  const struct UnBCL::String *v8; // rax
  struct UnBCL::String *v9; // rax
  const struct UnBCL::String *P; // rax
  DWORD v11; // edi
  __int64 v12; // rbx
  UnBCL::String *v13; // rax
  const char *v14; // rax
  struct tagLOG_PARTIAL_MSG *v15; // rax
  UnBCL::String *v17; // rax
  const WCHAR *CString; // rax
  struct UnBCL::String *v19; // rax
  DWORD v20; // edi
  __int64 v21; // rbx
  UnBCL::String *v22; // rax
  const char *v23; // rax
  struct tagLOG_PARTIAL_MSG *v24; // rax
  UnBCL::String *v25; // rax
  const WCHAR *v26; // rax
  __int64 v27; // rax
  CSetupPlatformApplyRollbackCheckpoint *v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rax
  int i; // ebx
  __int64 v32; // rax
  int (__fastcall ***v33)(_QWORD); // rcx
  __int64 v34; // rax
  __int64 v35; // rcx
  int v36; // eax
  struct UnBCL::String *v37; // rax
  struct UnBCL::String *v38; // rax
  UnBCL::String *v39; // rax
  struct UnBCL::String *v40; // rax
  UnBCL::String *v41; // rax
  struct UnBCL::String *v42; // rax
  __int64 v43; // rbx
  __int64 v44; // rax
  __int64 v45; // r9
  __int64 v46; // rax
  DWORD LastError; // edi
  __int64 v48; // rbx
  const char *v49; // rax
  struct tagLOG_PARTIAL_MSG *v50; // rax
  UnBCL::String *v51; // rax
  const WCHAR *v52; // rax
  __int64 v53; // rax
  CSetupPlatformApplyRollbackCheckpoint *v54; // rax
  __int64 v55; // rdx
  __int64 v56; // rax
  int j; // ebx
  __int64 v58; // rax
  int (__fastcall ***v59)(_QWORD); // rcx
  __int64 v60; // rax
  __int64 v61; // rcx
  int v62; // eax
  struct UnBCL::String *v63; // rax
  struct UnBCL::String *v64; // rax
  UnBCL::String *v65; // rax
  struct UnBCL::String *v66; // rax
  UnBCL::String *v67; // rax
  struct UnBCL::String *v68; // rax
  __int64 v69; // rbx
  __int64 v70; // rax
  __int64 v71; // r9
  __int64 v72; // rax
  DWORD v73; // edi
  __int64 v74; // rbx
  const char *v75; // rax
  struct tagLOG_PARTIAL_MSG *v76; // rax
  DWORD v77; // edi
  __int64 v78; // rbx
  struct tagLOG_PARTIAL_MSG *v79; // rax
  const struct UnBCL::String *v80; // rax
  struct UnBCL::String *v81; // rax
  UnBCL::String *v82; // rax
  const unsigned __int16 *v83; // rax
  int v84; // ebx
  UnBCL::String *v85; // rax
  const char *v86; // rax
  struct tagLOG_PARTIAL_MSG *v87; // rax
  const unsigned __int16 *v88; // rax
  DWORD v89; // edi
  __int64 v90; // rbx
  struct tagLOG_PARTIAL_MSG *v91; // rax
  const unsigned __int16 *v92; // rbx
  const unsigned __int16 *v93; // rax
  DWORD v94; // edi
  __int64 v95; // rbx
  struct tagLOG_PARTIAL_MSG *v96; // rax
  __int64 (__fastcall ***v97)(_QWORD); // rcx
  int v98; // eax
  DWORD v99; // edi
  __int64 v100; // rbx
  struct tagLOG_PARTIAL_MSG *v101; // rax
  UnBCL::String *v102; // rax
  const unsigned __int16 *v103; // rax
  DWORD v104; // edi
  __int64 v105; // rbx
  struct tagLOG_PARTIAL_MSG *v106; // rax
  DWORD v107; // edi
  int Major; // eax
  struct tagLOG_PARTIAL_MSG *v109; // rax
  UnBCL::String *v110; // rdi
  const char *v111; // rax
  struct tagLOG_PARTIAL_MSG *v112; // rax
  UnBCL::String *v113; // rax
  const char *v114; // rax
  struct tagLOG_PARTIAL_MSG *v115; // rax
  UnBCL::String *v116; // rax
  const unsigned __int16 *v117; // rbx
  const unsigned __int16 *v118; // rax
  int k; // edi
  __int64 v120; // rbx
  int (__fastcall ***v121)(_QWORD); // rcx
  __int64 v122; // rcx
  __int64 v123; // rbx
  UnBCL::String *v124; // rax
  UnBCL::String *v125; // rax
  const char *v126; // rax
  struct tagLOG_PARTIAL_MSG *v127; // rax
  UnBCL::String *v128; // rax
  UnBCL::String *v129; // rax
  const unsigned __int16 *v130; // rax
  DWORD v131; // edi
  __int64 v132; // rbx
  struct tagLOG_PARTIAL_MSG *v133; // rax
  DWORD v134; // edi
  __int64 v135; // rbx
  struct tagLOG_PARTIAL_MSG *v136; // rax
  DWORD v137; // edi
  __int64 v138; // rbx
  struct tagLOG_PARTIAL_MSG *v139; // rax
  DWORD v140; // edi
  __int64 v141; // rbx
  struct tagLOG_PARTIAL_MSG *v142; // rax
  DWORD v143; // edi
  __int64 v144; // rbx
  struct tagLOG_PARTIAL_MSG *v145; // rax
  DWORD v146; // edi
  __int64 v147; // rbx
  struct tagLOG_PARTIAL_MSG *v148; // rax
  DWORD v149; // edi
  __int64 v150; // rbx
  struct tagLOG_PARTIAL_MSG *v151; // rax
  __int64 v152; // rax
  __int64 v153; // rcx
  __int64 v154; // rdi
  UnBCL::String *v155; // rax
  const unsigned __int16 *v156; // rax
  UnBCL::String *v157; // rbx
  const struct UnBCL::String *v158; // rax
  struct UnBCL::String *v159; // rax
  UnBCL::String *v160; // rbx
  UnBCL::String *v161; // rax
  const unsigned __int16 *v162; // rax
  UnBCL::String *v163; // rax
  const WCHAR *v164; // rbx
  UnBCL::String *v165; // rax
  const WCHAR *v166; // rax
  LSTATUS KeyW; // ebx
  UnBCL::String *v168; // rax
  const unsigned __int16 *v169; // rax
  struct UnBCL::String *v170; // rax
  UnBCL::String *v171; // rax
  UnBCL::String *v172; // rax
  const char *v173; // rax
  struct tagLOG_PARTIAL_MSG *v174; // rax
  const struct UnBCL::String *v175; // rax
  struct UnBCL::String *v176; // rax
  UnBCL::String *v177; // rax
  const unsigned __int16 *v178; // rax
  struct UnBCL::String *v179; // rax
  UnBCL::String *v180; // rax
  const WCHAR *v181; // rbx
  UnBCL::String *v182; // rax
  const WCHAR *v183; // rax
  LSTATUS v184; // ebx
  UnBCL::String *v185; // rax
  const unsigned __int16 *v186; // rax
  struct UnBCL::String *v187; // rax
  UnBCL::String *v188; // rax
  const char *v189; // rdi
  UnBCL::String *v190; // rax
  const char *v191; // rax
  struct tagLOG_PARTIAL_MSG *v192; // rax
  DWORD v193; // edi
  __int64 v194; // rbx
  struct tagLOG_PARTIAL_MSG *v195; // rax
  DWORD v196; // edi
  const wchar_t *v197; // rax
  const wchar_t *v198; // rbx
  struct tagLOG_PARTIAL_MSG *v199; // rax
  DWORD v200; // edi
  __int64 v201; // rdx
  UnBCL::String *v202; // rax
  const wchar_t *v203; // rax
  struct tagLOG_PARTIAL_MSG *v204; // rax
  DWORD v205; // edi
  __int64 v206; // rdx
  UnBCL::String *v207; // rax
  const wchar_t *v208; // rax
  struct tagLOG_PARTIAL_MSG *v209; // rax
  DWORD v210; // edi
  const wchar_t *v211; // rax
  struct tagLOG_PARTIAL_MSG *v212; // rax
  DWORD v213; // edi
  __int64 v214; // rdx
  UnBCL::String *v215; // rax
  struct tagLOG_PARTIAL_MSG *v216; // rax
  __int64 v217; // rdx
  __int64 v218; // rdx
  UnBCL::String *v219; // rax
  const unsigned __int16 *v220; // rdi
  UnBCL::String *v221; // rax
  const unsigned __int16 *v222; // rbx
  const unsigned __int16 *v223; // rax
  int v224; // ebx
  __int64 v225; // rdx
  __int64 v226; // rdx
  UnBCL::String *v227; // rax
  const WCHAR *v228; // rax
  DWORD v229; // edi
  UnBCL::String *v230; // rax
  const char *v231; // rax
  struct tagLOG_PARTIAL_MSG *v232; // rax
  UnBCL::String *v233; // rax
  const WCHAR *v234; // rax
  DWORD v235; // edi
  UnBCL::String *v236; // rax
  const char *v237; // rax
  struct tagLOG_PARTIAL_MSG *v238; // rax
  DWORD v239; // edi
  __int64 v240; // rax
  bool v241; // sf
  __int64 v242; // rbx
  struct tagLOG_PARTIAL_MSG *v243; // rax
  struct tagLOG_PARTIAL_MSG *v244; // rax
  _BYTE *v245; // rbp
  __int64 v246; // rcx
  _BYTE *v247; // rbp
  __int64 v248; // rcx
  __int64 v249; // rcx
  _BYTE *v250; // rdx
  _BYTE *v251; // rdx
  _BYTE v252[32]; // [rsp+0h] [rbp-388h] BYREF
  DWORD dwAuthnLevel[2]; // [rsp+20h] [rbp-368h]
  DWORD dwImpLevel[2]; // [rsp+28h] [rbp-360h]
  const unsigned __int16 *v255; // [rsp+60h] [rbp-328h]
  int v256; // [rsp+68h] [rbp-320h]
  UnBCL::String *QueryInterface; // [rsp+70h] [rbp-318h]
  UnBCL::String *v258; // [rsp+78h] [rbp-310h] BYREF
  __int64 v259; // [rsp+80h] [rbp-308h]
  int v260; // [rsp+88h] [rbp-300h]
  unsigned int v261; // [rsp+8Ch] [rbp-2FCh]
  UnBCL::String *v262; // [rsp+90h] [rbp-2F8h]
  _BYTE v263[16]; // [rsp+98h] [rbp-2F0h] BYREF
  int v264[2]; // [rsp+A8h] [rbp-2E0h] BYREF
  IUnknown *pProxy; // [rsp+B0h] [rbp-2D8h] BYREF
  const char *v266; // [rsp+B8h] [rbp-2D0h]
  __int64 v267; // [rsp+C0h] [rbp-2C8h] BYREF
  _BYTE v268[16]; // [rsp+C8h] [rbp-2C0h] BYREF
  _BYTE v269[16]; // [rsp+D8h] [rbp-2B0h] BYREF
  _BYTE v270[16]; // [rsp+E8h] [rbp-2A0h] BYREF
  _BYTE v271[16]; // [rsp+F8h] [rbp-290h] BYREF
  _BYTE v272[16]; // [rsp+108h] [rbp-280h] BYREF
  _BYTE v273[16]; // [rsp+118h] [rbp-270h] BYREF
  _BYTE v274[16]; // [rsp+128h] [rbp-260h] BYREF
  _BYTE v275[16]; // [rsp+138h] [rbp-250h] BYREF
  const __int64 *v276; // [rsp+148h] [rbp-240h] BYREF
  _QWORD *v277; // [rsp+150h] [rbp-238h]
  const __int64 *v278; // [rsp+158h] [rbp-230h] BYREF
  _QWORD *v279; // [rsp+160h] [rbp-228h]
  _BYTE v280[16]; // [rsp+168h] [rbp-220h] BYREF
  _BYTE v281[16]; // [rsp+178h] [rbp-210h] BYREF
  _BYTE v282[16]; // [rsp+188h] [rbp-200h] BYREF
  _QWORD *pExceptionObject; // [rsp+198h] [rbp-1F0h] BYREF
  _QWORD *v284; // [rsp+1A0h] [rbp-1E8h] BYREF
  _QWORD *v285; // [rsp+1A8h] [rbp-1E0h] BYREF
  _QWORD *v286; // [rsp+1B0h] [rbp-1D8h] BYREF
  _QWORD *v287; // [rsp+1B8h] [rbp-1D0h] BYREF
  _QWORD *v288; // [rsp+1C0h] [rbp-1C8h] BYREF
  _QWORD *v289; // [rsp+1C8h] [rbp-1C0h] BYREF
  _QWORD *v290; // [rsp+1D0h] [rbp-1B8h] BYREF
  _BYTE v291[24]; // [rsp+1D8h] [rbp-1B0h] BYREF
  _BYTE v292[24]; // [rsp+1F0h] [rbp-198h] BYREF
  _BYTE v293[16]; // [rsp+208h] [rbp-180h] BYREF
  _BYTE v294[16]; // [rsp+218h] [rbp-170h] BYREF
  _QWORD v295[8]; // [rsp+228h] [rbp-160h] BYREF
  _QWORD v296[7]; // [rsp+268h] [rbp-120h] BYREF
  _BYTE v297[24]; // [rsp+2A0h] [rbp-E8h] BYREF
  _BYTE v298[24]; // [rsp+2B8h] [rbp-D0h] BYREF
  _BYTE v299[32]; // [rsp+2D0h] [rbp-B8h] BYREF
  _BYTE v300[152]; // [rsp+2F0h] [rbp-98h] BYREF
  CSetupPlatformApplyRollbackCheckpoint *v301; // [rsp+390h] [rbp+8h] BYREF
  const struct UnBCL::String *v302; // [rsp+398h] [rbp+10h]
  UnBCL::String *v303; // [rsp+3A0h] [rbp+18h]

  v303 = a3;
  v302 = a2;
  v301 = this;
  v295[7] = -2;
  v5 = a3;
  v6 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v292, L"CBS");
  v7 = UnBCL::Path::Combine(a4, v6);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v272, v7);
  UnBCL::String::~String((UnBCL::String *)v292);
  v8 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v291, L"TransformersRollback.ini");
  v9 = UnBCL::Path::Combine(a4, v8);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v270, v9);
  UnBCL::String::~String((UnBCL::String *)v291);
  P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v270);
  if ( UnBCL::File::Exists(P) )
  {
    v17 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v270);
    CString = UnBCL::String::get_CString(v17);
    v19 = SPReadConfigValue(L"Info", L"Version", CString);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v282, v19);
    if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v282) )
    {
      v25 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v270);
      v26 = UnBCL::String::get_CString(v25);
      v27 = SPGetSectionLines(v26, L"Transformers");
      UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::SmartPtr<UnBCL::Array<UnBCL::String *>>(v281, v27);
      v28 = (CSetupPlatformApplyRollbackCheckpoint *)UnBCL::Object::operator new(0x80u);
      v301 = v28;
      if ( v28 )
        v30 = UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>(
                v28,
                v29);
      else
        v30 = 0;
      UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>>::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>>(
        &v278,
        v30);
      (*(void (__fastcall **)(_QWORD *, __int64))(*v279 + 40LL))(v279, 1);
      if ( UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::get_P(v281) )
      {
        for ( i = 0; ; ++i )
        {
          v256 = i;
          v32 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v281);
          v33 = (int (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v32 + 8) + 12LL) + v32 + 8);
          if ( i >= (**v33)(v33) )
            break;
          v34 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v281);
          v35 = *(int *)(*(_QWORD *)(v34 + 8) + 16LL) + v34 + 8;
          v258 = *(UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v35 + 24LL))(
                                      v35,
                                      (unsigned int)i);
          v36 = UnBCL::String::IndexOf(v258, 0x3Du);
          v264[0] = v36;
          if ( v36 <= 0 )
          {
            LastError = GetLastError();
            v48 = CurrentIP();
            v49 = (const char *)UnBCL::String::get_CString(v258);
            v50 = ConstructPartialMsgW(
                    0x3000000u,
                    "Corrupt line in the %s section. Line: %s",
                    (const char *)L"Transformers",
                    v49);
            WdsSetupLogMessageW(
              v50,
              819200,
              L"D",
              0,
              2865,
              L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
              L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
              v48,
              LastError,
              0,
              0);
            i = v256;
            v5 = v303;
          }
          else
          {
            v37 = UnBCL::String::Substring(v258, 0, v36);
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v269, v37);
            v38 = UnBCL::String::Remove(v258, 0, v264[0] + 1);
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v263, v38);
            v39 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v263);
            v40 = UnBCL::String::Remove(v39, 0, 1);
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v271, v40);
            UnBCL::SmartPtr<UnBCL::String>::operator=(v263, v271);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v271);
            LODWORD(v301) = 63;
            LOWORD(v301) = *UnBCL::String::get_CString(v5);
            v41 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v263);
            v42 = UnBCL::String::Insert(v41, 0, (const unsigned __int16 *)&v301);
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v268, v42);
            UnBCL::SmartPtr<UnBCL::String>::operator=(v263, v268);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v268);
            v258 = (UnBCL::String *)((char *)v279 + *(int *)(v279[1] + 16LL) + 8);
            *(_QWORD *)v264 = *(_QWORD *)(*(_QWORD *)v258 + 40LL);
            QueryInterface = (UnBCL::String *)UnBCL::Object::operator new(0x40u);
            if ( QueryInterface )
            {
              v43 = UnBCL::SmartPtr<UnBCL::String>::Steal(v263);
              v44 = UnBCL::SmartPtr<UnBCL::String>::Steal(v269);
              v46 = UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>::DictionaryEntry<UnBCL::String *,UnBCL::String *>(
                      QueryInterface,
                      v44,
                      v43,
                      v45,
                      dwAuthnLevel[0],
                      dwImpLevel[0]);
              i = v256;
            }
            else
            {
              v46 = 0;
            }
            (*(void (__fastcall **)(UnBCL::String *, __int64))v264)(v258, v46);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v263);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v269);
          }
        }
      }
      v51 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v270);
      v52 = UnBCL::String::get_CString(v51);
      v53 = SPGetSectionLines(v52, L"Contexts");
      UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::SmartPtr<UnBCL::Array<UnBCL::String *>>(v280, v53);
      v54 = (CSetupPlatformApplyRollbackCheckpoint *)UnBCL::Object::operator new(0x80u);
      v301 = v54;
      if ( v54 )
        v56 = UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>(
                v54,
                v55);
      else
        v56 = 0;
      UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>>::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>>(
        &v276,
        v56);
      (*(void (__fastcall **)(_QWORD *, __int64))(*v277 + 40LL))(v277, 1);
      if ( UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::get_P(v280) )
      {
        for ( j = 0; ; ++j )
        {
          v256 = j;
          v58 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v280);
          v59 = (int (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v58 + 8) + 12LL) + v58 + 8);
          if ( j >= (**v59)(v59) )
            break;
          v60 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v280);
          v61 = *(int *)(*(_QWORD *)(v60 + 8) + 16LL) + v60 + 8;
          v258 = *(UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v61 + 24LL))(
                                      v61,
                                      (unsigned int)j);
          v62 = UnBCL::String::IndexOf(v258, 0x3Du);
          v264[0] = v62;
          if ( v62 <= 0 )
          {
            v73 = GetLastError();
            v74 = CurrentIP();
            v75 = (const char *)UnBCL::String::get_CString(v258);
            v76 = ConstructPartialMsgW(
                    0x3000000u,
                    "Corrupt line in the %s section. Line: %s",
                    (const char *)L"Contexts",
                    v75);
            WdsSetupLogMessageW(
              v76,
              819200,
              L"D",
              0,
              2893,
              L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
              L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
              v74,
              v73,
              0,
              0);
            j = v256;
            v5 = v303;
          }
          else
          {
            v63 = UnBCL::String::Substring(v258, 0, v62);
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v269, v63);
            v64 = UnBCL::String::Remove(v258, 0, v264[0] + 1);
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v263, v64);
            v65 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v263);
            v66 = UnBCL::String::Remove(v65, 0, 1);
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v271, v66);
            UnBCL::SmartPtr<UnBCL::String>::operator=(v263, v271);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v271);
            LODWORD(v301) = 63;
            LOWORD(v301) = *UnBCL::String::get_CString(v5);
            v67 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v263);
            v68 = UnBCL::String::Insert(v67, 0, (const unsigned __int16 *)&v301);
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v268, v68);
            UnBCL::SmartPtr<UnBCL::String>::operator=(v263, v268);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v268);
            v258 = (UnBCL::String *)((char *)v277 + *(int *)(v277[1] + 16LL) + 8);
            *(_QWORD *)v264 = *(_QWORD *)(*(_QWORD *)v258 + 40LL);
            QueryInterface = (UnBCL::String *)UnBCL::Object::operator new(0x40u);
            if ( QueryInterface )
            {
              v69 = UnBCL::SmartPtr<UnBCL::String>::Steal(v263);
              v70 = UnBCL::SmartPtr<UnBCL::String>::Steal(v269);
              v72 = UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>::DictionaryEntry<UnBCL::String *,UnBCL::String *>(
                      QueryInterface,
                      v70,
                      v69,
                      v71,
                      dwAuthnLevel[0],
                      dwImpLevel[0]);
              j = v256;
            }
            else
            {
              v72 = 0;
            }
            (*(void (__fastcall **)(UnBCL::String *, __int64))v264)(v258, v72);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v263);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v269);
          }
        }
      }
      v264[0] = 0;
      pProxy = 0;
      v267 = 0;
      v260 = 0;
      UnBCL::Exception::Exception((UnBCL::Exception *)v295);
      v295[0] = &`CSetupPlatformApplyRollbackCheckpoint::UndoTransformers'::`29'::CXXXXXHandledException::`vftable';
      try
      {
        try
        {
          LODWORD(v301) = SPInitializeCOM(v264);
          if ( (int)v301 < 0 )
          {
            v134 = GetLastError();
            v135 = CurrentIP();
            v136 = ConstructPartialMsgW(0x2000000u, "Failed to initialize COM. hr = 0x%08X", (_DWORD)v301);
            WdsSetupLogMessageW(
              v136,
              819200,
              L"D",
              0,
              2909,
              L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
              L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
              v135,
              v134,
              0,
              0);
            v260 = 1;
            pExceptionObject = v295;
            throw (`CSetupPlatformApplyRollbackCheckpoint::UndoTransformers(UnBCL::String *,UnBCL::String *,UnBCL::String *)'::`29'::CXXXXXHandledException **)&pExceptionObject;
          }
          v261 = 0;
          LODWORD(v301) = CoInitializeSecurity(0, -1, 0, 0, 5u, 3u, 0, 0, 0);
          if ( (int)v301 < 0 )
          {
            v77 = GetLastError();
            v78 = CurrentIP();
            v79 = ConstructPartialMsgW(
                    0x3000000u,
                    "Failed to initialize COM security. Will use CoSetProxyBlanket instead. hr = 0x%08X",
                    (_DWORD)v301);
            WdsSetupLogMessageW(
              v79,
              819200,
              L"D",
              0,
              2928,
              L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
              L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
              v78,
              v77,
              0,
              0);
            v261 = 1;
            v5 = v303;
          }
          v80 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v297, L"CBS.LOG");
          v81 = UnBCL::Path::Combine(v302, v80);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v271, v81);
          UnBCL::String::~String((UnBCL::String *)v297);
          v82 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v271);
          v83 = UnBCL::String::get_CString(v82);
          v84 = CbsOfflineSetLogFile(v83);
          LODWORD(v301) = v84;
          if ( v84 < 0 )
          {
            LODWORD(v255) = GetLastError();
            QueryInterface = (UnBCL::String *)CurrentIP();
            v85 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v271);
            v86 = (const char *)UnBCL::String::get_CString(v85);
            v87 = ConstructPartialMsgW(0x2000000u, "Failed to set the CBS log file to %s. hr = 0x%08X", v86, v84);
            WdsSetupLogMessageW(
              v87,
              819200,
              L"D",
              0,
              2937,
              L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
              L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
              QueryInterface,
              (_DWORD)v255,
              0,
              0);
          }
          v88 = UnBCL::String::get_CString(v5);
          LODWORD(v301) = CbsCreateOfflineSessionFromStackInImage(1, v88, &pProxy);
          if ( (int)v301 < 0 )
          {
            v137 = GetLastError();
            v138 = CurrentIP();
            v139 = ConstructPartialMsgW(0x2000000u, "Failed to create offline CBS session. hr = 0x%08X", (_DWORD)v301);
            WdsSetupLogMessageW(
              v139,
              819200,
              L"D",
              0,
              2949,
              L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
              L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
              v138,
              v137,
              0,
              0);
            v260 = 1;
            v284 = v295;
            throw (`CSetupPlatformApplyRollbackCheckpoint::UndoTransformers(UnBCL::String *,UnBCL::String *,UnBCL::String *)'::`29'::CXXXXXHandledException **)&v284;
          }
          if ( v261 )
          {
            LODWORD(v301) = CoSetProxyBlanket(
                              pProxy,
                              0xFFFFFFFF,
                              0xFFFFFFFF,
                              (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
                              5u,
                              3u,
                              0,
                              0);
            if ( (int)v301 < 0 )
            {
              v89 = GetLastError();
              v90 = CurrentIP();
              v91 = ConstructPartialMsgW(
                      0x3000000u,
                      "Failed to set proxy blanket for the CBS session. Error: 0x%08X",
                      (_DWORD)v301);
              WdsSetupLogMessageW(
                v91,
                819200,
                L"D",
                0,
                2968,
                L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
                v90,
                v89,
                0,
                0);
              v5 = v303;
            }
          }
          QueryInterface = (UnBCL::String *)pProxy->lpVtbl[1].QueryInterface;
          v92 = UnBCL::String::get_CString(v5);
          v93 = UnBCL::String::get_CString(v5);
          LODWORD(v255) = ((__int64 (__fastcall *)(IUnknown *, _QWORD, const wchar_t *, const unsigned __int16 *, const unsigned __int16 *))QueryInterface)(
                            pProxy,
                            0,
                            L"Setup Platform",
                            v93,
                            v92);
          LODWORD(v301) = (_DWORD)v255;
          if ( (int)v255 < 0 )
          {
            v140 = GetLastError();
            v141 = CurrentIP();
            v142 = ConstructPartialMsgW(0x2000000u, "Failed to initialize the CBS session. hr = 0x%08X", (_DWORD)v255);
            WdsSetupLogMessageW(
              v142,
              819200,
              L"D",
              0,
              2977,
              L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
              L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
              v141,
              v140,
              0,
              0);
            v260 = 1;
            v285 = v295;
            throw (`CSetupPlatformApplyRollbackCheckpoint::UndoTransformers(UnBCL::String *,UnBCL::String *,UnBCL::String *)'::`29'::CXXXXXHandledException **)&v285;
          }
          v94 = GetLastError();
          v95 = CurrentIP();
          v96 = ConstructPartialMsgW(0x4000000u, "Instantiating an ICbsSession9 interface");
          WdsSetupLogMessageW(
            v96,
            819200,
            L"D",
            0,
            2982,
            L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
            L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
            v95,
            v94,
            0,
            0);
          LODWORD(v255) = ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))pProxy->lpVtbl->QueryInterface)(
                            pProxy,
                            &GUID_9c7e3cf3_4c97_4d36_bdeb_e3093c228c22,
                            &v267);
          LODWORD(v301) = (_DWORD)v255;
          if ( (int)v255 < 0 )
          {
            v143 = GetLastError();
            v144 = CurrentIP();
            v145 = ConstructPartialMsgW(0x2000000u, "Failed to initialize the CBS session 8. hr = 0x%08X", (_DWORD)v255);
            WdsSetupLogMessageW(
              v145,
              819200,
              L"D",
              0,
              2986,
              L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
              L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
              v144,
              v143,
              0,
              0);
            v260 = 1;
            v286 = v295;
            throw (`CSetupPlatformApplyRollbackCheckpoint::UndoTransformers(UnBCL::String *,UnBCL::String *,UnBCL::String *)'::`29'::CXXXXXHandledException **)&v286;
          }
          v97 = (__int64 (__fastcall ***)(_QWORD))((char *)v277 + *(int *)(v277[1] + 12LL) + 8);
          v98 = (**v97)(v97) - 1;
          while ( 2 )
          {
            v261 = v98;
            if ( v98 >= 0 )
            {
              v258 = 0;
              v256 = 0;
              UnBCL::Exception::Exception((UnBCL::Exception *)v296);
              try
              {
                try
                {
                  v296[0] = &`CSetupPlatformApplyRollbackCheckpoint::UndoTransformers'::`63'::CXXXXXHandledException::`vftable';
                  v99 = GetLastError();
                  v100 = CurrentIP();
                  v101 = ConstructPartialMsgW(0x4000000u, "Creating a transformer executor");
                  WdsSetupLogMessageW(
                    v101,
                    819200,
                    L"D",
                    0,
                    2999,
                    L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                    L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
                    v100,
                    v99,
                    0,
                    0);
                  LODWORD(v255) = (*(__int64 (__fastcall **)(__int64, UnBCL::String **))(*(_QWORD *)v267 + 160LL))(
                                    v267,
                                    &v258);
                  if ( (int)v255 < 0 )
                  {
                    v146 = GetLastError();
                    v147 = CurrentIP();
                    v148 = ConstructPartialMsgW(
                             0x2000000u,
                             "Failed to create the transformer executor. hr = 0x%08X",
                             (_DWORD)v255);
                    WdsSetupLogMessageW(
                      v148,
                      819200,
                      L"D",
                      0,
                      3003,
                      L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                      L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
                      v147,
                      v146,
                      0,
                      0);
                    v256 = 1;
                    v287 = v296;
                    throw (`CSetupPlatformApplyRollbackCheckpoint::UndoTransformers(UnBCL::String *,UnBCL::String *,UnBCL::String *)'::`63'::CXXXXXHandledException **)&v287;
                  }
                  v102 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v282);
                  v103 = UnBCL::String::get_CString(v102);
                  UnBCL::Version::Version((UnBCL::Version *)v300, v103);
                  v104 = GetLastError();
                  v105 = CurrentIP();
                  v106 = ConstructPartialMsgW(0x4000000u, "Calling Transformer Initialize with parameters:");
                  WdsSetupLogMessageW(
                    v106,
                    819200,
                    L"D",
                    0,
                    3008,
                    L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                    L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
                    v105,
                    v104,
                    0,
                    0);
                  v107 = GetLastError();
                  QueryInterface = (UnBCL::String *)CurrentIP();
                  LODWORD(v255) = UnBCL::Version::get_Build((UnBCL::Version *)v300);
                  LODWORD(v105) = UnBCL::Version::get_Minor((UnBCL::Version *)v300);
                  Major = UnBCL::Version::get_Major((UnBCL::Version *)v300);
                  v109 = ConstructPartialMsgW(
                           0x4000000u,
                           "    Source OS version: %d.%d.%d.%d",
                           Major,
                           v105,
                           (_DWORD)v255,
                           0);
                  WdsSetupLogMessageW(
                    v109,
                    819200,
                    L"D",
                    0,
                    3009,
                    L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                    L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
                    QueryInterface,
                    v107,
                    0,
                    0);
                  LODWORD(v105) = GetLastError();
                  QueryInterface = (UnBCL::String *)CurrentIP();
                  v110 = v303;
                  v111 = (const char *)UnBCL::String::get_CString(v303);
                  v112 = ConstructPartialMsgW(0x4000000u, "    Windows directory: %s", v111);
                  WdsSetupLogMessageW(
                    v112,
                    819200,
                    L"D",
                    0,
                    3010,
                    L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                    L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
                    QueryInterface,
                    v105,
                    0,
                    0);
                  LODWORD(v105) = GetLastError();
                  QueryInterface = (UnBCL::String *)CurrentIP();
                  v113 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v272);
                  v114 = (const char *)UnBCL::String::get_CString(v113);
                  v115 = ConstructPartialMsgW(0x4000000u, "    CBS folder: %s", v114);
                  WdsSetupLogMessageW(
                    v115,
                    819200,
                    L"D",
                    0,
                    3011,
                    L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                    L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
                    QueryInterface,
                    v105,
                    0,
                    0);
                  v255 = 0;
                  WORD1(v255) = UnBCL::Version::get_Build((UnBCL::Version *)v300);
                  WORD2(v255) = UnBCL::Version::get_Minor((UnBCL::Version *)v300);
                  HIWORD(v255) = UnBCL::Version::get_Major((UnBCL::Version *)v300);
                  QueryInterface = *(UnBCL::String **)v258;
                  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v272) )
                  {
                    v116 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v272);
                    v117 = UnBCL::String::get_CString(v116);
                  }
                  else
                  {
                    v117 = 0;
                  }
                  v118 = UnBCL::String::get_CString(v110);
                  LODWORD(v262) = (*((__int64 (__fastcall **)(UnBCL::String *, __int64, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, _QWORD))QueryInterface
                                   + 3))(
                                    v258,
                                    78,
                                    v255,
                                    v118,
                                    v117,
                                    0);
                  if ( (int)v262 < 0 )
                  {
                    v149 = GetLastError();
                    v150 = CurrentIP();
                    v151 = ConstructPartialMsgW(
                             0x2000000u,
                             "Failure while calling Transformer Initialize. Error: 0x%08X",
                             (_DWORD)v262);
                    WdsSetupLogMessageW(
                      v151,
                      819200,
                      L"D",
                      0,
                      3033,
                      L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                      L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
                      v150,
                      v149,
                      0,
                      0);
                    LODWORD(v301) = (_DWORD)v262;
                    v256 = 1;
                    v290 = v296;
                    throw (`CSetupPlatformApplyRollbackCheckpoint::UndoTransformers(UnBCL::String *,UnBCL::String *,UnBCL::String *)'::`63'::CXXXXXHandledException **)&v290;
                  }
                  for ( k = 0; ; ++k )
                  {
                    LODWORD(v255) = k;
                    v120 = RAII::CAutoCleanupBase<void *>::operator->(&v278);
                    v121 = (int (__fastcall ***)(_QWORD))(v120 + 8 + *(int *)(*(_QWORD *)(v120 + 8) + 12LL));
                    if ( k >= (**v121)(v121) )
                      break;
                    v122 = v120 + *(int *)(*(_QWORD *)(v120 + 8) + 16LL) + 8LL;
                    v123 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v122 + 24LL))(
                                        v122,
                                        (unsigned int)k);
                    LODWORD(v262) = GetLastError();
                    v266 = (const char *)CurrentIP();
                    v124 = (UnBCL::String *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
                    QueryInterface = (UnBCL::String *)UnBCL::String::get_CString(v124);
                    v125 = (UnBCL::String *)(**(__int64 (__fastcall ***)(__int64))v123)(v123);
                    v126 = (const char *)UnBCL::String::get_CString(v125);
                    v127 = ConstructPartialMsgW(
                             0x4000000u,
                             "Calling transformer Uninstall for %s, manifest %s",
                             v126,
                             (const char *)QueryInterface);
                    WdsSetupLogMessageW(
                      v127,
                      819200,
                      L"D",
                      0,
                      3044,
                      L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                      L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
                      v266,
                      (_DWORD)v262,
                      0,
                      0);
                    QueryInterface = *(UnBCL::String **)(*(_QWORD *)v258 + 40LL);
                    v128 = (UnBCL::String *)(**(__int64 (__fastcall ***)(__int64))v123)(v123);
                    v266 = (const char *)UnBCL::String::get_CString(v128);
                    v129 = (UnBCL::String *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
                    v130 = UnBCL::String::get_CString(v129);
                    LODWORD(v262) = ((__int64 (__fastcall *)(UnBCL::String *, const unsigned __int16 *, const char *))QueryInterface)(
                                      v258,
                                      v130,
                                      v266);
                    if ( (int)v262 < 0 )
                    {
                      v131 = GetLastError();
                      v132 = CurrentIP();
                      v133 = ConstructPartialMsgW(
                               0x2000000u,
                               "Call to Transformer Uninstall failed. Error: 0x%08X",
                               (_DWORD)v262);
                      WdsSetupLogMessageW(
                        v133,
                        819200,
                        L"D",
                        0,
                        3051,
                        L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                        L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
                        v132,
                        v131,
                        0,
                        0);
                      LODWORD(v301) = (_DWORD)v262;
                      k = (int)v255;
                    }
                  }
                  v152 = RAII::CAutoCleanupBase<void *>::operator->(&v276);
                  v153 = *(int *)(*(_QWORD *)(v152 + 8) + 16LL) + v152 + 8;
                  v154 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v153 + 24LL))(v153, v261);
                  QueryInterface = 0;
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v263);
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v275);
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v273);
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v274);
                  v262 = 0;
                  v155 = (UnBCL::String *)(**(__int64 (__fastcall ***)(__int64))v154)(v154);
                  v156 = UnBCL::String::get_CString(v155);
                  if ( UnBCL::String::Compare(v156, L"SYSTEM", 1) )
                  {
                    QueryInterface = (UnBCL::String *)(**(__int64 (__fastcall ***)(__int64))v154)(v154);
                    v157 = (UnBCL::String *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v154 + 16LL))(v154);
                    v262 = v157;
                    v158 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v298, L"NTUSER.DAT");
                    v159 = UnBCL::Path::Combine(v157, v158);
                    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v268, v159);
                    UnBCL::String::~String((UnBCL::String *)v298);
                    v160 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
                    v259 = (__int64)v160;
                    if ( v160 )
                    {
                      v161 = (UnBCL::String *)(**(__int64 (__fastcall ***)(__int64))v154)(v154);
                      v162 = UnBCL::String::get_CString(v161);
                      UnBCL::String::String(v160, v162);
                      *(_QWORD *)v160 = &UnBCL::String::`local vftable';
                    }
                    else
                    {
                      v160 = 0;
                    }
                    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v293, v160);
                    UnBCL::SmartPtr<UnBCL::String>::operator=(v275, v293);
                    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v293);
                    v163 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v268);
                    v164 = UnBCL::String::get_CString(v163);
                    v165 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v275);
                    v166 = UnBCL::String::get_CString(v165);
                    KeyW = RegLoadKeyW(HKEY_USERS, v166, v164);
                    if ( KeyW )
                    {
                      LODWORD(v255) = GetLastError();
                      v259 = CurrentIP();
                      v171 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v275);
                      v266 = (const char *)UnBCL::String::get_CString(v171);
                      v172 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v268);
                      v173 = (const char *)UnBCL::String::get_CString(v172);
                      v174 = ConstructPartialMsgW(
                               0x2000000u,
                               "Cannot map user hive %s in HKEY_USERS\\%s. Error: 0x%08X",
                               v173,
                               v266,
                               KeyW);
                      WdsSetupLogMessageW(
                        v174,
                        819200,
                        L"D",
                        0,
                        3089,
                        L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                        L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
                        v259,
                        (_DWORD)v255,
                        0,
                        0);
                    }
                    else
                    {
                      v168 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v275);
                      v169 = UnBCL::String::get_CString(v168);
                      v170 = UnBCL::String::Format(L"HKEY_USERS\\%s", v169);
                      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v294, v170);
                      UnBCL::SmartPtr<UnBCL::String>::operator=(v263, v294);
                      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v294);
                    }
                    v175 = (const struct UnBCL::String *)UnBCL::String::String(
                                                           (UnBCL::String *)v299,
                                                           L"AppData\\Local\\Microsoft\\Windows\\UsrClass.dat");
                    v176 = UnBCL::Path::Combine(v262, v175);
                    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v269, v176);
                    UnBCL::String::~String((UnBCL::String *)v299);
                    v177 = (UnBCL::String *)(**(__int64 (__fastcall ***)(__int64))v154)(v154);
                    v178 = UnBCL::String::get_CString(v177);
                    v179 = UnBCL::String::Format(L"%s_Classes", v178);
                    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v291, v179);
                    UnBCL::SmartPtr<UnBCL::String>::operator=(v274, v291);
                    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v291);
                    v180 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v269);
                    v181 = UnBCL::String::get_CString(v180);
                    v182 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v274);
                    v183 = UnBCL::String::get_CString(v182);
                    v184 = RegLoadKeyW(HKEY_USERS, v183, v181);
                    if ( v184 )
                    {
                      LODWORD(v255) = GetLastError();
                      v259 = CurrentIP();
                      v188 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v274);
                      v189 = (const char *)UnBCL::String::get_CString(v188);
                      v190 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v269);
                      v191 = (const char *)UnBCL::String::get_CString(v190);
                      v192 = ConstructPartialMsgW(
                               0x2000000u,
                               "Cannot map classes hive %s in HKEY_USERS\\%s. Error: 0x%08X",
                               v191,
                               v189,
                               v184);
                      WdsSetupLogMessageW(
                        v192,
                        819200,
                        L"D",
                        0,
                        3107,
                        L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                        L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
                        v259,
                        (_DWORD)v255,
                        0,
                        0);
                    }
                    else
                    {
                      v185 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v274);
                      v186 = UnBCL::String::get_CString(v185);
                      v187 = UnBCL::String::Format(L"HKEY_USERS\\%s", v186);
                      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v292, v187);
                      UnBCL::SmartPtr<UnBCL::String>::operator=(v273, v292);
                      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v292);
                    }
                    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v269);
                    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v268);
                  }
                  v193 = GetLastError();
                  v194 = CurrentIP();
                  v195 = ConstructPartialMsgW(0x4000000u, "Calling Transformer Commit with parameters:");
                  WdsSetupLogMessageW(
                    v195,
                    819200,
                    L"D",
                    0,
                    3110,
                    L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                    L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
                    v194,
                    v193,
                    0,
                    0);
                  v196 = GetLastError();
                  v259 = CurrentIP();
                  if ( QueryInterface )
                  {
                    v197 = UnBCL::String::get_CString(QueryInterface);
                    v198 = L"<NULL>";
                  }
                  else
                  {
                    v198 = L"<NULL>";
                    v197 = L"<NULL>";
                  }
                  v199 = ConstructPartialMsgW(0x4000000u, "    User SID: %s", (const char *)v197);
                  WdsSetupLogMessageW(
                    v199,
                    819200,
                    L"D",
                    0,
                    3111,
                    L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                    L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
                    v259,
                    v196,
                    0,
                    0);
                  v200 = GetLastError();
                  v259 = CurrentIP();
                  if ( (unsigned __int8)UnBCL::operator!=(v263, v201) )
                  {
                    v202 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v263);
                    v203 = UnBCL::String::get_CString(v202);
                  }
                  else
                  {
                    v203 = L"<NULL>";
                  }
                  v204 = ConstructPartialMsgW(0x4000000u, "    User hive: %s", (const char *)v203);
                  WdsSetupLogMessageW(
                    v204,
                    819200,
                    L"D",
                    0,
                    3112,
                    L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                    L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
                    v259,
                    v200,
                    0,
                    0);
                  v205 = GetLastError();
                  v259 = CurrentIP();
                  if ( (unsigned __int8)UnBCL::operator!=(v273, v206) )
                  {
                    v207 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v273);
                    v208 = UnBCL::String::get_CString(v207);
                  }
                  else
                  {
                    v208 = L"<NULL>";
                  }
                  v209 = ConstructPartialMsgW(0x4000000u, "    Classes hive: %s", (const char *)v208);
                  WdsSetupLogMessageW(
                    v209,
                    819200,
                    L"D",
                    0,
                    3113,
                    L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                    L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
                    v259,
                    v205,
                    0,
                    0);
                  v210 = GetLastError();
                  v259 = CurrentIP();
                  if ( v262 )
                    v211 = UnBCL::String::get_CString(v262);
                  else
                    v211 = L"<NULL>";
                  v212 = ConstructPartialMsgW(0x4000000u, "    User Profile: %s", (const char *)v211);
                  WdsSetupLogMessageW(
                    v212,
                    819200,
                    L"D",
                    0,
                    3114,
                    L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                    L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
                    v259,
                    v210,
                    0,
                    0);
                  v213 = GetLastError();
                  v259 = CurrentIP();
                  if ( (unsigned __int8)UnBCL::operator!=(v272, v214) )
                  {
                    v215 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v272);
                    v198 = UnBCL::String::get_CString(v215);
                  }
                  v216 = ConstructPartialMsgW(0x4000000u, "    CBS folder: %s", (const char *)v198);
                  WdsSetupLogMessageW(
                    v216,
                    819200,
                    L"D",
                    0,
                    3115,
                    L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                    L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
                    v259,
                    v213,
                    0,
                    0);
                  v259 = *(_QWORD *)v258;
                  if ( v262 )
                    v255 = UnBCL::String::get_CString(v262);
                  else
                    v255 = 0;
                  if ( (unsigned __int8)UnBCL::operator!=(v273, v217) )
                  {
                    v219 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v273);
                    v220 = UnBCL::String::get_CString(v219);
                  }
                  else
                  {
                    v220 = 0;
                  }
                  if ( (unsigned __int8)UnBCL::operator!=(v263, v218) )
                  {
                    v221 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v263);
                    v222 = UnBCL::String::get_CString(v221);
                  }
                  else
                  {
                    v222 = 0;
                  }
                  if ( QueryInterface )
                    v223 = UnBCL::String::get_CString(QueryInterface);
                  else
                    v223 = 0;
                  v224 = (*(__int64 (__fastcall **)(UnBCL::String *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *))(v259 + 48))(
                           v258,
                           v223,
                           v222,
                           v220,
                           v255);
                  LODWORD(v255) = v224;
                  if ( (unsigned __int8)UnBCL::operator!=(v263, v225) )
                  {
                    v227 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v275);
                    v228 = UnBCL::String::get_CString(v227);
                    if ( RegUnLoadKeyW(HKEY_USERS, v228) )
                    {
                      v229 = GetLastError();
                      v259 = CurrentIP();
                      v230 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v263);
                      v231 = (const char *)UnBCL::String::get_CString(v230);
                      v232 = ConstructPartialMsgW(
                               0x2000000u,
                               "Failed to unload %s, this is most likely a registry leak from the transformer layer",
                               v231);
                      WdsSetupLogMessageW(
                        v232,
                        819200,
                        L"D",
                        0,
                        3132,
                        L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                        L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
                        v259,
                        v229,
                        0,
                        0);
                    }
                  }
                  if ( (unsigned __int8)UnBCL::operator!=(v273, v226) )
                  {
                    v233 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v274);
                    v234 = UnBCL::String::get_CString(v233);
                    if ( RegUnLoadKeyW(HKEY_USERS, v234) )
                    {
                      v235 = GetLastError();
                      v259 = CurrentIP();
                      v236 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v273);
                      v237 = (const char *)UnBCL::String::get_CString(v236);
                      v238 = ConstructPartialMsgW(
                               0x2000000u,
                               "Failed to unload %s, this is most likely a registry leak from the transformer layer",
                               v237);
                      WdsSetupLogMessageW(
                        v238,
                        819200,
                        L"D",
                        0,
                        3145,
                        L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                        L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
                        v259,
                        v235,
                        0,
                        0);
                    }
                  }
                  v239 = GetLastError();
                  v240 = CurrentIP();
                  v241 = v224 < 0;
                  v242 = v240;
                  if ( v241 )
                  {
                    v243 = ConstructPartialMsgW(
                             0x2000000u,
                             "Failure while calling Transformer Commit. Error: 0x%08X",
                             (_DWORD)v255);
                    WdsSetupLogMessageW(
                      v243,
                      819200,
                      L"D",
                      0,
                      3155,
                      L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                      L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
                      v242,
                      v239,
                      0,
                      0);
                    LODWORD(v301) = (_DWORD)v255;
                  }
                  else
                  {
                    v244 = ConstructPartialMsgW(0x4000000u, "Transformer Commit succeeded");
                    WdsSetupLogMessageW(
                      v244,
                      819200,
                      L"D",
                      0,
                      3163,
                      L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
                      L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
                      v242,
                      v239,
                      0,
                      0);
                  }
                  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v274);
                  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v273);
                  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v275);
                  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v263);
                  UnBCL::Version::`vbase destructor'((UnBCL::Version *)v300);
                }
                catch ( UnBCL::IEAAJPEAVString:: )
                {
                  CSetupPlatformApplyRollbackCheckpoint::UndoTransformers_::_1_::catch_46();
                  __eh34_caught_type(
                    3,
                    UnBCL::IEAAJPEAVString::`CSetupPlatformApplyRollbackCheckpoint::UndoTransformers'::`64'::CXXXXXTemp * `RTTI Type Descriptor');
                }
                v256 = 1;
                v289 = v296;
                throw (`CSetupPlatformApplyRollbackCheckpoint::UndoTransformers(UnBCL::String *,UnBCL::String *,UnBCL::String *)'::`63'::CXXXXXHandledException **)&v289;
              }
              catch ( UnBCL::Exception * )
              {
                v251 = v252;
                v245 = v251;
                v246 = *((_QWORD *)v251 + 15);
                if ( v246 )
                {
                  (*(void (**)(void))(*(_QWORD *)v246 + 16LL))();
                  *((_QWORD *)v245 + 15) = 0;
                }
                if ( !*((_DWORD *)v245 + 26) )
                  throw;
                UnBCL::Exception::~Exception((UnBCL::Exception *)v296);
                v98 = v261 - 1;
                continue;
              }
            }
            break;
          }
        }
        catch ( UnBCL::IEAAJPEAVString:: )
        {
          CSetupPlatformApplyRollbackCheckpoint::UndoTransformers_::_1_::catch_48();
          __eh34_caught_type(
            1,
            UnBCL::IEAAJPEAVString::`CSetupPlatformApplyRollbackCheckpoint::UndoTransformers'::`30'::CXXXXXTemp * `RTTI Type Descriptor');
        }
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v271);
        v260 = 1;
        v288 = v295;
        throw (`CSetupPlatformApplyRollbackCheckpoint::UndoTransformers(UnBCL::String *,UnBCL::String *,UnBCL::String *)'::`29'::CXXXXXHandledException **)&v288;
      }
      catch ( UnBCL::Exception * )
      {
        v250 = v252;
        v247 = v250;
        v248 = *((_QWORD *)v250 + 24);
        if ( v248 )
        {
          (*(void (**)(void))(*(_QWORD *)v248 + 16LL))();
          *((_QWORD *)v247 + 24) = 0;
        }
        v249 = *((_QWORD *)v247 + 22);
        if ( v249 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v249 + 16LL))(v249);
          *((_QWORD *)v247 + 22) = 0;
        }
        CbsOfflineFinalize();
        if ( *((_DWORD *)v247 + 42) )
          CoUninitialize();
        if ( !*((_DWORD *)v247 + 34) )
          throw;
        UnBCL::Exception::~Exception((UnBCL::Exception *)v295);
        v276 = &UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>>::`vftable';
        UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v276);
        UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::~SmartPtr<UnBCL::Array<UnBCL::String *>>(v280);
        v278 = &UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>>::`vftable';
        UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v278);
        UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::~SmartPtr<UnBCL::Array<UnBCL::String *>>(v281);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v282);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v270);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v272);
        return (unsigned int)v301;
      }
    }
    v20 = GetLastError();
    v21 = CurrentIP();
    v22 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v270);
    v23 = (const char *)UnBCL::String::get_CString(v22);
    v24 = ConstructPartialMsgW(0x3000000u, "OS Version info is missing from the transformers INI file %s", v23);
    WdsSetupLogMessageW(
      v24,
      819200,
      L"D",
      0,
      2838,
      L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
      L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
      v21,
      v20,
      0,
      0);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v282);
  }
  else
  {
    v11 = GetLastError();
    v12 = CurrentIP();
    v13 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v270);
    v14 = (const char *)UnBCL::String::get_CString(v13);
    v15 = ConstructPartialMsgW(0x3000000u, "Transformers INI file %s is missing.", v14);
    WdsSetupLogMessageW(
      v15,
      819200,
      L"D",
      0,
      2830,
      L"base\\ntsetup\\setupplatform\\lib\\rollback\\rollback.cpp",
      L"CSetupPlatformApplyRollbackCheckpoint::UndoTransformers",
      v12,
      v11,
      0,
      0);
  }
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v270);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v272);
  return 2147942402LL;
}

```

## disassembly

```asm
0x1802b31a0  mov     rax, rsp
0x1802b31a3  mov     [rax+18h], r8
0x1802b31a7  mov     [rax+10h], rdx
0x1802b31ab  mov     [rax+8], rcx
0x1802b31af  push    rbx
0x1802b31b0  push    rsi
0x1802b31b1  push    rdi
0x1802b31b2  push    r12
0x1802b31b4  push    r13
0x1802b31b6  push    r14
0x1802b31b8  push    r15
0x1802b31ba  sub     rsp, 350h
0x1802b31c1  mov     qword ptr [rax-128h], 0FFFFFFFFFFFFFFFEh
0x1802b31cc  mov     rbx, r9
0x1802b31cf  mov     rdi, r8
0x1802b31d2  lea     rdx, aCbs; "CBS"
0x1802b31d9  lea     rcx, [rax-198h]
0x1802b31e0  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1802b31e6  nop
0x1802b31e7  mov     rdx, rax
0x1802b31ea  mov     rcx, rbx
0x1802b31ed  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1802b31f3  mov     rdx, rax
0x1802b31f6  lea     rcx, [rsp+388h+var_280]
0x1802b31fe  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802b3204  nop
0x1802b3205  lea     rcx, [rsp+388h+var_198]
0x1802b320d  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1802b3213  lea     rdx, aTransformersro; "TransformersRollback.ini"
0x1802b321a  lea     rcx, [rsp+388h+var_1B0]
0x1802b3222  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1802b3228  nop
0x1802b3229  mov     rdx, rax
0x1802b322c  mov     rcx, rbx
0x1802b322f  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1802b3235  mov     rdx, rax
0x1802b3238  lea     rcx, [rsp+388h+var_2A0]
0x1802b3240  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802b3246  nop
0x1802b3247  lea     rcx, [rsp+388h+var_1B0]
0x1802b324f  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1802b3255  lea     rcx, [rsp+388h+var_2A0]
0x1802b325d  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1802b3263  mov     rcx, rax
0x1802b3266  call    cs:__imp_?Exists@File@UnBCL@@SAHPEBVString@2@@Z; UnBCL::File::Exists(UnBCL::String const *)
0x1802b326c  xor     esi, esi
0x1802b326e  test    eax, eax
0x1802b3270  jnz     loc_1802B3324
0x1802b3276  call    cs:__imp_GetLastError
0x1802b327c  mov     edi, eax
0x1802b327e  call    cs:__imp_CurrentIP
0x1802b3284  mov     rbx, rax
0x1802b3287  lea     rcx, [rsp+388h+var_2A0]
0x1802b328f  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802b3295  mov     rcx, rax
0x1802b3298  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802b329e  mov     r8, rax
0x1802b32a1  lea     rdx, aTransformersIn; "Transformers INI file %s is missing."
0x1802b32a8  mov     ecx, 3000000h; unsigned int
0x1802b32ad  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1802b32b2  mov     [rsp+388h+var_338], esi
0x1802b32b6  mov     [rsp+388h+var_340], rsi
0x1802b32bb  mov     dword ptr [rsp+388h+pReserved3], edi
0x1802b32bf  mov     qword ptr [rsp+388h+dwCapabilities], rbx
0x1802b32c4  lea     r12, aCsetupplatform_121; "CSetupPlatformApplyRollbackCheckpoint::"...
0x1802b32cb  mov     [rsp+388h+pAuthList], r12
0x1802b32d0  lea     r13, aBaseNtsetupSet_64; "base\\ntsetup\\setupplatform\\lib\\roll"...
0x1802b32d7  mov     qword ptr [rsp+388h+dwImpLevel], r13
0x1802b32dc  mov     [rsp+388h+dwAuthnLevel], 0B0Eh
0x1802b32e4  xor     r9d, r9d
0x1802b32e7  lea     r8, aD_0; "D"
0x1802b32ee  mov     edx, 0C8000h
0x1802b32f3  mov     rcx, rax
0x1802b32f6  call    cs:__imp_WdsSetupLogMessageW
0x1802b32fc  nop
0x1802b32fd  lea     rcx, [rsp+388h+var_2A0]
0x1802b3305  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802b330b  nop
0x1802b330c  lea     rcx, [rsp+388h+var_280]
0x1802b3314  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802b331a  mov     eax, 80070002h
0x1802b331f  jmp     loc_1802B4533
0x1802b3324  lea     rcx, [rsp+388h+var_2A0]
0x1802b332c  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802b3332  mov     rcx, rax
0x1802b3335  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802b333b  mov     r8, rax; lpFileName
0x1802b333e  lea     rdx, aVersion; "Version"
0x1802b3345  lea     rcx, aInfo; "Info"
0x1802b334c  call    ?SPReadConfigValue@@YAPEAVString@UnBCL@@PEBG00@Z; SPReadConfigValue(ushort const *,ushort const *,ushort const *)
0x1802b3351  mov     rdx, rax
0x1802b3354  lea     rcx, [rsp+388h+var_200]
0x1802b335c  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802b3362  nop
0x1802b3363  lea     rcx, [rsp+388h+var_200]
0x1802b336b  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1802b3371  test    rax, rax
0x1802b3374  jnz     loc_1802B3414
0x1802b337a  call    cs:__imp_GetLastError
0x1802b3380  mov     edi, eax
0x1802b3382  call    cs:__imp_CurrentIP
0x1802b3388  mov     rbx, rax
0x1802b338b  lea     rcx, [rsp+388h+var_2A0]
0x1802b3393  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802b3399  mov     rcx, rax
0x1802b339c  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802b33a2  mov     r8, rax
0x1802b33a5  lea     rdx, aOsVersionInfoI; "OS Version info is missing from the tra"...
0x1802b33ac  mov     ecx, 3000000h; unsigned int
0x1802b33b1  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1802b33b6  mov     [rsp+388h+var_338], esi
0x1802b33ba  mov     [rsp+388h+var_340], rsi
0x1802b33bf  mov     dword ptr [rsp+388h+pReserved3], edi
0x1802b33c3  mov     qword ptr [rsp+388h+dwCapabilities], rbx
0x1802b33c8  lea     r12, aCsetupplatform_121; "CSetupPlatformApplyRollbackCheckpoint::"...
0x1802b33cf  mov     [rsp+388h+pAuthList], r12
0x1802b33d4  lea     r13, aBaseNtsetupSet_64; "base\\ntsetup\\setupplatform\\lib\\roll"...
0x1802b33db  mov     qword ptr [rsp+388h+dwImpLevel], r13
0x1802b33e0  mov     [rsp+388h+dwAuthnLevel], 0B16h
0x1802b33e8  xor     r9d, r9d
0x1802b33eb  lea     r8, aD_0; "D"
0x1802b33f2  mov     edx, 0C8000h
0x1802b33f7  mov     rcx, rax
0x1802b33fa  call    cs:__imp_WdsSetupLogMessageW
0x1802b3400  nop
0x1802b3401  lea     rcx, [rsp+388h+var_200]
0x1802b3409  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802b340f  jmp     loc_1802B32FD
0x1802b3414  lea     rcx, [rsp+388h+var_2A0]
0x1802b341c  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802b3422  mov     rcx, rax
0x1802b3425  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802b342b  mov     rcx, rax; lpFileName
0x1802b342e  lea     rdx, aTransformers; "Transformers"
0x1802b3435  call    ?SPGetSectionLines@@YAPEAV?$Array@PEAVString@UnBCL@@@UnBCL@@PEBG0@Z; SPGetSectionLines(ushort const *,ushort const *)
0x1802b343a  mov     rdx, rax
0x1802b343d  lea     rcx, [rsp+388h+var_210]
0x1802b3445  call    cs:__imp_??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::SmartPtr<UnBCL::Array<UnBCL::String *>>(UnBCL::Array<UnBCL::String *> *)
0x1802b344b  nop
0x1802b344c  mov     ecx, 80h
0x1802b3451  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1802b3457  mov     [rsp+388h+arg_0], rax
0x1802b345f  test    rax, rax
0x1802b3462  jz      short loc_1802B346E
0x1802b3464  mov     rcx, rax
0x1802b3467  call    ??0?$ArrayList@PEAV?$DictionaryEntry@PEAVString@UnBCL@@PEAV12@@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>(void)
0x1802b346c  jmp     short loc_1802B3471
0x1802b346e  mov     rax, rsi
0x1802b3471  mov     rdx, rax
0x1802b3474  lea     rcx, [rsp+388h+var_230]
0x1802b347c  call    ??0?$SmartPtr@V?$ArrayList@PEAV?$DictionaryEntry@PEAVString@UnBCL@@PEAV12@@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAV?$DictionaryEntry@PEAVString@UnBCL@@PEAV12@@UnBCL@@@1@@Z; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>>::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>>(UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *> *)
0x1802b3481  nop
0x1802b3482  mov     rcx, [rsp+388h+var_228]
0x1802b348a  mov     rax, [rcx]
0x1802b348d  mov     edx, 1
0x1802b3492  mov     rax, [rax+28h]
0x1802b3496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b349b  lea     rcx, [rsp+388h+var_210]
0x1802b34a3  call    cs:__imp_?get_P@?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@2@XZ; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::get_P(void)
0x1802b34a9  lea     r12, aCsetupplatform_121; "CSetupPlatformApplyRollbackCheckpoint::"...
0x1802b34b0  lea     r13, aBaseNtsetupSet_64; "base\\ntsetup\\setupplatform\\lib\\roll"...
0x1802b34b7  lea     r14, aD_0; "D"
0x1802b34be  mov     r15d, 0C8000h
0x1802b34c4  test    rax, rax
0x1802b34c7  jz      loc_1802B3797
0x1802b34cd  mov     ebx, esi
0x1802b34cf  mov     [rsp+388h+var_320], ebx
0x1802b34d3  lea     rcx, [rsp+388h+var_210]
0x1802b34db  call    cs:__imp_??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(void)
0x1802b34e1  mov     rcx, [rax+8]
0x1802b34e5  movsxd  rdx, dword ptr [rcx+0Ch]
0x1802b34e9  lea     rcx, [rax+8]
0x1802b34ed  add     rcx, rdx
0x1802b34f0  mov     rax, [rcx]
0x1802b34f3  mov     rax, [rax]
0x1802b34f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b34fb  cmp     ebx, eax
0x1802b34fd  jge     loc_1802B3797
0x1802b3503  lea     rcx, [rsp+388h+var_210]
0x1802b350b  call    cs:__imp_??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(void)
0x1802b3511  mov     rcx, [rax+8]
0x1802b3515  movsxd  rdx, dword ptr [rcx+10h]
0x1802b3519  lea     rcx, [rax+8]
0x1802b351d  add     rcx, rdx
0x1802b3520  mov     rax, [rcx]
0x1802b3523  mov     edx, ebx
0x1802b3525  mov     rax, [rax+18h]
0x1802b3529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b352e  mov     rax, [rax]
0x1802b3531  mov     [rsp+388h+var_310], rax
0x1802b3536  mov     edx, 3Dh ; '='
0x1802b353b  mov     rcx, rax
0x1802b353e  call    cs:__imp_?IndexOf@String@UnBCL@@QEBAHG@Z; UnBCL::String::IndexOf(ushort)
0x1802b3544  mov     [rsp+388h+var_2E0], eax
0x1802b354b  test    eax, eax
0x1802b354d  jle     loc_1802B3717
0x1802b3553  mov     r8d, eax
0x1802b3556  xor     edx, edx
0x1802b3558  mov     rcx, [rsp+388h+var_310]
0x1802b355d  call    cs:__imp_?Substring@String@UnBCL@@QEBAPEAV12@HH@Z; UnBCL::String::Substring(int,int)
0x1802b3563  mov     rdx, rax
0x1802b3566  lea     rcx, [rsp+388h+var_2B0]
0x1802b356e  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802b3574  nop
0x1802b3575  mov     r8d, [rsp+388h+var_2E0]
0x1802b357d  inc     r8d
0x1802b3580  xor     edx, edx
0x1802b3582  mov     rcx, [rsp+388h+var_310]
0x1802b3587  call    cs:__imp_?Remove@String@UnBCL@@QEBAPEAV12@HH@Z; UnBCL::String::Remove(int,int)
0x1802b358d  mov     rdx, rax
0x1802b3590  lea     rcx, [rsp+388h+var_2F0]
0x1802b3598  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802b359e  nop
0x1802b359f  lea     rcx, [rsp+388h+var_2F0]
0x1802b35a7  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802b35ad  xor     edx, edx
0x1802b35af  lea     r8d, [rdx+1]
0x1802b35b3  mov     rcx, rax
0x1802b35b6  call    cs:__imp_?Remove@String@UnBCL@@QEBAPEAV12@HH@Z; UnBCL::String::Remove(int,int)
0x1802b35bc  mov     rdx, rax
0x1802b35bf  lea     rcx, [rsp+388h+var_290]
0x1802b35c7  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802b35cd  nop
0x1802b35ce  lea     rdx, [rsp+388h+var_290]
0x1802b35d6  lea     rcx, [rsp+388h+var_2F0]
0x1802b35de  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1802b35e4  nop
0x1802b35e5  lea     rcx, [rsp+388h+var_290]
0x1802b35ed  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802b35f3  mov     dword ptr [rsp+388h+arg_0], 3Fh ; '?'
0x1802b35fe  mov     rcx, rdi
0x1802b3601  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802b3607  movzx   ecx, word ptr [rax]
0x1802b360a  mov     word ptr [rsp+388h+arg_0], cx
0x1802b3612  lea     rcx, [rsp+388h+var_2F0]
0x1802b361a  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802b3620  lea     r8, [rsp+388h+arg_0]
0x1802b3628  xor     edx, edx
0x1802b362a  mov     rcx, rax
0x1802b362d  call    cs:__imp_?Insert@String@UnBCL@@QEBAPEAV12@HPEBG@Z; UnBCL::String::Insert(int,ushort const *)
0x1802b3633  mov     rdx, rax
0x1802b3636  lea     rcx, [rsp+388h+var_2C0]
0x1802b363e  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802b3644  nop
0x1802b3645  lea     rdx, [rsp+388h+var_2C0]
0x1802b364d  lea     rcx, [rsp+388h+var_2F0]
0x1802b3655  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1802b365b  nop
0x1802b365c  lea     rcx, [rsp+388h+var_2C0]
0x1802b3664  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802b366a  mov     rdx, [rsp+388h+var_228]
0x1802b3672  mov     rax, [rdx+8]
0x1802b3676  movsxd  rcx, dword ptr [rax+10h]
0x1802b367a  lea     rax, [rdx+8]
0x1802b367e  add     rax, rcx
0x1802b3681  mov     [rsp+388h+var_310], rax
0x1802b3686  mov     rax, [rax]
0x1802b3689  mov     rax, [rax+28h]
0x1802b368d  mov     qword ptr [rsp+388h+var_2E0], rax
0x1802b3695  mov     ecx, 40h ; '@'
0x1802b369a  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1802b36a0  mov     [rsp+388h+var_318], rax
0x1802b36a5  test    rax, rax
0x1802b36a8  jz      short loc_1802B36DF
0x1802b36aa  lea     rcx, [rsp+388h+var_2F0]
0x1802b36b2  call    cs:__imp_?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::Steal(void)
0x1802b36b8  mov     rbx, rax
0x1802b36bb  lea     rcx, [rsp+388h+var_2B0]
0x1802b36c3  call    cs:__imp_?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::Steal(void)
0x1802b36c9  mov     r8, rbx
0x1802b36cc  mov     rdx, rax
0x1802b36cf  mov     rcx, [rsp+388h+var_318]
0x1802b36d4  call    ??0?$DictionaryEntry@PEAVString@UnBCL@@PEAV12@@UnBCL@@QEAA@PEAVString@1@0HH@Z; UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>::DictionaryEntry<UnBCL::String *,UnBCL::String *>(UnBCL::String *,UnBCL::String *,int,int)
0x1802b36d9  mov     ebx, [rsp+388h+var_320]
0x1802b36dd  jmp     short loc_1802B36E2
0x1802b36df  mov     rax, rsi
0x1802b36e2  mov     rdx, rax
0x1802b36e5  mov     rcx, [rsp+388h+var_310]
0x1802b36ea  mov     rax, qword ptr [rsp+388h+var_2E0]
0x1802b36f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b36f7  nop
0x1802b36f8  lea     rcx, [rsp+388h+var_2F0]
0x1802b3700  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802b3706  nop
0x1802b3707  lea     rcx, [rsp+388h+var_2B0]
0x1802b370f  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802b3715  jmp     short loc_1802B3790
0x1802b3717  call    cs:__imp_GetLastError
0x1802b371d  mov     edi, eax
0x1802b371f  call    cs:__imp_CurrentIP
0x1802b3725  mov     rbx, rax
0x1802b3728  mov     rcx, [rsp+388h+var_310]
0x1802b372d  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802b3733  mov     r9, rax
0x1802b3736  lea     r8, aTransformers; "Transformers"
0x1802b373d  lea     rdx, aCorruptLineInT; "Corrupt line in the %s section. Line: %"...
0x1802b3744  mov     ecx, 3000000h; unsigned int
0x1802b3749  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1802b374e  mov     [rsp+388h+var_338], esi
0x1802b3752  mov     [rsp+388h+var_340], rsi
  ... truncated ...
```
