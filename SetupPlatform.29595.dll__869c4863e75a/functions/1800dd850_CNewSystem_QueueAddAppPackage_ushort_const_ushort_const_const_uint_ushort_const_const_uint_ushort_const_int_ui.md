# CNewSystem::QueueAddAppPackage(ushort const *,ushort const * * const,uint,ushort const * * const,uint,ushort const *,int,uint,int,unsigned __int64,SetupPlatform::SP_ERROR_HANDLING)

- ea: `0x1800dd850`
- end: `0x1800df39d`
- name: `?QueueAddAppPackage@CNewSystem@@UEAAJPEBGQEAPEBGI1I0HIH_KW4SP_ERROR_HANDLING@SetupPlatform@@@Z`
- size: `6989`
- prototype: `int __high(const unsigned __int16 *, const unsigned __int16 **const, unsigned int, const unsigned __int16 **const, unsigned int, const unsigned __int16 *, int, unsigned int, int, unsigned __int64, enum SetupPlatform::SP_ERROR_HANDLING)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callees

- `0x18001413d`
- `0x180044810`
- `0x180057dec`
- `0x18005dd24`
- `0x1800ae380`
- `0x1800c6158`
- `0x1800dd850`
- `0x18010f584`
- `0x180115ba4`
- `0x180157328`
- `0x18015fd04`
- `0x18015fe94`
- `0x180221598`
- `0x1802c6944`
- `0x1802cd658`
- `0x1802d6738`
- `0x1802d6bb0`
- `0x180509010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800dd8d6`
- `KERNEL32!GetLastError` at `0x1800dd965`
- `KERNEL32!GetLastError` at `0x1800ded6d`
- `KERNEL32!GetLastError` at `0x1800deddd`
- `KERNEL32!GetLastError` at `0x1800dee48`
- `KERNEL32!GetLastError` at `0x1800deeb9`
- `KERNEL32!GetLastError` at `0x1800deecf`
- `KERNEL32!GetLastError` at `0x1800deef2`
- `KERNEL32!GetLastError` at `0x1800def91`
- `KERNEL32!GetLastError` at `0x1800df038`
- `KERNEL32!GetLastError` at `0x1800df0df`
- `KERNEL32!GetLastError` at `0x1800dd8d6`
- `KERNEL32!GetLastError` at `0x1800dd965`
- `KERNEL32!GetLastError` at `0x1800ded6d`
- `KERNEL32!GetLastError` at `0x1800deddd`
- `KERNEL32!GetLastError` at `0x1800dee48`
- `KERNEL32!GetLastError` at `0x1800deeb9`
- `KERNEL32!GetLastError` at `0x1800deecf`
- `KERNEL32!GetLastError` at `0x1800deef2`
- `KERNEL32!GetLastError` at `0x1800def91`
- `KERNEL32!GetLastError` at `0x1800df038`
- `KERNEL32!GetLastError` at `0x1800df0df`
- `KERNEL32!EnterCriticalSection` at `0x1800dda22`
- `KERNEL32!EnterCriticalSection` at `0x1800dda22`
- `KERNEL32!GetFileAttributesW` at `0x1800ddacc`
- `KERNEL32!GetFileAttributesW` at `0x1800ddb2e`
- `KERNEL32!GetFileAttributesW` at `0x1800de1e3`
- `KERNEL32!GetFileAttributesW` at `0x1800ddacc`
- `KERNEL32!GetFileAttributesW` at `0x1800ddb2e`
- `KERNEL32!GetFileAttributesW` at `0x1800de1e3`
- `unbcl!?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800ddd7a`
- `unbcl!?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800de432`
- `unbcl!?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800dea91`
- `unbcl!?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800ddd7a`
- `unbcl!?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800de432`
- `unbcl!?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800dea91`
- `unbcl!?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800ddaa3`
- `unbcl!?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800ddf19`
- `unbcl!?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800ddaa3`
- `unbcl!?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800ddf19`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1800dde26`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1800de4d5`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1800deb34`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1800dde26`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1800de4d5`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1800deb34`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1800dda38`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1800dda38`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800ddc43`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800ddcaf`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800ddd28`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800dddc5`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800de2fc`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800de36d`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800de3e3`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800de47a`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800de95b`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800de9cc`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800dea42`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800dead9`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800ddc43`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800ddcaf`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800ddd28`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800dddc5`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800de2fc`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800de36d`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800de3e3`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800de47a`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800de95b`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800de9cc`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800dea42`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800dead9`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1800ded5b`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1800ded5b`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x1800de702`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x1800ded22`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x1800de702`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x1800ded22`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x1800de1ae`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x1800de6e4`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x1800de73b`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x1800de819`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x1800ded04`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x1800df18e`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x1800de1ae`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x1800de6e4`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x1800de73b`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x1800de819`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x1800ded04`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x1800df18e`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1800de156`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1800de7d0`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1800de156`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1800de7d0`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x1800de17a`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x1800de769`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x1800de7e5`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x1800df1bc`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x1800de17a`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x1800de769`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x1800de7e5`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x1800df1bc`
- `unbcl!??4?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800de191`
- `unbcl!??4?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800de780`
- `unbcl!??4?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800de7fc`
- `unbcl!??4?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800df1d3`
- `unbcl!??4?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800de191`
- `unbcl!??4?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800de780`
- `unbcl!??4?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800de7fc`
- `unbcl!??4?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800df1d3`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800de1a0`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800de78f`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800de80b`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800df1e2`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800df347`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800df356`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800de1a0`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800de78f`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800de80b`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800df1e2`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800df347`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800df356`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1800dda78`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1800dda87`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1800dda78`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1800dda87`
- `unbcl!?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x1800df248`
- `unbcl!?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x1800df25e`
- `unbcl!?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x1800df248`
- `unbcl!?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x1800df25e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800ddb60`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800ddb7f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800ddbaf`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800ddc0d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800ddc37`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800ddca3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800ddd0b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800ddd1c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800ddda8`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dddb9`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800ddf10`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de21f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de23e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de26c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de2ca`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de2f0`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de361`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de3c9`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de3d7`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de460`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de46e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de87e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de89d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de8cb`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de929`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de94f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de9c0`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dea28`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dea36`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800deabf`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800deacd`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800df26f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800ddb60`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800ddb7f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800ddbaf`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800ddc0d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800ddc37`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800ddca3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800ddd0b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800ddd1c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800ddda8`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dddb9`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800ddf10`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de21f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de23e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de26c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de2ca`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de2f0`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de361`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de3c9`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de3d7`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de460`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de46e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de87e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de89d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de8cb`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de929`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de94f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800de9c0`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dea28`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dea36`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800deabf`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800deacd`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800df26f`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1800dda69`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1800de1f1`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1800de850`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1800dda69`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1800de1f1`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1800de850`

## string_xrefs

- `0x1800dd91e`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800dd9b4`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800dedb5`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800dee20`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800dee87`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800def39`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800defdc`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800df083`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800df12a`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800def09`: `Failure while validating app path [%s]. Error: 0x%08X`
- `0x1800dde1f`: `Copy appx package payload from %s to %s`
- `0x1800defa5`: `Failure while requesting appx package payload copy. Error: 0x%08X`
- `0x1800df04c`: `Failure while requesting appx dependency package payload copy. Error: 0x%08X`
- `0x1800de4ce`: `Copy appx dependency package from %s to %s`
- `0x1800deb2d`: `Copy appx license from %s to %s`
- `0x1800df0f3`: `Failure while requesting appx license payload copy. Error: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=69
__int64 __fastcall CNewSystem::QueueAddAppPackage(
        __int64 a1,
        const char *a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6,
        __int64 a7,
        int a8,
        int a9,
        int a10,
        unsigned __int64 a11,
        int a12)
{
  __int64 v13; // rsi
  DWORD LastError; // edi
  __int64 v16; // rbx
  struct tagLOG_PARTIAL_MSG *v17; // rax
  unsigned int v18; // eax
  DWORD v19; // edi
  __int64 v20; // rbx
  struct tagLOG_PARTIAL_MSG *v21; // rax
  unsigned int v22; // eax
  const struct UnBCL::String *v23; // rax
  struct UnBCL::String *ParentPath; // rax
  struct UnBCL::String *v25; // rax
  UnBCL::String *v26; // rax
  const WCHAR *CString; // rax
  char FileAttributesW; // r15
  struct UnBCL::String *v29; // rbx
  int v30; // r13d
  struct UnBCL::String *P; // rax
  struct UnBCL::String *v32; // rdi
  struct UnBCL::String *v33; // rax
  bool v34; // di
  int v35; // r15d
  const struct UnBCL::String *v36; // rbx
  const struct UnBCL::String *v37; // rax
  struct UnBCL::String *v38; // rax
  unsigned __int64 v39; // rsi
  const struct UnBCL::String *v40; // rbx
  const struct UnBCL::String *v41; // rax
  struct UnBCL::String *v42; // rax
  const struct UnBCL::String *v43; // rbx
  const struct UnBCL::String *v44; // rax
  struct UnBCL::String *v45; // rax
  const struct UnBCL::String *v46; // rax
  struct UnBCL::String *FileName; // rax
  const struct UnBCL::String *v48; // rbx
  const struct UnBCL::String *v49; // rax
  struct UnBCL::String *v50; // rax
  UnBCL::String *v51; // rax
  const unsigned __int16 *v52; // rax
  struct UnBCL::String *v53; // rax
  void *v54; // rax
  void *v55; // rbx
  UnBCL::String *v56; // rax
  const unsigned __int16 *v57; // rax
  CCopyFilesAndFolders *v58; // rbx
  UnBCL::String *v59; // rax
  const unsigned __int16 *v60; // rax
  int v61; // esi
  const struct UnBCL::String *v62; // rax
  struct UnBCL::String *v63; // rax
  CCopyFilesAndFolders *v64; // rdi
  UnBCL::String *v65; // rax
  const unsigned __int16 *v66; // rbx
  UnBCL::String *v67; // rax
  const unsigned __int16 *v68; // rax
  CCopyFilesAndFolders *v69; // rbx
  UnBCL::String *v70; // rax
  const unsigned __int16 *v71; // rax
  __int64 v72; // rbx
  void (__fastcall *v73)(__int64, __int64); // rdi
  __int64 v74; // rax
  UnBCL::String *v75; // rax
  UnBCL::String *v76; // rbx
  bool v77; // zf
  unsigned __int64 v78; // rax
  __int64 v79; // rdi
  _QWORD *v80; // rax
  _QWORD *v81; // rbx
  __int64 v82; // rax
  __int64 v83; // r12
  const WCHAR *v84; // r14
  char v85; // r15
  struct UnBCL::String *v86; // rbx
  struct UnBCL::String *v87; // rax
  struct UnBCL::String *v88; // rdi
  struct UnBCL::String *v89; // rax
  bool v90; // bl
  const struct UnBCL::String *v91; // rdi
  const struct UnBCL::String *v92; // rax
  struct UnBCL::String *v93; // rax
  unsigned __int64 v94; // rsi
  const struct UnBCL::String *v95; // rbx
  const struct UnBCL::String *v96; // rax
  struct UnBCL::String *v97; // rax
  const struct UnBCL::String *v98; // rbx
  const struct UnBCL::String *v99; // rax
  struct UnBCL::String *v100; // rax
  const struct UnBCL::String *v101; // rax
  struct UnBCL::String *v102; // rax
  const struct UnBCL::String *v103; // rbx
  const struct UnBCL::String *v104; // rax
  struct UnBCL::String *v105; // rax
  UnBCL::String *v106; // rax
  const unsigned __int16 *v107; // rax
  struct UnBCL::String *v108; // rax
  void *v109; // rax
  void *v110; // rbx
  UnBCL::String *v111; // rax
  const unsigned __int16 *v112; // rax
  CCopyFilesAndFolders *v113; // rbx
  UnBCL::String *v114; // rax
  const unsigned __int16 *v115; // rax
  int v116; // esi
  __int64 v117; // rbx
  void (__fastcall *v118)(__int64, __int64); // rdi
  __int64 v119; // rax
  _BYTE *v120; // rcx
  UnBCL::String *v121; // rax
  UnBCL::String *v122; // rbx
  __int64 v123; // rax
  __int64 v124; // rbx
  void (__fastcall *v125)(__int64, __int64); // rdi
  __int64 v126; // rax
  __int64 v127; // rax
  unsigned int (__fastcall ***v128)(_QWORD); // rcx
  __int64 v129; // r14
  _QWORD *v130; // rax
  _QWORD *v131; // rbx
  __int64 v132; // rax
  __int64 v133; // r15
  const unsigned __int16 *v134; // r14
  struct UnBCL::String *v135; // rbx
  struct UnBCL::String *v136; // rax
  struct UnBCL::String *v137; // rdi
  struct UnBCL::String *v138; // rax
  bool v139; // bl
  const struct UnBCL::String *v140; // rdi
  const struct UnBCL::String *v141; // rax
  struct UnBCL::String *v142; // rax
  unsigned __int64 v143; // rsi
  const struct UnBCL::String *v144; // rbx
  const struct UnBCL::String *v145; // rax
  struct UnBCL::String *v146; // rax
  const struct UnBCL::String *v147; // rbx
  const struct UnBCL::String *v148; // rax
  struct UnBCL::String *v149; // rax
  const struct UnBCL::String *v150; // rax
  struct UnBCL::String *v151; // rax
  const struct UnBCL::String *v152; // rbx
  const struct UnBCL::String *v153; // rax
  struct UnBCL::String *v154; // rax
  UnBCL::String *v155; // rax
  const unsigned __int16 *v156; // rax
  struct UnBCL::String *v157; // rax
  void *v158; // rax
  void *v159; // rbx
  UnBCL::String *v160; // rax
  const unsigned __int16 *v161; // rax
  CCopyFilesAndFolders *v162; // rbx
  UnBCL::String *v163; // rax
  const unsigned __int16 *v164; // rax
  int v165; // esi
  __int64 v166; // rbx
  void (__fastcall *v167)(__int64, __int64); // rdi
  __int64 v168; // rax
  _BYTE *v169; // rcx
  UnBCL::String *v170; // rax
  UnBCL::String *v171; // rbx
  __int64 v172; // rax
  __int64 v173; // rbx
  void (__fastcall *v174)(__int64, __int64); // rdi
  __int64 v175; // rax
  DWORD v176; // edi
  __int64 v177; // rbx
  struct tagLOG_PARTIAL_MSG *v178; // rax
  DWORD v179; // edi
  __int64 v180; // rbx
  struct tagLOG_PARTIAL_MSG *v181; // rax
  DWORD v182; // edi
  __int64 v183; // rbx
  struct tagLOG_PARTIAL_MSG *v184; // rax
  signed int v185; // eax
  bool v186; // sf
  signed int v187; // eax
  unsigned int v188; // esi
  DWORD v189; // edi
  __int64 v190; // rbx
  struct tagLOG_PARTIAL_MSG *v191; // rax
  DWORD v192; // edi
  __int64 v193; // rbx
  struct tagLOG_PARTIAL_MSG *v194; // rax
  DWORD v195; // edi
  __int64 v196; // rbx
  struct tagLOG_PARTIAL_MSG *v197; // rax
  DWORD v198; // edi
  __int64 v199; // rbx
  struct tagLOG_PARTIAL_MSG *v200; // rax
  __int64 v201; // rax
  unsigned int (__fastcall ***v202)(_QWORD); // rcx
  __int64 v203; // rax
  __int64 v204; // rsi
  __int64 v205; // r13
  void *v206; // rax
  void *v207; // rbx
  unsigned int v208; // edi
  __int64 v209; // r12
  __int64 v210; // r15
  UnBCL::String *v211; // rax
  const unsigned __int16 *v212; // rax
  __int64 *v213; // rbp
  __int64 *v214; // rdx
  __int64 v215; // [rsp+0h] [rbp-278h] BYREF
  void **v216; // [rsp+70h] [rbp-208h] BYREF
  CCopyFilesAndFolders *v217; // [rsp+78h] [rbp-200h]
  int v218; // [rsp+80h] [rbp-1F8h]
  void **v219; // [rsp+88h] [rbp-1F0h] BYREF
  CCopyFilesAndFolders *v220; // [rsp+90h] [rbp-1E8h]
  unsigned __int64 v221; // [rsp+98h] [rbp-1E0h]
  unsigned __int64 v222; // [rsp+A0h] [rbp-1D8h]
  _QWORD v223[2]; // [rsp+A8h] [rbp-1D0h] BYREF
  _BYTE v224[24]; // [rsp+B8h] [rbp-1C0h] BYREF
  _BYTE v225[16]; // [rsp+D0h] [rbp-1A8h] BYREF
  _BYTE v226[16]; // [rsp+E0h] [rbp-198h] BYREF
  _BYTE v227[16]; // [rsp+F0h] [rbp-188h] BYREF
  _BYTE v228[16]; // [rsp+100h] [rbp-178h] BYREF
  _BYTE v229[16]; // [rsp+110h] [rbp-168h] BYREF
  _BYTE v230[16]; // [rsp+120h] [rbp-158h] BYREF
  _BYTE v231[16]; // [rsp+130h] [rbp-148h] BYREF
  _BYTE v232[16]; // [rsp+140h] [rbp-138h] BYREF
  _BYTE v233[24]; // [rsp+150h] [rbp-128h] BYREF
  _BYTE v234[24]; // [rsp+168h] [rbp-110h] BYREF
  _BYTE v235[24]; // [rsp+180h] [rbp-F8h] BYREF
  _BYTE v236[16]; // [rsp+198h] [rbp-E0h] BYREF
  _QWORD *pExceptionObject; // [rsp+1A8h] [rbp-D0h] BYREF
  _QWORD *v238; // [rsp+1B0h] [rbp-C8h] BYREF
  _QWORD *v239; // [rsp+1B8h] [rbp-C0h] BYREF
  _QWORD *v240; // [rsp+1C0h] [rbp-B8h] BYREF
  _QWORD *v241; // [rsp+1C8h] [rbp-B0h] BYREF
  _BYTE v242[16]; // [rsp+1D0h] [rbp-A8h] BYREF
  _BYTE v243[24]; // [rsp+1E0h] [rbp-98h] BYREF
  _QWORD v244[16]; // [rsp+1F8h] [rbp-80h] BYREF
  unsigned int v246; // [rsp+288h] [rbp+10h]

  v244[7] = -2;
  v13 = a1;
  LODWORD(v223[0]) = 0;
  if ( !a2 )
    return 2147942487LL;
  if ( a3 )
  {
    if ( !a4 )
      return 2147942487LL;
  }
  else if ( a4 )
  {
    return 2147942487LL;
  }
  if ( a5 )
  {
    if ( !a6 )
      return 2147942487LL;
  }
  else if ( a6 )
  {
    return 2147942487LL;
  }
  LastError = GetLastError();
  v16 = CurrentIP();
  v17 = ConstructPartialMsgW(0x4000000u, "QueueAddAppPackage called with [%s]", a2);
  WdsSetupLogMessageW(
    v17,
    819200,
    L"D",
    0,
    13343,
    L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
    L"CNewSystem::QueueAddAppPackage",
    v16,
    LastError,
    0,
    0);
  v18 = *(_DWORD *)(v13 - 140);
  if ( v18 > 1 && v18 != 6 )
  {
    v19 = GetLastError();
    v20 = CurrentIP();
    v21 = ConstructPartialMsgW(
            0x3000000u,
            "%hs: System state does not allow for more requests to be queued. Current state is %d",
            "CNewSystem::QueueAddAppPackage",
            *(_DWORD *)(v13 - 140));
    WdsSetupLogMessageW(
      v21,
      819200,
      L"D",
      0,
      13351,
      L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
      L"CNewSystem::QueueAddAppPackage",
      v20,
      v19,
      0,
      0);
    return 2147946720LL;
  }
  if ( (*(_BYTE *)(v13 + 172) & 2) != 0 && (*(_BYTE *)(*(_QWORD *)(v13 - 536) + 56LL) & 2) != 0 )
  {
    CDeploymentBase::ExitReadOnlyMode((CDeploymentBase *)(v13 - 600));
    EnterCriticalSection((LPCRITICAL_SECTION)(v13 - 584));
    v218 = 0;
    UnBCL::Exception::Exception((UnBCL::Exception *)v244);
    v244[0] = &`CNewSystem::QueueAddAppPackage'::`12'::CXXXXXHandledException::`vftable';
    try
    {
      try
      {
        v22 = *(_DWORD *)(v13 - 140);
        if ( v22 > 1 && v22 != 6 )
          goto LABEL_137;
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v226);
        UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v228);
        UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v227);
        v23 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v224, (const unsigned __int16 *)a2);
        ParentPath = UnBCL::Path::GetParentPath(v23);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v242, ParentPath);
        UnBCL::String::~String((UnBCL::String *)v224);
        if ( GetFileAttributesW((LPCWSTR)a2) == -1 )
        {
          v185 = GetLastError();
          v186 = v185 < 0;
          if ( v185 > 0 )
            v186 = 1;
          if ( v186 )
          {
            v187 = GetLastError();
            v188 = v187;
            if ( v187 > 0 )
              v188 = (unsigned __int16)v187 | 0x80070000;
          }
          else
          {
            v188 = -2147467259;
          }
          v189 = GetLastError();
          v190 = CurrentIP();
          v191 = ConstructPartialMsgW(0x2000000u, "Failure while validating app path [%s]. Error: 0x%08X", a2, v188);
          WdsSetupLogMessageW(
            v191,
            819200,
            L"D",
            0,
            13388,
            L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
            L"CNewSystem::QueueAddAppPackage",
            v190,
            v189,
            0,
            0);
          v218 = 1;
          pExceptionObject = v244;
          throw (`CNewSystem::QueueAddAppPackage(ushort const *,ushort const * * const,uint,ushort const * * const,uint,ushort const *,int,uint,int,unsigned __int64,SetupPlatform::SP_ERROR_HANDLING)'::`12'::CXXXXXHandledException **)&pExceptionObject;
        }
        v25 = SPGetGuidString();
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v236, v25);
        if ( a10 )
        {
          v26 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v242);
          CString = UnBCL::String::get_CString(v26);
        }
        else
        {
          CString = (const WCHAR *)a2;
        }
        v221 = SPGetFileSize(CString);
        FileAttributesW = GetFileAttributesW((LPCWSTR)a2);
        v29 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v233, (const unsigned __int16 *)a2);
        v30 = 1;
        LODWORD(v223[0]) = 1;
        P = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v13 - 448);
        v34 = 0;
        if ( !SPArePathsOnSameVolume(P, v29) )
        {
          if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(v13 - 384)
            || (v32 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v224, (const unsigned __int16 *)a2),
                v30 = 3,
                LODWORD(v223[0]) = 3,
                v33 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v13 - 384),
                !SPArePathsOnSameVolume(v33, v32)) )
          {
            v34 = 1;
          }
        }
        v35 = FileAttributesW & 0x10;
        if ( (v30 & 2) != 0 )
        {
          v30 &= ~2u;
          UnBCL::String::~String((UnBCL::String *)v224);
        }
        if ( (v30 & 1) != 0 )
        {
          v30 &= ~1u;
          UnBCL::String::~String((UnBCL::String *)v233);
        }
        if ( v34 )
        {
          if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v13 - 384) )
          {
            v36 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v224, L"Payload\\App");
            v37 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v13 - 384);
            v38 = UnBCL::Path::Combine(v37, v36);
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v219, v38);
            UnBCL::SmartPtr<UnBCL::String>::operator=(v226, &v219);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v219);
            UnBCL::String::~String((UnBCL::String *)v224);
            v39 = 0;
          }
          else
          {
            v40 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v224, L"Payload\\App");
            v41 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v13 - 448);
            v42 = UnBCL::Path::Combine(v41, v40);
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v219, v42);
            UnBCL::SmartPtr<UnBCL::String>::operator=(v226, &v219);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v219);
            UnBCL::String::~String((UnBCL::String *)v224);
            v39 = v221;
          }
          v43 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v236);
          v44 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v226);
          v45 = UnBCL::Path::Combine(v44, v43);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v219, v45);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v226, &v219);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v219);
          v46 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v224, (const unsigned __int16 *)a2);
          FileName = UnBCL::Path::GetFileName(v46);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v225, FileName);
          UnBCL::String::~String((UnBCL::String *)v224);
          v48 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v225);
          v49 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v226);
          v50 = UnBCL::Path::Combine(v49, v48);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v219, v50);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v226, &v219);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v219);
          v51 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v226);
          v52 = UnBCL::String::get_CString(v51);
          v53 = UnBCL::String::Format(L"Copy appx package payload from %s to %s", a2, v52);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v223, v53);
          v54 = UnBCL::Object::operator new(0x118u);
          v55 = v54;
          v222 = (unsigned __int64)v54;
          if ( v54 )
          {
            v56 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v223);
            v57 = UnBCL::String::get_CString(v56);
            v54 = (void *)CCopyFilesAndFolders::CCopyFilesAndFolders(v55, v39, v57, a12 == 1, 0, 12, 11);
          }
          UnBCL::SmartPtr<CCopyFilesAndFolders>::SmartPtr<CCopyFilesAndFolders>(&v216, v54);
          if ( v35 )
          {
            v58 = v217;
            v59 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v226);
            v60 = UnBCL::String::get_CString(v59);
            v61 = CCopyFilesAndFolders::AddFolderCopy(v58, (const unsigned __int16 *)a2, v60, 0, 0, 0, 0x32u);
          }
          else if ( a10 )
          {
            v62 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v226);
            v63 = UnBCL::Path::GetParentPath(v62);
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v219, v63);
            v64 = v217;
            v65 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v219);
            v66 = UnBCL::String::get_CString(v65);
            v67 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v242);
            v68 = UnBCL::String::get_CString(v67);
            v61 = CCopyFilesAndFolders::AddFolderCopy(v64, v68, v66, 0, 0, 0, 0x32u);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v219);
          }
          else
          {
            v69 = v217;
            v70 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v226);
            v71 = UnBCL::String::get_CString(v70);
            v61 = CCopyFilesAndFolders::AddFileCopy(v69, (const unsigned __int16 *)a2, v71, 0, 0, 0, 0, 5u);
          }
          if ( v61 < 0 )
          {
            v192 = GetLastError();
            v193 = CurrentIP();
            v194 = ConstructPartialMsgW(
                     0x2000000u,
                     "Failure while requesting appx package payload copy. Error: 0x%08X",
                     v61);
            WdsSetupLogMessageW(
              v194,
              819200,
              L"D",
              0,
              13456,
              L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
              L"CNewSystem::QueueAddAppPackage",
              v193,
              v192,
              0,
              0);
            v218 = 1;
            v238 = v244;
            throw (`CNewSystem::QueueAddAppPackage(ushort const *,ushort const * * const,uint,ushort const * * const,uint,ushort const *,int,uint,int,unsigned __int64,SetupPlatform::SP_ERROR_HANDLING)'::`12'::CXXXXXHandledException **)&v238;
          }
          v13 = a1;
          v72 = *(_QWORD *)(a1 - 104) + *(int *)(*(_QWORD *)(*(_QWORD *)(a1 - 104) + 8LL) + 16LL);
          v73 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(v72 + 8) + 40LL);
          v74 = UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,CDriverInstallInfo *>>::Steal(&v216);
          v73(v72 + 8, v74);
          v216 = &UnBCL::SmartPtr<CCopyFilesAndFolders>::`vftable';
          UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v216);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v223);
        }
        else
        {
          v75 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
          v76 = v75;
          v222 = (unsigned __int64)v75;
          if ( v75 )
          {
            UnBCL::String::String(v75, (const unsigned __int16 *)a2);
            *(_QWORD *)v76 = &UnBCL::String::`local vftable';
          }
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v225, v76);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v226, v225);
        }
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v225);
        v77 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupImproveLowDiskSpace>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SetupImproveLowDiskSpace>::GetImpl'::`2'::impl) == 0;
        v222 = a11;
        if ( v77 )
        {
          if ( !a11 )
          {
            v77 = v35 == 0;
            goto LABEL_51;
          }
        }
        else if ( !a11 )
        {
          if ( v35 )
            goto LABEL_55;
          v77 = a10 == 0;
LABEL_51:
          if ( v77 )
          {
            v78 = 10 * v221;
LABEL_56:
            v222 = v78;
            goto LABEL_57;
          }
LABEL_55:
          v78 = v221;
          goto LABEL_56;
        }
