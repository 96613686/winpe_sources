# CNewSystem::QueueAddCbsPackage(int,CCbsPackageList<UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *> *,int,SetupPlatform::SP_ERROR_HANDLING,ulong,OP_OPERATION_ID)

- ea: `0x1800df3a4`
- end: `0x1800e051e`
- name: `?QueueAddCbsPackage@CNewSystem@@IEAAJHPEAV?$CCbsPackageList@PEAV?$DictionaryEntry@PEAVString@UnBCL@@_K@UnBCL@@@@HW4SP_ERROR_HANDLING@SetupPlatform@@KW4OP_OPERATION_ID@@@Z`
- size: `4474`
- prototype: `__int64 __usercall@<rax>(CDeploymentBase *this@<rcx>, int, int, int)`
- caller_count: `2`
- callee_count: `23`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800e06b0`
- `0x18018f630`

## callees

- `0x18001413d`
- `0x180044810`
- `0x180057dec`
- `0x18005dd24`
- `0x1800ad6f0`
- `0x1800ae214`
- `0x1800ae380`
- `0x1800b3720`
- `0x1800c6158`
- `0x1800df3a4`
- `0x18010f584`
- `0x180157328`
- `0x18015835c`
- `0x18015fd04`
- `0x18015fe94`
- `0x1801bc5e4`
- `0x1802c6944`
- `0x1802cd658`
- `0x1802d6738`
- `0x1802d6bb0`
- `0x18034f808`
- `0x1804bbf62`
- `0x180509010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800df413`
- `KERNEL32!GetLastError` at `0x1800df48c`
- `KERNEL32!GetLastError` at `0x1800df536`
- `KERNEL32!GetLastError` at `0x1800df64d`
- `KERNEL32!GetLastError` at `0x1800df6d2`
- `KERNEL32!GetLastError` at `0x1800dff6b`
- `KERNEL32!GetLastError` at `0x1800dffe7`
- `KERNEL32!GetLastError` at `0x1800e0059`
- `KERNEL32!GetLastError` at `0x1800e00dc`
- `KERNEL32!GetLastError` at `0x1800e00f3`
- `KERNEL32!GetLastError` at `0x1800e0113`
- `KERNEL32!GetLastError` at `0x1800e01b7`
- `KERNEL32!GetLastError` at `0x1800df413`
- `KERNEL32!GetLastError` at `0x1800df48c`
- `KERNEL32!GetLastError` at `0x1800df536`
- `KERNEL32!GetLastError` at `0x1800df64d`
- `KERNEL32!GetLastError` at `0x1800df6d2`
- `KERNEL32!GetLastError` at `0x1800dff6b`
- `KERNEL32!GetLastError` at `0x1800dffe7`
- `KERNEL32!GetLastError` at `0x1800e0059`
- `KERNEL32!GetLastError` at `0x1800e00dc`
- `KERNEL32!GetLastError` at `0x1800e00f3`
- `KERNEL32!GetLastError` at `0x1800e0113`
- `KERNEL32!GetLastError` at `0x1800e01b7`
- `KERNEL32!EnterCriticalSection` at `0x1800df777`
- `KERNEL32!EnterCriticalSection` at `0x1800df777`
- `KERNEL32!GetFileAttributesW` at `0x1800df86e`
- `KERNEL32!GetFileAttributesW` at `0x1800df880`
- `KERNEL32!GetFileAttributesW` at `0x1800df86e`
- `KERNEL32!GetFileAttributesW` at `0x1800df880`
- `unbcl!?GetFileNameExtension@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800dfbae`
- `unbcl!?GetFileNameExtension@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800dfbae`
- `unbcl!?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800dfaff`
- `unbcl!?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800dfaff`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1800dfc12`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1800dfcdb`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1800dfc12`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1800dfcdb`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1800df78a`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1800df78a`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800dfa10`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800dfa81`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800dfc80`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800e02bc`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800dfa10`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800dfa81`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800dfc80`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1800e02bc`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1800dff5c`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1800dff5c`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x1800dff10`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x1800dff10`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800df932`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800df951`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800df97f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800df9d8`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dfa04`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dfa75`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dfc66`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dfc74`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800e02b0`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800df932`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800df951`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800df97f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800df9d8`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dfa04`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dfa75`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dfc66`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800dfc74`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800e02b0`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1800df905`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1800dfada`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1800e0279`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1800df905`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1800dfada`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1800e0279`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800df9ae`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800df9c6`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800dfa53`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800dfac4`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800dfb45`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800dfbce`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800e0302`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800df9ae`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800df9c6`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800dfa53`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800dfac4`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800dfb45`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800dfbce`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800e0302`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800df917`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800df967`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800df9f4`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800dfa65`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800dfaf5`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800dfba4`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800dfe94`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800e02a0`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800df917`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800df967`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800df9f4`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800dfa65`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800dfaf5`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800dfba4`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800dfe94`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800e02a0`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800df7bb`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800dfcf8`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800dfe78`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800e0342`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800e040f`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800e047f`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800df7bb`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800dfcf8`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800dfe78`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800e0342`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800e040f`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800e047f`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800dfa35`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800dfaa6`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800dfb27`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800dfb77`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800dfc3a`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800dfca5`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800dfec3`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800e02e4`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800dfa35`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800dfaa6`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800dfb27`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800dfb77`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800dfc3a`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800dfca5`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800dfec3`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800e02e4`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800dfbdc`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800dfbf6`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800dfcbf`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800dfd22`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800dfd7f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800e025f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800e0310`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800dfbdc`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800dfbf6`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800dfcbf`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800dfd22`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800dfd7f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800e025f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800e0310`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800df5b6`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800df862`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800dfbe5`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800dfbff`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800dfcc8`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800dfd2b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800dfd91`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800dfdbf`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800e0268`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800e0319`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800df5b6`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800df862`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800dfbe5`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800dfbff`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800dfcc8`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800dfd2b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800dfd91`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800dfdbf`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800e0268`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800e0319`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dfa44`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dfab5`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dfb36`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dfb86`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dfc49`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dfc58`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dfcb4`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dfe54`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dfe63`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dfed2`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dff42`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800e02f3`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800e04de`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dfa44`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dfab5`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dfb36`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dfb86`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dfc49`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dfc58`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dfcb4`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dfe54`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dfe63`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dfed2`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800dff42`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800e02f3`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800e04de`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800dfa21`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800dfa92`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800dfb10`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800dfb60`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800dfbbf`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800dfc23`

## string_xrefs

- `0x1800df45b`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800df4cb`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800df5f2`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800df69c`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800df716`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800dffb4`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800e0033`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800e009e`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800e0161`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800e0202`: `base\ntsetup\setupplatform\lib\src\installation.cpp`
- `0x1800e0291`: `SafeOS.Mount`
- `0x1800e042a`: `Complete servicing operations`
- `0x1800df49d`: `QueueAddCbsPackage called with 0 paths, skip.`
- `0x1800df427`: `QueueAddCbsPackage called with [%d] paths`
- `0x1800df5c2`: `QueueAddCbsPackage called with path %s; install size %llu`
- `0x1800df6e6`: `Get NULL at %d-th paths`
- `0x1800e012a`: `Failure while validating package path [%s]. Error: 0x%08X`
- `0x1800dfcd4`: `Copy package payload from %s to %s`
- `0x1800e049a`: `Complete SafeOS servicing operations`
- `0x1800e01cb`: `Failure while requesting package payload copy. Error: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=31
__int64 __fastcall CNewSystem::QueueAddCbsPackage(
        CDeploymentBase *this,
        int a2,
        __int64 a3,
        int a4,
        int a5,
        int a6,
        int a7)
{
  __int64 v7; // rsi
  int v9; // r13d
  __int64 (__fastcall ***v11)(_QWORD); // rcx
  DWORD LastError; // edi
  __int64 v13; // rbx
  struct tagLOG_PARTIAL_MSG *v14; // rax
  DWORD v15; // edi
  __int64 v16; // rbx
  struct tagLOG_PARTIAL_MSG *v17; // rax
  unsigned int i; // r12d
  __int64 v19; // rcx
  DWORD v20; // esi
  __int64 v21; // rdi
  __int64 v22; // rcx
  _QWORD *v23; // rax
  __int64 v24; // rbx
  __int64 v25; // rcx
  _QWORD *v26; // rax
  UnBCL::String *v27; // rax
  const char *CString; // rax
  struct tagLOG_PARTIAL_MSG *v29; // rax
  unsigned int v30; // eax
  DWORD v31; // edi
  __int64 v32; // rbx
  struct tagLOG_PARTIAL_MSG *v33; // rax
  DWORD v34; // edi
  __int64 v35; // rbx
  struct tagLOG_PARTIAL_MSG *v36; // rax
  unsigned int v37; // eax
  char *v38; // rax
  void *v39; // rbx
  __int64 v40; // r12
  unsigned int j; // edi
  __int64 v42; // rcx
  _QWORD *v43; // rax
  UnBCL::String *v44; // rax
  const char *v45; // r12
  DWORD v46; // ebx
  __int64 v47; // rcx
  _QWORD *v48; // rax
  struct UnBCL::String *v49; // rbx
  struct UnBCL::String *P; // rax
  struct UnBCL::String *v51; // rdi
  struct UnBCL::String *v52; // rax
  bool v53; // di
  unsigned int v54; // edi
  const struct UnBCL::String *v55; // rbx
  const struct UnBCL::String *v56; // rax
  struct UnBCL::String *v57; // rax
  unsigned __int64 v58; // rsi
  const struct UnBCL::String *v59; // rbx
  const struct UnBCL::String *v60; // rax
  struct UnBCL::String *v61; // rax
  const struct UnBCL::String *v62; // rcx
  struct UnBCL::String *FileName; // rax
  struct UnBCL::String *v64; // rax
  const struct UnBCL::String *v65; // rax
  struct UnBCL::String *FileNameExtension; // rax
  UnBCL::String *v67; // rax
  const unsigned __int16 *v68; // rbx
  UnBCL::String *v69; // rax
  const unsigned __int16 *v70; // rax
  struct UnBCL::String *v71; // rax
  const struct UnBCL::String *v72; // rbx
  const struct UnBCL::String *v73; // rax
  struct UnBCL::String *v74; // rax
  UnBCL::String *v75; // rax
  const unsigned __int16 *v76; // rax
  struct UnBCL::String *v77; // rax
  void *v78; // rbx
  UnBCL::String *v79; // rax
  const unsigned __int16 *v80; // rax
  __int64 v81; // rax
  CCopyFilesAndFolders *v82; // rbx
  UnBCL::String *v83; // rax
  const unsigned __int16 *v84; // rax
  int v85; // esi
  const unsigned __int16 *v86; // rax
  __int64 v87; // rbx
  void (__fastcall *v88)(__int64, __int64); // rdi
  __int64 v89; // rax
  UnBCL::String *v90; // rax
  UnBCL::String *v91; // rbx
  char *v92; // rbx
  void (__fastcall *v93)(char *, __int64); // rdi
  __int64 v94; // rax
  DWORD v95; // edi
  __int64 v96; // rbx
  struct tagLOG_PARTIAL_MSG *v97; // rax
  DWORD v98; // edi
  __int64 v99; // rbx
  struct tagLOG_PARTIAL_MSG *v100; // rax
  DWORD v101; // edi
  __int64 v102; // rbx
  struct tagLOG_PARTIAL_MSG *v103; // rax
  signed int v104; // eax
  bool v105; // sf
  signed int v106; // eax
  unsigned int v107; // esi
  DWORD v108; // edi
  __int64 v109; // rbx
  struct tagLOG_PARTIAL_MSG *v110; // rax
  DWORD v111; // edi
  __int64 v112; // rbx
  struct tagLOG_PARTIAL_MSG *v113; // rax
  UnBCL::String *v114; // rax
  unsigned int v115; // edi
  const struct UnBCL::String *v116; // rbx
  const struct UnBCL::String *v117; // rax
  struct UnBCL::String *v118; // rax
  UnBCL::String *v119; // rax
  __int64 v120; // rax
  __int64 v121; // rbx
  __int64 v122; // rsi
  void *v123; // rax
  int v124; // eax
  int v125; // r9d
  int v126; // r10d
  int v127; // r11d
  __int64 v128; // rcx
  __int64 v129; // rax
  __int64 v130; // rbx
  __int64 v131; // rdi
  void *v132; // rax
  __int64 v133; // rax
  __int64 *v134; // rbp
  __int64 *v135; // rdx
  __int64 v136; // [rsp+0h] [rbp-258h] BYREF
  unsigned int v137; // [rsp+60h] [rbp-1F8h]
  int v138; // [rsp+64h] [rbp-1F4h]
  unsigned int v139; // [rsp+68h] [rbp-1F0h]
  unsigned int v140; // [rsp+6Ch] [rbp-1ECh]
  _BYTE v141[16]; // [rsp+70h] [rbp-1E8h] BYREF
  unsigned __int64 v142; // [rsp+80h] [rbp-1D8h]
  void *v143; // [rsp+88h] [rbp-1D0h]
  UnBCL::String *v144; // [rsp+90h] [rbp-1C8h]
  __int64 v145; // [rsp+98h] [rbp-1C0h]
  unsigned __int64 v146; // [rsp+A0h] [rbp-1B8h]
  char *v147; // [rsp+A8h] [rbp-1B0h]
  _BYTE v148[16]; // [rsp+B0h] [rbp-1A8h] BYREF
  _QWORD v149[2]; // [rsp+C0h] [rbp-198h] BYREF
  _BYTE v150[16]; // [rsp+D0h] [rbp-188h] BYREF
  _BYTE v151[24]; // [rsp+E0h] [rbp-178h] BYREF
  char v152[8]; // [rsp+F8h] [rbp-160h] BYREF
  _QWORD *v153; // [rsp+100h] [rbp-158h]
  _QWORD *pExceptionObject; // [rsp+108h] [rbp-150h] BYREF
  _QWORD *v155; // [rsp+110h] [rbp-148h] BYREF
  _QWORD *v156; // [rsp+118h] [rbp-140h] BYREF
  _BYTE v157[16]; // [rsp+120h] [rbp-138h] BYREF
  _BYTE v158[16]; // [rsp+130h] [rbp-128h] BYREF
  _BYTE v159[16]; // [rsp+140h] [rbp-118h] BYREF
  _BYTE v160[16]; // [rsp+150h] [rbp-108h] BYREF
  _BYTE v161[16]; // [rsp+160h] [rbp-F8h] BYREF
  _BYTE v162[16]; // [rsp+170h] [rbp-E8h] BYREF
  _BYTE v163[16]; // [rsp+180h] [rbp-D8h] BYREF
  _BYTE v164[16]; // [rsp+190h] [rbp-C8h] BYREF
  _BYTE v165[16]; // [rsp+1A0h] [rbp-B8h] BYREF
  _BYTE v166[24]; // [rsp+1B0h] [rbp-A8h] BYREF
  __int64 v167; // [rsp+1C8h] [rbp-90h]
  _QWORD v168[7]; // [rsp+1D0h] [rbp-88h] BYREF
  _BYTE v169[80]; // [rsp+208h] [rbp-50h] BYREF

  v167 = -2;
  v7 = a3;
  v9 = 0;
  LODWORD(v143) = 0;
  if ( !a3 )
    return 2147942487LL;
  v11 = (__int64 (__fastcall ***)(_QWORD))(a3 + 8 + *(int *)(*(_QWORD *)(a3 + 8) + 12LL));
  v139 = (**v11)(v11);
  LastError = GetLastError();
  v13 = CurrentIP();
  v14 = ConstructPartialMsgW(0x4000000u, "QueueAddCbsPackage called with [%d] paths", v139);
  WdsSetupLogMessageW(
    v14,
    819200,
    L"D",
    0,
    12790,
    L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
    L"CNewSystem::QueueAddCbsPackage",
    v13,
    LastError,
    0,
    0);
  if ( !v139 )
  {
    v15 = GetLastError();
    v16 = CurrentIP();
    v17 = ConstructPartialMsgW(0x4000000u, "QueueAddCbsPackage called with 0 paths, skip.");
    WdsSetupLogMessageW(
      v17,
      819200,
      L"D",
      0,
      12793,
      L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
      L"CNewSystem::QueueAddCbsPackage",
      v16,
      v15,
      0,
      0);
    return 0;
  }
  for ( i = 0; i < v139; ++i )
  {
    v19 = v7 + *(int *)(*(_QWORD *)(v7 + 8) + 16LL) + 8LL;
    if ( !*(_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v19 + 24LL))(v19, i) )
    {
      v34 = GetLastError();
      v35 = CurrentIP();
      v36 = ConstructPartialMsgW(0x2000000u, "Get NULL at %d-th paths", i);
      WdsSetupLogMessageW(
        v36,
        819200,
        L"D",
        0,
        12801,
        L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
        L"CNewSystem::QueueAddCbsPackage",
        v35,
        v34,
        0,
        0);
      return 2147942487LL;
    }
    v20 = GetLastError();
    v21 = CurrentIP();
    v22 = *(int *)(*(_QWORD *)(a3 + 8) + 16LL) + a3 + 8;
    v23 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v22 + 24LL))(v22, i);
    v24 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v23 + 16LL))(*v23);
    v25 = *(int *)(*(_QWORD *)(a3 + 8) + 16LL) + a3 + 8;
    v26 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v25 + 24LL))(v25, i);
    v27 = (UnBCL::String *)(**(__int64 (__fastcall ***)(_QWORD))*v26)(*v26);
    CString = (const char *)UnBCL::String::get_CString(v27);
    v29 = ConstructPartialMsgW(0x4000000u, "QueueAddCbsPackage called with path %s; install size %llu", CString, v24);
    WdsSetupLogMessageW(
      v29,
      819200,
      L"D",
      0,
      12804,
      L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
      L"CNewSystem::QueueAddCbsPackage",
      v21,
      v20,
      0,
      0);
    v7 = a3;
  }
  v30 = *((_DWORD *)this + 115);
  if ( v30 > 1 && v30 != 6 )
  {
    v31 = GetLastError();
    v32 = CurrentIP();
    v33 = ConstructPartialMsgW(
            0x3000000u,
            "%hs: System state does not allow for more requests to be queued. Current state is %d",
            "CNewSystem::QueueAddCbsPackage",
            *((_DWORD *)this + 115));
    WdsSetupLogMessageW(
      v33,
      819200,
      L"D",
      0,
      12813,
      L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
      L"CNewSystem::QueueAddCbsPackage",
      v32,
      v31,
      0,
      0);
    return 2147946720LL;
  }
  if ( (*((_BYTE *)this + 772) & 2) != 0 )
  {
    v137 = -2147024883;
    if ( (*(_BYTE *)(*((_QWORD *)this + 8) + 56LL) & 2) != 0 )
    {
      CDeploymentBase::ExitReadOnlyMode(this);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      v138 = 0;
      UnBCL::Exception::Exception((UnBCL::Exception *)v168);
      v168[0] = &`CNewSystem::QueueAddCbsPackage'::`20'::CXXXXXHandledException::`vftable';
      try
      {
        try
        {
          v37 = *((_DWORD *)this + 115);
          if ( v37 <= 1 || v37 == 6 )
          {
            v38 = (char *)UnBCL::Object::operator new(0xB0u);
            v39 = v38;
            v147 = v38;
            if ( v38 )
            {
              memset_0(v38, 0, 0xB0u);
              v38 = (char *)CCbsPackageList<UnBCL::String *>::CCbsPackageList<UnBCL::String *>(v39);
            }
            UnBCL::SmartPtr<CCbsPackageList<UnBCL::String *>>::SmartPtr<CCbsPackageList<UnBCL::String *>>(v152, v38);
            (*(void (__fastcall **)(_QWORD *, __int64))(*v153 + 40LL))(v153, 1);
            v146 = 0;
            v40 = 0;
            v147 = 0;
            for ( j = 0; ; j = v140 + 1 )
            {
              v140 = j;
              if ( j >= v139 )
                break;
              v42 = v7 + *(int *)(*(_QWORD *)(v7 + 8) + 16LL) + 8LL;
              v43 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v42 + 24LL))(v42, j);
              v44 = (UnBCL::String *)(**(__int64 (__fastcall ***)(_QWORD))*v43)(*v43);
              v45 = (const char *)UnBCL::String::get_CString(v44);
              if ( GetFileAttributesW((LPCWSTR)v45) == -1 )
              {
                v104 = GetLastError();
                v105 = v104 < 0;
                if ( v104 > 0 )
                  v105 = 1;
                if ( v105 )
                {
                  v106 = GetLastError();
                  v107 = v106;
                  if ( v106 > 0 )
                    v107 = (unsigned __int16)v106 | 0x80070000;
                }
                else
                {
                  v107 = -2147467259;
                }
                v137 = v107;
                v108 = GetLastError();
                v109 = CurrentIP();
                v110 = ConstructPartialMsgW(
                         0x2000000u,
                         "Failure while validating package path [%s]. Error: 0x%08X",
                         v45,
                         v107);
                WdsSetupLogMessageW(
                  v110,
                  819200,
                  L"D",
                  0,
                  12853,
                  L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
                  L"CNewSystem::QueueAddCbsPackage",
                  v109,
                  v108,
                  0,
                  0);
                v138 = 1;
                pExceptionObject = v168;
                throw (`CNewSystem::QueueAddCbsPackage(int,CCbsPackageList<UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *> *,int,SetupPlatform::SP_ERROR_HANDLING,ulong,OP_OPERATION_ID)'::`20'::CXXXXXHandledException **)&pExceptionObject;
              }
              v46 = GetFileAttributesW((LPCWSTR)v45) & 0x10;
              LODWORD(v144) = v46;
              v142 = SPGetFileSize((LPCWSTR)v45);
              v47 = v7 + *(int *)(*(_QWORD *)(v7 + 8) + 16LL) + 8LL;
              v48 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v47 + 24LL))(v47, j);
              v145 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v48 + 16LL))(*v48);
              if ( !v145 )
              {
                if ( v46 )
                  v145 = v142;
                else
                  v145 = 10 * v142;
              }
              UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v141);
              v49 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v151, (const unsigned __int16 *)v45);
              v9 |= 1u;
              LODWORD(v143) = v9;
              P = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 152);
              v53 = 0;
              if ( !SPArePathsOnSameVolume(P, v49) )
              {
                if ( !UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 216)
                  || (v51 = (struct UnBCL::String *)UnBCL::String::String(
                                                      (UnBCL::String *)v169,
                                                      (const unsigned __int16 *)v45),
                      v9 |= 2u,
                      LODWORD(v143) = v9,
                      v52 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 216),
                      !SPArePathsOnSameVolume(v52, v51)) )
                {
                  v53 = 1;
                }
              }
              if ( (v9 & 2) != 0 )
              {
                v9 &= ~2u;
                UnBCL::String::~String((UnBCL::String *)v169);
              }
              if ( (v9 & 1) != 0 )
              {
                v9 &= ~1u;
                UnBCL::String::~String((UnBCL::String *)v151);
              }
              if ( v53 )
              {
                v54 = 0;
                if ( UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 216) )
                {
                  v55 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v166, L"Payload\\Package");
                  v56 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 216);
                  v57 = UnBCL::Path::Combine(v56, v55);
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v158, v57);
                  UnBCL::SmartPtr<UnBCL::String>::operator=(v141, v158);
                  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v158);
                  UnBCL::String::~String((UnBCL::String *)v166);
                  v58 = 0;
                }
                else
                {
                  v59 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v151, L"Payload\\Package");
                  v60 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 152);
                  v61 = UnBCL::Path::Combine(v60, v59);
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v159, v61);
                  UnBCL::SmartPtr<UnBCL::String>::operator=(v141, v159);
                  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v159);
                  UnBCL::String::~String((UnBCL::String *)v151);
                  v58 = v142;
                }
                UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v148);
                if ( a4 )
                {
                  v62 = (const struct UnBCL::String *)UnBCL::String::String(
                                                        (UnBCL::String *)v151,
                                                        (const unsigned __int16 *)v45);
                  FileName = UnBCL::Path::GetFileName(v62);
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v160, FileName);
                  UnBCL::SmartPtr<UnBCL::String>::operator=(v148, v160);
                  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v160);
                  UnBCL::String::~String((UnBCL::String *)v151);
                }
                else
                {
                  v64 = SPGetGuidString();
                  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v161, v64);
                  UnBCL::SmartPtr<UnBCL::String>::operator=(v148, v161);
                  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v161);
                  if ( !(_DWORD)v144 )
                  {
                    v65 = (const struct UnBCL::String *)UnBCL::String::String(
                                                          (UnBCL::String *)v151,
                                                          (const unsigned __int16 *)v45);
                    FileNameExtension = UnBCL::Path::GetFileNameExtension(v65);
                    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v163, FileNameExtension);
                    UnBCL::String::~String((UnBCL::String *)v151);
                    v67 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v163);
                    v68 = UnBCL::String::get_CString(v67);
                    v69 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v148);
                    v70 = UnBCL::String::get_CString(v69);
                    v71 = UnBCL::String::Format(L"%s%s", v70, v68);
                    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v162, v71);
                    UnBCL::SmartPtr<UnBCL::String>::operator=(v148, v162);
                    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v162);
                    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v163);
                  }
                }
                v72 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v148);
                v73 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v141);
                v74 = UnBCL::Path::Combine(v73, v72);
                UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v164, v74);
                UnBCL::SmartPtr<UnBCL::String>::operator=(v141, v164);
                UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v164);
                v75 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v141);
                v76 = UnBCL::String::get_CString(v75);
                v77 = UnBCL::String::Format(L"Copy package payload from %s to %s", v45, v76);
                UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v165, v77);
                v78 = UnBCL::Object::operator new(0x118u);
                v143 = v78;
                if ( v78 )
                {
                  LOBYTE(v54) = a5 == 1;
                  v79 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v165);
                  v80 = UnBCL::String::get_CString(v79);
                  v81 = CCopyFilesAndFolders::CCopyFilesAndFolders(v78, v58, v80, v54, 0, 10, 9);
                }
                else
                {
                  v81 = 0;
                }
                UnBCL::SmartPtr<CCopyFilesAndFolders>::SmartPtr<CCopyFilesAndFolders>(v149, v81);
                v82 = (CCopyFilesAndFolders *)v149[1];
                v83 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v141);
                if ( (_DWORD)v144 )
                {
                  v84 = UnBCL::String::get_CString(v83);
                  v85 = CCopyFilesAndFolders::AddFolderCopy(v82, (const unsigned __int16 *)v45, v84, 0, 0, 0, 0x32u);
                }
                else
                {
                  v86 = UnBCL::String::get_CString(v83);
                  v85 = CCopyFilesAndFolders::AddFileCopy(v82, (const unsigned __int16 *)v45, v86, 0, 0, 0, 0, 5u);
                }
                v137 = v85;
                if ( v85 < 0 )
                {
                  v111 = GetLastError();
                  v112 = CurrentIP();
                  v113 = ConstructPartialMsgW(
                           0x2000000u,
                           "Failure while requesting package payload copy. Error: 0x%08X",
                           v85);
                  WdsSetupLogMessageW(
                    v113,
                    819200,
                    L"D",
                    0,
                    12928,
                    L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
                    L"CNewSystem::QueueAddCbsPackage",
                    v112,
                    v111,
                    0,
                    0);
                  v138 = 1;
                  v155 = v168;
                  throw (`CNewSystem::QueueAddCbsPackage(int,CCbsPackageList<UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *> *,int,SetupPlatform::SP_ERROR_HANDLING,ulong,OP_OPERATION_ID)'::`20'::CXXXXXHandledException **)&v155;
                }
                v87 = *((_QWORD *)this + 62) + *(int *)(*(_QWORD *)(*((_QWORD *)this + 62) + 8LL) + 16LL);
                v88 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(v87 + 8) + 40LL);
                v89 = UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,CDriverInstallInfo *>>::Steal(v149);
                v88(v87 + 8, v89);
                v149[0] = &UnBCL::SmartPtr<CCopyFilesAndFolders>::`vftable';
                UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(v149);
                UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v165);
                UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v148);
                v7 = a3;
              }
              else
              {
                v90 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
                v91 = v90;
                v144 = v90;
                if ( v90 )
                {
                  UnBCL::String::String(v90, (const unsigned __int16 *)v45);
                  *(_QWORD *)v91 = &UnBCL::String::`local vftable';
                }
                UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v150, v91);
                UnBCL::SmartPtr<UnBCL::String>::operator=(v141, v150);
                UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v150);
              }
              v146 += v142;
              v92 = (char *)v153 + *(int *)(v153[1] + 16LL);
              v93 = *(void (__fastcall **)(char *, __int64))(*((_QWORD *)v92 + 1) + 40LL);
              v94 = UnBCL::SmartPtr<UnBCL::String>::Steal(v141);
              v93(v92 + 8, v94);
              v40 = (__int64)&v147[v145];
              v147 += v145;
              UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v141);
            }
            v114 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)this + 648);
            v115 = (unsigned int)UnBCL::String::get_CString(v114);
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v157);
            if ( !a2 )
            {
              v116 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v166, L"SafeOS.Mount");
              v117 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 248);
              v118 = UnBCL::Path::Combine(v117, v116);
              UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v150, v118);
              UnBCL::SmartPtr<UnBCL::String>::operator=(v157, v150);
              UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v150);
              UnBCL::String::~String((UnBCL::String *)v166);
              v119 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v157);
              v115 = (unsigned int)UnBCL::String::get_CString(v119);
            }
            v120 = RAII::CAutoCleanupBase<void *>::operator->((char *)this + 488);
            v121 = v120 + *(int *)(*(_QWORD *)(v120 + 8) + 16LL);
            v122 = *(_QWORD *)(v121 + 8);
            v123 = UnBCL::Object::operator new(0x138u);
            if ( v123 )
            {
              SPCalculateWeight(v146);
              v124 = RAII::CAutoCleanupBase<void *>::operator->(v152);
              v123 = (void *)CAddCbsPackage::CAddCbsPackage(v127, v115, v124, v125, v40, v126, a6, a7);
            }
            (*(void (__fastcall **)(__int64, void *))(v122 + 40))(v121 + 8, v123);
            v128 = RAII::CAutoCleanupBase<void *>::operator->((char *)this + 488);
            if ( a2 )
            {
              if ( !(unsigned int)COperationQueue::IsOperationPresent(v128, 37) )
              {
                v129 = RAII::CAutoCleanupBase<void *>::operator->((char *)this + 488);
                v130 = v129 + *(int *)(*(_QWORD *)(v129 + 8) + 16LL);
                v131 = *(_QWORD *)(v130 + 8);
                v132 = UnBCL::Object::operator new(0x108u);
                if ( v132 )
                  v132 = (void *)CEmptyOperation::CEmptyOperation(v132, 1, L"Complete servicing operations", 114, 37);
                goto LABEL_76;
              }
            }
            else if ( !(unsigned int)COperationQueue::IsOperationPresent(v128, 25) )
            {
              v133 = RAII::CAutoCleanupBase<void *>::operator->((char *)this + 488);
              v130 = v133 + *(int *)(*(_QWORD *)(v133 + 8) + 16LL);
              v131 = *(_QWORD *)(v130 + 8);
              v132 = UnBCL::Object::operator new(0x108u);
              if ( v132 )
                v132 = (void *)CEmptyOperation::CEmptyOperation(
                                 v132,
                                 1,
                                 L"Complete SafeOS servicing operations",
                                 60,
                                 25);
LABEL_76:
              (*(void (__fastcall **)(__int64, void *))(v131 + 40))(v130 + 8, v132);
            }
            if ( *((_DWORD *)this + 115) )
              *((_DWORD *)this + 115) = 1;
            v137 = 0;
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v157);
            UnBCL::SmartPtr<CCbsPackageList<UnBCL::String *>>::~SmartPtr<CCbsPackageList<UnBCL::String *>>(v152);
          }
        }
        catch ( ___R0PEAVCXXXXXTemp__BF___QueueAddCbsPackage_CNewSystem__IEAAJHPEAV__CCbsPackageList_PEAV__DictionaryEntry_PEAVString_UnBCL___K_UnBCL____HW4SP_ERROR_HANDLING_SetupPlatform__KW4OP_OPERATION_ID___Z__8 )
        {
          CNewSystem::QueueAddCbsPackage_::_1_::catch_33();
          __eh34_caught_type(
            1,
            ___R0PEAVCXXXXXTemp__BF___QueueAddCbsPackage_CNewSystem__IEAAJHPEAV__CCbsPackageList_PEAV__DictionaryEntry_PEAVString_UnBCL___K_UnBCL____HW4SP_ERROR_HANDLING_SetupPlatform__KW4OP_OPERATION_ID___Z__8);
        }
        v138 = 1;
        v156 = v168;
        throw (`CNewSystem::QueueAddCbsPackage(int,CCbsPackageList<UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *> *,int,SetupPlatform::SP_ERROR_HANDLING,ulong,OP_OPERATION_ID)'::`20'::CXXXXXHandledException **)&v156;
      }
      catch ( UnBCL::Exception * )
      {
        v135 = &v136;
        v134 = v135;
        LeaveCriticalSection((LPCRITICAL_SECTION)(v135[76] + 16));
        if ( !*((_DWORD *)v134 + 25) )
          throw;
        UnBCL::Exception::~Exception((UnBCL::Exception *)v168);
        return v137;
      }
    }
  }
  v95 = GetLastError();
  v96 = CurrentIP();
  v97 = ConstructPartialMsgW(
          0x3000000u,
          "%hs: Capabilities not met, request is not supported",
          "CNewSystem::QueueAddCbsPackage");
  WdsSetupLogMessageW(
    v97,
    819200,
    L"D",
    0,
    12821,
    L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
    L"CNewSystem::QueueAddCbsPackage",
    v96,
    v95,
    0,
    0);
  v98 = GetLastError();
  v99 = CurrentIP();
  v100 = ConstructPartialMsgW(
           0x4000000u,
           "CAPABILITIES: DL Platform capabilities: 0x%08X",
           *(_DWORD *)(*((_QWORD *)this + 8) + 56LL));
  WdsSetupLogMessageW(
    v100,
    819200,
    L"D",
    0,
    12822,
    L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
    L"CNewSystem::QueueAddCbsPackage",
    v99,
    v98,
    0,
    0);
  v101 = GetLastError();
  v102 = CurrentIP();
  v103 = ConstructPartialMsgW(0x4000000u, "CAPABILITIES: Image capabilities: 0x%08X", *((_DWORD *)this + 193));
  WdsSetupLogMessageW(
    v103,
    819200,
    L"D",
    0,
    12823,
    L"base\\ntsetup\\setupplatform\\lib\\src\\installation.cpp",
    L"CNewSystem::QueueAddCbsPackage",
    v102,
    v101,
    0,
    0);
  return 2147942450LL;
}

