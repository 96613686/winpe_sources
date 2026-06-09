# CProcessDrivers::ProcessDriverInstallation(_DismDriverPackage *,_DismDriver * const,uint,IExecutionContext *,uint,UnBCL::Hashtable<UnBCL::String *,int> *,UnBCL::ArrayList<UnBCL::DictionaryEntry<CGlobalPath *,CDriverInstallInfo *> *> *,int &,UnBCL::String *,SP_DRIVER_REFLECT_STATUS *)

- ea: `0x1801b3c20`
- end: `0x1801b5322`
- name: `?ProcessDriverInstallation@CProcessDrivers@@IEAAJPEAU_DismDriverPackage@@QEAU_DismDriver@@IPEAUIExecutionContext@@IPEAV?$Hashtable@PEAVString@UnBCL@@H@UnBCL@@PEAV?$ArrayList@PEAV?$DictionaryEntry@PEAVCGlobalPath@@PEAVCDriverInstallInfo@@@UnBCL@@@6@AEAHPEAVString@6@PEAW4SP_DRIVER_REFLECT_STATUS@@@Z`
- size: `5890`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1801ab850`

## callees

- `0x180057dec`
- `0x1800b4664`
- `0x1800c2e14`
- `0x18012b26c`
- `0x18019ea34`
- `0x1801af718`
- `0x1801b3c20`
- `0x1802f2618`
- `0x180301ae0`
- `0x18036e758`
- `0x18036e81c`
- `0x18036e8e4`
- `0x180509010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801b3cc1`
- `KERNEL32!GetLastError` at `0x1801b3e1b`
- `KERNEL32!GetLastError` at `0x1801b3e87`
- `KERNEL32!GetLastError` at `0x1801b3ef6`
- `KERNEL32!GetLastError` at `0x1801b3f66`
- `KERNEL32!GetLastError` at `0x1801b3fd6`
- `KERNEL32!GetLastError` at `0x1801b4046`
- `KERNEL32!GetLastError` at `0x1801b40b6`
- `KERNEL32!GetLastError` at `0x1801b4144`
- `KERNEL32!GetLastError` at `0x1801b41c9`
- `KERNEL32!GetLastError` at `0x1801b43f5`
- `KERNEL32!GetLastError` at `0x1801b447a`
- `KERNEL32!GetLastError` at `0x1801b44eb`
- `KERNEL32!GetLastError` at `0x1801b4570`
- `KERNEL32!GetLastError` at `0x1801b464c`
- `KERNEL32!GetLastError` at `0x1801b4700`
- `KERNEL32!GetLastError` at `0x1801b47ea`
- `KERNEL32!GetLastError` at `0x1801b48c6`
- `KERNEL32!GetLastError` at `0x1801b4981`
- `KERNEL32!GetLastError` at `0x1801b4a42`
- `KERNEL32!GetLastError` at `0x1801b4aec`
- `KERNEL32!GetLastError` at `0x1801b4ba5`
- `KERNEL32!GetLastError` at `0x1801b4d4b`
- `KERNEL32!GetLastError` at `0x1801b4e30`
- `KERNEL32!GetLastError` at `0x1801b4ec0`
- `KERNEL32!GetLastError` at `0x1801b4f82`
- `KERNEL32!GetLastError` at `0x1801b5073`
- `KERNEL32!GetLastError` at `0x1801b3cc1`
- `KERNEL32!GetLastError` at `0x1801b3e1b`
- `KERNEL32!GetLastError` at `0x1801b3e87`
- `KERNEL32!GetLastError` at `0x1801b3ef6`
- `KERNEL32!GetLastError` at `0x1801b3f66`
- `KERNEL32!GetLastError` at `0x1801b3fd6`
- `KERNEL32!GetLastError` at `0x1801b4046`
- `KERNEL32!GetLastError` at `0x1801b40b6`
- `KERNEL32!GetLastError` at `0x1801b4144`
- `KERNEL32!GetLastError` at `0x1801b41c9`
- `KERNEL32!GetLastError` at `0x1801b43f5`
- `KERNEL32!GetLastError` at `0x1801b447a`
- `KERNEL32!GetLastError` at `0x1801b44eb`
- `KERNEL32!GetLastError` at `0x1801b4570`
- `KERNEL32!GetLastError` at `0x1801b464c`
- `KERNEL32!GetLastError` at `0x1801b4700`
- `KERNEL32!GetLastError` at `0x1801b47ea`
- `KERNEL32!GetLastError` at `0x1801b48c6`
- `KERNEL32!GetLastError` at `0x1801b4981`
- `KERNEL32!GetLastError` at `0x1801b4a42`
- `KERNEL32!GetLastError` at `0x1801b4aec`
- `KERNEL32!GetLastError` at `0x1801b4ba5`
- `KERNEL32!GetLastError` at `0x1801b4d4b`
- `KERNEL32!GetLastError` at `0x1801b4e30`
- `KERNEL32!GetLastError` at `0x1801b4ec0`
- `KERNEL32!GetLastError` at `0x1801b4f82`
- `KERNEL32!GetLastError` at `0x1801b5073`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x1801b51e9`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x1801b51e9`
- `unbcl!?ToLower@String@UnBCL@@QEBAPEAV12@XZ` at `0x1801b4ca6`
- `unbcl!?ToLower@String@UnBCL@@QEBAPEAV12@XZ` at `0x1801b4ca6`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x1801b3de1`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x1801b3de1`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x1801b434c`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x1801b434c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801b3d59`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801b3d80`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801b4371`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801b4676`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801b472a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801b4818`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801b48f4`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801b49ab`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801b4a6c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801b4b16`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801b4bcf`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801b4cef`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801b4d1f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801b3d59`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801b3d80`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801b4371`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801b4676`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801b472a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801b4818`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801b48f4`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801b49ab`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801b4a6c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801b4b16`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801b4bcf`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801b4cef`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801b4d1f`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1801b41e4`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1801b41e4`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1801b3dc6`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1801b4f74`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1801b52ed`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1801b3dc6`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1801b4f74`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1801b52ed`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801b3da1`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801b4229`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801b426f`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801b42c2`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801b4312`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801b4c7c`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801b4f4f`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801b529d`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801b3da1`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801b4229`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801b426f`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801b42c2`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801b4312`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801b4c7c`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801b4f4f`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801b529d`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801b4201`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801b429f`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801b42ef`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801b4c63`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801b5158`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801b5227`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801b5242`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801b5280`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801b4201`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801b429f`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801b42ef`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801b4c63`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801b5158`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801b5227`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801b5242`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801b5280`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1801b424d`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1801b4293`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1801b42e6`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1801b4336`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1801b4cc3`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1801b424d`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1801b4293`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1801b42e6`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1801b4336`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1801b4cc3`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1801b3d67`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1801b4c9d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1801b3d67`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1801b4c9d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801b3d70`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801b437a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801b4584`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801b467f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801b4733`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801b4821`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801b48fd`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801b49b4`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801b4a75`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801b4b1f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801b4bd8`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801b51b3`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801b3d70`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801b437a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801b4584`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801b467f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801b4733`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801b4821`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801b48fd`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801b49b4`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801b4a75`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801b4b1f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801b4bd8`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801b51b3`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801b4341`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801b435a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801b43ef`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801b46f0`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801b47a4`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801b4892`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801b496e`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801b4a25`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801b4ae6`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801b4b90`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801b4c49`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801b4cce`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801b5006`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801b5025`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801b4341`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801b435a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801b43ef`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801b46f0`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801b47a4`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801b4892`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801b496e`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801b4a25`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801b4ae6`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801b4b90`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801b4c49`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801b4cce`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801b5006`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801b5025`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1801b423d`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1801b4283`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1801b42d6`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1801b4326`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1801b4367`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1801b466c`

## string_xrefs

- `0x1801b4f93`: `Ignoring error due to operation configuration.`
- `0x1801b3cd5`: `Failed to create device database, error 0x%08X.`
- `0x1801b3e4f`: `CProcessDrivers::ProcessDriverInstallation`
- `0x1801b3ebe`: `CProcessDrivers::ProcessDriverInstallation`
- `0x1801b3f2e`: `CProcessDrivers::ProcessDriverInstallation`
- `0x1801b3f9e`: `CProcessDrivers::ProcessDriverInstallation`
- `0x1801b400e`: `CProcessDrivers::ProcessDriverInstallation`
- `0x1801b407e`: `CProcessDrivers::ProcessDriverInstallation`
- `0x1801b410c`: `CProcessDrivers::ProcessDriverInstallation`
- `0x1801b4191`: `CProcessDrivers::ProcessDriverInstallation`
- `0x1801b43b2`: `CProcessDrivers::ProcessDriverInstallation`
- `0x1801b4442`: `CProcessDrivers::ProcessDriverInstallation`
- `0x1801b44b3`: `CProcessDrivers::ProcessDriverInstallation`
- `0x1801b4528`: `CProcessDrivers::ProcessDriverInstallation`
- `0x1801b45b8`: `CProcessDrivers::ProcessDriverInstallation`
- `0x1801b46b3`: `CProcessDrivers::ProcessDriverInstallation`
- `0x1801b4767`: `CProcessDrivers::ProcessDriverInstallation`
- `0x1801b4855`: `CProcessDrivers::ProcessDriverInstallation`
- `0x1801b4931`: `CProcessDrivers::ProcessDriverInstallation`
- `0x1801b49e8`: `CProcessDrivers::ProcessDriverInstallation`
- `0x1801b4aa9`: `CProcessDrivers::ProcessDriverInstallation`
- `0x1801b4b53`: `CProcessDrivers::ProcessDriverInstallation`
- `0x1801b4c0c`: `CProcessDrivers::ProcessDriverInstallation`
- `0x1801b4dbc`: `CProcessDrivers::ProcessDriverInstallation`
- `0x1801b4e7f`: `CProcessDrivers::ProcessDriverInstallation`
- `0x1801b4f0f`: `CProcessDrivers::ProcessDriverInstallation`
- `0x1801b4fb7`: `CProcessDrivers::ProcessDriverInstallation`
- `0x1801b50a8`: `CProcessDrivers::ProcessDriverInstallation`
- `0x1801b4a7e`: `  Resolved default install decision for external package (WinPE): %s`
- `0x1801b49bd`: `  Resolved default install decision for external package: %s`
- `0x1801b5084`: `DRVINST: Setup and DISM disagree about boot critical driver status, we will need an extra driver installation phase for WinRE`

## pseudocode

```c
// Hidden C++ exception states: #wind=34
__int64 __fastcall CProcessDrivers::ProcessDriverInstallation(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        UnBCL::String *a5,
        unsigned int a6,
        __int64 a7,
        __int64 a8,
        _DWORD *a9,
        UnBCL::String *a10,
        int *a11)
{
  const unsigned __int16 *v13; // r13
  __int64 v14; // rbx
  struct IDeviceIdDatabase **v15; // rax
  int v16; // edx
  const struct _GUID *v17; // rcx
  int v18; // esi
  DWORD LastError; // edi
  __int64 v20; // rbx
  struct tagLOG_PARTIAL_MSG *v21; // rax
  int v22; // r14d
  __int64 (__fastcall ***v23)(_QWORD, __int64, _QWORD, const unsigned __int16 *); // rsi
  __int64 (__fastcall *v24)(_QWORD, __int64, _QWORD, const unsigned __int16 *); // r14
  UnBCL::String *v25; // rax
  const unsigned __int16 *CString; // rdi
  unsigned int v27; // ebx
  __int64 v28; // rax
  BOOL v29; // r13d
  DWORD v30; // edi
  __int64 v31; // rbx
  struct tagLOG_PARTIAL_MSG *v32; // rax
  DWORD v33; // edi
  __int64 v34; // rbx
  struct tagLOG_PARTIAL_MSG *v35; // rax
  DWORD v36; // edi
  __int64 v37; // rbx
  struct tagLOG_PARTIAL_MSG *v38; // rax
  DWORD v39; // edi
  __int64 v40; // rbx
  struct tagLOG_PARTIAL_MSG *v41; // rax
  DWORD v42; // edi
  __int64 v43; // rbx
  struct tagLOG_PARTIAL_MSG *v44; // rax
  DWORD v45; // edi
  __int64 v46; // rbx
  struct tagLOG_PARTIAL_MSG *v47; // rax
  DWORD v48; // edi
  __int64 v49; // rbx
  const unsigned __int16 *v50; // r8
  struct tagLOG_PARTIAL_MSG *v51; // rax
  DWORD v52; // edi
  __int64 v53; // rbx
  const unsigned __int16 *v54; // r8
  struct tagLOG_PARTIAL_MSG *v55; // rax
  DWORD v56; // edi
  int v57; // ebx
  int v58; // ebx
  UnBCL::String *v59; // rax
  bool v60; // zf
  UnBCL::String *v61; // rbx
  UnBCL::String *v62; // rax
  UnBCL::String *v63; // rax
  __int64 v64; // rbx
  __int64 v65; // rcx
  UnBCL::String *P; // rax
  const char *v67; // rax
  struct tagLOG_PARTIAL_MSG *v68; // rax
  DWORD v69; // edi
  __int64 v70; // rbx
  const unsigned __int16 *v71; // r8
  struct tagLOG_PARTIAL_MSG *v72; // rax
  DWORD v73; // edi
  __int64 v74; // rbx
  struct tagLOG_PARTIAL_MSG *v75; // rax
  DWORD v76; // edi
  __int64 v77; // rbx
  struct tagLOG_PARTIAL_MSG *v78; // rax
  UnBCL::String *v79; // r14
  DWORD v80; // edi
  __int64 v81; // rbx
  const char *v82; // rax
  struct tagLOG_PARTIAL_MSG *v83; // rax
  unsigned int v84; // r14d
  unsigned int v85; // r13d
  DWORD v86; // edi
  __int64 v87; // rbx
  __int64 AnswerString; // rax
  __int64 v89; // rax
  UnBCL::String *v90; // rax
  const char *v91; // rax
  struct tagLOG_PARTIAL_MSG *v92; // rax
  DWORD v93; // edi
  __int64 v94; // rbx
  __int64 v95; // rax
  __int64 v96; // rax
  UnBCL::String *v97; // rax
  const char *v98; // rax
  struct tagLOG_PARTIAL_MSG *v99; // rax
  __int64 (__fastcall ***v100)(_QWORD, __int64, _QWORD); // rax
  __int64 (__fastcall ***v101)(_QWORD, __int64, _QWORD); // rbx
  DWORD v102; // edi
  __int64 v103; // rbx
  __int64 v104; // rax
  __int64 v105; // rax
  UnBCL::String *v106; // rax
  const char *v107; // rax
  struct tagLOG_PARTIAL_MSG *v108; // rax
  DWORD v109; // edi
  __int64 v110; // rbx
  __int64 v111; // rax
  __int64 v112; // rax
  UnBCL::String *v113; // rax
  const char *v114; // rax
  struct tagLOG_PARTIAL_MSG *v115; // rax
  DWORD v116; // edi
  __int64 v117; // rbx
  __int64 v118; // rax
  __int64 v119; // rax
  UnBCL::String *v120; // rax
  const char *v121; // rax
  struct tagLOG_PARTIAL_MSG *v122; // rax
  DWORD v123; // edi
  __int64 v124; // rbx
  __int64 v125; // rax
  __int64 v126; // rax
  UnBCL::String *v127; // rax
  const char *v128; // rax
  struct tagLOG_PARTIAL_MSG *v129; // rax
  DWORD v130; // edi
  __int64 v131; // rbx
  __int64 v132; // rax
  __int64 v133; // rax
  UnBCL::String *v134; // rax
  const char *v135; // rax
  struct tagLOG_PARTIAL_MSG *v136; // rax
  DWORD v137; // edi
  __int64 v138; // rbx
  __int64 v139; // rax
  __int64 v140; // rax
  UnBCL::String *v141; // rax
  const char *v142; // rax
  struct tagLOG_PARTIAL_MSG *v143; // rax
  UnBCL::String *v144; // rax
  UnBCL::String *v145; // rbx
  UnBCL::String *v146; // rax
  struct UnBCL::String *v147; // rax
  __int64 v148; // rdi
  unsigned int (__fastcall *v149)(__int64, __int64); // rbx
  __int64 v150; // rax
  __int64 v151; // rdi
  unsigned int (__fastcall *v152)(__int64, __int64); // rbx
  __int64 v153; // rax
  BOOL v154; // eax
  unsigned int v155; // esi
  DWORD v156; // edi
  __int64 v157; // rbx
  const wchar_t *v158; // r9
  const wchar_t *v159; // r8
  struct tagLOG_PARTIAL_MSG *v160; // rax
  __int64 v161; // r8
  int v162; // esi
  DWORD v163; // edi
  __int64 v164; // rbx
  const wchar_t *v165; // r8
  struct tagLOG_PARTIAL_MSG *v166; // rax
  int v167; // ecx
  DWORD v168; // edi
  __int64 v169; // rbx
  const wchar_t *v170; // r8
  struct tagLOG_PARTIAL_MSG *v171; // rax
  struct UnBCL::String *v172; // rax
  int v173; // ebx
  DWORD v174; // edi
  __int64 v175; // rbx
  struct tagLOG_PARTIAL_MSG *v176; // rax
  int v178; // eax
  unsigned int v179; // esi
  DWORD v180; // edi
  __int64 v181; // rbx
  struct tagLOG_PARTIAL_MSG *v182; // rax
  UnBCL::String *v183; // rdi
  UnBCL::MultiSz *v184; // rax
  UnBCL::MultiSz *v185; // rbx
  const unsigned __int16 *v186; // rax
  int v187; // ebx
  _OWORD *v188; // r12
  __int64 v189; // r14
  void (__fastcall *v190)(__int64, UnBCL::String *); // r13
  UnBCL::String *v191; // rax
  UnBCL::String *v192; // rdi
  UnBCL::String *v193; // rax
  __int64 v194; // rsi
  CGlobalPath *v195; // rax
  CGlobalPath *v196; // rbx
  struct UnBCL::String *v197; // rax
  char v198; // r15
  void **v199; // [rsp+60h] [rbp-81h] BYREF
  UnBCL::MultiSz *v200; // [rsp+68h] [rbp-79h]
  _BYTE v201[24]; // [rsp+70h] [rbp-71h] BYREF
  _OWORD v202[2]; // [rsp+88h] [rbp-59h] BYREF
  int v203; // [rsp+A8h] [rbp-39h]
  int v204; // [rsp+ACh] [rbp-35h]
  __int64 (__fastcall ***v205)(_QWORD, __int64, _QWORD); // [rsp+B0h] [rbp-31h]
  int v206; // [rsp+B8h] [rbp-29h]
  _QWORD v207[2]; // [rsp+C0h] [rbp-21h] BYREF
  __int64 v208; // [rsp+D0h] [rbp-11h]
  __int64 v209; // [rsp+D8h] [rbp-9h]
  BOOL v210; // [rsp+130h] [rbp+4Fh]
  unsigned int v211; // [rsp+138h] [rbp+57h]
  __int64 v212; // [rsp+140h] [rbp+5Fh] BYREF
  int v213; // [rsp+148h] [rbp+67h]

  v213 = a4;
  v212 = a3;
  v209 = -2;
  v204 = 0;
  v206 = 0;
  v211 = 0;
  v208 = (*(__int64 (__fastcall **)(UnBCL::String *))(*(_QWORD *)a5 + 64LL))(a5);
  v13 = *(const unsigned __int16 **)(a2 + 8);
  v14 = a1 + 408;
  v212 = 0;
  if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(a1 + 408) + 40LL))(a1 + 408, &v212)
    && (v15 = (struct IDeviceIdDatabase **)(**(__int64 (__fastcall ***)(__int64))v14)(a1 + 408),
        v18 = SPCreateDeviceIdDatabase(v17, v16, v15),
        v18 < 0) )
  {
    LastError = GetLastError();
    v20 = CurrentIP();
    v21 = ConstructPartialMsgW(0x2000000u, "Failed to create device database, error 0x%08X.", v18);
    WdsSetupLogMessageW(
      v21,
      819200,
      L"D",
      0,
      252,
      L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
      L"CProcessDrivers::IsDriverPackageApplicable",
      v20,
      LastError,
      0,
      0);
    v22 = 0;
    LODWORD(v205) = 0;
  }
  else
  {
    v23 = (__int64 (__fastcall ***)(_QWORD, __int64, _QWORD, const unsigned __int16 *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(a1 + 408);
    v24 = **v23;
    if ( UnBCL::SmartPtr<UnBCL::String>::get_P(a1 + 264) )
    {
      v25 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(a1 + 264);
      CString = UnBCL::String::get_CString(v25);
    }
    else
    {
      CString = 0;
    }
    if ( UnBCL::SmartPtr<UnBCL::String>::get_P(a1 + 264) )
      v27 = *(_DWORD *)(a1 + 256);
    else
      v27 = 0xFFFF;
    v28 = UnBCL::String::String((UnBCL::String *)v201, v13);
    v22 = v24(v23, v28, v27, CString);
    LODWORD(v205) = v22;
    UnBCL::String::~String((UnBCL::String *)v201);
  }
  v203 = UnBCL::String::Compare(*(const unsigned __int16 **)(a2 + 36), L"{F2E7DD72-6468-4E36-B6F1-6488F42C1B52}", 1);
  v29 = *(_DWORD *)(a2 + 52)
     && (*(_DWORD *)(a1 + 348)
      || (unsigned int)SPIsStorageClass(*(const unsigned __int16 **)(a2 + 36), *(_DWORD *)(a1 + 352)));
  v210 = v29;
  v30 = GetLastError();
  v31 = CurrentIP();
  v32 = ConstructPartialMsgW(0x4000000u, "Deciding injection of external driver package:");
  WdsSetupLogMessageW(
    v32,
    819200,
    L"D",
    0,
    1394,
    L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
    L"CProcessDrivers::ProcessDriverInstallation",
    v31,
    v30,
    0,
    0);
  v33 = GetLastError();
  v34 = CurrentIP();
  v35 = ConstructPartialMsgW(0x4000000u, "  Published Name: %s", *(const char **)a2);
  WdsSetupLogMessageW(
    v35,
    819200,
    L"D",
    0,
    1395,
    L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
    L"CProcessDrivers::ProcessDriverInstallation",
    v34,
    v33,
    0,
    0);
  v36 = GetLastError();
  v37 = CurrentIP();
  v38 = ConstructPartialMsgW(0x4000000u, "  Provider: %s", *(const char **)(a2 + 60));
  WdsSetupLogMessageW(
    v38,
    819200,
    L"D",
    0,
    1396,
    L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
    L"CProcessDrivers::ProcessDriverInstallation",
    v37,
    v36,
    0,
    0);
  v39 = GetLastError();
  v40 = CurrentIP();
  v41 = ConstructPartialMsgW(0x4000000u, "  Class GUID: %s", *(const char **)(a2 + 36));
  WdsSetupLogMessageW(
    v41,
    819200,
    L"D",
    0,
    1397,
    L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
    L"CProcessDrivers::ProcessDriverInstallation",
    v40,
    v39,
    0,
    0);
  v42 = GetLastError();
  v43 = CurrentIP();
  v44 = ConstructPartialMsgW(0x4000000u, "  Class Name: %s", *(const char **)(a2 + 28));
  WdsSetupLogMessageW(
    v44,
    819200,
    L"D",
    0,
    1398,
    L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
    L"CProcessDrivers::ProcessDriverInstallation",
    v43,
    v42,
    0,
    0);
  v45 = GetLastError();
  v46 = CurrentIP();
  v47 = ConstructPartialMsgW(0x4000000u, "  Package file: %s", *(const char **)(a2 + 8));
  WdsSetupLogMessageW(
    v47,
    819200,
    L"D",
    0,
    1399,
    L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
    L"CProcessDrivers::ProcessDriverInstallation",
    v46,
    v45,
    0,
    0);
  v48 = GetLastError();
  v49 = CurrentIP();
  v50 = L"Yes";
  if ( !*(_DWORD *)(a2 + 52) )
    v50 = L"No";
  v51 = ConstructPartialMsgW(0x4000000u, "  DISM boot critical: %s", (const char *)v50);
  WdsSetupLogMessageW(
    v51,
    819200,
    L"D",
    0,
    1400,
    L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
    L"CProcessDrivers::ProcessDriverInstallation",
    v49,
    v48,
    0,
    0);
  v52 = GetLastError();
  v53 = CurrentIP();
  v54 = L"Yes";
  if ( !v29 )
    v54 = L"No";
  v55 = ConstructPartialMsgW(0x4000000u, "  Upgrade boot critical: %s", (const char *)v54);
  WdsSetupLogMessageW(
    v55,
    819200,
    L"D",
    0,
    1401,
    L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
    L"CProcessDrivers::ProcessDriverInstallation",
    v53,
    v52,
    0,
    0);
  v56 = GetLastError();
  v212 = CurrentIP();
  v57 = *(_DWORD *)(a2 + 56);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v199);
  if ( v57 )
  {
    v58 = v57 - 1;
    if ( v58 )
    {
      v59 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
      v60 = v58 == 1;
      v61 = v59;
      v207[0] = v59;
      if ( v60 )
      {
        if ( v59 )
        {
          UnBCL::String::String(v59, L"Signed");
          *(_QWORD *)v61 = &UnBCL::String::`local vftable';
        }
        else
        {
          v61 = 0;
        }
      }
      else if ( v59 )
      {
        UnBCL::String::String(v59, L"Unexpected!");
        *(_QWORD *)v61 = &UnBCL::String::`local vftable';
      }
      else
      {
        v61 = 0;
      }
    }
    else
    {
      v62 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
      v61 = v62;
      v207[0] = v62;
      if ( v62 )
      {
        UnBCL::String::String(v62, L"Unsigned");
        *(_QWORD *)v61 = &UnBCL::String::`local vftable';
      }
      else
      {
        v61 = 0;
      }
    }
  }
  else
  {
    v63 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
    v61 = v63;
    v207[0] = v63;
    if ( v63 )
    {
      UnBCL::String::String(v63, L"Unknown");
      *(_QWORD *)v61 = &UnBCL::String::`local vftable';
    }
    else
    {
      v61 = 0;
    }
  }
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v202, v61);
  UnBCL::SmartPtr<UnBCL::String>::operator=(&v199, v202);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v202);
  v64 = UnBCL::SmartPtr<UnBCL::String>::Steal(&v199);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v199);
  v65 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v201, v64);
  P = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v65);
  v67 = (const char *)UnBCL::String::get_CString(P);
  v68 = ConstructPartialMsgW(0x4000000u, "  Signature status: %s", v67);
  WdsSetupLogMessageW(
    v68,
    819200,
    L"D",
    0,
    1402,
    L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
    L"CProcessDrivers::ProcessDriverInstallation",
    v212,
    v56,
    0,
    0);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v201);
  v69 = GetLastError();
  v70 = CurrentIP();
  v71 = L"Yes";
  if ( !v22 )
    v71 = L"No";
  v72 = ConstructPartialMsgW(0x4000000u, "  Applicable: %s", (const char *)v71);
  WdsSetupLogMessageW(
    v72,
    819200,
    L"D",
    0,
    1403,
    L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
    L"CProcessDrivers::ProcessDriverInstallation",
    v70,
    v69,
    0,
    0);
  v73 = GetLastError();
  v74 = CurrentIP();
  v75 = ConstructPartialMsgW(0x4000000u, "  Number of drivers: %d", v213);
  WdsSetupLogMessageW(
    v75,
    819200,
    L"D",
    0,
    1404,
    L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
    L"CProcessDrivers::ProcessDriverInstallation",
    v74,
    v73,
    0,
    0);
  v76 = GetLastError();
  v77 = CurrentIP();
  v78 = ConstructPartialMsgW(0x4000000u, "  Default answer: %u", *(_DWORD *)(a1 + 368));
  WdsSetupLogMessageW(
    v78,
    819200,
    L"D",
    0,
    1405,
    L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
    L"CProcessDrivers::ProcessDriverInstallation",
    v77,
    v76,
    0,
    0);
  v79 = a10;
  if ( a10 )
  {
    v80 = GetLastError();
    v81 = CurrentIP();
    v82 = (const char *)UnBCL::String::get_CString(v79);
    v83 = ConstructPartialMsgW(0x4000000u, "  Flight ID: %s", v82);
    WdsSetupLogMessageW(
      v83,
      819200,
      L"D",
      0,
      1408,
      L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
      L"CProcessDrivers::ProcessDriverInstallation",
      v81,
      v80,
      0,
      0);
  }
  v84 = *(_DWORD *)(a1 + 368);
  if ( v84 )
  {
    v85 = *(_DWORD *)(a1 + 368);
    LODWORD(v212) = v85;
    goto LABEL_49;
  }
  LODWORD(v212) = 1;
  if ( *(_DWORD *)(a1 + 256) && *(_DWORD *)(a2 + 56) == 1 )
    goto LABEL_47;
  if ( v29 && v203 )
  {
    v84 = 2;
    v85 = 2;
    LODWORD(v212) = 2;
    goto LABEL_49;
  }
  v84 = 1;
  if ( !(_DWORD)v205 )