LABEL_57:
        v79 = a3;
        if ( a3 )
        {
          v80 = UnBCL::Object::operator new(0xB0u);
          v81 = v80;
          v223[0] = v80;
          if ( v80 )
          {
            UnBCL::ArrayList<UnBCL::String *>::ArrayList<UnBCL::String *>(v80, 1);
            v81[6] = UnBCL::ArrayList<UnBCL::String *>::`local vftable'{for `UnBCL::Object'};
            v79 = a3;
          }
          UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v225, v81);
          UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator=(v228, v225);
          UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v225);
          v82 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v228);
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v82 + 40LL))(v82, 1);
          v83 = 0;
          while ( (unsigned int)v83 < a4 )
          {
            v84 = *(const WCHAR **)(v79 + 8 * v83);
            v85 = GetFileAttributesW(v84);
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v216);
            v86 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v234, v84);
            v30 |= 4u;
            LODWORD(v223[0]) = v30;
            v87 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v13 - 448);
            v90 = 0;
            if ( !SPArePathsOnSameVolume(v87, v86) )
            {
              if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(v13 - 384)
                || (v88 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v243, v84),
                    v30 |= 8u,
                    LODWORD(v223[0]) = v30,
                    v89 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v13 - 384),
                    !SPArePathsOnSameVolume(v89, v88)) )
              {
                v90 = 1;
              }
            }
            if ( (v30 & 8) != 0 )
            {
              v30 &= ~8u;
              UnBCL::String::~String((UnBCL::String *)v243);
            }
            if ( (v30 & 4) != 0 )
            {
              v30 &= ~4u;
              UnBCL::String::~String((UnBCL::String *)v234);
            }
            if ( v90 )
            {
              if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v13 - 384) )
              {
                v91 = (const struct UnBCL::String *)UnBCL::String::String(
                                                      (UnBCL::String *)v235,
                                                      L"Payload\\App\\DependencyPackages");
                v92 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v13 - 384);
                v93 = UnBCL::Path::Combine(v92, v91);
                UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v225, v93);
                UnBCL::SmartPtr<UnBCL::String>::operator=(&v216, v225);
                UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v225);
                UnBCL::String::~String((UnBCL::String *)v235);
                v94 = 0;
              }
              else
              {
                v95 = (const struct UnBCL::String *)UnBCL::String::String(
                                                      (UnBCL::String *)v234,
                                                      L"Payload\\App\\DependencyPackages");
                v96 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v13 - 448);
                v97 = UnBCL::Path::Combine(v96, v95);
                UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v229, v97);
                UnBCL::SmartPtr<UnBCL::String>::operator=(&v216, v229);
                UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v229);
                UnBCL::String::~String((UnBCL::String *)v234);
                v94 = SPGetFileSize(v84);
              }
              v98 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v236);
              v99 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(&v216);
              v100 = UnBCL::Path::Combine(v99, v98);
              UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v230, v100);
              UnBCL::SmartPtr<UnBCL::String>::operator=(&v216, v230);
              UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v230);
              v101 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v234, v84);
              v102 = UnBCL::Path::GetFileName(v101);
              UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v233, v102);
              UnBCL::String::~String((UnBCL::String *)v234);
              v103 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v233);
              v104 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(&v216);
              v105 = UnBCL::Path::Combine(v104, v103);
              UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v231, v105);
              UnBCL::SmartPtr<UnBCL::String>::operator=(&v216, v231);
              UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v231);
              v106 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v216);
              v107 = UnBCL::String::get_CString(v106);
              v108 = UnBCL::String::Format(L"Copy appx dependency package from %s to %s", v84, v107);
              UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v232, v108);
              v109 = UnBCL::Object::operator new(0x118u);
              v110 = v109;
              v223[0] = v109;
              if ( v109 )
              {
                v111 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v232);
                v112 = UnBCL::String::get_CString(v111);
                v109 = (void *)CCopyFilesAndFolders::CCopyFilesAndFolders(v110, v94, v112, a12 == 1, 0, 10, 9);
              }
              UnBCL::SmartPtr<CCopyFilesAndFolders>::SmartPtr<CCopyFilesAndFolders>(&v219, v109);
              v113 = v220;
              v114 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v216);
              v115 = UnBCL::String::get_CString(v114);
              if ( (v85 & 0x10) != 0 )
                v116 = CCopyFilesAndFolders::AddFolderCopy(v113, v84, v115, 0, 0, 0, 0x32u);
              else
                v116 = CCopyFilesAndFolders::AddFileCopy(v113, v84, v115, 0, 0, 0, 0, 5u);
              if ( v116 < 0 )
              {
                v195 = GetLastError();
                v196 = CurrentIP();
                v197 = ConstructPartialMsgW(
                         0x2000000u,
                         "Failure while requesting appx dependency package payload copy. Error: 0x%08X",
                         v116);
                WdsSetupLogMessageW(
                  v197,
                  819200,
                  L"D",
                  0,
                  13530,
                  L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
                  L"CNewSystem::QueueAddAppPackage",
                  v196,
                  v195,
                  0,
                  0);
                v218 = 1;
                v239 = v244;
                throw (`CNewSystem::QueueAddAppPackage(ushort const *,ushort const * * const,uint,ushort const * * const,uint,ushort const *,int,uint,int,unsigned __int64,SetupPlatform::SP_ERROR_HANDLING)'::`12'::CXXXXXHandledException **)&v239;
              }
              v13 = a1;
              v117 = *(_QWORD *)(a1 - 104) + *(int *)(*(_QWORD *)(*(_QWORD *)(a1 - 104) + 8LL) + 16LL);
              v118 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(v117 + 8) + 40LL);
              v119 = UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,CDriverInstallInfo *>>::Steal(&v219);
              v118(v117 + 8, v119);
              v219 = &UnBCL::SmartPtr<CCopyFilesAndFolders>::`vftable';
              UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v219);
              UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v232);
              v120 = v233;
            }
            else
            {
              v121 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
              v122 = v121;
              v223[0] = v121;
              if ( v121 )
              {
                UnBCL::String::String(v121, v84);
                *(_QWORD *)v122 = &UnBCL::String::`local vftable';
              }
              UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v224, v122);
              UnBCL::SmartPtr<UnBCL::String>::operator=(&v216, v224);
              v120 = v224;
            }
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v120);
            v123 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v228);
            v124 = v123 + *(int *)(*(_QWORD *)(v123 + 8) + 16LL);
            v125 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(v124 + 8) + 40LL);
            v126 = UnBCL::SmartPtr<UnBCL::String>::Steal(&v216);
            v125(v124 + 8, v126);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v216);
            v83 = (unsigned int)(v83 + 1);
            v79 = a3;
          }
          v127 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v228);
          v128 = (unsigned int (__fastcall ***)(_QWORD))(v127 + 8 + *(int *)(*(_QWORD *)(v127 + 8) + 12LL));
          if ( !(**v128)(v128) )
          {
            UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v224, 0);
            UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator=(v228, v224);
            UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v224);
          }
        }
        v129 = a5;
        if ( a5 )
        {
          v130 = UnBCL::Object::operator new(0xB0u);
          v131 = v130;
          v223[0] = v130;
          if ( v130 )
          {
            UnBCL::ArrayList<UnBCL::String *>::ArrayList<UnBCL::String *>(v130, 1);
            v131[6] = UnBCL::ArrayList<UnBCL::String *>::`local vftable'{for `UnBCL::Object'};
          }
          UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v224, v131);
          UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator=(v227, v224);
          UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v224);
          v132 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v227);
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v132 + 40LL))(v132, 1);
          v133 = 0;
          while ( (unsigned int)v133 < a6 )
          {
            v134 = *(const unsigned __int16 **)(v129 + 8 * v133);
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v216);
            v135 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v234, v134);
            v30 |= 0x10u;
            LODWORD(v223[0]) = v30;
            v136 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v13 - 448);
            v139 = 0;
            if ( !SPArePathsOnSameVolume(v136, v135) )
            {
              if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(v13 - 384)
                || (v137 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v235, v134),
                    v30 |= 0x20u,
                    LODWORD(v223[0]) = v30,
                    v138 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v13 - 384),
                    !SPArePathsOnSameVolume(v138, v137)) )
              {
                v139 = 1;
              }
            }
            if ( (v30 & 0x20) != 0 )
            {
              v30 &= ~0x20u;
              UnBCL::String::~String((UnBCL::String *)v235);
            }
            if ( (v30 & 0x10) != 0 )
            {
              v30 &= ~0x10u;
              UnBCL::String::~String((UnBCL::String *)v234);
            }
            if ( v139 )
            {
              if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v13 - 384) )
              {
                v140 = (const struct UnBCL::String *)UnBCL::String::String(
                                                       (UnBCL::String *)v243,
                                                       L"Payload\\App\\Licenses");
                v141 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v13 - 384);
                v142 = UnBCL::Path::Combine(v141, v140);
                UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v224, v142);
                UnBCL::SmartPtr<UnBCL::String>::operator=(&v216, v224);
                UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v224);
                UnBCL::String::~String((UnBCL::String *)v243);
                v143 = 0;
              }
              else
              {
                v144 = (const struct UnBCL::String *)UnBCL::String::String(
                                                       (UnBCL::String *)v235,
                                                       L"Payload\\App\\Licenses");
                v145 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v13 - 448);
                v146 = UnBCL::Path::Combine(v145, v144);
                UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v233, v146);
                UnBCL::SmartPtr<UnBCL::String>::operator=(&v216, v233);
                UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v233);
                UnBCL::String::~String((UnBCL::String *)v235);
                v143 = SPGetFileSize(v134);
              }
              v147 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v236);
              v148 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(&v216);
              v149 = UnBCL::Path::Combine(v148, v147);
              UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v232, v149);
              UnBCL::SmartPtr<UnBCL::String>::operator=(&v216, v232);
              UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v232);
              v150 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v235, v134);
              v151 = UnBCL::Path::GetFileName(v150);
              UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v229, v151);
              UnBCL::String::~String((UnBCL::String *)v235);
              v152 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v229);
              v153 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(&v216);
              v154 = UnBCL::Path::Combine(v153, v152);
              UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v231, v154);
              UnBCL::SmartPtr<UnBCL::String>::operator=(&v216, v231);
              UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v231);
              v155 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v216);
              v156 = UnBCL::String::get_CString(v155);
              v157 = UnBCL::String::Format(L"Copy appx license from %s to %s", v134, v156);
              UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v230, v157);
              v158 = UnBCL::Object::operator new(0x118u);
              v159 = v158;
              v223[0] = v158;
              if ( v158 )
              {
                v160 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v230);
                v161 = UnBCL::String::get_CString(v160);
                v158 = (void *)CCopyFilesAndFolders::CCopyFilesAndFolders(v159, v143, v161, a12 == 1, 0, 10, 9);
              }
              UnBCL::SmartPtr<CCopyFilesAndFolders>::SmartPtr<CCopyFilesAndFolders>(&v219, v158);
              v162 = v220;
              v163 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v216);
              v164 = UnBCL::String::get_CString(v163);
              v165 = CCopyFilesAndFolders::AddFileCopy(v162, v134, v164, 0, 0, 0, 0, 5u);
              if ( v165 < 0 )
              {
                v198 = GetLastError();
                v199 = CurrentIP();
                v200 = ConstructPartialMsgW(
                         0x2000000u,
                         "Failure while requesting appx license payload copy. Error: 0x%08X",
                         v165);
                WdsSetupLogMessageW(
                  v200,
                  819200,
                  L"D",
                  0,
                  13596,
                  L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
                  L"CNewSystem::QueueAddAppPackage",
                  v199,
                  v198,
                  0,
                  0);
                v218 = 1;
                v240 = v244;
                throw (`CNewSystem::QueueAddAppPackage(ushort const *,ushort const * * const,uint,ushort const * * const,uint,ushort const *,int,uint,int,unsigned __int64,SetupPlatform::SP_ERROR_HANDLING)'::`12'::CXXXXXHandledException **)&v240;
              }
              v13 = a1;
              v166 = *(_QWORD *)(a1 - 104) + *(int *)(*(_QWORD *)(*(_QWORD *)(a1 - 104) + 8LL) + 16LL);
              v167 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(v166 + 8) + 40LL);
              v168 = UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,CDriverInstallInfo *>>::Steal(&v219);
              v167(v166 + 8, v168);
              v219 = &UnBCL::SmartPtr<CCopyFilesAndFolders>::`vftable';
              UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v219);
              UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v230);
              v169 = v229;
            }
            else
            {
              v170 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
              v171 = v170;
              v223[0] = v170;
              if ( v170 )
              {
                UnBCL::String::String(v170, v134);
                *(_QWORD *)v171 = &UnBCL::String::`local vftable';
              }
              UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v225, v171);
              UnBCL::SmartPtr<UnBCL::String>::operator=(&v216, v225);
              v169 = v225;
            }
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v169);
            v172 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v227);
            v173 = v172 + *(int *)(*(_QWORD *)(v172 + 8) + 16LL);
            v174 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(v173 + 8) + 40LL);
            v175 = UnBCL::SmartPtr<UnBCL::String>::Steal(&v216);
            v174(v173 + 8, v175);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v216);
            v133 = (unsigned int)(v133 + 1);
            v129 = a5;
          }
          v201 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v227);
          v202 = (unsigned int (__fastcall ***)(_QWORD))(v201 + 8 + *(int *)(*(_QWORD *)(v201 + 8) + 12LL));
          if ( !(**v202)(v202) )
          {
            UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v224, 0);
            UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator=(v227, v224);
            UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v224);
          }
        }
        v203 = RAII::CAutoCleanupBase<void *>::operator->(v13 - 112);
        v204 = v203 + *(int *)(*(_QWORD *)(v203 + 8) + 16LL);
        v205 = *(_QWORD *)(v204 + 8);
        v206 = UnBCL::Object::operator new(0x160u);
        v207 = v206;
        v223[0] = v206;
        if ( v206 )
        {
          v208 = 10 * SPCalculateWeight(v221);
          v221 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::get_P(v227);
          v209 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::get_P(v228);
          v210 = UnBCL::SmartPtr<UnBCL::String>::get_P(v226);
          v211 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(a1 + 48);
          v212 = UnBCL::String::get_CString(v211);
          v206 = (void *)CAddAppPackage::CAddAppPackage(v207, v212, v210, v209, v221, a7, a8, a9, a12 == 1, v222, v208);
        }
        (*(void (__fastcall **)(__int64, void *))(v205 + 40))(v204 + 8, v206);
        if ( *(_DWORD *)(a1 - 140) )
          *(_DWORD *)(a1 - 140) = 1;
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v236);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v242);
        UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v227);
        UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v228);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v226);
      }
      catch ( ___R0PEAVCXXXXXTemp__N___QueueAddAppPackage_CNewSystem__UEAAJPEBGQEAPEBGI1I0HIH_KW4SP_ERROR_HANDLING_SetupPlatform___Z__8 )
      {
        CNewSystem::QueueAddAppPackage_::_1_::catch_68();
        __eh34_caught_type(
          1,
          ___R0PEAVCXXXXXTemp__N___QueueAddAppPackage_CNewSystem__UEAAJPEBGQEAPEBGI1I0HIH_KW4SP_ERROR_HANDLING_SetupPlatform___Z__8);
      }