```

## disassembly

```asm
0x1800df3a4  mov     rax, rsp
0x1800df3a7  mov     [rax+20h], r9d
0x1800df3ab  mov     [rax+18h], r8
0x1800df3af  mov     [rax+10h], edx
0x1800df3b2  mov     [rax+8], rcx
0x1800df3b6  push    rbx
0x1800df3b7  push    rsi
0x1800df3b8  push    rdi
0x1800df3b9  push    r12
0x1800df3bb  push    r13
0x1800df3bd  push    r14
0x1800df3bf  push    r15
0x1800df3c1  sub     rsp, 220h
0x1800df3c8  mov     qword ptr [rax-90h], 0FFFFFFFFFFFFFFFEh
0x1800df3d3  mov     rsi, r8
0x1800df3d6  mov     r14, rcx
0x1800df3d9  xor     r13d, r13d
0x1800df3dc  mov     [rax-1D0h], r13d
0x1800df3e3  test    r8, r8
0x1800df3e6  jnz     short loc_1800DF3F2
0x1800df3e8  mov     eax, 80070057h
0x1800df3ed  jmp     loc_1800E00C9
0x1800df3f2  mov     rax, [r8+8]
0x1800df3f6  movsxd  rcx, dword ptr [rax+0Ch]
0x1800df3fa  add     r8, 8
0x1800df3fe  add     rcx, r8
0x1800df401  mov     rax, [rcx]
0x1800df404  mov     rax, [rax]
0x1800df407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df40c  mov     r15d, eax
0x1800df40f  mov     [rsp+258h+var_1F0], eax
0x1800df413  call    cs:__imp_GetLastError
0x1800df419  mov     edi, eax
0x1800df41b  call    cs:__imp_CurrentIP
0x1800df421  mov     rbx, rax
0x1800df424  mov     r8d, r15d
0x1800df427  lea     rdx, aQueueaddcbspac_1; "QueueAddCbsPackage called with [%d] pat"...
0x1800df42e  mov     r12d, 4000000h
0x1800df434  mov     ecx, r12d; unsigned int
0x1800df437  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800df43c  mov     [rsp+258h+var_208], r13d
0x1800df441  mov     [rsp+258h+var_210], r13
0x1800df446  mov     [rsp+258h+var_218], edi
0x1800df44a  mov     qword ptr [rsp+258h+var_220], rbx
0x1800df44f  lea     rcx, aCnewsystemQueu_58; "CNewSystem::QueueAddCbsPackage"
0x1800df456  mov     qword ptr [rsp+258h+var_228], rcx
0x1800df45b  lea     rcx, aBaseNtsetupSet_34; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1800df462  mov     qword ptr [rsp+258h+var_230], rcx
0x1800df467  mov     [rsp+258h+var_238], 31F6h
0x1800df46f  xor     r9d, r9d
0x1800df472  lea     r8, aD_0; "D"
0x1800df479  mov     edx, 0C8000h
0x1800df47e  mov     rcx, rax
0x1800df481  call    cs:__imp_WdsSetupLogMessageW
0x1800df487  test    r15d, r15d
0x1800df48a  jnz     short loc_1800DF4FE
0x1800df48c  call    cs:__imp_GetLastError
0x1800df492  mov     edi, eax
0x1800df494  call    cs:__imp_CurrentIP
0x1800df49a  mov     rbx, rax
0x1800df49d  lea     rdx, aQueueaddcbspac_2; "QueueAddCbsPackage called with 0 paths,"...
0x1800df4a4  mov     ecx, r12d; unsigned int
0x1800df4a7  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800df4ac  mov     [rsp+258h+var_208], r13d
0x1800df4b1  mov     [rsp+258h+var_210], r13
0x1800df4b6  mov     [rsp+258h+var_218], edi
0x1800df4ba  mov     qword ptr [rsp+258h+var_220], rbx
0x1800df4bf  lea     rcx, aCnewsystemQueu_58; "CNewSystem::QueueAddCbsPackage"
0x1800df4c6  mov     qword ptr [rsp+258h+var_228], rcx
0x1800df4cb  lea     rcx, aBaseNtsetupSet_34; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1800df4d2  mov     qword ptr [rsp+258h+var_230], rcx
0x1800df4d7  mov     [rsp+258h+var_238], 31F9h
0x1800df4df  xor     r9d, r9d
0x1800df4e2  lea     r8, aD_0; "D"
0x1800df4e9  mov     edx, 0C8000h
0x1800df4ee  mov     rcx, rax
0x1800df4f1  call    cs:__imp_WdsSetupLogMessageW
0x1800df4f7  xor     eax, eax
0x1800df4f9  jmp     loc_1800E00C9
0x1800df4fe  xor     r12d, r12d
0x1800df501  test    r15d, r15d
0x1800df504  lea     r15d, [r12+1]
0x1800df509  jz      loc_1800DF634
0x1800df50f  mov     rax, [rsi+8]
0x1800df513  movsxd  rcx, dword ptr [rax+10h]
0x1800df517  add     rcx, 8
0x1800df51b  add     rcx, rsi
0x1800df51e  mov     rax, [rcx]
0x1800df521  mov     edx, r12d
0x1800df524  mov     rax, [rax+18h]
0x1800df528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df52d  cmp     [rax], r13
0x1800df530  jz      loc_1800DF6D2
0x1800df536  call    cs:__imp_GetLastError
0x1800df53c  mov     esi, eax
0x1800df53e  call    cs:__imp_CurrentIP
0x1800df544  mov     rdi, rax
0x1800df547  mov     rax, [rsp+258h+arg_10]
0x1800df54f  mov     rcx, [rax+8]
0x1800df553  movsxd  rdx, dword ptr [rcx+10h]
0x1800df557  lea     rcx, [rax+8]
0x1800df55b  add     rcx, rdx
0x1800df55e  mov     rdx, [rcx]
0x1800df561  mov     rax, [rdx+18h]
0x1800df565  mov     edx, r12d
0x1800df568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df56d  mov     rcx, [rax]
0x1800df570  mov     rdx, [rcx]
0x1800df573  mov     rax, [rdx+10h]
0x1800df577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df57c  mov     rbx, rax
0x1800df57f  mov     rax, [rsp+258h+arg_10]
0x1800df587  mov     rcx, [rax+8]
0x1800df58b  movsxd  rdx, dword ptr [rcx+10h]
0x1800df58f  lea     rcx, [rax+8]
0x1800df593  add     rcx, rdx
0x1800df596  mov     rdx, [rcx]
0x1800df599  mov     rax, [rdx+18h]
0x1800df59d  mov     edx, r12d
0x1800df5a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df5a5  mov     rcx, [rax]
0x1800df5a8  mov     rdx, [rcx]
0x1800df5ab  mov     rax, [rdx]
0x1800df5ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df5b3  mov     rcx, rax
0x1800df5b6  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1800df5bc  mov     r9, rbx
0x1800df5bf  mov     r8, rax
0x1800df5c2  lea     rdx, aQueueaddcbspac_0; "QueueAddCbsPackage called with path %s;"...
0x1800df5c9  mov     ecx, 4000000h; unsigned int
0x1800df5ce  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800df5d3  mov     [rsp+258h+var_208], r13d
0x1800df5d8  mov     [rsp+258h+var_210], r13
0x1800df5dd  mov     [rsp+258h+var_218], esi
0x1800df5e1  mov     qword ptr [rsp+258h+var_220], rdi
0x1800df5e6  lea     rcx, aCnewsystemQueu_58; "CNewSystem::QueueAddCbsPackage"
0x1800df5ed  mov     qword ptr [rsp+258h+var_228], rcx
0x1800df5f2  lea     rcx, aBaseNtsetupSet_34; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1800df5f9  mov     qword ptr [rsp+258h+var_230], rcx
0x1800df5fe  mov     [rsp+258h+var_238], 3204h
0x1800df606  xor     r9d, r9d
0x1800df609  lea     r8, aD_0; "D"
0x1800df610  mov     edx, 0C8000h
0x1800df615  mov     rcx, rax
0x1800df618  call    cs:__imp_WdsSetupLogMessageW
0x1800df61e  add     r12d, r15d
0x1800df621  cmp     r12d, [rsp+258h+var_1F0]
0x1800df626  mov     rsi, [rsp+258h+arg_10]
0x1800df62e  jb      loc_1800DF50F
0x1800df634  mov     eax, [r14+1CCh]
0x1800df63b  cmp     eax, r15d
0x1800df63e  jbe     loc_1800DF747
0x1800df644  cmp     eax, 6
0x1800df647  jz      loc_1800DF747
0x1800df64d  call    cs:__imp_GetLastError
0x1800df653  mov     edi, eax
0x1800df655  call    cs:__imp_CurrentIP
0x1800df65b  mov     rbx, rax
0x1800df65e  mov     r9d, [r14+1CCh]
0x1800df665  lea     r8, aCnewsystemQueu_77; "CNewSystem::QueueAddCbsPackage"
0x1800df66c  lea     rdx, aHsSystemStateD_1; "%hs: System state does not allow for mo"...
0x1800df673  mov     ecx, 3000000h; unsigned int
0x1800df678  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800df67d  mov     [rsp+258h+var_208], r13d
0x1800df682  mov     [rsp+258h+var_210], r13
0x1800df687  mov     [rsp+258h+var_218], edi
0x1800df68b  mov     qword ptr [rsp+258h+var_220], rbx
0x1800df690  lea     rcx, aCnewsystemQueu_58; "CNewSystem::QueueAddCbsPackage"
0x1800df697  mov     qword ptr [rsp+258h+var_228], rcx
0x1800df69c  lea     rcx, aBaseNtsetupSet_34; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1800df6a3  mov     qword ptr [rsp+258h+var_230], rcx
0x1800df6a8  mov     [rsp+258h+var_238], 320Dh
0x1800df6b0  xor     r9d, r9d
0x1800df6b3  lea     r8, aD_0; "D"
0x1800df6ba  mov     edx, 0C8000h
0x1800df6bf  mov     rcx, rax
0x1800df6c2  call    cs:__imp_WdsSetupLogMessageW
0x1800df6c8  mov     eax, 800710E0h
0x1800df6cd  jmp     loc_1800E00C9
0x1800df6d2  call    cs:__imp_GetLastError
0x1800df6d8  mov     edi, eax
0x1800df6da  call    cs:__imp_CurrentIP
0x1800df6e0  mov     rbx, rax
0x1800df6e3  mov     r8d, r12d
0x1800df6e6  lea     rdx, aGetNullAtDThPa; "Get NULL at %d-th paths"
0x1800df6ed  mov     ecx, 2000000h; unsigned int
0x1800df6f2  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800df6f7  mov     [rsp+258h+var_208], r13d
0x1800df6fc  mov     [rsp+258h+var_210], r13
0x1800df701  mov     [rsp+258h+var_218], edi
0x1800df705  mov     qword ptr [rsp+258h+var_220], rbx
0x1800df70a  lea     rcx, aCnewsystemQueu_58; "CNewSystem::QueueAddCbsPackage"
0x1800df711  mov     qword ptr [rsp+258h+var_228], rcx
0x1800df716  lea     rcx, aBaseNtsetupSet_34; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1800df71d  mov     qword ptr [rsp+258h+var_230], rcx
0x1800df722  mov     [rsp+258h+var_238], 3201h
0x1800df72a  xor     r9d, r9d
0x1800df72d  lea     r8, aD_0; "D"
0x1800df734  mov     edx, 0C8000h
0x1800df739  mov     rcx, rax
0x1800df73c  call    cs:__imp_WdsSetupLogMessageW
0x1800df742  jmp     loc_1800DF3E8
0x1800df747  test    byte ptr [r14+304h], 2
0x1800df74f  jz      loc_1800DFF6B
0x1800df755  mov     [rsp+258h+var_1F8], 8007000Dh
0x1800df75d  mov     rax, [r14+40h]
0x1800df761  test    byte ptr [rax+38h], 2
0x1800df765  jz      loc_1800DFF6B
0x1800df76b  mov     rcx, r14; this
0x1800df76e  call    ?ExitReadOnlyMode@CDeploymentBase@@QEAAXXZ; CDeploymentBase::ExitReadOnlyMode(void)
0x1800df773  lea     rcx, [r14+10h]; lpCriticalSection
0x1800df777  call    cs:__imp_EnterCriticalSection
0x1800df77d  mov     [rsp+258h+var_1F4], r13d
0x1800df782  lea     rcx, [rsp+258h+var_88]
0x1800df78a  call    cs:__imp_??0Exception@UnBCL@@QEAA@XZ; UnBCL::Exception::Exception(void)
0x1800df790  lea     rax, ??_7CXXXXXHandledException@?BE@??QueueAddCbsPackage@CNewSystem@@IEAAJHPEAV?$CCbsPackageList@PEAV?$DictionaryEntry@PEAVString@UnBCL@@_K@UnBCL@@@@HW4SP_ERROR_HANDLING@SetupPlatform@@KW4OP_OPERATION_ID@@@Z@6B@; const `CNewSystem::QueueAddCbsPackage(int,CCbsPackageList<UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *> *,int,SetupPlatform::SP_ERROR_HANDLING,ulong,OP_OPERATION_ID)'::`20'::CXXXXXHandledException::`vftable'
0x1800df797  mov     [rsp+258h+var_88], rax
0x1800df79f  mov     eax, [r14+1CCh]
0x1800df7a6  cmp     eax, r15d
0x1800df7a9  jbe     short loc_1800DF7B4
0x1800df7ab  cmp     eax, 6
0x1800df7ae  jnz     loc_1800E04F3
0x1800df7b4  mov     edi, 0B0h
0x1800df7b9  mov     ecx, edi
0x1800df7bb  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800df7c1  mov     rbx, rax
0x1800df7c4  mov     [rsp+258h+var_1B0], rax
0x1800df7cc  test    rax, rax
0x1800df7cf  jz      short loc_1800DF7E7
0x1800df7d1  mov     r8d, edi; Size
0x1800df7d4  xor     edx, edx; Val
0x1800df7d6  mov     rcx, rax; void *
0x1800df7d9  call    memset_0
0x1800df7de  mov     rcx, rbx
0x1800df7e1  call    ??0?$CCbsPackageList@PEAVString@UnBCL@@@@QEAA@XZ; CCbsPackageList<UnBCL::String *>::CCbsPackageList<UnBCL::String *>(void)
0x1800df7e6  nop
0x1800df7e7  mov     rdx, rax
0x1800df7ea  lea     rcx, [rsp+258h+var_160]
0x1800df7f2  call    ??0?$SmartPtr@V?$CCbsPackageList@PEAVString@UnBCL@@@@@UnBCL@@QEAA@PEAV?$CCbsPackageList@PEAVString@UnBCL@@@@@Z; UnBCL::SmartPtr<CCbsPackageList<UnBCL::String *>>::SmartPtr<CCbsPackageList<UnBCL::String *>>(CCbsPackageList<UnBCL::String *> *)
0x1800df7f7  nop
0x1800df7f8  mov     rcx, [rsp+258h+var_158]
0x1800df800  mov     rax, [rcx]
0x1800df803  mov     edx, r15d
0x1800df806  mov     rax, [rax+28h]
0x1800df80a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df80f  xor     ecx, ecx
0x1800df811  mov     [rsp+258h+var_1B8], rcx
0x1800df819  xor     r12d, r12d
0x1800df81c  mov     [rsp+258h+var_1B0], r12
0x1800df824  xor     edi, edi
0x1800df826  mov     [rsp+258h+var_1EC], edi
0x1800df82a  cmp     edi, [rsp+258h+var_1F0]
0x1800df82e  jnb     loc_1800E0258
0x1800df834  mov     rax, [rsi+8]
0x1800df838  movsxd  rcx, dword ptr [rax+10h]
0x1800df83c  add     rcx, 8
0x1800df840  add     rcx, rsi
0x1800df843  mov     rax, [rcx]
0x1800df846  mov     edx, edi
0x1800df848  mov     rax, [rax+18h]
0x1800df84c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df851  mov     rcx, [rax]
0x1800df854  mov     rax, [rcx]
0x1800df857  mov     rax, [rax]
0x1800df85a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df85f  mov     rcx, rax
0x1800df862  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1800df868  mov     r12, rax
0x1800df86b  mov     rcx, rax; lpFileName
0x1800df86e  call    cs:__imp_GetFileAttributesW
0x1800df874  cmp     eax, 0FFFFFFFFh
0x1800df877  jz      loc_1800E00DC
0x1800df87d  mov     rcx, r12; lpFileName
0x1800df880  call    cs:__imp_GetFileAttributesW
0x1800df886  mov     ebx, eax
0x1800df888  and     ebx, 10h
0x1800df88b  mov     dword ptr [rsp+258h+var_1C8], ebx
0x1800df892  mov     rcx, r12; lpFileName
0x1800df895  call    ?SPGetFileSize@@YA_KPEBG@Z; SPGetFileSize(ushort const *)
0x1800df89a  mov     [rsp+258h+var_1D8], rax
0x1800df8a2  mov     rcx, [rsi+8]
0x1800df8a6  movsxd  rcx, dword ptr [rcx+10h]
0x1800df8aa  add     rcx, 8
0x1800df8ae  add     rcx, rsi
0x1800df8b1  mov     rdx, [rcx]
0x1800df8b4  mov     rax, [rdx+18h]
0x1800df8b8  mov     edx, edi
0x1800df8ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df8bf  mov     rcx, [rax]
0x1800df8c2  mov     rax, [rcx]
0x1800df8c5  mov     rax, [rax+10h]
0x1800df8c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df8ce  mov     [rsp+258h+var_1C0], rax
0x1800df8d6  test    rax, rax
0x1800df8d9  jnz     short loc_1800DF900
0x1800df8db  mov     rax, [rsp+258h+var_1D8]
0x1800df8e3  test    ebx, ebx
0x1800df8e5  jnz     short loc_1800DF8F8
0x1800df8e7  lea     rdi, [rax+rax*4]
0x1800df8eb  add     rdi, rdi
  ... truncated ...
```
