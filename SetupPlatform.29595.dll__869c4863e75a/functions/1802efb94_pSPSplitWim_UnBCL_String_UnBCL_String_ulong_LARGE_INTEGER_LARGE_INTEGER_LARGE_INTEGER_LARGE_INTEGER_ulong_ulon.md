# pSPSplitWim(UnBCL::String *,UnBCL::String *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,void *,int)

- ea: `0x1802efb94`
- end: `0x1802f0a60`
- name: `?pSPSplitWim@@YAJPEAVString@UnBCL@@0P6AKT_LARGE_INTEGER@@111KKPEAX22@Z22H@Z`
- size: `3788`
- prototype: `void __fastcall __noreturn(struct UnBCL::String *, struct UnBCL::String *, unsigned int (*)(union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, unsigned int, void *, void *, void *), void *, void *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, installer_update`

## callers

- `0x1802cd8b0`

## callees

- `0x180013804`
- `0x18001413d`
- `0x1800197c0`
- `0x180057dec`
- `0x1802efb94`
- `0x1803f2ca0`
- `0x180406640`
- `0x1804bbfa0`
- `0x180509010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1802efd1a`
- `KERNEL32!GetLastError` at `0x1802efeaa`
- `KERNEL32!GetLastError` at `0x1802efec2`
- `KERNEL32!GetLastError` at `0x1802efee5`
- `KERNEL32!GetLastError` at `0x1802f038f`
- `KERNEL32!GetLastError` at `0x1802f03a7`
- `KERNEL32!GetLastError` at `0x1802f03c3`
- `KERNEL32!GetLastError` at `0x1802f047e`
- `KERNEL32!GetLastError` at `0x1802f0496`
- `KERNEL32!GetLastError` at `0x1802f04b2`
- `KERNEL32!GetLastError` at `0x1802f056d`
- `KERNEL32!GetLastError` at `0x1802f0580`
- `KERNEL32!GetLastError` at `0x1802f0595`
- `KERNEL32!GetLastError` at `0x1802f0650`
- `KERNEL32!GetLastError` at `0x1802f0663`
- `KERNEL32!GetLastError` at `0x1802f0682`
- `KERNEL32!GetLastError` at `0x1802f072d`
- `KERNEL32!GetLastError` at `0x1802f07dc`
- `KERNEL32!GetLastError` at `0x1802f0884`
- `KERNEL32!GetLastError` at `0x1802f0897`
- `KERNEL32!GetLastError` at `0x1802f08ac`
- `KERNEL32!GetLastError` at `0x1802f0972`
- `KERNEL32!GetLastError` at `0x1802f0987`
- `KERNEL32!GetLastError` at `0x1802efd1a`
- `KERNEL32!GetLastError` at `0x1802efeaa`
- `KERNEL32!GetLastError` at `0x1802efec2`
- `KERNEL32!GetLastError` at `0x1802efee5`
- `KERNEL32!GetLastError` at `0x1802f038f`
- `KERNEL32!GetLastError` at `0x1802f03a7`
- `KERNEL32!GetLastError` at `0x1802f03c3`
- `KERNEL32!GetLastError` at `0x1802f047e`
- `KERNEL32!GetLastError` at `0x1802f0496`
- `KERNEL32!GetLastError` at `0x1802f04b2`
- `KERNEL32!GetLastError` at `0x1802f056d`
- `KERNEL32!GetLastError` at `0x1802f0580`
- `KERNEL32!GetLastError` at `0x1802f0595`
- `KERNEL32!GetLastError` at `0x1802f0650`
- `KERNEL32!GetLastError` at `0x1802f0663`
- `KERNEL32!GetLastError` at `0x1802f0682`
- `KERNEL32!GetLastError` at `0x1802f072d`
- `KERNEL32!GetLastError` at `0x1802f07dc`
- `KERNEL32!GetLastError` at `0x1802f0884`
- `KERNEL32!GetLastError` at `0x1802f0897`
- `KERNEL32!GetLastError` at `0x1802f08ac`
- `KERNEL32!GetLastError` at `0x1802f0972`
- `KERNEL32!GetLastError` at `0x1802f0987`
- `KERNEL32!CloseHandle` at `0x1802f0162`
- `KERNEL32!CloseHandle` at `0x1802f0162`
- `KERNEL32!CreateFileW` at `0x1802efe05`
- `KERNEL32!CreateFileW` at `0x1802effd6`
- `KERNEL32!CreateFileW` at `0x1802f0239`
- `KERNEL32!CreateFileW` at `0x1802efe05`
- `KERNEL32!CreateFileW` at `0x1802effd6`
- `KERNEL32!CreateFileW` at `0x1802f0239`
- `KERNEL32!WriteFile` at `0x1802f008b`
- `KERNEL32!WriteFile` at `0x1802f008b`
- `KERNEL32!GetFileSizeEx` at `0x1802efe27`
- `KERNEL32!GetFileSizeEx` at `0x1802efe27`
- `KERNEL32!ReadFile` at `0x1802f0053`
- `KERNEL32!ReadFile` at `0x1802f0053`
- `unbcl!?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802efe46`
- `unbcl!?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802efe46`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802f01a7`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1802f01a7`
- `unbcl!?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802efbfd`
- `unbcl!?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802efc66`
- `unbcl!?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802efbfd`
- `unbcl!?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1802efc66`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1802efd05`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1802efd05`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1802f02ea`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1802f034e`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1802f02ea`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x1802f034e`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1802f026c`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1802f026c`
- `unbcl!?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z` at `0x1802efc2f`
- `unbcl!?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z` at `0x1802efc92`
- `unbcl!?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z` at `0x1802efc2f`
- `unbcl!?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z` at `0x1802efc92`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802efc1d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802efc86`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802efe3d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802efc1d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802efc86`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802efe3d`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802efcdb`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802f0179`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802efcdb`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1802f0179`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802f02ca`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802f032e`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802f02ca`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1802f032e`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802efc51`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802efcb4`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802efe6e`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802f01cf`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802efc51`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802efcb4`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802efe6e`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1802f01cf`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802efd33`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802efd4d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802efdd7`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802efe8b`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802efeff`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802effab`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802f018b`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802f0206`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802f03dc`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802f04cb`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802f05ae`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802f08c5`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802efd33`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802efd4d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802efdd7`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802efe8b`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802efeff`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802effab`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802f018b`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802f0206`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802f03dc`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802f04cb`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802f05ae`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1802f08c5`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802efd3c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802efd56`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802efde0`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802efe94`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802eff08`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802effb4`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802f0194`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802f020f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802f03e5`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802f04d4`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802f05b7`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802f08ce`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802efd3c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802efd56`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802efde0`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802efe94`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802eff08`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802effb4`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802f0194`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802f020f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802f03e5`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802f04d4`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802f05b7`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1802f08ce`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802efc5d`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802efcc0`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802efe7d`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802f01de`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802f0259`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802f027b`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802f028a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802f0299`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802efc5d`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802efcc0`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802efe7d`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802f01de`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802f0259`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802f027b`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802f028a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802f0299`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802efc0e`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802efc3d`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802efc77`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802efca0`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802efe57`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802f01b8`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802efc0e`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802efc3d`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802efc77`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802efca0`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802efe57`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802f01b8`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802efdb8`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802eff72`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802f044f`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802f053e`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802f0621`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802f06f3`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802f07a2`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802f0851`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802f093f`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802f09ff`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802efdb8`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802eff72`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802f044f`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802f053e`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802f0621`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802f06f3`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802f07a2`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802f0851`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802f093f`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802f09ff`
- `WDSCORE!CurrentIP` at `0x1802efd22`
- `WDSCORE!CurrentIP` at `0x1802efeee`

## string_xrefs

- `0x1802f09a2`: `%hs: Failed to write file. Error: 0x%08X`
- `0x1802f07f4`: `%hs: Copy operation cancelled by the progress routine.`
- `0x1802f05cb`: `%hs: Failed to open destination file %s. Error: 0x%08X`
- `0x1802f08e2`: `%hs: Failed to open destination file %s. Error: 0x%08X`
- `0x1802f069d`: `%hs: Failed to allocate buffer for copy operation. Error: 0x%08X`
- `0x1802f03f9`: `%hs: Failed to open source file %s. Error: 0x%08X`
- `0x1802f0344`: `PartPath`
- `0x1802f0745`: `%hs: Copy operation cancelled by the cancel parameter.`
- `0x1802eff14`: `pSPSplitWim: Failed to create folder %s (0x%08x)`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall __noreturn pSPSplitWim(
        struct UnBCL::String *a1,
        struct UnBCL::String *a2,
        unsigned int (*a3)(union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, unsigned int, void *, void *, void *),
        void *a4,
        void *a5,
        int a6)
{
  struct UnBCL::String *FullPath; // rax
  const struct UnBCL::String *P; // rax
  struct UnBCL::String *v9; // rax
  struct UnBCL::String *v10; // rax
  const struct UnBCL::String *v11; // rax
  struct UnBCL::String *v12; // rax
  DWORD LastError; // edi
  __int64 v14; // rsi
  UnBCL::String *v15; // rax
  const char *CString; // rbx
  UnBCL::String *v17; // rax
  const char *v18; // rax
  struct tagLOG_PARTIAL_MSG *v19; // rax
  UnBCL::String *v20; // rax
  const WCHAR *v21; // rax
  HANDLE FileW; // rax
  void *v23; // r13
  const struct UnBCL::String *v24; // rax
  struct UnBCL::String *ParentPath; // rax
  UnBCL::String *v26; // rax
  const unsigned __int16 *v27; // rax
  signed int v28; // eax
  bool v29; // sf
  signed int v30; // eax
  unsigned int v31; // ebx
  signed int v32; // esi
  DWORD v33; // r14d
  __int64 v34; // r15
  UnBCL::String *v35; // rax
  const char *v36; // rax
  struct tagLOG_PARTIAL_MSG *v37; // rax
  UnBCL::String *v38; // rax
  const WCHAR *v39; // rax
  HANDLE v40; // r14
  void *v41; // r12
  unsigned int v42; // r15d
  __int64 v43; // rbx
  DWORD v44; // ecx
  int v45; // eax
  int v46; // eax
  UnBCL::String *v47; // rax
  const unsigned __int16 *v48; // rax
  struct UnBCL::String *v49; // rax
  UnBCL::String *v50; // rax
  const WCHAR *v51; // rax
  _QWORD *v52; // rax
  _QWORD *v53; // rbx
  _QWORD *v54; // rax
  _QWORD *v55; // rbx
  signed int v56; // eax
  bool v57; // sf
  signed int v58; // eax
  unsigned int v59; // esi
  DWORD v60; // ebx
  __int64 v61; // rdi
  UnBCL::String *v62; // rax
  const char *v63; // rax
  struct tagLOG_PARTIAL_MSG *v64; // rax
  signed int v65; // eax
  bool v66; // sf
  signed int v67; // eax
  unsigned int v68; // esi
  DWORD v69; // ebx
  __int64 v70; // rdi
  UnBCL::String *v71; // rax
  const char *v72; // rax
  struct tagLOG_PARTIAL_MSG *v73; // rax
  signed int v74; // eax
  bool v75; // sf
  signed int v76; // eax
  DWORD v77; // ebx
  __int64 v78; // rdi
  UnBCL::String *v79; // rax
  const char *v80; // rax
  struct tagLOG_PARTIAL_MSG *v81; // rax
  signed int v82; // eax
  bool v83; // sf
  signed int v84; // eax
  DWORD v85; // edi
  __int64 v86; // rbx
  struct tagLOG_PARTIAL_MSG *v87; // rax
  DWORD v88; // edi
  __int64 v89; // rbx
  struct tagLOG_PARTIAL_MSG *v90; // rax
  DWORD v91; // edi
  __int64 v92; // rbx
  struct tagLOG_PARTIAL_MSG *v93; // rax
  signed int v94; // eax
  bool v95; // sf
  signed int v96; // eax
  DWORD v97; // ebx
  __int64 v98; // rdi
  UnBCL::String *v99; // rax
  const char *v100; // rax
  struct tagLOG_PARTIAL_MSG *v101; // rax
  signed int v102; // eax
  unsigned int v103; // esi
  DWORD v104; // edi
  __int64 v105; // rbx
  struct tagLOG_PARTIAL_MSG *v106; // rax
  __int64 *v107; // rbp
  void *v108; // rcx
  void *v109; // rcx
  void *v110; // rcx
  __int64 *v111; // rdx
  __int64 v112; // [rsp+0h] [rbp-1D8h] BYREF
  int v113; // [rsp+60h] [rbp-178h]
  int v114; // [rsp+64h] [rbp-174h]
  __int64 v115; // [rsp+68h] [rbp-170h]
  _QWORD v116[2]; // [rsp+70h] [rbp-168h] BYREF
  void *v117; // [rsp+80h] [rbp-158h]
  unsigned int (*v118)(union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, unsigned int, void *, void *, void *); // [rsp+88h] [rbp-150h]
  void *v119; // [rsp+90h] [rbp-148h]
  __int64 pExceptionObject; // [rsp+98h] [rbp-140h] BYREF
  __int64 v121; // [rsp+A0h] [rbp-138h] BYREF
  _QWORD *v122; // [rsp+A8h] [rbp-130h] BYREF
  _QWORD *v123; // [rsp+B0h] [rbp-128h] BYREF
  _QWORD *v124; // [rsp+B8h] [rbp-120h] BYREF
  _QWORD *v125; // [rsp+C0h] [rbp-118h] BYREF
  void *v126; // [rsp+C8h] [rbp-110h]
  _QWORD *v127; // [rsp+D0h] [rbp-108h] BYREF
  _QWORD *v128; // [rsp+D8h] [rbp-100h] BYREF
  _QWORD *v129; // [rsp+E0h] [rbp-F8h] BYREF
  _QWORD *v130; // [rsp+E8h] [rbp-F0h] BYREF
  _QWORD *v131; // [rsp+F0h] [rbp-E8h] BYREF
  _BYTE v132[16]; // [rsp+F8h] [rbp-E0h] BYREF
  __int64 v133; // [rsp+108h] [rbp-D0h]
  DWORD NumberOfBytesRead; // [rsp+110h] [rbp-C8h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+114h] [rbp-C4h] BYREF
  _QWORD v136[2]; // [rsp+118h] [rbp-C0h] BYREF
  _BYTE v137[16]; // [rsp+128h] [rbp-B0h] BYREF
  LARGE_INTEGER FileSize; // [rsp+138h] [rbp-A0h] BYREF
  _BYTE v139[16]; // [rsp+140h] [rbp-98h] BYREF
  _BYTE v140[16]; // [rsp+150h] [rbp-88h] BYREF
  _QWORD v141[7]; // [rsp+160h] [rbp-78h] BYREF

  v133 = -2;
  v126 = a4;
  v118 = a3;
  v117 = a5;
  if ( !a1 )
  {
    v52 = UnBCL::Object::operator new(0x38u);
    v53 = v52;
    v117 = v52;
    if ( v52 )
    {
      UnBCL::ArgumentNullException::ArgumentNullException((UnBCL::ArgumentNullException *)v52, L"SrcWimFile");
      *v53 = &UnBCL::ArgumentNullException::`local vftable';
    }
    else
    {
      v53 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v53,
                         "long __cdecl pSPSplitWim(class UnBCL::String *,class UnBCL::String *,unsigned long (__cdecl *)("
                         "union _LARGE_INTEGER,union _LARGE_INTEGER,union _LARGE_INTEGER,union _LARGE_INTEGER,unsigned lo"
                         "ng,unsigned long,void *,void *,void *),void *,void *,int)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  if ( !a2 )
  {
    v54 = UnBCL::Object::operator new(0x38u);
    v55 = v54;
    v117 = v54;
    if ( v54 )
    {
      UnBCL::ArgumentNullException::ArgumentNullException((UnBCL::ArgumentNullException *)v54, L"PartPath");
      *v55 = &UnBCL::ArgumentNullException::`local vftable';
    }
    else
    {
      v55 = 0;
    }
    v121 = AddStackTraceToException<UnBCL::InvalidOperationException>(
             v55,
             "long __cdecl pSPSplitWim(class UnBCL::String *,class UnBCL::String *,unsigned long (__cdecl *)(union _LARGE"
             "_INTEGER,union _LARGE_INTEGER,union _LARGE_INTEGER,union _LARGE_INTEGER,unsigned long,unsigned long,void *,"
             "void *,void *),void *,void *,int)");
    throw (UnBCL::ArgumentNullException **)&v121;
  }
  FullPath = UnBCL::Path::GetFullPath(a1);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v139, FullPath);
  P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v139);
  v9 = UnBCL::Path::WithLongPrefix(P, 1);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v116, v9);
  UnBCL::SmartPtr<UnBCL::String>::operator=(v139, v116);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v116);
  v10 = UnBCL::Path::GetFullPath(a2);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v137, v10);
  v11 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v137);
  v12 = UnBCL::Path::WithLongPrefix(v11, 1);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v116, v12);
  UnBCL::SmartPtr<UnBCL::String>::operator=(v137, v116);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v116);
  v113 = 0;
  FileSize.QuadPart = 0;
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v140);
  v116[0] = -1;
  v115 = -1;
  v119 = 0;
  v114 = 0;
  UnBCL::Exception::Exception((UnBCL::Exception *)v141);
  try
  {
    try
    {
      v141[0] = &`pSPSplitWim'::`11'::CXXXXXHandledException::`vftable';
      LastError = GetLastError();
      v14 = CurrentIP();
      v15 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v137);
      CString = (const char *)UnBCL::String::get_CString(v15);
      v17 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v139);
      v18 = (const char *)UnBCL::String::get_CString(v17);
      v19 = ConstructPartialMsgW(0x4000000u, "Splitting WIM file %s to %s", v18, CString);
      WdsSetupLogMessageW(
        v19,
        819200,
        L"D",
        0,
        5475,
        L"base\\ntsetup\\setupplatform\\lib\\util\\utilities.cpp",
        L"pSPSplitWim",
        v14,
        LastError,
        0,
        0);
      v20 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v139);
      v21 = UnBCL::String::get_CString(v20);
      FileW = CreateFileW(v21, 0x80000000, 1u, 0, 3u, a6 != 0 ? 0x2000000 : 0, 0);
      v23 = FileW;
      v116[0] = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        v56 = GetLastError();
        v57 = v56 < 0;
        if ( v56 > 0 )
          v57 = 1;
        if ( v57 )
        {
          v58 = GetLastError();
          v59 = v58;
          if ( v58 > 0 )
            v59 = (unsigned __int16)v58 | 0x80070000;
        }
        else
        {
          v59 = -2147467259;
        }
        v113 = v59;
        v60 = GetLastError();
        v61 = CurrentIP();
        v62 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v139);
        v63 = (const char *)UnBCL::String::get_CString(v62);
        v64 = ConstructPartialMsgW(
                0x4000000u,
                "%hs: Failed to open source file %s. Error: 0x%08X",
                "pSPSplitWim",
                v63,
                v59);
        WdsSetupLogMessageW(
          v64,
          819200,
          L"D",
          0,
          5489,
          L"base\\ntsetup\\setupplatform\\lib\\util\\utilities.cpp",
          L"pSPSplitWim",
          v61,
          v60,
          0,
          0);
        v114 = 1;
        v122 = v141;
        throw (`pSPSplitWim(UnBCL::String *,UnBCL::String *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,void *,int)'::`11'::CXXXXXHandledException **)&v122;
      }
      if ( !GetFileSizeEx(FileW, &FileSize) )
      {
        v65 = GetLastError();
        v66 = v65 < 0;
        if ( v65 > 0 )
          v66 = 1;
        if ( v66 )
        {
          v67 = GetLastError();
          v68 = v67;
          if ( v67 > 0 )
            v68 = (unsigned __int16)v67 | 0x80070000;
        }
        else
        {
          v68 = -2147467259;
        }
        v113 = v68;
        v69 = GetLastError();
        v70 = CurrentIP();
        v71 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v139);
        v72 = (const char *)UnBCL::String::get_CString(v71);
        v73 = ConstructPartialMsgW(
                0x4000000u,
                "%hs: Failed to get the size for source file %s. Error: 0x%08X",
                "pSPSplitWim",
                v72,
                v68);
        WdsSetupLogMessageW(
          v73,
          819200,
          L"D",
          0,
          5496,
          L"base\\ntsetup\\setupplatform\\lib\\util\\utilities.cpp",
          L"pSPSplitWim",
          v70,
          v69,
          0,
          0);
        v114 = 1;
        v123 = v141;
        throw (`pSPSplitWim(UnBCL::String *,UnBCL::String *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,void *,int)'::`11'::CXXXXXHandledException **)&v123;
      }
      v24 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v137);
      ParentPath = UnBCL::Path::GetParentPath(v24);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v136, ParentPath);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v140, v136);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v136);
      v26 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v140);
      v27 = UnBCL::String::get_CString(v26);
      if ( (unsigned int)CreatePath(v27) )
      {
        v32 = -2147467259;
      }
      else
      {
        v28 = GetLastError();
        v29 = v28 < 0;
        if ( v28 > 0 )
          v29 = 1;
        if ( v29 )
        {
          v30 = GetLastError();
          v31 = v30;
          if ( v30 > 0 )
            v31 = (unsigned __int16)v30 | 0x80070000;
          v32 = -2147467259;
        }
        else
        {
          v32 = -2147467259;
          v31 = -2147467259;
        }
        v33 = GetLastError();
        v34 = CurrentIP();
        v35 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v140);
        v36 = (const char *)UnBCL::String::get_CString(v35);
        v37 = ConstructPartialMsgW(0x3000000u, "pSPSplitWim: Failed to create folder %s (0x%08x)", v36, v31);
        WdsSetupLogMessageW(
          v37,
          819200,
          L"D",
          0,
          5504,
          L"base\\ntsetup\\setupplatform\\lib\\util\\utilities.cpp",
          L"pSPSplitWim",
          v34,
          v33,
          0,
          0);
        v113 = 0;
      }
      v38 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v137);
      v39 = UnBCL::String::get_CString(v38);
      v40 = CreateFileW(v39, 0x40000000u, 0, 0, 1u, a6 != 0 ? 167772160 : 0x8000000, 0);
      v115 = (__int64)v40;
      if ( v40 == (HANDLE)-1LL )
      {
        v74 = GetLastError();
        v75 = v74 < 0;
        if ( v74 > 0 )
          v75 = 1;
        if ( v75 )
        {
          v76 = GetLastError();
          v32 = v76;
          if ( v76 > 0 )
            v32 = (unsigned __int16)v76 | 0x80070000;
        }
        v113 = v32;
        v77 = GetLastError();
        v78 = CurrentIP();
        v79 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v137);
        v80 = (const char *)UnBCL::String::get_CString(v79);
        v81 = ConstructPartialMsgW(
                0x4000000u,
                "%hs: Failed to open destination file %s. Error: 0x%08X",
                "pSPSplitWim",
                v80,
                v32);
        WdsSetupLogMessageW(
          v81,
          819200,
          L"D",
          0,
          5520,
          L"base\\ntsetup\\setupplatform\\lib\\util\\utilities.cpp",
          L"pSPSplitWim",
          v78,
          v77,
          0,
          0);
        v114 = 1;
        v124 = v141;
        throw (`pSPSplitWim(UnBCL::String *,UnBCL::String *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,void *,int)'::`11'::CXXXXXHandledException **)&v124;
      }
      v41 = operator new[](0x400000u);
      v119 = v41;
      if ( !v41 )
      {
        v82 = GetLastError();
        v83 = v82 < 0;
        if ( v82 > 0 )
          v83 = 1;
        if ( v83 )
        {
          v84 = GetLastError();
          v32 = v84;
          if ( v84 > 0 )
            v32 = (unsigned __int16)v84 | 0x80070000;
          if ( v32 >= 0 )
            v32 = -2147024888;
        }
        v113 = v32;
        v85 = GetLastError();
        v86 = CurrentIP();
        v87 = ConstructPartialMsgW(
                0x4000000u,
                "%hs: Failed to allocate buffer for copy operation. Error: 0x%08X",
                "pSPSplitWim",
                v32);
        WdsSetupLogMessageW(
          v87,
          819200,
          L"D",
          0,
          5532,
          L"base\\ntsetup\\setupplatform\\lib\\util\\utilities.cpp",
          L"pSPSplitWim",
          v86,
          v85,
          0,
          0);
        v114 = 1;
        v125 = v141;
        throw (`pSPSplitWim(UnBCL::String *,UnBCL::String *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,void *,int)'::`11'::CXXXXXHandledException **)&v125;
      }
      v136[0] = 0;
      NumberOfBytesRead = 0;
      NumberOfBytesWritten = 0;
      v42 = 1;
      v43 = 0;
      while ( ReadFile(v23, v41, 0x400000u, &NumberOfBytesRead, 0) )
      {
        NumberOfBytesWritten = 0;
        if ( !WriteFile(v40, v41, NumberOfBytesRead, &NumberOfBytesWritten, 0)
          || (v44 = NumberOfBytesRead, NumberOfBytesWritten != NumberOfBytesRead) )
        {
          v102 = GetLastError();
          v103 = v102;
          if ( v102 > 0 )
            v103 = (unsigned __int16)v102 | 0x80070000;
          v113 = v103;
          v104 = GetLastError();
          v105 = CurrentIP();
          v106 = ConstructPartialMsgW(0x4000000u, "%hs: Failed to write file. Error: 0x%08X", "pSPSplitWim", v103);
          WdsSetupLogMessageW(
            v106,
            819200,
            L"D",
            0,
            5546,
            L"base\\ntsetup\\setupplatform\\lib\\util\\utilities.cpp",
            L"pSPSplitWim",
            v105,
            v104,
            0,
            0);
          v114 = 1;
          v130 = v141;
          throw (`pSPSplitWim(UnBCL::String *,UnBCL::String *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,void *,int)'::`11'::CXXXXXHandledException **)&v130;
        }
        v43 += NumberOfBytesRead;
        if ( v118 )
        {
          v45 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD))v118)(
                  (LARGE_INTEGER)FileSize.QuadPart,
                  v43,
                  (LARGE_INTEGER)FileSize.QuadPart,
                  v43,
                  1,
                  0,
                  v23,
                  v40,
                  v126)
              - 1;
          if ( !v45 || (v46 = v45 - 1) == 0 )
          {
            v113 = -2147023673;
            v91 = GetLastError();
            v92 = CurrentIP();
            v93 = ConstructPartialMsgW(
                    0x4000000u,
                    "%hs: Copy operation cancelled by the progress routine.",
                    "pSPSplitWim");
            WdsSetupLogMessageW(
              v93,
              819200,
              L"D",
              0,
              5568,
              L"base\\ntsetup\\setupplatform\\lib\\util\\utilities.cpp",
              L"pSPSplitWim",
              v92,
              v91,
              0,
              0);
            v114 = 1;
            v127 = v141;
            throw (`pSPSplitWim(UnBCL::String *,UnBCL::String *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,void *,int)'::`11'::CXXXXXHandledException **)&v127;
          }
          v44 = NumberOfBytesRead;
          if ( v46 == 1 )
            v118 = 0;
        }
        if ( v44 < 0x400000 )
          break;
        if ( (unsigned int)SPIsEventSet(v117) )
        {
          v113 = -2147023673;
          v88 = GetLastError();
          v89 = CurrentIP();
          v90 = ConstructPartialMsgW(
                  0x4000000u,
                  "%hs: Copy operation cancelled by the cancel parameter.",
                  "pSPSplitWim");
          WdsSetupLogMessageW(
            v90,
            819200,
            L"D",
            0,
            5582,
            L"base\\ntsetup\\setupplatform\\lib\\util\\utilities.cpp",
            L"pSPSplitWim",
            v89,
            v88,
            0,
            0);
          v114 = 1;
          v128 = v141;
          throw (`pSPSplitWim(UnBCL::String *,UnBCL::String *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,void *,int)'::`11'::CXXXXXHandledException **)&v128;
        }
        if ( v43 == 3355443200LL * v42 )
        {
          CloseHandle(v40);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v136);
          ++v42;
          v47 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v137);
          v48 = UnBCL::String::get_CString(v47);
          v49 = UnBCL::String::Format(L"%s.00%d", v48, v42);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v132, v49);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v136, v132);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v132);
          v50 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v136);
          v51 = UnBCL::String::get_CString(v50);
          v40 = CreateFileW(v51, 0x40000000u, 0, 0, 1u, a6 != 0 ? 167772160 : 0x8000000, 0);
          v115 = (__int64)v40;
          if ( v40 == (HANDLE)-1LL )
          {
            v94 = GetLastError();
            v95 = v94 < 0;
            if ( v94 > 0 )
              v95 = 1;
            if ( v95 )
            {
              v96 = GetLastError();
              v32 = v96;
              if ( v96 > 0 )
                v32 = (unsigned __int16)v96 | 0x80070000;
            }
            v113 = v32;
            v97 = GetLastError();
            v98 = CurrentIP();
            v99 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v136);
            v100 = (const char *)UnBCL::String::get_CString(v99);
            v101 = ConstructPartialMsgW(
                     0x4000000u,
                     "%hs: Failed to open destination file %s. Error: 0x%08X",
                     "pSPSplitWim",
                     v100,
                     v32);
            WdsSetupLogMessageW(
              v101,
              819200,
              L"D",
              0,
              5617,
              L"base\\ntsetup\\setupplatform\\lib\\util\\utilities.cpp",
              L"pSPSplitWim",
              v98,
              v97,
              0,
              0);
            v114 = 1;
            v129 = v141;
            throw (`pSPSplitWim(UnBCL::String *,UnBCL::String *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,void *,int)'::`11'::CXXXXXHandledException **)&v129;
          }
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v136);
        }
      }
    }
    catch ( UnBCL::YAJPEAVString:: )
    {
      pSPSplitWim_::_1_::catch_14();
      __eh34_caught_type(1, UnBCL::YAJPEAVString::`pSPSplitWim'::`12'::CXXXXXTemp * `RTTI Type Descriptor');
    }
    v114 = 1;
    v131 = v141;
    throw (`pSPSplitWim(UnBCL::String *,UnBCL::String *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,void *,int)'::`11'::CXXXXXHandledException **)&v131;
  }
  catch ( UnBCL::Exception * )
  {
    v111 = &v112;
    v107 = v111;
    v108 = (void *)v111[18];
    if ( v108 )
      operator delete[](v108);
    v109 = (void *)v107[13];
    if ( v109 != (void *)-1LL )
      CloseHandle(v109);
    v110 = (void *)v107[14];
    if ( v110 != (void *)-1LL )
      CloseHandle(v110);
    if ( !*((_DWORD *)v107 + 25) )
      throw;
    UnBCL::Exception::~Exception((UnBCL::Exception *)v141);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v140);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v137);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v139);
  }
}