LABEL_137:
      v218 = 1;
      v241 = v244;
      throw (`CNewSystem::QueueAddAppPackage(ushort const *,ushort const * * const,uint,ushort const * * const,uint,ushort const *,int,uint,int,unsigned __int64,SetupPlatform::SP_ERROR_HANDLING)'::`12'::CXXXXXHandledException **)&v241;
    }
    catch ( UnBCL::Exception * )
    {
      v214 = &v215;
      v213 = v214;
      LeaveCriticalSection((LPCRITICAL_SECTION)(v214[80] - 584));
      if ( !*((_DWORD *)v213 + 32) )
        throw;
      UnBCL::Exception::~Exception((UnBCL::Exception *)v244);
      return v246;
    }
  }
  v176 = GetLastError();
  v177 = CurrentIP();
  v178 = ConstructPartialMsgW(
           0x3000000u,
           "%hs: Capabilities not met, request is not supported",
           "CNewSystem::QueueAddAppPackage");
  WdsSetupLogMessageW(
    v178,
    819200,
    L"D",
    0,
    13359,
    L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
    L"CNewSystem::QueueAddAppPackage",
    v177,
    v176,
    0,
    0);
  v179 = GetLastError();
  v180 = CurrentIP();
  v181 = ConstructPartialMsgW(
           0x4000000u,
           "CAPABILITIES: DL Platform capabilities: 0x%08X",
           *(_DWORD *)(*(_QWORD *)(v13 - 536) + 56LL));
  WdsSetupLogMessageW(
    v181,
    819200,
    L"D",
    0,
    13360,
    L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
    L"CNewSystem::QueueAddAppPackage",
    v180,
    v179,
    0,
    0);
  v182 = GetLastError();
  v183 = CurrentIP();
  v184 = ConstructPartialMsgW(0x4000000u, "CAPABILITIES: Image capabilities: 0x%08X", *(_DWORD *)(v13 + 172));
  WdsSetupLogMessageW(
    v184,
    819200,
    L"D",
    0,
    13361,
    L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
    L"CNewSystem::QueueAddAppPackage",
    v183,
    v182,
    0,
    0);
  return 2147942450LL;
}

