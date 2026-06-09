# CAddProvisioningPackage::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)

- ea: `0x180227970`
- end: `0x180228e22`
- name: `?DoExecute@CAddProvisioningPackage@@UEAAJPEAUIExecutionContext@@PEAXPEAUIInternalOperationsProgress@@@Z`
- size: `5298`
- prototype: `void __noreturn(CAddProvisioningPackage *__hidden this, struct IExecutionContext *, void *, struct IInternalOperationsProgress *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18001413d`
- `0x180057dec`
- `0x180227970`
- `0x180229c3c`
- `0x1802c6944`
- `0x1802d010c`
- `0x1802d8f5c`
- `0x1802db0f8`
- `0x1802fb1a8`
- `0x18035734c`
- `0x180509010`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x180228411`
- `ADVAPI32!RegGetValueW` at `0x180228411`
- `ADVAPI32!RegSetValueExW` at `0x18022865a`
- `ADVAPI32!RegSetValueExW` at `0x18022865a`
- `ADVAPI32!RegCreateKeyExW` at `0x18022835f`
- `ADVAPI32!RegCreateKeyExW` at `0x18022835f`
- `KERNEL32!GetLastError` at `0x180227ad5`
- `KERNEL32!GetLastError` at `0x180227b8c`
- `KERNEL32!GetLastError` at `0x180227df7`
- `KERNEL32!GetLastError` at `0x180227e65`
- `KERNEL32!GetLastError` at `0x180227f3e`
- `KERNEL32!GetLastError` at `0x180228038`
- `KERNEL32!GetLastError` at `0x18022821b`
- `KERNEL32!GetLastError` at `0x1802282b6`
- `KERNEL32!GetLastError` at `0x1802286bc`
- `KERNEL32!GetLastError` at `0x180228759`
- `KERNEL32!GetLastError` at `0x1802287f6`
- `KERNEL32!GetLastError` at `0x180228896`
- `KERNEL32!GetLastError` at `0x180228930`
- `KERNEL32!GetLastError` at `0x180228946`
- `KERNEL32!GetLastError` at `0x180228966`
- `KERNEL32!GetLastError` at `0x1802289ff`
- `KERNEL32!GetLastError` at `0x180228a9e`
- `KERNEL32!GetLastError` at `0x180228b54`
- `KERNEL32!GetLastError` at `0x180228c0a`
- `KERNEL32!GetLastError` at `0x180228d52`
- `KERNEL32!GetLastError` at `0x180227ad5`
- `KERNEL32!GetLastError` at `0x180227b8c`
- `KERNEL32!GetLastError` at `0x180227df7`
- `KERNEL32!GetLastError` at `0x180227e65`
- `KERNEL32!GetLastError` at `0x180227f3e`
- `KERNEL32!GetLastError` at `0x180228038`
- `KERNEL32!GetLastError` at `0x18022821b`
- `KERNEL32!GetLastError` at `0x1802282b6`
- `KERNEL32!GetLastError` at `0x1802286bc`
- `KERNEL32!GetLastError` at `0x180228759`
- `KERNEL32!GetLastError` at `0x1802287f6`
- `KERNEL32!GetLastError` at `0x180228896`
- `KERNEL32!GetLastError` at `0x180228930`
- `KERNEL32!GetLastError` at `0x180228946`
- `KERNEL32!GetLastError` at `0x180228966`
- `KERNEL32!GetLastError` at `0x1802289ff`
- `KERNEL32!GetLastError` at `0x180228a9e`
- `KERNEL32!GetLastError` at `0x180228b54`
- `KERNEL32!GetLastError` at `0x180228c0a`
- `KERNEL32!GetLastError` at `0x180228d52`
- `ole32!CoInitializeSecurity` at `0x180227f2e`
- `ole32!CoInitializeSecurity` at `0x180227f2e`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x1802284db`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x180228619`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x1802284db`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x180228619`
- `unbcl!?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x180227d21`
- `unbcl!?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x180227d21`
- `unbcl!?Remove@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x180227c7e`
- `unbcl!?Remove@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x180227c7e`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18022839b`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18022839b`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1802284b4`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1802284b4`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1802279e5`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1802279e5`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x180227c07`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x180227c07`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180227d7c`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180228199`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802285ab`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180227d7c`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180228199`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802285ab`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x180228695`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x180228695`
- `unbcl!?IndexOf@String@UnBCL@@QEBAHPEBG@Z` at `0x180228524`
- `unbcl!?IndexOf@String@UnBCL@@QEBAHPEBG@Z` at `0x180228524`
- `unbcl!?Substring@String@UnBCL@@QEBAPEAV12@H@Z` at `0x1802284e6`
- `unbcl!?Substring@String@UnBCL@@QEBAPEAV12@H@Z` at `0x180228547`
- `unbcl!?Substring@String@UnBCL@@QEBAPEAV12@H@Z` at `0x1802284e6`
- `unbcl!?Substring@String@UnBCL@@QEBAPEAV12@H@Z` at `0x180228547`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z` at `0x180227cd6`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z` at `0x180227cd6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180227a19`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180227b66`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180227b77`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180227d18`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180227d41`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180227d70`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180227dcd`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180227dde`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180228018`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18022818d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180228457`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180228463`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180228586`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180227a19`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180227b66`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180227b77`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180227d18`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180227d41`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180227d70`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180227dcd`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180227dde`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180228018`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18022818d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180228457`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180228463`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180228586`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180227a02`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180228388`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180228481`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180227a02`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180228388`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180228481`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180227dc2`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802281b9`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802285ee`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180227dc2`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802281b9`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802285ee`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180227a89`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180227d5f`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180228181`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18022859e`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180227a89`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180227d5f`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180228181`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18022859e`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180227a5a`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180227a5a`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180227a4c`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180227ac0`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180227ca3`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180227cfb`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180227da4`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802283c3`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18022850b`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18022856c`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802285d0`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180227a4c`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180227ac0`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180227ca3`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180227cfb`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180227da4`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802283c3`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18022850b`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18022856c`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802285d0`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180227a74`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180227aee`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180227c13`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180227c31`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180227c50`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180227c6f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180227cbd`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180227e0d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180228051`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802280ce`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180228116`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802281c7`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802283e0`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180228490`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18022849c`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802284c6`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802284d2`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180228514`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18022853c`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802285f9`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180228610`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18022862e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180228ab7`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180228b6d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180228c23`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180228c3a`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180228d66`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180228d80`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180227a74`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180227aee`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180227c13`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180227c31`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180227c50`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180227c6f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180227cbd`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180227e0d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180228051`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802280ce`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180228116`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802281c7`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802283e0`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180228490`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18022849c`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802284c6`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802284d2`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180228514`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18022853c`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802285f9`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180228610`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18022862e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180228ab7`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180228b6d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180228c23`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180228c3a`