```

## disassembly

```asm
0x1802efb94  push    rbx
0x1802efb96  push    rsi
0x1802efb97  push    rdi
0x1802efb98  push    r12
0x1802efb9a  push    r13
0x1802efb9c  push    r14
0x1802efb9e  push    r15
0x1802efba0  sub     rsp, 1A0h
0x1802efba7  mov     [rsp+1D8h+var_D0], 0FFFFFFFFFFFFFFFEh
0x1802efbb3  mov     rax, cs:__security_cookie
0x1802efbba  xor     rax, rsp
0x1802efbbd  mov     [rsp+1D8h+var_40], rax
0x1802efbc5  mov     [rsp+1D8h+var_110], r9
0x1802efbcd  mov     [rsp+1D8h+var_150], r8
0x1802efbd5  mov     rbx, rdx
0x1802efbd8  mov     rax, [rsp+1D8h+arg_20]
0x1802efbe0  mov     [rsp+1D8h+var_158], rax
0x1802efbe8  xor     r15d, r15d
0x1802efbeb  test    rcx, rcx
0x1802efbee  jz      loc_1802F02C6
0x1802efbf4  test    rbx, rbx
0x1802efbf7  jz      loc_1802F032B
0x1802efbfd  call    cs:__imp_?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFullPath(UnBCL::String const *)
0x1802efc03  mov     rdx, rax
0x1802efc06  lea     rcx, [rsp+1D8h+var_98]
0x1802efc0e  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802efc14  nop
0x1802efc15  lea     rcx, [rsp+1D8h+var_98]
0x1802efc1d  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1802efc23  mov     rcx, rax
0x1802efc26  mov     r12d, 1
0x1802efc2c  mov     edx, r12d
0x1802efc2f  call    cs:__imp_?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z; UnBCL::Path::WithLongPrefix(UnBCL::String const *,int)
0x1802efc35  mov     rdx, rax
0x1802efc38  lea     rcx, [rsp+1D8h+var_168]
0x1802efc3d  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802efc43  nop
0x1802efc44  lea     rdx, [rsp+1D8h+var_168]
0x1802efc49  lea     rcx, [rsp+1D8h+var_98]
0x1802efc51  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1802efc57  nop
0x1802efc58  lea     rcx, [rsp+1D8h+var_168]
0x1802efc5d  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802efc63  mov     rcx, rbx
0x1802efc66  call    cs:__imp_?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFullPath(UnBCL::String const *)
0x1802efc6c  mov     rdx, rax
0x1802efc6f  lea     rcx, [rsp+1D8h+var_B0]
0x1802efc77  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802efc7d  nop
0x1802efc7e  lea     rcx, [rsp+1D8h+var_B0]
0x1802efc86  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1802efc8c  mov     rcx, rax
0x1802efc8f  mov     edx, r12d
0x1802efc92  call    cs:__imp_?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z; UnBCL::Path::WithLongPrefix(UnBCL::String const *,int)
0x1802efc98  mov     rdx, rax
0x1802efc9b  lea     rcx, [rsp+1D8h+var_168]
0x1802efca0  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802efca6  nop
0x1802efca7  lea     rdx, [rsp+1D8h+var_168]
0x1802efcac  lea     rcx, [rsp+1D8h+var_B0]
0x1802efcb4  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1802efcba  nop
0x1802efcbb  lea     rcx, [rsp+1D8h+var_168]
0x1802efcc0  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802efcc6  mov     [rsp+1D8h+var_178], r15d
0x1802efccb  mov     qword ptr [rsp+1D8h+FileSize], r15
0x1802efcd3  lea     rcx, [rsp+1D8h+var_88]
0x1802efcdb  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x1802efce1  nop
0x1802efce2  or      r14, 0FFFFFFFFFFFFFFFFh
0x1802efce6  mov     [rsp+1D8h+var_168], r14
0x1802efceb  mov     [rsp+1D8h+var_170], r14
0x1802efcf0  mov     [rsp+1D8h+var_148], r15
0x1802efcf8  mov     [rsp+1D8h+var_174], r15d
0x1802efcfd  lea     rcx, [rsp+1D8h+var_78]
0x1802efd05  call    cs:__imp_??0Exception@UnBCL@@QEAA@XZ; UnBCL::Exception::Exception(void)
0x1802efd0b  lea     rax, ??_7CXXXXXHandledException@?L@??pSPSplitWim@@YAJPEAVString@UnBCL@@0P6AKT_LARGE_INTEGER@@111KKPEAX22@Z22H@Z@6B@; const `pSPSplitWim(UnBCL::String *,UnBCL::String *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,void *,int)'::`11'::CXXXXXHandledException::`vftable'
0x1802efd12  mov     [rsp+1D8h+var_78], rax
0x1802efd1a  call    cs:__imp_GetLastError
0x1802efd20  mov     edi, eax
0x1802efd22  call    cs:__imp_CurrentIP
0x1802efd28  mov     rsi, rax
0x1802efd2b  lea     rcx, [rsp+1D8h+var_B0]
0x1802efd33  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802efd39  mov     rcx, rax
0x1802efd3c  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802efd42  mov     rbx, rax
0x1802efd45  lea     rcx, [rsp+1D8h+var_98]
0x1802efd4d  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802efd53  mov     rcx, rax
0x1802efd56  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802efd5c  mov     r9, rbx
0x1802efd5f  mov     r8, rax
0x1802efd62  lea     rdx, aSplittingWimFi; "Splitting WIM file %s to %s"
0x1802efd69  mov     ecx, 4000000h; unsigned int
0x1802efd6e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1802efd73  mov     [rsp+1D8h+var_188], r15d
0x1802efd78  mov     [rsp+1D8h+var_190], r15
0x1802efd7d  mov     dword ptr [rsp+1D8h+var_198], edi
0x1802efd81  mov     [rsp+1D8h+var_1A0], rsi
0x1802efd86  lea     rcx, aPspsplitwim; "pSPSplitWim"
0x1802efd8d  mov     [rsp+1D8h+hTemplateFile], rcx
0x1802efd92  lea     rcx, aBaseNtsetupSet_29; "base\\ntsetup\\setupplatform\\lib\\util"...
0x1802efd99  mov     qword ptr [rsp+1D8h+dwFlagsAndAttributes], rcx
0x1802efd9e  mov     [rsp+1D8h+dwCreationDisposition], 1563h
0x1802efda6  xor     r9d, r9d
0x1802efda9  lea     r8, aD_0; "D"
0x1802efdb0  mov     edx, 0C8000h
0x1802efdb5  mov     rcx, rax
0x1802efdb8  call    cs:__imp_WdsSetupLogMessageW
0x1802efdbe  mov     eax, [rsp+1D8h+arg_28]
0x1802efdc5  neg     eax
0x1802efdc7  sbb     ebx, ebx
0x1802efdc9  and     ebx, 2000000h
0x1802efdcf  lea     rcx, [rsp+1D8h+var_98]
0x1802efdd7  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802efddd  mov     rcx, rax
0x1802efde0  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802efde6  mov     [rsp+1D8h+hTemplateFile], r15; hTemplateFile
0x1802efdeb  mov     [rsp+1D8h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x1802efdef  mov     [rsp+1D8h+dwCreationDisposition], 3; dwCreationDisposition
0x1802efdf7  xor     r9d, r9d; lpSecurityAttributes
0x1802efdfa  mov     r8d, r12d; dwShareMode
0x1802efdfd  mov     edx, 80000000h; dwDesiredAccess
0x1802efe02  mov     rcx, rax; lpFileName
0x1802efe05  call    cs:__imp_CreateFileW
0x1802efe0b  mov     r13, rax
0x1802efe0e  mov     [rsp+1D8h+var_168], rax
0x1802efe13  cmp     rax, r14
0x1802efe16  jz      loc_1802F038F
0x1802efe1c  lea     rdx, [rsp+1D8h+FileSize]; lpFileSize
0x1802efe24  mov     rcx, r13; hFile
0x1802efe27  call    cs:__imp_GetFileSizeEx
0x1802efe2d  test    eax, eax
0x1802efe2f  jz      loc_1802F047E
0x1802efe35  lea     rcx, [rsp+1D8h+var_B0]
0x1802efe3d  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1802efe43  mov     rcx, rax
0x1802efe46  call    cs:__imp_?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetParentPath(UnBCL::String const *)
0x1802efe4c  mov     rdx, rax
0x1802efe4f  lea     rcx, [rsp+1D8h+var_C0]
0x1802efe57  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802efe5d  nop
0x1802efe5e  lea     rdx, [rsp+1D8h+var_C0]
0x1802efe66  lea     rcx, [rsp+1D8h+var_88]
0x1802efe6e  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x1802efe74  nop
0x1802efe75  lea     rcx, [rsp+1D8h+var_C0]
0x1802efe7d  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1802efe83  lea     rcx, [rsp+1D8h+var_88]
0x1802efe8b  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802efe91  mov     rcx, rax
0x1802efe94  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802efe9a  mov     rcx, rax
0x1802efe9d  call    CreatePath
0x1802efea2  test    eax, eax
0x1802efea4  jnz     loc_1802EFF82
0x1802efeaa  call    cs:__imp_GetLastError
0x1802efeb0  mov     edi, 80070000h
0x1802efeb5  test    eax, eax
0x1802efeb7  jle     short loc_1802EFEC0
0x1802efeb9  movzx   eax, ax
0x1802efebc  or      eax, edi
0x1802efebe  test    eax, eax
0x1802efec0  jns     short loc_1802EFEDA
0x1802efec2  call    cs:__imp_GetLastError
0x1802efec8  mov     ebx, eax
0x1802efeca  test    eax, eax
0x1802efecc  jle     short loc_1802EFED3
0x1802efece  movzx   ebx, ax
0x1802efed1  or      ebx, edi
0x1802efed3  mov     esi, 80004005h
0x1802efed8  jmp     short loc_1802EFEE1
0x1802efeda  mov     esi, 80004005h
0x1802efedf  mov     ebx, esi
0x1802efee1  mov     [rsp+1D8h+var_178], ebx
0x1802efee5  call    cs:__imp_GetLastError
0x1802efeeb  mov     r14d, eax
0x1802efeee  call    cs:__imp_CurrentIP
0x1802efef4  mov     r15, rax
0x1802efef7  lea     rcx, [rsp+1D8h+var_88]
0x1802efeff  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802eff05  mov     rcx, rax
0x1802eff08  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802eff0e  mov     r9d, ebx
0x1802eff11  mov     r8, rax
0x1802eff14  lea     rdx, aPspsplitwimFai; "pSPSplitWim: Failed to create folder %s"...
0x1802eff1b  mov     ecx, 3000000h; unsigned int
0x1802eff20  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1802eff25  mov     [rsp+1D8h+var_188], 0
0x1802eff2d  mov     [rsp+1D8h+var_190], 0
0x1802eff36  mov     dword ptr [rsp+1D8h+var_198], r14d
0x1802eff3b  mov     [rsp+1D8h+var_1A0], r15
0x1802eff40  lea     rcx, aPspsplitwim; "pSPSplitWim"
0x1802eff47  mov     [rsp+1D8h+hTemplateFile], rcx
0x1802eff4c  lea     rcx, aBaseNtsetupSet_29; "base\\ntsetup\\setupplatform\\lib\\util"...
0x1802eff53  mov     qword ptr [rsp+1D8h+dwFlagsAndAttributes], rcx
0x1802eff58  mov     [rsp+1D8h+dwCreationDisposition], 1580h
0x1802eff60  xor     r9d, r9d
0x1802eff63  lea     r8, aD_0; "D"
0x1802eff6a  mov     edx, 0C8000h
0x1802eff6f  mov     rcx, rax
0x1802eff72  call    cs:__imp_WdsSetupLogMessageW
0x1802eff78  xor     r15d, r15d
0x1802eff7b  mov     [rsp+1D8h+var_178], r15d
0x1802eff80  jmp     short loc_1802EFF8C
0x1802eff82  mov     edi, 80070000h
0x1802eff87  mov     esi, 80004005h
0x1802eff8c  mov     eax, [rsp+1D8h+arg_28]
0x1802eff93  neg     eax
0x1802eff95  sbb     ebx, ebx
0x1802eff97  and     ebx, 2000000h
0x1802eff9d  add     ebx, 8000000h
0x1802effa3  lea     rcx, [rsp+1D8h+var_B0]
0x1802effab  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1802effb1  mov     rcx, rax
0x1802effb4  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1802effba  mov     [rsp+1D8h+hTemplateFile], r15; hTemplateFile
0x1802effbf  mov     [rsp+1D8h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x1802effc3  mov     [rsp+1D8h+dwCreationDisposition], r12d; dwCreationDisposition
0x1802effc8  xor     r9d, r9d; lpSecurityAttributes
0x1802effcb  xor     r8d, r8d; dwShareMode
0x1802effce  mov     edx, 40000000h; dwDesiredAccess
0x1802effd3  mov     rcx, rax; lpFileName
0x1802effd6  call    cs:__imp_CreateFileW
0x1802effdc  mov     r14, rax
0x1802effdf  mov     [rsp+1D8h+var_170], rax
0x1802effe4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1802effe8  jz      loc_1802F056D
0x1802effee  mov     ecx, 400000h; unsigned __int64
0x1802efff3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1802efff8  mov     r12, rax
0x1802efffb  mov     [rsp+1D8h+var_148], rax
0x1802f0003  test    rax, rax
0x1802f0006  jz      loc_1802F0650
0x1802f000c  mov     [rsp+1D8h+var_C0], 0
0x1802f0018  mov     [rsp+1D8h+NumberOfBytesRead], r15d
0x1802f0020  mov     [rsp+1D8h+NumberOfBytesWritten], r15d
0x1802f0028  mov     r15d, 1
0x1802f002e  mov     rbx, [rsp+1D8h+var_C0]
0x1802f0036  mov     qword ptr [rsp+1D8h+dwCreationDisposition], 0; lpOverlapped
0x1802f003f  lea     r9, [rsp+1D8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1802f0047  mov     r8d, 400000h; nNumberOfBytesToRead
0x1802f004d  mov     rdx, r12; lpBuffer
0x1802f0050  mov     rcx, r13; hFile
0x1802f0053  call    cs:__imp_ReadFile
0x1802f0059  test    eax, eax
0x1802f005b  jz      loc_1802F0A32
0x1802f0061  mov     [rsp+1D8h+NumberOfBytesWritten], 0
0x1802f006c  mov     qword ptr [rsp+1D8h+dwCreationDisposition], 0; lpOverlapped
0x1802f0075  lea     r9, [rsp+1D8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1802f007d  mov     r8d, [rsp+1D8h+NumberOfBytesRead]; nNumberOfBytesToWrite
0x1802f0085  mov     rdx, r12; lpBuffer
0x1802f0088  mov     rcx, r14; hFile
0x1802f008b  call    cs:__imp_WriteFile
0x1802f0091  test    eax, eax
0x1802f0093  jz      loc_1802F0972
0x1802f0099  mov     ecx, [rsp+1D8h+NumberOfBytesRead]
0x1802f00a0  cmp     [rsp+1D8h+NumberOfBytesWritten], ecx
0x1802f00a7  jnz     loc_1802F0972
0x1802f00ad  add     rbx, rcx
0x1802f00b0  mov     rax, [rsp+1D8h+var_150]
0x1802f00b8  test    rax, rax
0x1802f00bb  jz      short loc_1802F0123
0x1802f00bd  mov     rcx, [rsp+1D8h+var_110]
0x1802f00c5  mov     [rsp+1D8h+var_198], rcx
0x1802f00ca  mov     [rsp+1D8h+var_1A0], r14
0x1802f00cf  mov     [rsp+1D8h+hTemplateFile], r13
0x1802f00d4  mov     [rsp+1D8h+dwFlagsAndAttributes], 0
0x1802f00dc  mov     [rsp+1D8h+dwCreationDisposition], 1
0x1802f00e4  mov     r9, rbx
0x1802f00e7  mov     rcx, qword ptr [rsp+1D8h+FileSize]
0x1802f00ef  mov     r8, rcx
0x1802f00f2  mov     rdx, rbx
0x1802f00f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802f00fa  sub     eax, 1
0x1802f00fd  jz      loc_1802F07D4
0x1802f0103  sub     eax, 1
0x1802f0106  jz      loc_1802F07D4
0x1802f010c  mov     ecx, [rsp+1D8h+NumberOfBytesRead]
0x1802f0113  cmp     eax, 1
0x1802f0116  jnz     short loc_1802F0123
0x1802f0118  xor     r8d, r8d
0x1802f011b  mov     [rsp+1D8h+var_150], r8
0x1802f0123  cmp     ecx, 400000h
0x1802f0129  jb      loc_1802F0A32
0x1802f012f  mov     rcx, [rsp+1D8h+var_158]; void *
0x1802f0137  call    ?SPIsEventSet@@YAHPEAX@Z; SPIsEventSet(void *)
0x1802f013c  test    eax, eax
0x1802f013e  jnz     loc_1802F0725
0x1802f0144  mov     eax, r15d
0x1802f0147  mov     ecx, 0C8000000h
0x1802f014c  imul    rax, rcx
0x1802f0150  cmp     rbx, rax
0x1802f0153  jnz     loc_1802F0036
0x1802f0159  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1802f015d  jz      short loc_1802F0171
0x1802f015f  mov     rcx, r14; hObject
0x1802f0162  call    cs:__imp_CloseHandle
0x1802f0168  mov     [rsp+1D8h+var_170], 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```