```

## disassembly

```asm
0x1800dd850  mov     r11, rsp
0x1800dd853  mov     [r11+20h], r9d
0x1800dd857  mov     [r11+18h], r8
0x1800dd85b  mov     [r11+8], rcx
0x1800dd85f  push    rbx
0x1800dd860  push    rsi
0x1800dd861  push    rdi
0x1800dd862  push    r12
0x1800dd864  push    r13
0x1800dd866  push    r14
0x1800dd868  push    r15
0x1800dd86a  sub     rsp, 240h
0x1800dd871  mov     qword ptr [r11-48h], 0FFFFFFFFFFFFFFFEh
0x1800dd879  mov     eax, r9d
0x1800dd87c  mov     r14, rdx
0x1800dd87f  mov     rsi, rcx
0x1800dd882  xor     r15d, r15d
0x1800dd885  mov     [r11-1D0h], r15d
0x1800dd88c  test    rdx, rdx
0x1800dd88f  jz      short loc_1800DD89A
0x1800dd891  test    r8, r8
0x1800dd894  jz      short loc_1800DD8B2
0x1800dd896  test    eax, eax
0x1800dd898  jnz     short loc_1800DD8B6
0x1800dd89a  mov     eax, 80070057h
0x1800dd89f  add     rsp, 240h
0x1800dd8a6  pop     r15
0x1800dd8a8  pop     r14
0x1800dd8aa  pop     r13
0x1800dd8ac  pop     r12
0x1800dd8ae  pop     rdi
0x1800dd8af  pop     rsi
0x1800dd8b0  pop     rbx
0x1800dd8b1  retn
0x1800dd8b2  test    eax, eax
0x1800dd8b4  jnz     short loc_1800DD89A
0x1800dd8b6  cmp     [rsp+278h+arg_20], r15
0x1800dd8be  jz      short loc_1800DD8CC
0x1800dd8c0  cmp     [rsp+278h+arg_28], r15d
0x1800dd8c8  jz      short loc_1800DD89A
0x1800dd8ca  jmp     short loc_1800DD8D6
0x1800dd8cc  cmp     [rsp+278h+arg_28], r15d
0x1800dd8d4  jnz     short loc_1800DD89A
0x1800dd8d6  call    cs:__imp_GetLastError
0x1800dd8dc  mov     edi, eax
0x1800dd8de  call    cs:__imp_CurrentIP
0x1800dd8e4  mov     rbx, rax
0x1800dd8e7  mov     r8, r14
0x1800dd8ea  lea     rdx, aQueueaddapppac; "QueueAddAppPackage called with [%s]"
0x1800dd8f1  mov     r12d, 4000000h
0x1800dd8f7  mov     ecx, r12d; unsigned int
0x1800dd8fa  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800dd8ff  mov     [rsp+278h+var_228], r15d
0x1800dd904  mov     [rsp+278h+var_230], r15
0x1800dd909  mov     [rsp+278h+var_238], edi
0x1800dd90d  mov     qword ptr [rsp+278h+var_240], rbx
0x1800dd912  lea     rcx, aCnewsystemQueu_24; "CNewSystem::QueueAddAppPackage"
0x1800dd919  mov     qword ptr [rsp+278h+var_248], rcx
0x1800dd91e  lea     rcx, aBaseNtsetupSet_34; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1800dd925  mov     qword ptr [rsp+278h+var_250], rcx
0x1800dd92a  mov     [rsp+278h+var_258], 341Fh
0x1800dd932  xor     r9d, r9d
0x1800dd935  lea     r13, aD_0; "D"
0x1800dd93c  mov     r8, r13
0x1800dd93f  mov     edx, 0C8000h
0x1800dd944  mov     rcx, rax
0x1800dd947  call    cs:__imp_WdsSetupLogMessageW
0x1800dd94d  mov     eax, [rsi-8Ch]
0x1800dd953  cmp     eax, 1
0x1800dd956  jbe     loc_1800DD9E6
0x1800dd95c  cmp     eax, 6
0x1800dd95f  jz      loc_1800DD9E6
0x1800dd965  call    cs:__imp_GetLastError
0x1800dd96b  mov     edi, eax
0x1800dd96d  call    cs:__imp_CurrentIP
0x1800dd973  mov     rbx, rax
0x1800dd976  mov     r9d, [rsi-8Ch]
0x1800dd97d  lea     r8, aCnewsystemQueu_47; "CNewSystem::QueueAddAppPackage"
0x1800dd984  lea     rdx, aHsSystemStateD_1; "%hs: System state does not allow for mo"...
0x1800dd98b  mov     ecx, 3000000h; unsigned int
0x1800dd990  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800dd995  mov     [rsp+278h+var_228], r15d
0x1800dd99a  mov     [rsp+278h+var_230], r15
0x1800dd99f  mov     [rsp+278h+var_238], edi
0x1800dd9a3  mov     qword ptr [rsp+278h+var_240], rbx
0x1800dd9a8  lea     r14, aCnewsystemQueu_24; "CNewSystem::QueueAddAppPackage"
0x1800dd9af  mov     qword ptr [rsp+278h+var_248], r14
0x1800dd9b4  lea     rcx, aBaseNtsetupSet_34; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1800dd9bb  mov     qword ptr [rsp+278h+var_250], rcx
0x1800dd9c0  mov     [rsp+278h+var_258], 3427h
0x1800dd9c8  xor     r9d, r9d
0x1800dd9cb  mov     r8, r13
0x1800dd9ce  mov     edx, 0C8000h
0x1800dd9d3  mov     rcx, rax
0x1800dd9d6  call    cs:__imp_WdsSetupLogMessageW
0x1800dd9dc  mov     eax, 800710E0h
0x1800dd9e1  jmp     loc_1800DD89F
0x1800dd9e6  test    byte ptr [rsi+0ACh], 2
0x1800dd9ed  jz      loc_1800DED6D
0x1800dd9f3  mov     [rsp+278h+arg_8], 8007000Dh
0x1800dd9fe  mov     rax, [rsi-218h]
0x1800dda05  test    byte ptr [rax+38h], 2
0x1800dda09  jz      loc_1800DED6D
0x1800dda0f  lea     rcx, [rsi-258h]; this
0x1800dda16  call    ?ExitReadOnlyMode@CDeploymentBase@@QEAAXXZ; CDeploymentBase::ExitReadOnlyMode(void)
0x1800dda1b  lea     rcx, [rsi-248h]; lpCriticalSection
0x1800dda22  call    cs:__imp_EnterCriticalSection
0x1800dda28  mov     [rsp+278h+var_1F8], r15d
0x1800dda30  lea     rcx, [rsp+278h+var_80]
0x1800dda38  call    cs:__imp_??0Exception@UnBCL@@QEAA@XZ; UnBCL::Exception::Exception(void)
0x1800dda3e  lea     rax, ??_7CXXXXXHandledException@?M@??QueueAddAppPackage@CNewSystem@@UEAAJPEBGQEAPEBGI1I0HIH_KW4SP_ERROR_HANDLING@SetupPlatform@@@Z@6B@; const `CNewSystem::QueueAddAppPackage(ushort const *,ushort const * * const,uint,ushort const * * const,uint,ushort const *,int,uint,int,unsigned __int64,SetupPlatform::SP_ERROR_HANDLING)'::`12'::CXXXXXHandledException::`vftable'
0x1800dda45  mov     [rsp+278h+var_80], rax
0x1800dda4d  mov     eax, [rsi-8Ch]
0x1800dda53  cmp     eax, 1
0x1800dda56  jbe     short loc_1800DDA61
0x1800dda58  cmp     eax, 6
0x1800dda5b  jnz     loc_1800DF36C
0x1800dda61  lea     rcx, [rsp+278h+var_198]
0x1800dda69  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x1800dda6f  nop
0x1800dda70  lea     rcx, [rsp+278h+var_178]
0x1800dda78  call    cs:__imp_??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(void)
0x1800dda7e  nop
0x1800dda7f  lea     rcx, [rsp+278h+var_188]
0x1800dda87  call    cs:__imp_??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(void)
0x1800dda8d  nop
0x1800dda8e  mov     rdx, r14
0x1800dda91  lea     rcx, [rsp+278h+var_1C0]
0x1800dda99  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800dda9f  nop
0x1800ddaa0  mov     rcx, rax
0x1800ddaa3  call    cs:__imp_?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetParentPath(UnBCL::String const *)
0x1800ddaa9  mov     rdx, rax
0x1800ddaac  lea     rcx, [rsp+278h+var_A8]
0x1800ddab4  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800ddaba  nop
0x1800ddabb  lea     rcx, [rsp+278h+var_1C0]
0x1800ddac3  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800ddac9  mov     rcx, r14; lpFileName
0x1800ddacc  call    cs:__imp_GetFileAttributesW
0x1800ddad2  cmp     eax, 0FFFFFFFFh
0x1800ddad5  jz      loc_1800DEEB9
0x1800ddadb  call    ?SPGetGuidString@@YAPEAVString@UnBCL@@XZ; SPGetGuidString(void)
0x1800ddae0  mov     rdx, rax
0x1800ddae3  lea     rcx, [rsp+278h+var_E0]
0x1800ddaeb  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800ddaf1  nop
0x1800ddaf2  mov     r12d, [rsp+278h+arg_48]
0x1800ddafa  test    r12d, r12d
0x1800ddafd  jz      short loc_1800DDB18
0x1800ddaff  lea     rcx, [rsp+278h+var_A8]
0x1800ddb07  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1800ddb0d  mov     rcx, rax
0x1800ddb10  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1800ddb16  jmp     short loc_1800DDB1B
0x1800ddb18  mov     rax, r14
0x1800ddb1b  mov     rcx, rax; lpFileName
0x1800ddb1e  call    ?SPGetFileSize@@YA_KPEBG@Z; SPGetFileSize(ushort const *)
0x1800ddb23  mov     [rsp+278h+var_1E0], rax
0x1800ddb2b  mov     rcx, r14; lpFileName
0x1800ddb2e  call    cs:__imp_GetFileAttributesW
0x1800ddb34  mov     r15d, eax
0x1800ddb37  mov     rdx, r14
0x1800ddb3a  lea     rcx, [rsp+278h+var_128]
0x1800ddb42  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800ddb48  mov     rbx, rax
0x1800ddb4b  mov     r13d, 1
0x1800ddb51  mov     dword ptr [rsp+278h+var_1D0], r13d
0x1800ddb59  lea     rcx, [rsi-1C0h]
0x1800ddb60  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800ddb66  mov     rdx, rbx; struct UnBCL::String *
0x1800ddb69  mov     rcx, rax; struct UnBCL::String *
0x1800ddb6c  call    ?SPArePathsOnSameVolume@@YAHPEAVString@UnBCL@@0@Z; SPArePathsOnSameVolume(UnBCL::String *,UnBCL::String *)
0x1800ddb71  lea     rbx, [rsi-180h]
0x1800ddb78  test    eax, eax
0x1800ddb7a  jnz     short loc_1800DDBC9
0x1800ddb7c  mov     rcx, rbx
0x1800ddb7f  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800ddb85  test    rax, rax
0x1800ddb88  jz      short loc_1800DDBC4
0x1800ddb8a  mov     rdx, r14
0x1800ddb8d  lea     rcx, [rsp+278h+var_1C0]
0x1800ddb95  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800ddb9b  mov     rdi, rax
0x1800ddb9e  mov     r13d, 3
0x1800ddba4  mov     dword ptr [rsp+278h+var_1D0], r13d
0x1800ddbac  mov     rcx, rbx
0x1800ddbaf  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800ddbb5  mov     rdx, rdi; struct UnBCL::String *
0x1800ddbb8  mov     rcx, rax; struct UnBCL::String *
0x1800ddbbb  call    ?SPArePathsOnSameVolume@@YAHPEAVString@UnBCL@@0@Z; SPArePathsOnSameVolume(UnBCL::String *,UnBCL::String *)
0x1800ddbc0  test    eax, eax
0x1800ddbc2  jnz     short loc_1800DDBC9
0x1800ddbc4  mov     dil, 1
0x1800ddbc7  jmp     short loc_1800DDBCC
0x1800ddbc9  xor     dil, dil
0x1800ddbcc  and     r15d, 10h
0x1800ddbd0  test    r13b, 2
0x1800ddbd4  jz      short loc_1800DDBE9
0x1800ddbd6  and     r13d, 0FFFFFFFDh
0x1800ddbda  lea     rcx, [rsp+278h+var_1C0]
0x1800ddbe2  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800ddbe8  nop
0x1800ddbe9  test    r13b, 1
0x1800ddbed  jz      short loc_1800DDC01
0x1800ddbef  and     r13d, 0FFFFFFFEh
0x1800ddbf3  lea     rcx, [rsp+278h+var_128]
0x1800ddbfb  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800ddc01  test    dil, dil
0x1800ddc04  jz      loc_1800DE060
0x1800ddc0a  mov     rcx, rbx
0x1800ddc0d  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800ddc13  lea     rdx, aPayloadApp; "Payload\\App"
0x1800ddc1a  lea     rcx, [rsp+278h+var_1C0]
0x1800ddc22  test    rax, rax
0x1800ddc25  jz      short loc_1800DDC93
0x1800ddc27  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800ddc2d  mov     rbx, rax
0x1800ddc30  lea     rcx, [rsi-180h]
0x1800ddc37  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800ddc3d  mov     rdx, rbx
0x1800ddc40  mov     rcx, rax
0x1800ddc43  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1800ddc49  mov     rdx, rax
0x1800ddc4c  lea     rcx, [rsp+278h+var_1F0]
0x1800ddc54  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800ddc5a  nop
0x1800ddc5b  lea     rdx, [rsp+278h+var_1F0]
0x1800ddc63  lea     rcx, [rsp+278h+var_198]
0x1800ddc6b  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1800ddc71  nop
0x1800ddc72  lea     rcx, [rsp+278h+var_1F0]
0x1800ddc7a  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800ddc80  nop
0x1800ddc81  lea     rcx, [rsp+278h+var_1C0]
0x1800ddc89  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800ddc8f  xor     esi, esi
0x1800ddc91  jmp     short loc_1800DDD03
0x1800ddc93  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800ddc99  mov     rbx, rax
0x1800ddc9c  lea     rcx, [rsi-1C0h]
0x1800ddca3  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800ddca9  mov     rdx, rbx
0x1800ddcac  mov     rcx, rax
0x1800ddcaf  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1800ddcb5  mov     rdx, rax
0x1800ddcb8  lea     rcx, [rsp+278h+var_1F0]
0x1800ddcc0  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800ddcc6  nop
0x1800ddcc7  lea     rdx, [rsp+278h+var_1F0]
0x1800ddccf  lea     rcx, [rsp+278h+var_198]
0x1800ddcd7  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1800ddcdd  nop
0x1800ddcde  lea     rcx, [rsp+278h+var_1F0]
0x1800ddce6  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800ddcec  nop
0x1800ddced  lea     rcx, [rsp+278h+var_1C0]
0x1800ddcf5  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800ddcfb  mov     rsi, [rsp+278h+var_1E0]
0x1800ddd03  lea     rcx, [rsp+278h+var_E0]
0x1800ddd0b  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800ddd11  mov     rbx, rax
0x1800ddd14  lea     rcx, [rsp+278h+var_198]
0x1800ddd1c  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800ddd22  mov     rdx, rbx
0x1800ddd25  mov     rcx, rax
0x1800ddd28  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1800ddd2e  mov     rdx, rax
0x1800ddd31  lea     rcx, [rsp+278h+var_1F0]
0x1800ddd39  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800ddd3f  nop
0x1800ddd40  lea     rdx, [rsp+278h+var_1F0]
0x1800ddd48  lea     rcx, [rsp+278h+var_198]
0x1800ddd50  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1800ddd56  nop
0x1800ddd57  lea     rcx, [rsp+278h+var_1F0]
0x1800ddd5f  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800ddd65  mov     rdx, r14
0x1800ddd68  lea     rcx, [rsp+278h+var_1C0]
0x1800ddd70  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800ddd76  nop
0x1800ddd77  mov     rcx, rax
0x1800ddd7a  call    cs:__imp_?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFileName(UnBCL::String const *)
0x1800ddd80  mov     rdx, rax
0x1800ddd83  lea     rcx, [rsp+278h+var_1A8]
0x1800ddd8b  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800ddd91  nop
0x1800ddd92  lea     rcx, [rsp+278h+var_1C0]
0x1800ddd9a  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800ddda0  lea     rcx, [rsp+278h+var_1A8]
0x1800ddda8  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800dddae  mov     rbx, rax
0x1800dddb1  lea     rcx, [rsp+278h+var_198]
0x1800dddb9  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800dddbf  mov     rdx, rbx
0x1800dddc2  mov     rcx, rax
0x1800dddc5  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1800dddcb  mov     rdx, rax
0x1800dddce  lea     rcx, [rsp+278h+var_1F0]
0x1800dddd6  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
  ... truncated ...
```