## string_xrefs

- `0x180228233`: `%hs: Cannot enable SE_BACKUP_NAME privilege`
- `0x1802282a6`: `SeRestorePrivilege`
- `0x18022820b`: `SeBackupPrivilege`
- `0x1802282ce`: `%hs: Cannot enable SE_RESTORE_NAME privilege`
- `0x180228063`: `Opening DISM session for %s`
- `0x180227b00`: `Installing provisioning package: %s`
- `0x1802286d1`: `CAddProvisioningPackage::DoExecute: Failed to initialize COM. hr = 0x%08X`
- `0x180227f52`: `CAddProvisioningPackage::DoExecute: Failed to initialize COM security. Was it initialized before us? hr = 0x%08X`
- `0x18022880a`: `CAddProvisioningPackage::DoExecute: Failed to open new OS DISM session. Error: 0x%08X`
- `0x180227b9d`: `Provisioning package is not on the OS partition, cannot write install order for it.`
- `0x180227d50`: `InstallOrder.ini`
- `0x180227e1f`: `Cannot write install order for provisioning package %s`
- `0x180227e76`: `Cannot calculate the installation order file`
- `0x180228b7f`: `CAddProvisioningPackage::DoExecute: Invalid provisioning package path: %s`
- `0x180228c5c`: `CAddProvisioningPackage::DoExecute: Failed to write package path %s to registry at %s [%s]: 0x%08x`
- `0x180228d95`: `CAddProvisioningPackage::DoExecute: Cannot register provisioning package [%s] because it resides on a different volume than the main OS [%s]`
- `0x180228a1a`: `CAddProvisioningPackage::DoExecute: Failed to create or open package locations key %s: 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=22 #try_helpers=2
void __fastcall __noreturn CAddProvisioningPackage::DoExecute(
        CAddProvisioningPackage *this,
        struct IExecutionContext *a2,
        void *a3,
        struct IInternalOperationsProgress *a4)
{
  struct UnBCL::String *P; // rax
  struct UnBCL::String *v8; // rax
  UnBCL::String *v9; // rbx
  UnBCL::String *v10; // rax
  const unsigned __int16 *CString; // rax
  DWORD LastError; // ebx
  __int64 v13; // rdi
  UnBCL::String *v14; // rax
  const char *v15; // rax
  struct tagLOG_PARTIAL_MSG *v16; // rax
  struct UnBCL::String *v17; // rbx
  struct UnBCL::String *v18; // rax
  DWORD v19; // edi
  __int64 v20; // rbx
  struct tagLOG_PARTIAL_MSG *v21; // rax
  UnBCL::String *v22; // rax
  UnBCL::String *v23; // rax
  UnBCL::String *v24; // rax
  UnBCL::String *v25; // rax
  struct UnBCL::String *v26; // rax
  UnBCL::String *v27; // rax
  const unsigned __int16 *v28; // rax
  struct UnBCL::String *v29; // rax
  const struct UnBCL::String *v30; // rax
  struct UnBCL::String *ParentPath; // rax
  const struct UnBCL::String *v32; // rbx
  const struct UnBCL::String *v33; // rax
  struct UnBCL::String *v34; // rax
  __int64 v35; // rbx
  __int64 v36; // rax
  DWORD v37; // ebx
  __int64 v38; // rdi
  UnBCL::String *v39; // rax
  const char *v40; // rax
  struct tagLOG_PARTIAL_MSG *v41; // rax
  DWORD v42; // edi
  __int64 v43; // rbx
  struct tagLOG_PARTIAL_MSG *v44; // rax
  int v45; // esi
  HRESULT v46; // esi
  DWORD v47; // edi
  __int64 v48; // rbx
  struct tagLOG_PARTIAL_MSG *v49; // rax
  UnBCL::String *v50; // rax
  const unsigned __int16 *v51; // rbx
  UnBCL::String *v52; // rax
  const unsigned __int16 *v53; // rax
  int v54; // esi
  char *v55; // r14
  struct UnBCL::String *v56; // rax
  struct UnBCL::String *v57; // rax
  DWORD v58; // ebx
  __int64 v59; // rdi
  UnBCL::String *v60; // rax
  const char *v61; // rax
  struct tagLOG_PARTIAL_MSG *v62; // rax
  UnBCL::String *v63; // rax
  const unsigned __int16 *v64; // rax
  int v65; // esi
  UnBCL::String *v66; // rax
  const unsigned __int16 *v67; // rax
  int v68; // esi
  const struct UnBCL::String *v69; // rbx
  const struct UnBCL::String *v70; // rax
  struct UnBCL::String *v71; // rax
  UnBCL::String *v72; // rax
  const unsigned __int16 *v73; // rax
  HKEY v74; // rsi
  DWORD v75; // edi
  __int64 v76; // rbx
  struct tagLOG_PARTIAL_MSG *v77; // rax
  DWORD v78; // edi
  __int64 v79; // rbx
  struct tagLOG_PARTIAL_MSG *v80; // rax
  LSTATUS v81; // eax
  signed int v82; // esi
  unsigned int i; // ebx
  struct UnBCL::String *v84; // rax
  UnBCL::String *v85; // rax
  const WCHAR *v86; // rax
  int ValueW; // eax
  bool v88; // sf
  struct UnBCL::String *v89; // rbx
  struct UnBCL::String *v90; // rax
  UnBCL::String *v91; // rbx
  UnBCL::String *v92; // rax
  const unsigned __int16 *v93; // rax
  UnBCL::String *v94; // rbx
  UnBCL::String *v95; // rax
  int Length; // eax
  struct UnBCL::String *v97; // rax
  UnBCL::String *v98; // rax
  int v99; // ebx
  UnBCL::String *v100; // rax
  struct UnBCL::String *v101; // rax
  const struct UnBCL::String *v102; // rbx
  const struct UnBCL::String *v103; // rax
  struct UnBCL::String *v104; // rax
  UnBCL::String *v105; // rax
  const BYTE *v106; // rdi
  UnBCL::String *v107; // rax
  UnBCL::String *v108; // rax
  const WCHAR *v109; // rax
  LSTATUS v110; // eax
  signed int v111; // ebx
  DWORD v112; // edi
  __int64 v113; // rbx
  struct tagLOG_PARTIAL_MSG *v114; // rax
  DWORD v115; // edi
  __int64 v116; // rbx
  struct tagLOG_PARTIAL_MSG *v117; // rax
  DWORD v118; // edi
  __int64 v119; // rbx
  struct tagLOG_PARTIAL_MSG *v120; // rax
  DWORD v121; // edi
  __int64 v122; // rbx
  struct tagLOG_PARTIAL_MSG *v123; // rax
  signed int v124; // eax
  bool v125; // sf
  signed int v126; // eax
  unsigned int v127; // esi
  DWORD v128; // edi
  __int64 v129; // rbx
  struct tagLOG_PARTIAL_MSG *v130; // rax
  DWORD v131; // edi
  __int64 v132; // rbx
  struct tagLOG_PARTIAL_MSG *v133; // rax
  DWORD v134; // ebx
  __int64 v135; // rdi
  UnBCL::String *v136; // rax
  const char *v137; // rax
  struct tagLOG_PARTIAL_MSG *v138; // rax
  DWORD v139; // ebx
  __int64 v140; // rdi
  UnBCL::String *v141; // rax
  const char *v142; // rax
  struct tagLOG_PARTIAL_MSG *v143; // rax
  DWORD v144; // esi
  __int64 v145; // r14
  UnBCL::String *v146; // rax
  const char *v147; // rdi
  UnBCL::String *v148; // rax
  const char *v149; // rax
  struct tagLOG_PARTIAL_MSG *v150; // rax
  DWORD v151; // edi
  __int64 v152; // rsi
  UnBCL::String *v153; // rax
  const char *v154; // rbx
  UnBCL::String *v155; // rax
  const char *v156; // rax
  struct tagLOG_PARTIAL_MSG *v157; // rax
  unsigned int v158; // [rsp+68h] [rbp-180h] BYREF
  _QWORD v159[2]; // [rsp+70h] [rbp-178h] BYREF
  _BYTE v160[16]; // [rsp+80h] [rbp-168h] BYREF
  _BYTE v161[16]; // [rsp+90h] [rbp-158h] BYREF
  int v162; // [rsp+A0h] [rbp-148h]
  int v163; // [rsp+A4h] [rbp-144h] BYREF
  int v164; // [rsp+A8h] [rbp-140h] BYREF
  int v165; // [rsp+ACh] [rbp-13Ch] BYREF
  HKEY phkResult; // [rsp+B0h] [rbp-138h] BYREF
  _BYTE v167[16]; // [rsp+B8h] [rbp-130h] BYREF
  _BYTE v168[16]; // [rsp+C8h] [rbp-120h] BYREF
  HKEY v169; // [rsp+D8h] [rbp-110h]
  _QWORD *pExceptionObject; // [rsp+E0h] [rbp-108h] BYREF
  _QWORD *v171; // [rsp+E8h] [rbp-100h] BYREF
  _QWORD *v172; // [rsp+F0h] [rbp-F8h] BYREF
  _QWORD *v173; // [rsp+F8h] [rbp-F0h] BYREF
  _QWORD *v174; // [rsp+100h] [rbp-E8h] BYREF
  _QWORD *v175; // [rsp+108h] [rbp-E0h] BYREF
  _QWORD *v176; // [rsp+110h] [rbp-D8h] BYREF
  _QWORD *v177; // [rsp+118h] [rbp-D0h] BYREF
  _QWORD *v178; // [rsp+120h] [rbp-C8h] BYREF
  _QWORD *v179; // [rsp+128h] [rbp-C0h] BYREF
  _QWORD *v180; // [rsp+130h] [rbp-B8h] BYREF
  _BYTE v181[16]; // [rsp+138h] [rbp-B0h] BYREF
  _BYTE v182[24]; // [rsp+148h] [rbp-A0h] BYREF
  _QWORD v183[7]; // [rsp+160h] [rbp-88h] BYREF
  _QWORD v184[2]; // [rsp+198h] [rbp-50h] BYREF
  _BYTE v185[16]; // [rsp+1A8h] [rbp-40h] BYREF
  __int64 v186; // [rsp+1B8h] [rbp-30h]

  v186 = -2;
  v163 = 0;
  v162 = 0;
  v158 = 0;
  v169 = 0;
  phkResult = 0;
  v164 = 0;
  v165 = 0;
  UnBCL::Exception::Exception((UnBCL::Exception *)v183);
  v183[0] = &`CAddProvisioningPackage::DoExecute'::`3'::CXXXXXHandledException::`vftable';
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v161);
  if ( *((_DWORD *)this + 60) )
  {
    P = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 224);
    v8 = SPGetStoredPath(a2, P);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v167, v8);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v161, v167);
  }
  else
  {
    v9 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
    v159[0] = v9;
    if ( v9 )
    {
      v10 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)this + 224);
      CString = UnBCL::String::get_CString(v10);
      UnBCL::String::String(v9, CString);
      *(_QWORD *)v9 = &UnBCL::String::`local vftable';
    }
    else
    {
      v9 = 0;
    }
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v167, v9);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v161, v167);
  }
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v167);
  LastError = GetLastError();
  v13 = CurrentIP();
  v14 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v161);
  v15 = (const char *)UnBCL::String::get_CString(v14);
  v16 = ConstructPartialMsgW(0x4000000u, "Installing provisioning package: %s", v15);
  WdsSetupLogMessageW(
    v16,
    819200,
    L"D",
    0,
    146,
    L"base\\ntsetup\\setupplatform\\lib\\src\\provisioning.cpp",
    L"CAddProvisioningPackage::DoExecute",
    v13,
    LastError,
    0,
    0);
  v17 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 208);
  v18 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v161);
  if ( SPArePathsOnSameVolume(v18, v17) )
  {
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v159, v161);
    v22 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v159);
    if ( *UnBCL::String::get_CString(v22) )
    {
      v23 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v159);
      if ( UnBCL::String::get_CString(v23)[1] == 58 )
      {
        v24 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v159);
        if ( UnBCL::String::get_CString(v24)[2] == 92 )
        {
          v25 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v159);
          v26 = UnBCL::String::Remove(v25, 0, 2);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v160, v26);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v159, v160);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v160);
          v27 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v159);
          v28 = UnBCL::String::get_CString(v27);
          v29 = UnBCL::String::Concat(L"%SystemDrive%", v28);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v160, v29);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v159, v160);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v160);
        }
      }
    }
    v30 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v161);
    ParentPath = UnBCL::Path::GetParentPath(v30);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v167, ParentPath);
    if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v167) )
    {
      v32 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v182, L"InstallOrder.ini");
      v33 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v167);
      v34 = UnBCL::Path::Combine(v33, v32);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v160, v34);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v167, v160);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v160);
      UnBCL::String::~String((UnBCL::String *)v182);
      v35 = UnBCL::SmartPtr<UnBCL::String>::get_P(v159);
      v36 = UnBCL::SmartPtr<UnBCL::String>::get_P(v167);
      if ( !(unsigned int)WriteInstallOrder(v36, v35) )
      {
        v37 = GetLastError();
        v38 = CurrentIP();
        v39 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v159);
        v40 = (const char *)UnBCL::String::get_CString(v39);
        v41 = ConstructPartialMsgW(0x3000000u, "Cannot write install order for provisioning package %s", v40);
        WdsSetupLogMessageW(
          v41,
          819200,
          L"D",
          0,
          172,
          L"base\\ntsetup\\setupplatform\\lib\\src\\provisioning.cpp",
          L"CAddProvisioningPackage::DoExecute",
          v38,
          v37,
          0,
          0);
      }
    }
    else
    {
      v42 = GetLastError();
      v43 = CurrentIP();
      v44 = ConstructPartialMsgW(0x3000000u, "Cannot calculate the installation order file");
      WdsSetupLogMessageW(
        v44,
        819200,
        L"D",
        0,
        177,
        L"base\\ntsetup\\setupplatform\\lib\\src\\provisioning.cpp",
        L"CAddProvisioningPackage::DoExecute",
        v43,
        v42,
        0,
        0);
    }
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v167);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v159);
  }
  else
  {
    v19 = GetLastError();
    v20 = CurrentIP();
    v21 = ConstructPartialMsgW(
            0x3000000u,
            "Provisioning package is not on the OS partition, cannot write install order for it.");
    WdsSetupLogMessageW(
      v21,
      819200,
      L"D",
      0,
      153,
      L"base\\ntsetup\\setupplatform\\lib\\src\\provisioning.cpp",
      L"CAddProvisioningPackage::DoExecute",
      v20,
      v19,
      0,
      0);
  }
  v45 = SPInitializeCOM(&v163);
  if ( v45 >= 0 )
  {
    v46 = CoInitializeSecurity(0, -1, 0, 0, 5u, 3u, 0, 0, 0);
    if ( v46 < 0 )
    {
      v47 = GetLastError();
      v48 = CurrentIP();
      v49 = ConstructPartialMsgW(
              0x3000000u,
              "CAddProvisioningPackage::DoExecute: Failed to initialize COM security. Was it initialized before us? hr = 0x%08X",
              v46);
      WdsSetupLogMessageW(
        v49,
        819200,
        L"D",
        0,
        214,
        L"base\\ntsetup\\setupplatform\\lib\\src\\provisioning.cpp",
        L"CAddProvisioningPackage::DoExecute",
        v48,
        v47,
        0,
        0);
    }
    v50 = (UnBCL::String *)(*(__int64 (__fastcall **)(struct IExecutionContext *))(*(_QWORD *)a2 + 8LL))(a2);
    v51 = UnBCL::String::get_CString(v50);
    v52 = (UnBCL::String *)(*(__int64 (__fastcall **)(struct IExecutionContext *))(*(_QWORD *)a2 + 24LL))(a2);
    v53 = UnBCL::String::get_CString(v52);
    v54 = DismInitialize(2, v53, v51);
    if ( v54 >= 0 )
    {
      v162 = 1;
      v55 = (char *)this + 208;
      v56 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 208);
      v57 = SPGetDirectoryPath(v56);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v181, v57);
      v58 = GetLastError();
      v59 = CurrentIP();
      v60 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v181);
      v61 = (const char *)UnBCL::String::get_CString(v60);
      v62 = ConstructPartialMsgW(0x4000000u, "Opening DISM session for %s", v61);
      WdsSetupLogMessageW(
        v62,
        819200,
        L"D",
        0,
        227,
        L"base\\ntsetup\\setupplatform\\lib\\src\\provisioning.cpp",
        L"CAddProvisioningPackage::DoExecute",
        v59,
        v58,
        0,
        0);
      v63 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v181);
      v64 = UnBCL::String::get_CString(v63);
      v65 = DismOpenSession(v64, 0, 0, &v158);
      if ( v65 >= 0 )
      {
        v184[0] = this;
        v184[1] = a4;
        v66 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v161);
        v67 = UnBCL::String::get_CString(v66);
        v68 = _DismApplyProvisioningPackage(v158, v67, a3, SPDismProgressCallback, v184);
        if ( v68 >= 0 )
        {
          if ( v158 )
          {
            DismCloseSession();
            v158 = 0;
          }
          v69 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v182, L"WINDOWS");
          v70 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v55);
          v71 = UnBCL::Path::Combine(v70, v69);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v185, v71);
          UnBCL::String::~String((UnBCL::String *)v182);
          v72 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v185);
          v73 = UnBCL::String::get_CString(v72);
          v74 = SPMountOfflineHive(v73, L"SOFTWARE", L"$OFFLINE_RW$SOFTWARE");
          v169 = v74;
          if ( v74 )
          {
            if ( !(unsigned int)SPEnablePrivilege(L"SeBackupPrivilege", 1, &v164) )
            {
              v75 = GetLastError();
              v76 = CurrentIP();
              v77 = ConstructPartialMsgW(
                      0x2000000u,
                      "%hs: Cannot enable SE_BACKUP_NAME privilege",
                      "CAddProvisioningPackage::DoExecute");
              WdsSetupLogMessageW(
                v77,
                819200,
                L"D",
                0,
                282,
                L"base\\ntsetup\\setupplatform\\lib\\src\\provisioning.cpp",
                L"CAddProvisioningPackage::DoExecute",
                v76,
                v75,
                0,
                0);
            }
            if ( !(unsigned int)SPEnablePrivilege(L"SeRestorePrivilege", 1, &v165) )
            {
              v78 = GetLastError();
              v79 = CurrentIP();
              v80 = ConstructPartialMsgW(
                      0x2000000u,
                      "%hs: Cannot enable SE_RESTORE_NAME privilege",
                      "CAddProvisioningPackage::DoExecute");
              WdsSetupLogMessageW(
                v80,
                819200,
                L"D",
                0,
                287,
                L"base\\ntsetup\\setupplatform\\lib\\src\\provisioning.cpp",
                L"CAddProvisioningPackage::DoExecute",
                v79,
                v78,
                0,
                0);
            }
            v81 = RegCreateKeyExW(
                    v74,
                    L"Microsoft\\Provisioning\\PackageLocations",
                    0,
                    0,
                    4u,
                    0x2001Fu,
                    0,
                    &phkResult,
                    0);
            v82 = v81;
            if ( v81 > 0 )
              v82 = (unsigned __int16)v81 | 0x80070000;
            if ( v82 >= 0 )
            {
              UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v168);
              for ( i = 0; ; ++i )
              {
                v84 = UnBCL::String::Format(L"%u", i);
                UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v160, v84);
                UnBCL::SmartPtr<UnBCL::String>::operator=(v168, v160);
                UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v160);
                v85 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v168);
                v86 = UnBCL::String::get_CString(v85);
                ValueW = RegGetValueW(phkResult, 0, v86, 0xFFFFu, 0, 0, 0);
                v88 = ValueW < 0;
                if ( ValueW > 0 )
                {
                  ValueW = (unsigned __int16)ValueW | 0x80070000;
                  v88 = ValueW < 0;
                }
                if ( v88 && ValueW != -2147024662 )
                {
                  if ( ValueW == -2147023728 || (unsigned int)(ValueW + 2147024894) <= 1 )
                  {
                    v89 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v161);
                    v90 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v55);
                    if ( SPArePathsOnSameVolume(v90, v89) )
                    {
                      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v159);
                      v91 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v161);
                      v92 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v55);
                      v93 = UnBCL::String::get_CString(v92);
                      if ( UnBCL::String::StartsWith(v91, v93, 1) )
                      {
                        v94 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v161);
                        v95 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v55);
                        Length = UnBCL::String::get_Length(v95);
                        v97 = UnBCL::String::Substring(v94, Length);
                        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v160, v97);
                        UnBCL::SmartPtr<UnBCL::String>::operator=(v159, v160);
                      }
                      else
                      {
                        v98 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v161);
                        v99 = UnBCL::String::IndexOf(v98, L"\\");
                        if ( v99 < 0 )
                        {
                          v139 = GetLastError();
                          v140 = CurrentIP();
                          v141 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v161);
                          v142 = (const char *)UnBCL::String::get_CString(v141);
                          v143 = ConstructPartialMsgW(
                                   0x2000000u,
                                   "CAddProvisioningPackage::DoExecute: Invalid provisioning package path: %s",
                                   v142);
                          WdsSetupLogMessageW(
                            v143,
                            819200,
                            L"D",
                            0,
                            345,
                            L"base\\ntsetup\\setupplatform\\lib\\src\\provisioning.cpp",
                            L"CAddProvisioningPackage::DoExecute",
                            v140,
                            v139,
                            0,
                            0);
                          v177 = v183;
                          throw (`CAddProvisioningPackage::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v177;
                        }
                        v100 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v161);
                        v101 = UnBCL::String::Substring(v100, v99);
                        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v160, v101);
                        UnBCL::SmartPtr<UnBCL::String>::operator=(v159, v160);
                      }
                      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v160);
                      v102 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v159);
                      v103 = (const struct UnBCL::String *)UnBCL::String::String(
                                                             (UnBCL::String *)v182,
                                                             L"%SystemDrive%");
                      v104 = UnBCL::Path::Combine(v103, v102);
                      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v160, v104);
                      UnBCL::SmartPtr<UnBCL::String>::operator=(v159, v160);
                      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v160);
                      UnBCL::String::~String((UnBCL::String *)v182);
                      v105 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v159);
                      v106 = (const BYTE *)UnBCL::String::get_CString(v105);
                      v107 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v159);
                      LODWORD(v102) = 2 * UnBCL::String::get_Length(v107) + 2;
                      v108 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v168);
                      v109 = UnBCL::String::get_CString(v108);
                      v110 = RegSetValueExW(phkResult, v109, 0, 2u, v106, (DWORD)v102);
                      v111 = v110;
                      if ( v110 > 0 )
                        v111 = (unsigned __int16)v110 | 0x80070000;
                      if ( v111 < 0 )
                      {
                        v144 = GetLastError();
                        v145 = CurrentIP();
                        v146 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v168);
                        v147 = (const char *)UnBCL::String::get_CString(v146);
                        v148 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v159);
                        v149 = (const char *)UnBCL::String::get_CString(v148);
                        v150 = ConstructPartialMsgW(
                                 0x2000000u,
                                 "CAddProvisioningPackage::DoExecute: Failed to write package path %s to registry at %s [%s]: 0x%08x",
                                 v149,
                                 (const char *)L"Microsoft\\Provisioning\\PackageLocations",
                                 v147,
                                 v111);
                        WdsSetupLogMessageW(
                          v150,
                          819200,
                          L"D",
                          0,
                          365,
                          L"base\\ntsetup\\setupplatform\\lib\\src\\provisioning.cpp",
                          L"CAddProvisioningPackage::DoExecute",
                          v145,
                          v144,
                          0,
                          0);
                        v178 = v183;
                        throw (`CAddProvisioningPackage::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v178;
                      }
                      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v159);
                      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v168);
                      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v185);
                      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v181);
                      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v161);
                      v179 = v183;
                      throw (`CAddProvisioningPackage::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v179;
                    }
                    v151 = GetLastError();
                    v152 = CurrentIP();
                    v153 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v55);
                    v154 = (const char *)UnBCL::String::get_CString(v153);
                    v155 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v161);
                    v156 = (const char *)UnBCL::String::get_CString(v155);
                    v157 = ConstructPartialMsgW(
                             0x2000000u,
                             "CAddProvisioningPackage::DoExecute: Cannot register provisioning package [%s] because it re"
                             "sides on a different volume than the main OS [%s]",
                             v156,
                             v154);
                    WdsSetupLogMessageW(
                      v157,
                      819200,
                      L"D",
                      0,
                      376,
                      L"base\\ntsetup\\setupplatform\\lib\\src\\provisioning.cpp",
                      L"CAddProvisioningPackage::DoExecute",
                      v152,
                      v151,
                      0,
                      0);
                    v180 = v183;
                    throw (`CAddProvisioningPackage::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v180;
                  }
                  v134 = GetLastError();
                  v135 = CurrentIP();
                  v136 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v168);
                  v137 = (const char *)UnBCL::String::get_CString(v136);
                  v138 = ConstructPartialMsgW(
                           0x2000000u,
                           "CAddProvisioningPackage::DoExecute: Failed to query whether %s has a value named %s",
                           (const char *)L"Microsoft\\Provisioning\\PackageLocations",
                           v137);
                  WdsSetupLogMessageW(
                    v138,
                    819200,
                    L"D",
                    0,
                    321,
                    L"base\\ntsetup\\setupplatform\\lib\\src\\provisioning.cpp",
                    L"CAddProvisioningPackage::DoExecute",
                    v135,
                    v134,
                    0,
                    0);
                  v176 = v183;
                  throw (`CAddProvisioningPackage::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v176;
                }
              }
            }
            v131 = GetLastError();
            v132 = CurrentIP();
            v133 = ConstructPartialMsgW(
                     0x2000000u,
                     "CAddProvisioningPackage::DoExecute: Failed to create or open package locations key %s: 0x%08x",
                     (const char *)L"Microsoft\\Provisioning\\PackageLocations",
                     v82);
            WdsSetupLogMessageW(
              v133,
              819200,
              L"D",
              0,
              303,
              L"base\\ntsetup\\setupplatform\\lib\\src\\provisioning.cpp",
              L"CAddProvisioningPackage::DoExecute",
              v132,
              v131,
              0,
              0);
            v175 = v183;
            throw (`CAddProvisioningPackage::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v175;
          }
          v124 = GetLastError();
          v125 = v124 < 0;
          if ( v124 > 0 )
            v125 = 1;
          if ( v125 )
          {
            v126 = GetLastError();
            v127 = v126;
            if ( v126 > 0 )
              v127 = (unsigned __int16)v126 | 0x80070000;
          }
          else
          {
            v127 = -2147467259;
          }
          v128 = GetLastError();
          v129 = CurrentIP();
          v130 = ConstructPartialMsgW(
                   0x2000000u,
                   "CAddProvisioningPackage::DoExecute: Failed to load offline SOFTWARE hive: 0x%08x",
                   v127);
          WdsSetupLogMessageW(
            v130,
            819200,
            L"D",
            0,
            275,
            L"base\\ntsetup\\setupplatform\\lib\\src\\provisioning.cpp",
            L"CAddProvisioningPackage::DoExecute",
            v129,
            v128,
            0,
            0);
          v174 = v183;
          throw (`CAddProvisioningPackage::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v174;
        }
        v121 = GetLastError();
        v122 = CurrentIP();
        v123 = ConstructPartialMsgW(
                 0x2000000u,
                 "CAddProvisioningPackage::DoExecute: Failed to apply provisioning package. Error: 0x%08X",
                 v68);
        WdsSetupLogMessageW(
          v123,
          819200,
          L"D",
          0,
          250,
          L"base\\ntsetup\\setupplatform\\lib\\src\\provisioning.cpp",
          L"CAddProvisioningPackage::DoExecute",
          v122,
          v121,
          0,
          0);
        v173 = v183;
        throw (`CAddProvisioningPackage::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v173;
      }
      v118 = GetLastError();
      v119 = CurrentIP();
      v120 = ConstructPartialMsgW(
               0x2000000u,
               "CAddProvisioningPackage::DoExecute: Failed to open new OS DISM session. Error: 0x%08X",
               v65);
      WdsSetupLogMessageW(
        v120,
        819200,
        L"D",
        0,
        231,
        L"base\\ntsetup\\setupplatform\\lib\\src\\provisioning.cpp",
        L"CAddProvisioningPackage::DoExecute",
        v119,
        v118,
        0,
        0);
      v172 = v183;
      throw (`CAddProvisioningPackage::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v172;
    }
    v115 = GetLastError();
    v116 = CurrentIP();
    v117 = ConstructPartialMsgW(
             0x2000000u,
             "CAddProvisioningPackage::DoExecute: Failed to initialize DISM. Error: 0x%08X",
             v54);
    WdsSetupLogMessageW(
      v117,
      819200,
      L"D",
      0,
      221,
      L"base\\ntsetup\\setupplatform\\lib\\src\\provisioning.cpp",
      L"CAddProvisioningPackage::DoExecute",
      v116,
      v115,
      0,
      0);
    v171 = v183;
    throw (`CAddProvisioningPackage::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v171;
  }
  v112 = GetLastError();
  v113 = CurrentIP();
  v114 = ConstructPartialMsgW(
           0x2000000u,
           "CAddProvisioningPackage::DoExecute: Failed to initialize COM. hr = 0x%08X",
           v45);
  WdsSetupLogMessageW(
    v114,
    819200,
    L"D",
    0,
    196,
    L"base\\ntsetup\\setupplatform\\lib\\src\\provisioning.cpp",
    L"CAddProvisioningPackage::DoExecute",
    v113,
    v112,
    0,
    0);
  pExceptionObject = v183;
  throw (`CAddProvisioningPackage::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&pExceptionObject;
}

```

## disassembly

```asm
0x180227970  mov     rax, rsp
0x180227973  mov     [rax+18h], r8
0x180227977  push    rdi
0x180227978  push    r12
0x18022797a  push    r13
0x18022797c  push    r14
0x18022797e  push    r15
0x180227980  sub     rsp, 1C0h
0x180227987  mov     qword ptr [rax-30h], 0FFFFFFFFFFFFFFFEh
0x18022798f  mov     [rax+8], rbx
0x180227993  mov     [rax+10h], rsi
0x180227997  mov     r12, r9
0x18022799a  mov     r14, rdx
0x18022799d  mov     r13, rcx
0x1802279a0  xor     r15d, r15d
0x1802279a3  mov     [rsp+1E8h+var_188], r15d
0x1802279a8  mov     [rax-144h], r15d
0x1802279af  mov     [rsp+1E8h+var_148], r15d
0x1802279b7  mov     [rsp+1E8h+var_180], r15d
0x1802279bc  mov     [rsp+1E8h+var_110], r15
0x1802279c4  mov     [rax-138h], r15
0x1802279cb  mov     [rax-140h], r15d
0x1802279d2  mov     [rax-13Ch], r15d
0x1802279d9  mov     [rsp+1E8h+var_184], r15d
0x1802279de  lea     rcx, [rax-88h]
0x1802279e5  call    cs:__imp_??0Exception@UnBCL@@QEAA@XZ; UnBCL::Exception::Exception(void)
0x1802279eb  lea     rax, ??_7CXXXXXHandledException@?2??DoExecute@CAddProvisioningPackage@@UEAAJPEAUIExecutionContext@@PEAXPEAUIInternalOperationsProgress@@@Z@6B@; const `CAddProvisioningPackage::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException::`vftable'
0x1802279f2  mov     [rsp+1E8h+var_88], rax
0x1802279fa  lea     rcx, [rsp+1E8h+var_158]
0x180227a02  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x180227a08  nop
0x180227a09  cmp     [r13+0F0h], r15d
0x180227a10  jz      short loc_180227A55
0x180227a12  lea     rcx, [r13+0E0h]
0x180227a19  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180227a1f  mov     rdx, rax; struct UnBCL::String *
0x180227a22  mov     rcx, r14; struct IExecutionContext *
0x180227a25  call    ?SPGetStoredPath@@YAPEAVString@UnBCL@@PEAUIExecutionContext@@PEAV12@@Z; SPGetStoredPath(IExecutionContext *,UnBCL::String *)
0x180227a2a  mov     rdx, rax
0x180227a2d  lea     rcx, [rsp+1E8h+var_130]
0x180227a35  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180227a3b  nop
0x180227a3c  lea     rdx, [rsp+1E8h+var_130]
0x180227a44  lea     rcx, [rsp+1E8h+var_158]
0x180227a4c  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180227a52  nop
0x180227a53  jmp     short loc_180227AC7
0x180227a55  mov     ecx, 18h
0x180227a5a  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180227a60  mov     rbx, rax
0x180227a63  mov     [rsp+1E8h+var_178], rax
0x180227a68  test    rax, rax
0x180227a6b  jz      short loc_180227A9B
0x180227a6d  lea     rcx, [r13+0E0h]
0x180227a74  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180227a7a  mov     rcx, rax
0x180227a7d  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180227a83  mov     rdx, rax
0x180227a86  mov     rcx, rbx
0x180227a89  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180227a8f  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x180227a96  mov     [rbx], rax
0x180227a99  jmp     short loc_180227A9E
0x180227a9b  mov     rbx, r15
0x180227a9e  mov     rdx, rbx
0x180227aa1  lea     rcx, [rsp+1E8h+var_130]
0x180227aa9  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180227aaf  nop
0x180227ab0  lea     rdx, [rsp+1E8h+var_130]
0x180227ab8  lea     rcx, [rsp+1E8h+var_158]
0x180227ac0  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180227ac6  nop
0x180227ac7  lea     rcx, [rsp+1E8h+var_130]
0x180227acf  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180227ad5  call    cs:__imp_GetLastError
0x180227adb  mov     ebx, eax
0x180227add  call    cs:__imp_CurrentIP
0x180227ae3  mov     rdi, rax
0x180227ae6  lea     rcx, [rsp+1E8h+var_158]
0x180227aee  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180227af4  mov     rcx, rax
0x180227af7  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180227afd  mov     r8, rax
0x180227b00  lea     rdx, aInstallingProv; "Installing provisioning package: %s"
0x180227b07  mov     ecx, 4000000h; unsigned int
0x180227b0c  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180227b11  mov     [rsp+1E8h+var_198], r15d
0x180227b16  mov     [rsp+1E8h+var_1A0], r15
0x180227b1b  mov     dword ptr [rsp+1E8h+pReserved3], ebx
0x180227b1f  mov     qword ptr [rsp+1E8h+dwCapabilities], rdi
0x180227b24  lea     rcx, aCaddprovisioni; "CAddProvisioningPackage::DoExecute"
0x180227b2b  mov     [rsp+1E8h+pAuthList], rcx
0x180227b30  lea     rcx, aBaseNtsetupSet_36; "base\\ntsetup\\setupplatform\\lib\\src"...
0x180227b37  mov     qword ptr [rsp+1E8h+dwImpLevel], rcx
0x180227b3c  mov     [rsp+1E8h+dwAuthnLevel], 92h
0x180227b44  xor     r9d, r9d
0x180227b47  lea     rsi, aD_0; "D"
0x180227b4e  mov     r8, rsi
0x180227b51  mov     edx, 0C8000h
0x180227b56  mov     rcx, rax
0x180227b59  call    cs:__imp_WdsSetupLogMessageW
0x180227b5f  lea     rcx, [r13+0D0h]
0x180227b66  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180227b6c  mov     rbx, rax
0x180227b6f  lea     rcx, [rsp+1E8h+var_158]
0x180227b77  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180227b7d  mov     rdx, rbx; struct UnBCL::String *
0x180227b80  mov     rcx, rax; struct UnBCL::String *
0x180227b83  call    ?SPArePathsOnSameVolume@@YAHPEAVString@UnBCL@@0@Z; SPArePathsOnSameVolume(UnBCL::String *,UnBCL::String *)
0x180227b88  test    eax, eax
0x180227b8a  jnz     short loc_180227BFA
0x180227b8c  call    cs:__imp_GetLastError
0x180227b92  mov     edi, eax
0x180227b94  call    cs:__imp_CurrentIP
0x180227b9a  mov     rbx, rax
0x180227b9d  lea     rdx, aProvisioningPa_1; "Provisioning package is not on the OS p"...
0x180227ba4  mov     ecx, 3000000h; unsigned int
0x180227ba9  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180227bae  mov     [rsp+1E8h+var_198], r15d
0x180227bb3  mov     [rsp+1E8h+var_1A0], r15
0x180227bb8  mov     dword ptr [rsp+1E8h+pReserved3], edi
0x180227bbc  mov     qword ptr [rsp+1E8h+dwCapabilities], rbx
0x180227bc1  lea     rcx, aCaddprovisioni; "CAddProvisioningPackage::DoExecute"
0x180227bc8  mov     [rsp+1E8h+pAuthList], rcx
0x180227bcd  lea     rcx, aBaseNtsetupSet_36; "base\\ntsetup\\setupplatform\\lib\\src"...
0x180227bd4  mov     qword ptr [rsp+1E8h+dwImpLevel], rcx
0x180227bd9  mov     [rsp+1E8h+dwAuthnLevel], 99h
0x180227be1  xor     r9d, r9d
0x180227be4  mov     r8, rsi
0x180227be7  mov     edx, 0C8000h
0x180227bec  mov     rcx, rax
0x180227bef  call    cs:__imp_WdsSetupLogMessageW
0x180227bf5  jmp     loc_180227EE9
0x180227bfa  lea     rdx, [rsp+1E8h+var_158]
0x180227c02  lea     rcx, [rsp+1E8h+var_178]
0x180227c07  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::SmartPtr<UnBCL::String> const &)
0x180227c0d  nop
0x180227c0e  lea     rcx, [rsp+1E8h+var_178]
0x180227c13  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180227c19  mov     rcx, rax
0x180227c1c  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180227c22  cmp     [rax], r15w
0x180227c26  jz      loc_180227D10
0x180227c2c  lea     rcx, [rsp+1E8h+var_178]
0x180227c31  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180227c37  mov     rcx, rax
0x180227c3a  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180227c40  cmp     word ptr [rax+2], 3Ah ; ':'
0x180227c45  jnz     loc_180227D10
0x180227c4b  lea     rcx, [rsp+1E8h+var_178]
0x180227c50  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180227c56  mov     rcx, rax
0x180227c59  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180227c5f  cmp     word ptr [rax+4], 5Ch ; '\'
0x180227c64  jnz     loc_180227D10
0x180227c6a  lea     rcx, [rsp+1E8h+var_178]
0x180227c6f  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180227c75  xor     edx, edx
0x180227c77  lea     r8d, [rdx+2]
0x180227c7b  mov     rcx, rax
0x180227c7e  call    cs:__imp_?Remove@String@UnBCL@@QEBAPEAV12@HH@Z; UnBCL::String::Remove(int,int)
0x180227c84  mov     rdx, rax
0x180227c87  lea     rcx, [rsp+1E8h+var_168]
0x180227c8f  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180227c95  nop
0x180227c96  lea     rdx, [rsp+1E8h+var_168]
0x180227c9e  lea     rcx, [rsp+1E8h+var_178]
0x180227ca3  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180227ca9  nop
0x180227caa  lea     rcx, [rsp+1E8h+var_168]
0x180227cb2  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180227cb8  lea     rcx, [rsp+1E8h+var_178]
0x180227cbd  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180227cc3  mov     rcx, rax
0x180227cc6  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180227ccc  mov     rdx, rax
0x180227ccf  lea     rcx, aSystemdrive_3; "%SystemDrive%"
0x180227cd6  call    cs:__imp_?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z; UnBCL::String::Concat(ushort const *,ushort const *)
0x180227cdc  mov     rdx, rax
0x180227cdf  lea     rcx, [rsp+1E8h+var_168]
0x180227ce7  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180227ced  nop
0x180227cee  lea     rdx, [rsp+1E8h+var_168]
0x180227cf6  lea     rcx, [rsp+1E8h+var_178]
0x180227cfb  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180227d01  nop
0x180227d02  lea     rcx, [rsp+1E8h+var_168]
0x180227d0a  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180227d10  lea     rcx, [rsp+1E8h+var_158]
0x180227d18  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180227d1e  mov     rcx, rax
0x180227d21  call    cs:__imp_?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetParentPath(UnBCL::String const *)
0x180227d27  mov     rdx, rax
0x180227d2a  lea     rcx, [rsp+1E8h+var_130]
0x180227d32  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180227d38  nop
0x180227d39  lea     rcx, [rsp+1E8h+var_130]
0x180227d41  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180227d47  test    rax, rax
0x180227d4a  jz      loc_180227E65
0x180227d50  lea     rdx, aInstallorderIn; "InstallOrder.ini"
0x180227d57  lea     rcx, [rsp+1E8h+var_A0]
0x180227d5f  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180227d65  mov     rbx, rax
0x180227d68  lea     rcx, [rsp+1E8h+var_130]
0x180227d70  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180227d76  mov     rdx, rbx
0x180227d79  mov     rcx, rax
0x180227d7c  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x180227d82  mov     rdx, rax
0x180227d85  lea     rcx, [rsp+1E8h+var_168]
0x180227d8d  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180227d93  nop
0x180227d94  lea     rdx, [rsp+1E8h+var_168]
0x180227d9c  lea     rcx, [rsp+1E8h+var_130]
0x180227da4  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180227daa  nop
0x180227dab  lea     rcx, [rsp+1E8h+var_168]
0x180227db3  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180227db9  nop
0x180227dba  lea     rcx, [rsp+1E8h+var_A0]
0x180227dc2  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180227dc8  lea     rcx, [rsp+1E8h+var_178]
0x180227dcd  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180227dd3  mov     rbx, rax
0x180227dd6  lea     rcx, [rsp+1E8h+var_130]
0x180227dde  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180227de4  mov     rdx, rbx
0x180227de7  mov     rcx, rax
0x180227dea  call    WriteInstallOrder
0x180227def  test    eax, eax
0x180227df1  jnz     loc_180227ECF
0x180227df7  call    cs:__imp_GetLastError
0x180227dfd  mov     ebx, eax
0x180227dff  call    cs:__imp_CurrentIP
0x180227e05  mov     rdi, rax
0x180227e08  lea     rcx, [rsp+1E8h+var_178]
0x180227e0d  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180227e13  mov     rcx, rax
0x180227e16  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180227e1c  mov     r8, rax
0x180227e1f  lea     rdx, aCannotWriteIns; "Cannot write install order for provisio"...
0x180227e26  mov     ecx, 3000000h; unsigned int
0x180227e2b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180227e30  mov     [rsp+1E8h+var_198], r15d
0x180227e35  mov     [rsp+1E8h+var_1A0], r15
0x180227e3a  mov     dword ptr [rsp+1E8h+pReserved3], ebx
0x180227e3e  mov     qword ptr [rsp+1E8h+dwCapabilities], rdi
0x180227e43  lea     rcx, aCaddprovisioni; "CAddProvisioningPackage::DoExecute"
0x180227e4a  mov     [rsp+1E8h+pAuthList], rcx
0x180227e4f  lea     rcx, aBaseNtsetupSet_36; "base\\ntsetup\\setupplatform\\lib\\src"...
0x180227e56  mov     qword ptr [rsp+1E8h+dwImpLevel], rcx
0x180227e5b  mov     [rsp+1E8h+dwAuthnLevel], 0ACh
0x180227e63  jmp     short loc_180227EBA
0x180227e65  call    cs:__imp_GetLastError
0x180227e6b  mov     edi, eax
0x180227e6d  call    cs:__imp_CurrentIP
0x180227e73  mov     rbx, rax
0x180227e76  lea     rdx, aCannotCalculat; "Cannot calculate the installation order"...
0x180227e7d  mov     ecx, 3000000h; unsigned int
0x180227e82  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180227e87  mov     [rsp+1E8h+var_198], r15d
0x180227e8c  mov     [rsp+1E8h+var_1A0], r15
0x180227e91  mov     dword ptr [rsp+1E8h+pReserved3], edi
0x180227e95  mov     qword ptr [rsp+1E8h+dwCapabilities], rbx
0x180227e9a  lea     rcx, aCaddprovisioni; "CAddProvisioningPackage::DoExecute"
0x180227ea1  mov     [rsp+1E8h+pAuthList], rcx
0x180227ea6  lea     rcx, aBaseNtsetupSet_36; "base\\ntsetup\\setupplatform\\lib\\src"...
0x180227ead  mov     qword ptr [rsp+1E8h+dwImpLevel], rcx
0x180227eb2  mov     [rsp+1E8h+dwAuthnLevel], 0B1h
0x180227eba  xor     r9d, r9d
0x180227ebd  mov     r8, rsi
0x180227ec0  mov     edx, 0C8000h
0x180227ec5  mov     rcx, rax
0x180227ec8  call    cs:__imp_WdsSetupLogMessageW
0x180227ece  nop
0x180227ecf  lea     rcx, [rsp+1E8h+var_130]
0x180227ed7  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180227edd  nop
0x180227ede  lea     rcx, [rsp+1E8h+var_178]
0x180227ee3  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180227ee9  lea     rcx, [rsp+1E8h+var_144]; int *
0x180227ef1  call    ?SPInitializeCOM@@YAJAEAH@Z; SPInitializeCOM(int &)
0x180227ef6  mov     esi, eax
0x180227ef8  mov     [rsp+1E8h+var_188], eax
0x180227efc  test    eax, eax
0x180227efe  js      loc_1802286BC
0x180227f04  mov     [rsp+1E8h+pReserved3], r15; pReserved3
0x180227f09  mov     [rsp+1E8h+dwCapabilities], r15d; dwCapabilities
0x180227f0e  mov     [rsp+1E8h+pAuthList], r15; pAuthList
0x180227f13  mov     [rsp+1E8h+dwImpLevel], 3; dwImpLevel
0x180227f1b  mov     [rsp+1E8h+dwAuthnLevel], 5; dwAuthnLevel
0x180227f23  xor     r9d, r9d; pReserved1
0x180227f26  xor     r8d, r8d; asAuthSvc
0x180227f29  or      edx, 0FFFFFFFFh; cAuthSvc
0x180227f2c  xor     ecx, ecx; pSecDesc
0x180227f2e  call    cs:__imp_CoInitializeSecurity
0x180227f34  mov     esi, eax
0x180227f36  mov     [rsp+1E8h+var_188], eax
0x180227f3a  test    eax, eax
  ... truncated ...
```