LABEL_47:
    v84 = 3;
  v85 = 3;
LABEL_49:
  v86 = GetLastError();
  v87 = CurrentIP();
  AnswerString = CProcessDrivers::GetAnswerString(v84);
  v89 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v201, AnswerString);
  v90 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v89);
  v91 = (const char *)UnBCL::String::get_CString(v90);
  v92 = ConstructPartialMsgW(0x4000000u, "Initial decision for external package: %s", v91);
  WdsSetupLogMessageW(
    v92,
    819200,
    L"D",
    0,
    1462,
    L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
    L"CProcessDrivers::ProcessDriverInstallation",
    v87,
    v86,
    0,
    0);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v201);
  if ( a6 )
  {
    v93 = GetLastError();
    v94 = CurrentIP();
    v95 = CProcessDrivers::GetAnswerString(v85);
    v96 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v201, v95);
    v97 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v96);
    v98 = (const char *)UnBCL::String::get_CString(v97);
    v99 = ConstructPartialMsgW(0x4000000u, "Initial decision for external package (WinPE): %s", v98);
    WdsSetupLogMessageW(
      v99,
      819200,
      L"D",
      0,
      1465,
      L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
      L"CProcessDrivers::ProcessDriverInstallation",
      v94,
      v93,
      0,
      0);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v201);
  }
  v100 = (__int64 (__fastcall ***)(_QWORD, __int64, _QWORD))(*(__int64 (__fastcall **)(UnBCL::String *))(*(_QWORD *)a5 + 88LL))(a5);
  v101 = v100;
  v205 = v100;
  if ( v100 )
  {
    LODWORD(a5) = (**v100)(v100, a2, v84);
    if ( (_DWORD)a5 != v84 )
    {
      v102 = GetLastError();
      v103 = CurrentIP();
      v84 = (unsigned int)a5;
      v104 = CProcessDrivers::GetAnswerString((unsigned int)a5);
      v105 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v201, v104);
      v106 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v105);
      v107 = (const char *)UnBCL::String::get_CString(v106);
      v108 = ConstructPartialMsgW(0x4000000u, "  Specific callback decision for external package: %s", v107);
      WdsSetupLogMessageW(
        v108,
        819200,
        L"D",
        0,
        1475,
        L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
        L"CProcessDrivers::ProcessDriverInstallation",
        v103,
        v102,
        0,
        0);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v201);
      v101 = v205;
    }
    if ( a6 )
    {
      LODWORD(a5) = (**v101)(v101, a2, v85);
      if ( (_DWORD)a5 != v85 )
      {
        v109 = GetLastError();
        v110 = CurrentIP();
        v85 = (unsigned int)a5;
        v111 = CProcessDrivers::GetAnswerString((unsigned int)a5);
        v112 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v201, v111);
        v113 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v112);
        v114 = (const char *)UnBCL::String::get_CString(v113);
        v115 = ConstructPartialMsgW(0x4000000u, "  Specific callback decision for external package (WinPE): %s", v114);
        WdsSetupLogMessageW(
          v115,
          819200,
          L"D",
          0,
          1483,
          L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
          L"CProcessDrivers::ProcessDriverInstallation",
          v110,
          v109,
          0,
          0);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v201);
      }
    }
  }
  if ( !v84 )
  {
    v84 = v212;
    v116 = GetLastError();
    v117 = CurrentIP();
    v118 = CProcessDrivers::GetAnswerString(v84);
    v119 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v201, v118);
    v120 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v119);
    v121 = (const char *)UnBCL::String::get_CString(v120);
    v122 = ConstructPartialMsgW(0x4000000u, "  Resolved default install decision for external package: %s", v121);
    WdsSetupLogMessageW(
      v122,
      819200,
      L"D",
      0,
      1493,
      L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
      L"CProcessDrivers::ProcessDriverInstallation",
      v117,
      v116,
      0,
      0);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v201);
  }
  if ( a6 && !v85 )
  {
    v85 = v212;
    v123 = GetLastError();
    v124 = CurrentIP();
    v125 = CProcessDrivers::GetAnswerString(v85);
    v126 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v201, v125);
    v127 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v126);
    v128 = (const char *)UnBCL::String::get_CString(v127);
    v129 = ConstructPartialMsgW(
             0x4000000u,
             "  Resolved default install decision for external package (WinPE): %s",
             v128);
    WdsSetupLogMessageW(
      v129,
      819200,
      L"D",
      0,
      1500,
      L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
      L"CProcessDrivers::ProcessDriverInstallation",
      v124,
      v123,
      0,
      0);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v201);
  }
  v130 = GetLastError();
  v131 = CurrentIP();
  v132 = CProcessDrivers::GetAnswerString(v84);
  v133 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v201, v132);
  v134 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v133);
  v135 = (const char *)UnBCL::String::get_CString(v134);
  v136 = ConstructPartialMsgW(0x4000000u, "Final decision for external driver package: %s", v135);
  WdsSetupLogMessageW(
    v136,
    819200,
    L"D",
    0,
    1504,
    L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
    L"CProcessDrivers::ProcessDriverInstallation",
    v131,
    v130,
    0,
    0);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v201);
  if ( a6 )
  {
    v137 = GetLastError();
    v138 = CurrentIP();
    v139 = CProcessDrivers::GetAnswerString(v85);
    v140 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v201, v139);
    v141 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v140);
    v142 = (const char *)UnBCL::String::get_CString(v141);
    v143 = ConstructPartialMsgW(0x4000000u, "Final decision for external driver package (WinPE): %s", v142);
    WdsSetupLogMessageW(
      v143,
      819200,
      L"D",
      0,
      1507,
      L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
      L"CProcessDrivers::ProcessDriverInstallation",
      v138,
      v137,
      0,
      0);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v201);
    if ( ((v85 - 2) & 0xFFFFFFFD) == 0 )
    {
      v144 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
      v145 = v144;
      a5 = v144;
      if ( v144 )
      {
        UnBCL::String::String(v144, *(const unsigned __int16 **)(a2 + 36));
        *(_QWORD *)v145 = &UnBCL::String::`local vftable';
      }
      else
      {
        v145 = 0;
      }
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v199, v145);
      v146 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v199);
      v147 = UnBCL::String::ToLower(v146);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v202, v147);
      UnBCL::SmartPtr<UnBCL::String>::operator=(&v199, v202);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v202);
      v154 = 0;
      if ( !v210 )
      {
        v148 = a7;
        if ( a7 )
        {
          v149 = *(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)a7 + 32LL);
          v150 = UnBCL::SmartPtr<UnBCL::String>::get_P(&v199);
          if ( !v149(v148, v150)
            || (v151 = *(int *)(*(_QWORD *)(v148 + 8) + 16LL) + v148,
                v152 = *(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)(v151 + 8) + 16LL),
                v153 = UnBCL::SmartPtr<UnBCL::String>::get_P(&v199),
                v152(v151 + 8, v153)) )
          {
            v154 = 1;
          }
        }
      }
      LODWORD(a5) = v154;
      v155 = 4 * v154 + 8;
      v156 = GetLastError();
      v157 = CurrentIP();
      v158 = L"F6 ";
      if ( v85 != 4 )
        v158 = &cchOriginalDestLength;
      v159 = L"Force-reflecting ";
      if ( !(_DWORD)a5 )
        v159 = L"Reflecting ";
      v160 = ConstructPartialMsgW(
               0x4000000u,
               "DRVINST: %s%sdriver package into WinPE: %s",
               (const char *)v159,
               (const char *)v158,
               *(const char **)(a2 + 8));
      WdsSetupLogMessageW(
        v160,
        819200,
        L"D",
        0,
        1546,
        L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
        L"CProcessDrivers::ProcessDriverInstallation",
        v157,
        v156,
        0,
        0);
      v161 = v155 | 0x10;
      if ( v85 != 4 )
        v161 = v155;
      v162 = _DismAddDriverEx(a6, *(_QWORD *)(a2 + 8), v161, 0xFFFF, 0, 0);
      v211 = v162;
      if ( v162 < 0 )
      {
        v168 = GetLastError();
        v169 = CurrentIP();
        v170 = L"force-";
        if ( !(_DWORD)a5 )
          v170 = &cchOriginalDestLength;
        v171 = ConstructPartialMsgW(
                 0x2000000u,
                 "DRVINST: Failed to %sreflect driver package in WinRE: %s.",
                 (const char *)v170,
                 *(const char **)(a2 + 8));
        WdsSetupLogMessageW(
          v171,
          819200,
          L"D",
          0,
          1563,
          L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
          L"CProcessDrivers::ProcessDriverInstallation",
          v169,
          v168,
          0,
          0);
        v172 = (struct UnBCL::String *)UnBCL::String::String(
                                         (UnBCL::String *)v201,
                                         *(const unsigned __int16 **)(a2 + 36));
        v173 = SPIsDriverFailureIgnorable(*(_DWORD *)(a1 + 356), *(_DWORD *)(a1 + 348), v172);
        UnBCL::String::~String((UnBCL::String *)v201);
        if ( !v173 )
        {
          *a11 = 2;
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v199);
          return (unsigned int)v162;
        }
        v174 = GetLastError();
        v175 = CurrentIP();
        v176 = ConstructPartialMsgW(0x4000000u, "Ignoring error due to operation configuration.");
        WdsSetupLogMessageW(
          v176,
          819200,
          L"D",
          0,
          1569,
          L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
          L"CProcessDrivers::ProcessDriverInstallation",
          v175,
          v174,
          0,
          0);
        v211 = 0;
        v167 = 3;
      }
      else
      {
        v163 = GetLastError();
        v164 = CurrentIP();
        v165 = L"force-";
        if ( !(_DWORD)a5 )
          v165 = &cchOriginalDestLength;
        v166 = ConstructPartialMsgW(
                 0x4000000u,
                 "DRVINST: Successfully %sreflected driver package in WinPE: %s.",
                 (const char *)v165,
                 *(const char **)(a2 + 8));
        WdsSetupLogMessageW(
          v166,
          819200,
          L"D",
          0,
          1555,
          L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
          L"CProcessDrivers::ProcessDriverInstallation",
          v164,
          v163,
          0,
          0);
        v167 = 1;
      }
      *a11 = v167;
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v199);
    }
  }
  if ( v84 != 3 )
  {
    if ( v84 == 2 )
    {
      v178 = v210;
      v179 = !v210 + 2;
    }
    else
    {
      v179 = 0;
      if ( v84 == 4 )
        v179 = 4;
      v178 = v210;
    }
    if ( v178 != *(_DWORD *)(a2 + 52) )
    {
      v180 = GetLastError();
      v181 = CurrentIP();
      v182 = ConstructPartialMsgW(
               0x4000000u,
               "DRVINST: Setup and DISM disagree about boot critical driver status, we will need an extra driver installa"
               "tion phase for WinRE");
      WdsSetupLogMessageW(
        v182,
        819200,
        L"D",
        0,
        1606,
        L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
        L"CProcessDrivers::ProcessDriverInstallation",
        v181,
        v180,
        0,
        0);
      *a9 = 1;
      (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)v208 + 16LL))(
        v208,
        L"SP_DRIVER_INFO",
        L"DriverWinREExtraMigrationPhaseReason",
        L"ExternalDriverBootCriticalConflict");
    }
    if ( ((v84 - 2) & 0xFFFFFFFD) != 0 && *(_DWORD *)(a2 + 52) && v203 )
      v179 = 1;
    v199 = &UnBCL::SmartPtr<UnBCL::MultiSz>::`vftable';
    v200 = 0;
    memset(v202, 0, 28);
    v183 = a10;
    if ( a10 )
    {
      v184 = (UnBCL::MultiSz *)UnBCL::Object::operator new(0x70u);
      v185 = v184;
      a5 = v184;
      if ( v184 )
      {
        UnBCL::MultiSz::MultiSz(v184);
        *((_QWORD *)v185 + 5) = &UnBCL::MultiSz::`local vftable'{for `UnBCL::Object'};
      }
      else
      {
        v185 = 0;
      }
      UnBCL::SmartPtr<UnBCL::MultiSz>::SmartPtr<UnBCL::MultiSz>(v207, v185);
      UnBCL::SmartPtr<UnBCL::RegistryKey>::operator=(&v199, v207);
      v207[0] = &UnBCL::SmartPtr<UnBCL::MultiSz>::`vftable';
      UnBCL::SmartPtr<OC::COptionalComponent>::DeAssign(v207);
      v186 = UnBCL::String::get_CString(v183);
      UnBCL::MultiSz::Add(v200, v186);
      *(_QWORD *)&v202[0] = DEVPKEY_DriverPackage_DriverFlightIds;
      DWORD2(v202[0]) = 8210;
      *(_QWORD *)&v202[1] = UnBCL::MultiSz::get_Buffer(v200);
      HIDWORD(v202[0]) = 2 * UnBCL::String::get_Length(v183) + 4;
      v187 = 1;
      v188 = v202;
    }
    else
    {
      v188 = 0;
      v187 = 0;
    }
    v189 = a8 + *(int *)(*(_QWORD *)(a8 + 8) + 16LL);
    v190 = *(void (__fastcall **)(__int64, UnBCL::String *))(*(_QWORD *)(v189 + 8) + 40LL);
    v191 = (UnBCL::String *)UnBCL::Object::operator new(0x40u);
    v192 = v191;
    a5 = v191;
    if ( v191 )
    {
      v193 = (UnBCL::String *)UnBCL::Object::operator new(0x48u);
      a10 = v193;
      if ( v193 )
        v194 = CDriverInstallInfo::CDriverInstallInfo(v193, v179, 0xFFFF, v188, v187, *(_QWORD *)(a2 + 36));
      else
        v194 = 0;
      v195 = (CGlobalPath *)UnBCL::Object::operator new(0x58u);
      v196 = v195;
      a10 = v195;
      if ( v195 )
      {
        v197 = (struct UnBCL::String *)UnBCL::String::String(
                                         (UnBCL::String *)v201,
                                         *(const unsigned __int16 **)(a2 + 8));
        v198 = 1;
        v206 = 1;
        v195 = CGlobalPath::CGlobalPath(v196, v197);
      }
      else
      {
        v198 = v204;
      }
      v191 = (UnBCL::String *)UnBCL::DictionaryEntry<CGlobalPath *,CDriverInstallInfo *>::DictionaryEntry<CGlobalPath *,CDriverInstallInfo *>(
                                v192,
                                v195,
                                v194);
    }
    else
    {
      v198 = v204;
    }
    v190(v189 + 8, v191);
    if ( (v198 & 1) != 0 )
      UnBCL::String::~String((UnBCL::String *)v201);
    v199 = &UnBCL::SmartPtr<UnBCL::MultiSz>::`vftable';
    UnBCL::SmartPtr<OC::COptionalComponent>::DeAssign(&v199);
  }
  return v211;
}

```

## disassembly

```asm
0x1801b3c20  mov     [rsp-8+arg_18], r9d
0x1801b3c25  mov     [rsp-8+arg_10], r8
0x1801b3c2a  push    rbp
0x1801b3c2b  push    rbx
0x1801b3c2c  push    rsi
0x1801b3c2d  push    rdi
0x1801b3c2e  push    r12
0x1801b3c30  push    r13
0x1801b3c32  push    r14
0x1801b3c34  push    r15
0x1801b3c36  lea     rbp, [rsp-7]
0x1801b3c3b  sub     rsp, 0E8h
0x1801b3c42  mov     [rbp+3Fh+var_48], 0FFFFFFFFFFFFFFFEh
0x1801b3c4a  mov     r15, rdx
0x1801b3c4d  mov     r12, rcx
0x1801b3c50  xor     eax, eax
0x1801b3c52  mov     [rbp+3Fh+var_74], eax
0x1801b3c55  mov     [rbp+3Fh+var_68], eax
0x1801b3c58  mov     [rbp+3Fh+arg_8], eax
0x1801b3c5b  mov     rcx, [rbp+3Fh+arg_20]
0x1801b3c5f  mov     rax, [rcx]
0x1801b3c62  mov     rax, [rax+40h]
0x1801b3c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b3c6b  mov     [rbp+3Fh+var_50], rax
0x1801b3c6f  mov     r13, [r15+8]
0x1801b3c73  lea     rbx, [r12+198h]
0x1801b3c7b  mov     [rbp+3Fh+arg_10], 0
0x1801b3c83  mov     rax, [rbx]
0x1801b3c86  lea     rdx, [rbp+3Fh+arg_10]
0x1801b3c8a  mov     rcx, rbx
0x1801b3c8d  mov     rax, [rax+28h]
0x1801b3c91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b3c96  lea     r14, aBaseNtsetupSet_14; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1801b3c9d  test    al, al
0x1801b3c9f  jz      loc_1801B3D36
0x1801b3ca5  mov     rax, [rbx]
0x1801b3ca8  mov     rcx, rbx
0x1801b3cab  mov     rax, [rax]
0x1801b3cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b3cb3  mov     r8, rax; struct IDeviceIdDatabase **
0x1801b3cb6  call    ?SPCreateDeviceIdDatabase@@YAJPEBU_GUID@@HPEAPEAUIDeviceIdDatabase@@@Z; SPCreateDeviceIdDatabase(_GUID const *,int,IDeviceIdDatabase * *)
0x1801b3cbb  mov     esi, eax
0x1801b3cbd  test    eax, eax
0x1801b3cbf  jns     short loc_1801B3D36
0x1801b3cc1  call    cs:__imp_GetLastError
0x1801b3cc7  mov     edi, eax
0x1801b3cc9  call    cs:__imp_CurrentIP
0x1801b3ccf  mov     rbx, rax
0x1801b3cd2  mov     r8d, esi
0x1801b3cd5  lea     rdx, aFailedToCreate_29; "Failed to create device database, error"...
0x1801b3cdc  mov     ecx, 2000000h; unsigned int
0x1801b3ce1  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801b3ce6  xor     esi, esi
0x1801b3ce8  mov     [rsp+120h+var_D0], esi
0x1801b3cec  mov     [rsp+120h+var_D8], rsi
0x1801b3cf1  mov     [rsp+120h+var_E0], edi
0x1801b3cf5  mov     [rsp+120h+var_E8], rbx
0x1801b3cfa  lea     rcx, aCprocessdriver_10; "CProcessDrivers::IsDriverPackageApplica"...
0x1801b3d01  mov     [rsp+120h+var_F0], rcx
0x1801b3d06  mov     [rsp+120h+var_F8], r14
0x1801b3d0b  mov     dword ptr [rsp+120h+var_100], 0FCh
0x1801b3d13  xor     r9d, r9d
0x1801b3d16  lea     r8, aD_0; "D"
0x1801b3d1d  mov     edx, 0C8000h
0x1801b3d22  mov     rcx, rax
0x1801b3d25  call    cs:__imp_WdsSetupLogMessageW
0x1801b3d2b  mov     r14d, esi
0x1801b3d2e  mov     dword ptr [rbp+3Fh+var_70], esi
0x1801b3d31  jmp     loc_1801B3DCE
0x1801b3d36  mov     rax, [rbx]
0x1801b3d39  mov     rcx, rbx
0x1801b3d3c  mov     rax, [rax+8]
0x1801b3d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b3d45  mov     rsi, rax
0x1801b3d48  mov     rax, [rax]
0x1801b3d4b  mov     r14, [rax]
0x1801b3d4e  lea     rbx, [r12+108h]
0x1801b3d56  mov     rcx, rbx
0x1801b3d59  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1801b3d5f  test    rax, rax
0x1801b3d62  jz      short loc_1801B3D7B
0x1801b3d64  mov     rcx, rbx
0x1801b3d67  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1801b3d6d  mov     rcx, rax
0x1801b3d70  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1801b3d76  mov     rdi, rax
0x1801b3d79  jmp     short loc_1801B3D7D
0x1801b3d7b  xor     edi, edi
0x1801b3d7d  mov     rcx, rbx
0x1801b3d80  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1801b3d86  test    rax, rax
0x1801b3d89  jz      short loc_1801B3D95
0x1801b3d8b  mov     ebx, [r12+100h]
0x1801b3d93  jmp     short loc_1801B3D9A
0x1801b3d95  mov     ebx, 0FFFFh
0x1801b3d9a  mov     rdx, r13
0x1801b3d9d  lea     rcx, [rbp+3Fh+var_B0]
0x1801b3da1  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1801b3da7  nop
0x1801b3da8  mov     r9, rdi
0x1801b3dab  mov     r8d, ebx
0x1801b3dae  mov     rdx, rax
0x1801b3db1  mov     rcx, rsi
0x1801b3db4  mov     rax, r14
0x1801b3db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b3dbc  mov     r14d, eax
0x1801b3dbf  mov     dword ptr [rbp+3Fh+var_70], eax
0x1801b3dc2  lea     rcx, [rbp+3Fh+var_B0]
0x1801b3dc6  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1801b3dcc  xor     esi, esi
0x1801b3dce  mov     ebx, 1
0x1801b3dd3  mov     r8d, ebx
0x1801b3dd6  lea     rdx, aF2e7dd7264684e; "{F2E7DD72-6468-4E36-B6F1-6488F42C1B52}"
0x1801b3ddd  mov     rcx, [r15+24h]
0x1801b3de1  call    cs:__imp_?Compare@String@UnBCL@@SAHPEBG0H@Z; UnBCL::String::Compare(ushort const *,ushort const *,int)
0x1801b3de7  mov     [rbp+3Fh+var_78], eax
0x1801b3dea  cmp     [r15+34h], esi
0x1801b3dee  jz      short loc_1801B3E14
0x1801b3df0  cmp     [r12+15Ch], esi
0x1801b3df8  jnz     short loc_1801B3E0F
0x1801b3dfa  mov     edx, [r12+160h]; int
0x1801b3e02  mov     rcx, [r15+24h]; unsigned __int16 *
0x1801b3e06  call    ?SPIsStorageClass@@YAHPEBGH@Z; SPIsStorageClass(ushort const *,int)
0x1801b3e0b  test    eax, eax
0x1801b3e0d  jz      short loc_1801B3E14
0x1801b3e0f  mov     r13d, ebx
0x1801b3e12  jmp     short loc_1801B3E17
0x1801b3e14  mov     r13d, esi
0x1801b3e17  mov     [rbp+3Fh+arg_0], r13d
0x1801b3e1b  call    cs:__imp_GetLastError
0x1801b3e21  mov     edi, eax
0x1801b3e23  call    cs:__imp_CurrentIP
0x1801b3e29  mov     rbx, rax
0x1801b3e2c  lea     rdx, aDecidingInject; "Deciding injection of external driver p"...
0x1801b3e33  mov     ecx, 4000000h; unsigned int
0x1801b3e38  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801b3e3d  mov     [rsp+120h+var_D0], esi
0x1801b3e41  mov     [rsp+120h+var_D8], rsi
0x1801b3e46  mov     [rsp+120h+var_E0], edi
0x1801b3e4a  mov     [rsp+120h+var_E8], rbx
0x1801b3e4f  lea     rcx, aCprocessdriver_4; "CProcessDrivers::ProcessDriverInstallat"...
0x1801b3e56  mov     [rsp+120h+var_F0], rcx
0x1801b3e5b  lea     rcx, aBaseNtsetupSet_14; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1801b3e62  mov     [rsp+120h+var_F8], rcx
0x1801b3e67  mov     dword ptr [rsp+120h+var_100], 572h
0x1801b3e6f  xor     r9d, r9d
0x1801b3e72  lea     r8, aD_0; "D"
0x1801b3e79  mov     edx, 0C8000h
0x1801b3e7e  mov     rcx, rax
0x1801b3e81  call    cs:__imp_WdsSetupLogMessageW
0x1801b3e87  call    cs:__imp_GetLastError
0x1801b3e8d  mov     edi, eax
0x1801b3e8f  call    cs:__imp_CurrentIP
0x1801b3e95  mov     rbx, rax
0x1801b3e98  mov     r8, [r15]
0x1801b3e9b  lea     rdx, aPublishedNameS; "  Published Name: %s"
0x1801b3ea2  mov     ecx, 4000000h; unsigned int
0x1801b3ea7  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801b3eac  mov     [rsp+120h+var_D0], esi
0x1801b3eb0  mov     [rsp+120h+var_D8], rsi
0x1801b3eb5  mov     [rsp+120h+var_E0], edi
0x1801b3eb9  mov     [rsp+120h+var_E8], rbx
0x1801b3ebe  lea     rcx, aCprocessdriver_4; "CProcessDrivers::ProcessDriverInstallat"...
0x1801b3ec5  mov     [rsp+120h+var_F0], rcx
0x1801b3eca  lea     rcx, aBaseNtsetupSet_14; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1801b3ed1  mov     [rsp+120h+var_F8], rcx
0x1801b3ed6  mov     dword ptr [rsp+120h+var_100], 573h
0x1801b3ede  xor     r9d, r9d
0x1801b3ee1  lea     r8, aD_0; "D"
0x1801b3ee8  mov     edx, 0C8000h
0x1801b3eed  mov     rcx, rax
0x1801b3ef0  call    cs:__imp_WdsSetupLogMessageW
0x1801b3ef6  call    cs:__imp_GetLastError
0x1801b3efc  mov     edi, eax
0x1801b3efe  call    cs:__imp_CurrentIP
0x1801b3f04  mov     rbx, rax
0x1801b3f07  mov     r8, [r15+3Ch]
0x1801b3f0b  lea     rdx, aProviderS; "  Provider: %s"
0x1801b3f12  mov     ecx, 4000000h; unsigned int
0x1801b3f17  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801b3f1c  mov     [rsp+120h+var_D0], esi
0x1801b3f20  mov     [rsp+120h+var_D8], rsi
0x1801b3f25  mov     [rsp+120h+var_E0], edi
0x1801b3f29  mov     [rsp+120h+var_E8], rbx
0x1801b3f2e  lea     rcx, aCprocessdriver_4; "CProcessDrivers::ProcessDriverInstallat"...
0x1801b3f35  mov     [rsp+120h+var_F0], rcx
0x1801b3f3a  lea     rcx, aBaseNtsetupSet_14; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1801b3f41  mov     [rsp+120h+var_F8], rcx
0x1801b3f46  mov     dword ptr [rsp+120h+var_100], 574h
0x1801b3f4e  xor     r9d, r9d
0x1801b3f51  lea     r8, aD_0; "D"
0x1801b3f58  mov     edx, 0C8000h
0x1801b3f5d  mov     rcx, rax
0x1801b3f60  call    cs:__imp_WdsSetupLogMessageW
0x1801b3f66  call    cs:__imp_GetLastError
0x1801b3f6c  mov     edi, eax
0x1801b3f6e  call    cs:__imp_CurrentIP
0x1801b3f74  mov     rbx, rax
0x1801b3f77  mov     r8, [r15+24h]
0x1801b3f7b  lea     rdx, aClassGuidS; "  Class GUID: %s"
0x1801b3f82  mov     ecx, 4000000h; unsigned int
0x1801b3f87  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801b3f8c  mov     [rsp+120h+var_D0], esi
0x1801b3f90  mov     [rsp+120h+var_D8], rsi
0x1801b3f95  mov     [rsp+120h+var_E0], edi
0x1801b3f99  mov     [rsp+120h+var_E8], rbx
0x1801b3f9e  lea     rcx, aCprocessdriver_4; "CProcessDrivers::ProcessDriverInstallat"...
0x1801b3fa5  mov     [rsp+120h+var_F0], rcx
0x1801b3faa  lea     rcx, aBaseNtsetupSet_14; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1801b3fb1  mov     [rsp+120h+var_F8], rcx
0x1801b3fb6  mov     dword ptr [rsp+120h+var_100], 575h
0x1801b3fbe  xor     r9d, r9d
0x1801b3fc1  lea     r8, aD_0; "D"
0x1801b3fc8  mov     edx, 0C8000h
0x1801b3fcd  mov     rcx, rax
0x1801b3fd0  call    cs:__imp_WdsSetupLogMessageW
0x1801b3fd6  call    cs:__imp_GetLastError
0x1801b3fdc  mov     edi, eax
0x1801b3fde  call    cs:__imp_CurrentIP
0x1801b3fe4  mov     rbx, rax
0x1801b3fe7  mov     r8, [r15+1Ch]
0x1801b3feb  lea     rdx, aClassNameS_0; "  Class Name: %s"
0x1801b3ff2  mov     ecx, 4000000h; unsigned int
0x1801b3ff7  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801b3ffc  mov     [rsp+120h+var_D0], esi
0x1801b4000  mov     [rsp+120h+var_D8], rsi
0x1801b4005  mov     [rsp+120h+var_E0], edi
0x1801b4009  mov     [rsp+120h+var_E8], rbx
0x1801b400e  lea     rcx, aCprocessdriver_4; "CProcessDrivers::ProcessDriverInstallat"...
0x1801b4015  mov     [rsp+120h+var_F0], rcx
0x1801b401a  lea     rcx, aBaseNtsetupSet_14; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1801b4021  mov     [rsp+120h+var_F8], rcx
0x1801b4026  mov     dword ptr [rsp+120h+var_100], 576h
0x1801b402e  xor     r9d, r9d
0x1801b4031  lea     r8, aD_0; "D"
0x1801b4038  mov     edx, 0C8000h
0x1801b403d  mov     rcx, rax
0x1801b4040  call    cs:__imp_WdsSetupLogMessageW
0x1801b4046  call    cs:__imp_GetLastError
0x1801b404c  mov     edi, eax
0x1801b404e  call    cs:__imp_CurrentIP
0x1801b4054  mov     rbx, rax
0x1801b4057  mov     r8, [r15+8]
0x1801b405b  lea     rdx, aPackageFileS; "  Package file: %s"
0x1801b4062  mov     ecx, 4000000h; unsigned int
0x1801b4067  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801b406c  mov     [rsp+120h+var_D0], esi
0x1801b4070  mov     [rsp+120h+var_D8], rsi
0x1801b4075  mov     [rsp+120h+var_E0], edi
0x1801b4079  mov     [rsp+120h+var_E8], rbx
0x1801b407e  lea     rcx, aCprocessdriver_4; "CProcessDrivers::ProcessDriverInstallat"...
0x1801b4085  mov     [rsp+120h+var_F0], rcx
0x1801b408a  lea     rcx, aBaseNtsetupSet_14; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1801b4091  mov     [rsp+120h+var_F8], rcx
0x1801b4096  mov     dword ptr [rsp+120h+var_100], 577h
0x1801b409e  xor     r9d, r9d
0x1801b40a1  lea     r8, aD_0; "D"
0x1801b40a8  mov     edx, 0C8000h
0x1801b40ad  mov     rcx, rax
0x1801b40b0  call    cs:__imp_WdsSetupLogMessageW
0x1801b40b6  call    cs:__imp_GetLastError
0x1801b40bc  mov     edi, eax
0x1801b40be  call    cs:__imp_CurrentIP
0x1801b40c4  mov     rbx, rax
0x1801b40c7  lea     rax, aNo; "No"
0x1801b40ce  lea     rsi, aYes_1; "Yes"
0x1801b40d5  mov     r8, rsi
0x1801b40d8  cmp     dword ptr [r15+34h], 0
0x1801b40dd  cmovz   r8, rax
0x1801b40e1  lea     rdx, aDismBootCritic; "  DISM boot critical: %s"
0x1801b40e8  mov     ecx, 4000000h; unsigned int
0x1801b40ed  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801b40f2  mov     [rsp+120h+var_D0], 0
0x1801b40fa  mov     [rsp+120h+var_D8], 0
0x1801b4103  mov     [rsp+120h+var_E0], edi
0x1801b4107  mov     [rsp+120h+var_E8], rbx
0x1801b410c  lea     rcx, aCprocessdriver_4; "CProcessDrivers::ProcessDriverInstallat"...
0x1801b4113  mov     [rsp+120h+var_F0], rcx
0x1801b4118  lea     rcx, aBaseNtsetupSet_14; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1801b411f  mov     [rsp+120h+var_F8], rcx
0x1801b4124  mov     dword ptr [rsp+120h+var_100], 578h
0x1801b412c  xor     r9d, r9d
0x1801b412f  lea     r8, aD_0; "D"
0x1801b4136  mov     edx, 0C8000h
0x1801b413b  mov     rcx, rax
0x1801b413e  call    cs:__imp_WdsSetupLogMessageW
0x1801b4144  call    cs:__imp_GetLastError
0x1801b414a  mov     edi, eax
0x1801b414c  call    cs:__imp_CurrentIP
0x1801b4152  mov     rbx, rax
0x1801b4155  mov     r8, rsi
0x1801b4158  test    r13d, r13d
0x1801b415b  lea     rax, aNo; "No"
0x1801b4162  cmovz   r8, rax
0x1801b4166  lea     rdx, aUpgradeBootCri; "  Upgrade boot critical: %s"
0x1801b416d  mov     ecx, 4000000h; unsigned int
0x1801b4172  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801b4177  mov     [rsp+120h+var_D0], 0
0x1801b417f  mov     [rsp+120h+var_D8], 0
0x1801b4188  mov     [rsp+120h+var_E0], edi
  ... truncated ...
```
