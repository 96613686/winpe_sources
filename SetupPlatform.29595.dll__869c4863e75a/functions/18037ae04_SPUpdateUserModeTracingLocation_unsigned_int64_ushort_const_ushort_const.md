# SPUpdateUserModeTracingLocation(unsigned __int64,ushort const *,ushort const *)

- ea: `0x18037ae04`
- end: `0x18037b989`
- name: `?SPUpdateUserModeTracingLocation@@YAJ_KPEBG1@Z`
- size: `2949`
- prototype: `int(unsigned __int64, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x18037ff20`

## callees

- `0x180013804`
- `0x180035de8`
- `0x18003d0e8`
- `0x180057dec`
- `0x18009a328`
- `0x1802c6538`
- `0x18037ae04`
- `0x18037d540`
- `0x18037deb8`
- `0x1804bbf62`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18037b917`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18037b917`
- `ADVAPI32!ControlTraceW` at `0x18037af27`
- `ADVAPI32!ControlTraceW` at `0x18037b563`
- `ADVAPI32!ControlTraceW` at `0x18037b5de`
- `ADVAPI32!ControlTraceW` at `0x18037af27`
- `ADVAPI32!ControlTraceW` at `0x18037b563`
- `ADVAPI32!ControlTraceW` at `0x18037b5de`
- `KERNEL32!GetLastError` at `0x18037af3e`
- `KERNEL32!GetLastError` at `0x18037b0df`
- `KERNEL32!GetLastError` at `0x18037b1ae`
- `KERNEL32!GetLastError` at `0x18037b22d`
- `KERNEL32!GetLastError` at `0x18037b2c2`
- `KERNEL32!GetLastError` at `0x18037b396`
- `KERNEL32!GetLastError` at `0x18037b3ac`
- `KERNEL32!GetLastError` at `0x18037b3c8`
- `KERNEL32!GetLastError` at `0x18037b4f7`
- `KERNEL32!GetLastError` at `0x18037b57a`
- `KERNEL32!GetLastError` at `0x18037b5f5`
- `KERNEL32!GetLastError` at `0x18037b716`
- `KERNEL32!GetLastError` at `0x18037b72c`
- `KERNEL32!GetLastError` at `0x18037b748`
- `KERNEL32!GetLastError` at `0x18037b7b8`
- `KERNEL32!GetLastError` at `0x18037b898`
- `KERNEL32!GetLastError` at `0x18037af3e`
- `KERNEL32!GetLastError` at `0x18037b0df`
- `KERNEL32!GetLastError` at `0x18037b1ae`
- `KERNEL32!GetLastError` at `0x18037b22d`
- `KERNEL32!GetLastError` at `0x18037b2c2`
- `KERNEL32!GetLastError` at `0x18037b396`
- `KERNEL32!GetLastError` at `0x18037b3ac`
- `KERNEL32!GetLastError` at `0x18037b3c8`
- `KERNEL32!GetLastError` at `0x18037b4f7`
- `KERNEL32!GetLastError` at `0x18037b57a`
- `KERNEL32!GetLastError` at `0x18037b5f5`
- `KERNEL32!GetLastError` at `0x18037b716`
- `KERNEL32!GetLastError` at `0x18037b72c`
- `KERNEL32!GetLastError` at `0x18037b748`
- `KERNEL32!GetLastError` at `0x18037b7b8`
- `KERNEL32!GetLastError` at `0x18037b898`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18037b21e`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18037b4d9`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18037b21e`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18037b4d9`
- `unbcl!?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18037b010`
- `unbcl!?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18037b010`
- `unbcl!?Exists@File@UnBCL@@SAHPEBVString@2@@Z` at `0x18037b2b4`
- `unbcl!?Exists@File@UnBCL@@SAHPEBVString@2@@Z` at `0x18037b2b4`
- `unbcl!?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18037b055`
- `unbcl!?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18037b055`
- `unbcl!?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z` at `0x18037b461`
- `unbcl!?CreateDir@Directory@UnBCL@@SAPEAVDirectoryInfo@2@PEBVString@2@@Z` at `0x18037b461`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x18037b446`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x18037b446`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18037b0ae`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18037b670`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18037b0ae`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18037b670`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18037b007`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18037b04c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18037b091`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18037b0a2`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18037b188`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18037b199`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18037b2ab`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18037b387`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18037b43d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18037b458`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18037b653`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18037b664`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18037b707`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18037b007`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18037b04c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18037b091`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18037b0a2`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18037b188`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18037b199`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18037b2ab`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18037b387`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18037b43d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18037b458`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18037b653`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18037b664`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18037b707`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18037ae36`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18037ae45`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18037ae54`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18037aeb6`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18037aec5`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18037ae36`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18037ae45`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18037ae54`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18037aeb6`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18037aec5`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18037ae83`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18037afc3`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18037ae83`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18037afc3`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18037ae64`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18037afa5`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18037ae64`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18037afa5`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18037afed`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18037b032`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18037b077`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18037b0cd`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18037b370`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18037b692`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18037b6ed`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18037afed`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18037b032`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18037b077`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18037b0cd`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18037b370`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18037b692`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18037b6ed`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b0f5`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b10f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b215`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b243`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b2d8`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b336`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b3de`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b4b9`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b4d0`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b6ac`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b761`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b7d1`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b7eb`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b856`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b870`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b8b1`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b0f5`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b10f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b215`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b243`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b2d8`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b336`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b3de`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b4b9`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b4d0`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b6ac`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b761`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b7d1`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b7eb`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b856`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b870`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037b8b1`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18037b0fe`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18037b118`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18037b24c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18037b2e1`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18037b33f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18037b3e7`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18037b4c2`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18037b6b5`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18037b76a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18037b7da`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18037b7f4`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18037b85f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18037b879`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18037b8ba`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18037b0fe`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18037b118`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18037b24c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18037b2e1`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18037b33f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18037b3e7`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18037b4c2`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18037b6b5`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18037b76a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18037b7da`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18037b7f4`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18037b85f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18037b879`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18037b8ba`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18037aff9`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18037b03e`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18037b083`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18037b0d9`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18037b37c`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18037b69e`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18037b6f9`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18037b926`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18037b932`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18037b941`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18037b950`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18037b95f`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18037b96e`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18037aff9`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18037b03e`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18037b083`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18037b0d9`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18037b37c`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18037b69e`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18037b6f9`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18037b926`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18037b932`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18037b941`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18037b950`

## string_xrefs

- `0x18037b50b`: `Copy string failed: 0x%x`
- `0x18037af76`: `SPUpdateUserModeTracingLocation`
- `0x18037b148`: `SPUpdateUserModeTracingLocation`
- `0x18037b484`: `SPUpdateUserModeTracingLocation`
- `0x18037b124`: `Update telemetry log file from [%s] to [%s]`
- `0x18037b1bf`: `The current log location and new log location is same, no need to move`
- `0x18037b2ea`: `File [%s] already exists, will try a new file name`
- `0x18037b34b`: `.Move.`
- `0x18037b3f3`: `Failed to create unique new file name from [%s]: 0x%x`
- `0x18037b58e`: `ControlTrace(update) failed: 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall SPUpdateUserModeTracingLocation(__int64 a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  UnBCL::String *v5; // rax
  UnBCL::String *v6; // rbx
  struct _EVENT_TRACE_PROPERTIES *v7; // rax
  struct _EVENT_TRACE_PROPERTIES *v8; // r15
  unsigned int v9; // esi
  signed int v10; // eax
  DWORD v11; // edi
  __int64 v12; // rbx
  struct tagLOG_PARTIAL_MSG *v13; // rax
  UnBCL::String *v14; // rax
  UnBCL::String *v15; // rbx
  const struct UnBCL::String *P; // rax
  struct UnBCL::String *FileName; // rax
  const struct UnBCL::String *v18; // rax
  struct UnBCL::String *ParentPath; // rax
  const struct UnBCL::String *v20; // rbx
  const struct UnBCL::String *v21; // rax
  struct UnBCL::String *v22; // rax
  DWORD LastError; // esi
  __int64 v24; // rdi
  UnBCL::String *v25; // rax
  const char *CString; // rbx
  UnBCL::String *v27; // rax
  const char *v28; // rax
  struct tagLOG_PARTIAL_MSG *v29; // rax
  struct UnBCL::String *v30; // rbx
  struct UnBCL::String *v31; // rax
  _BYTE v33[16]; // [rsp+60h] [rbp-B8h] BYREF
  _BYTE v34[16]; // [rsp+70h] [rbp-A8h] BYREF
  _BYTE v35[16]; // [rsp+80h] [rbp-98h] BYREF
  _BYTE v36[16]; // [rsp+90h] [rbp-88h] BYREF
  _BYTE v37[16]; // [rsp+A0h] [rbp-78h] BYREF
  _BYTE v38[16]; // [rsp+B0h] [rbp-68h] BYREF
  _BYTE v39[16]; // [rsp+C0h] [rbp-58h] BYREF
  __int64 v40; // [rsp+D0h] [rbp-48h]
  UnBCL::String *v41; // [rsp+D8h] [rbp-40h]

  v40 = -2;
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v35);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v38);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v39);
  v5 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
  v6 = v5;
  if ( v5 )
  {
    UnBCL::String::String(v5, a3);
    *(_QWORD *)v6 = &UnBCL::String::`local vftable';
  }
  else
  {
    v6 = 0;
  }
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v37, v6);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v34);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v36);
  v7 = (struct _EVENT_TRACE_PROPERTIES *)operator new[](0x1078u);
  v8 = v7;
  if ( v7 )
  {
    memset_0(v7, 0, 0x1078u);
    v8->Wnode.BufferSize = 4216;
    v8->LoggerNameOffset = 120;
    v8->LogFileNameOffset = 2168;
    v10 = ControlTraceW(0, a2, v8, 0);
    v9 = v10;
    if ( !v10 )
    {
      v14 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
      v15 = v14;
      v41 = v14;
      if ( v14 )
      {
        UnBCL::String::String(v14, (const unsigned __int16 *)((char *)v8 + v8->LogFileNameOffset));
        *(_QWORD *)v15 = &UnBCL::String::`local vftable';
      }
      else
      {
        v15 = 0;
      }
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v33, v15);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v35, v33);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v33);
      P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v35);
      FileName = UnBCL::Path::GetFileName(P);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v33, FileName);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v38, v33);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v33);
      v18 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v35);
      ParentPath = UnBCL::Path::GetParentPath(v18);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v33, ParentPath);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v39, v33);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v33);
      v20 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v38);
      v21 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v37);
      v22 = UnBCL::Path::Combine(v21, v20);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v33, v22);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v34, v33);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v33);
      LastError = GetLastError();
      v24 = CurrentIP();
      v25 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v34);
      CString = (const char *)UnBCL::String::get_CString(v25);
      v27 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v35);
      v28 = (const char *)UnBCL::String::get_CString(v27);
      v29 = ConstructPartialMsgW(0x4000000u, "Update telemetry log file from [%s] to [%s]", v28, CString);
      WdsSetupLogMessageW(
        v29,
        0,
        L"D",
        0,
        2731,
        L"base\\ntsetup\\setupplatform\\lib\\tracing\\tracing.cpp",
        L"SPUpdateUserModeTracingLocation",
        v24,
        LastError,
        0,
        0);
      v30 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v37);
      v31 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v39);
      SPArePathsEqual(v31, v30);
    }
    if ( v10 > 0 )
      v9 = (unsigned __int16)v10 | 0x80070000;
    v11 = GetLastError();
    v12 = CurrentIP();
    v13 = ConstructPartialMsgW(0x2000000u, "Query trace failed: 0x%x", v9);
    WdsSetupLogMessageW(
      v13,
      0,
      L"D",
      0,
      2721,
      L"base\\ntsetup\\setupplatform\\lib\\tracing\\tracing.cpp",
      L"SPUpdateUserModeTracingLocation",
      v12,
      v11,
      0,
      0);
    operator delete[](v8);
  }
  else
  {
    v9 = -2147024882;
  }
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v36);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v34);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v37);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v39);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v38);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v35);
  return v9;
}

```

## disassembly

```asm
0x18037ae04  mov     rax, rsp
0x18037ae07  mov     [rax+10h], rdx
0x18037ae0b  mov     [rax+8], rcx
0x18037ae0f  push    rbx
0x18037ae10  push    rsi
0x18037ae11  push    rdi
0x18037ae12  push    r12
0x18037ae14  push    r13
0x18037ae16  push    r14
0x18037ae18  push    r15
0x18037ae1a  sub     rsp, 0E0h
0x18037ae21  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18037ae29  mov     rdi, r8
0x18037ae2c  mov     rsi, rdx
0x18037ae2f  lea     rcx, [rax-98h]
0x18037ae36  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x18037ae3c  nop
0x18037ae3d  lea     rcx, [rsp+118h+var_68]
0x18037ae45  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x18037ae4b  nop
0x18037ae4c  lea     rcx, [rsp+118h+var_58]
0x18037ae54  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x18037ae5a  nop
0x18037ae5b  mov     r13d, 18h
0x18037ae61  mov     ecx, r13d
0x18037ae64  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18037ae6a  mov     rbx, rax
0x18037ae6d  mov     [rsp+118h+arg_0], rax
0x18037ae75  xor     r14d, r14d
0x18037ae78  test    rax, rax
0x18037ae7b  jz      short loc_18037AE95
0x18037ae7d  mov     rdx, rdi
0x18037ae80  mov     rcx, rax
0x18037ae83  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18037ae89  lea     r12, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x18037ae90  mov     [rbx], r12
0x18037ae93  jmp     short loc_18037AE9F
0x18037ae95  mov     rbx, r14
0x18037ae98  lea     r12, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x18037ae9f  mov     rdx, rbx
0x18037aea2  lea     rcx, [rsp+118h+var_78]
0x18037aeaa  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18037aeb0  nop
0x18037aeb1  lea     rcx, [rsp+118h+var_A8]
0x18037aeb6  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x18037aebc  nop
0x18037aebd  lea     rcx, [rsp+118h+var_88]
0x18037aec5  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x18037aecb  nop
0x18037aecc  mov     ebx, 1078h
0x18037aed1  mov     ecx, ebx; unsigned __int64
0x18037aed3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18037aed8  mov     r15, rax
0x18037aedb  mov     [rsp+118h+arg_0], rax
0x18037aee3  test    rax, rax
0x18037aee6  jnz     short loc_18037AEF2
0x18037aee8  mov     esi, 8007000Eh
0x18037aeed  jmp     loc_18037B91E
0x18037aef2  mov     r8, rbx; Size
0x18037aef5  xor     edx, edx; Val
0x18037aef7  mov     rcx, r15; void *
0x18037aefa  call    memset_0
0x18037aeff  mov     [r15], ebx
0x18037af02  mov     dword ptr [r15+74h], 78h ; 'x'
0x18037af0a  lea     rdi, [r15+70h]
0x18037af0e  mov     [rsp+118h+arg_18], rdi
0x18037af16  mov     dword ptr [rdi], 878h
0x18037af1c  xor     r9d, r9d; ControlCode
0x18037af1f  mov     r8, r15; Properties
0x18037af22  mov     rdx, rsi; InstanceName
0x18037af25  xor     ecx, ecx; TraceHandle
0x18037af27  call    cs:__imp_ControlTraceW
0x18037af2d  mov     esi, eax
0x18037af2f  test    eax, eax
0x18037af31  jz      short loc_18037AFA2
0x18037af33  jle     short loc_18037AF3E
0x18037af35  movzx   esi, ax
0x18037af38  or      esi, 80070000h
0x18037af3e  call    cs:__imp_GetLastError
0x18037af44  mov     edi, eax
0x18037af46  call    cs:__imp_CurrentIP
0x18037af4c  mov     rbx, rax
0x18037af4f  mov     r8d, esi
0x18037af52  lea     rdx, aQueryTraceFail; "Query trace failed: 0x%x"
0x18037af59  mov     ecx, 2000000h; unsigned int
0x18037af5e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18037af63  mov     [rsp+118h+var_C8], r14d
0x18037af68  mov     [rsp+118h+var_D0], r14
0x18037af6d  mov     [rsp+118h+var_D8], edi
0x18037af71  mov     [rsp+118h+var_E0], rbx
0x18037af76  lea     r13, aSpupdateusermo; "SPUpdateUserModeTracingLocation"
0x18037af7d  mov     [rsp+118h+var_E8], r13
0x18037af82  lea     rcx, aBaseNtsetupSet_22; "base\\ntsetup\\setupplatform\\lib\\trac"...
0x18037af89  mov     [rsp+118h+var_F0], rcx
0x18037af8e  mov     [rsp+118h+var_F8], 0AA1h
0x18037af96  lea     r8, aD_0; "D"
0x18037af9d  jmp     loc_18037B906
0x18037afa2  mov     rcx, r13
0x18037afa5  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18037afab  mov     rbx, rax
0x18037afae  mov     [rsp+118h+var_40], rax
0x18037afb6  test    rax, rax
0x18037afb9  jz      short loc_18037AFCE
0x18037afbb  mov     edx, [rdi]
0x18037afbd  add     rdx, r15
0x18037afc0  mov     rcx, rax
0x18037afc3  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18037afc9  mov     [rbx], r12
0x18037afcc  jmp     short loc_18037AFD1
0x18037afce  mov     rbx, r14
0x18037afd1  mov     rdx, rbx
0x18037afd4  lea     rcx, [rsp+118h+var_B8]
0x18037afd9  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18037afdf  nop
0x18037afe0  lea     rdx, [rsp+118h+var_B8]
0x18037afe5  lea     rcx, [rsp+118h+var_98]
0x18037afed  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x18037aff3  nop
0x18037aff4  lea     rcx, [rsp+118h+var_B8]
0x18037aff9  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18037afff  lea     rcx, [rsp+118h+var_98]
0x18037b007  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18037b00d  mov     rcx, rax
0x18037b010  call    cs:__imp_?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFileName(UnBCL::String const *)
0x18037b016  mov     rdx, rax
0x18037b019  lea     rcx, [rsp+118h+var_B8]
0x18037b01e  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18037b024  nop
0x18037b025  lea     rdx, [rsp+118h+var_B8]
0x18037b02a  lea     rcx, [rsp+118h+var_68]
0x18037b032  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x18037b038  nop
0x18037b039  lea     rcx, [rsp+118h+var_B8]
0x18037b03e  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18037b044  lea     rcx, [rsp+118h+var_98]
0x18037b04c  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18037b052  mov     rcx, rax
0x18037b055  call    cs:__imp_?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetParentPath(UnBCL::String const *)
0x18037b05b  mov     rdx, rax
0x18037b05e  lea     rcx, [rsp+118h+var_B8]
0x18037b063  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18037b069  nop
0x18037b06a  lea     rdx, [rsp+118h+var_B8]
0x18037b06f  lea     rcx, [rsp+118h+var_58]
0x18037b077  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x18037b07d  nop
0x18037b07e  lea     rcx, [rsp+118h+var_B8]
0x18037b083  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18037b089  lea     rcx, [rsp+118h+var_68]
0x18037b091  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18037b097  mov     rbx, rax
0x18037b09a  lea     rcx, [rsp+118h+var_78]
0x18037b0a2  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18037b0a8  mov     rdx, rbx
0x18037b0ab  mov     rcx, rax
0x18037b0ae  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x18037b0b4  mov     rdx, rax
0x18037b0b7  lea     rcx, [rsp+118h+var_B8]
0x18037b0bc  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18037b0c2  nop
0x18037b0c3  lea     rdx, [rsp+118h+var_B8]
0x18037b0c8  lea     rcx, [rsp+118h+var_A8]
0x18037b0cd  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x18037b0d3  nop
0x18037b0d4  lea     rcx, [rsp+118h+var_B8]
0x18037b0d9  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18037b0df  call    cs:__imp_GetLastError
0x18037b0e5  mov     esi, eax
0x18037b0e7  call    cs:__imp_CurrentIP
0x18037b0ed  mov     rdi, rax
0x18037b0f0  lea     rcx, [rsp+118h+var_A8]
0x18037b0f5  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18037b0fb  mov     rcx, rax
0x18037b0fe  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18037b104  mov     rbx, rax
0x18037b107  lea     rcx, [rsp+118h+var_98]
0x18037b10f  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18037b115  mov     rcx, rax
0x18037b118  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18037b11e  mov     r9, rbx
0x18037b121  mov     r8, rax
0x18037b124  lea     rdx, aUpdateTelemetr; "Update telemetry log file from [%s] to "...
0x18037b12b  mov     ecx, 4000000h; unsigned int
0x18037b130  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18037b135  mov     [rsp+118h+var_C8], r14d
0x18037b13a  mov     [rsp+118h+var_D0], r14
0x18037b13f  mov     [rsp+118h+var_D8], esi
0x18037b143  mov     [rsp+118h+var_E0], rdi
0x18037b148  lea     r13, aSpupdateusermo; "SPUpdateUserModeTracingLocation"
0x18037b14f  mov     [rsp+118h+var_E8], r13
0x18037b154  lea     rsi, aBaseNtsetupSet_22; "base\\ntsetup\\setupplatform\\lib\\trac"...
0x18037b15b  mov     [rsp+118h+var_F0], rsi
0x18037b160  mov     [rsp+118h+var_F8], 0AABh
0x18037b168  xor     r9d, r9d
0x18037b16b  lea     r12, aD_0; "D"
0x18037b172  mov     r8, r12
0x18037b175  xor     edx, edx
0x18037b177  mov     rcx, rax
0x18037b17a  call    cs:__imp_WdsSetupLogMessageW
0x18037b180  lea     rcx, [rsp+118h+var_78]
0x18037b188  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18037b18e  mov     rbx, rax
0x18037b191  lea     rcx, [rsp+118h+var_58]
0x18037b199  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18037b19f  mov     rdx, rbx; struct UnBCL::String *
0x18037b1a2  mov     rcx, rax; struct UnBCL::String *
0x18037b1a5  call    ?SPArePathsEqual@@YAHPEAVString@UnBCL@@0@Z; SPArePathsEqual(UnBCL::String *,UnBCL::String *)
0x18037b1aa  test    eax, eax
0x18037b1ac  jz      short loc_18037B210
0x18037b1ae  call    cs:__imp_GetLastError
0x18037b1b4  mov     edi, eax
0x18037b1b6  call    cs:__imp_CurrentIP
0x18037b1bc  mov     rbx, rax
0x18037b1bf  lea     rdx, aTheCurrentLogL; "The current log location and new log lo"...
0x18037b1c6  mov     ecx, 4000000h; unsigned int
0x18037b1cb  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18037b1d0  mov     [rsp+118h+var_C8], r14d
0x18037b1d5  mov     [rsp+118h+var_D0], r14
0x18037b1da  mov     [rsp+118h+var_D8], edi
0x18037b1de  mov     [rsp+118h+var_E0], rbx
0x18037b1e3  mov     [rsp+118h+var_E8], r13
0x18037b1e8  mov     [rsp+118h+var_F0], rsi
0x18037b1ed  mov     [rsp+118h+var_F8], 0AAEh
0x18037b1f5  xor     r9d, r9d
0x18037b1f8  mov     r8, r12
0x18037b1fb  xor     edx, edx
0x18037b1fd  mov     rcx, rax
0x18037b200  call    cs:__imp_WdsSetupLogMessageW
0x18037b206  mov     esi, 1
0x18037b20b  jmp     loc_18037B914
0x18037b210  lea     rcx, [rsp+118h+var_A8]
0x18037b215  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18037b21b  mov     rcx, rax
0x18037b21e  call    cs:__imp_?get_Length@String@UnBCL@@QEBAHXZ; UnBCL::String::get_Length(void)
0x18037b224  inc     eax
0x18037b226  cmp     eax, 400h
0x18037b22b  jle     short loc_18037B2A6
0x18037b22d  call    cs:__imp_GetLastError
0x18037b233  mov     edi, eax
0x18037b235  call    cs:__imp_CurrentIP
0x18037b23b  mov     rbx, rax
0x18037b23e  lea     rcx, [rsp+118h+var_A8]
0x18037b243  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18037b249  mov     rcx, rax
0x18037b24c  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18037b252  mov     r8, rax
0x18037b255  lea     rdx, aNewTraceFileNa; "New trace file name [%s] is longger tha"...
0x18037b25c  mov     ecx, 2000000h; unsigned int
0x18037b261  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18037b266  mov     [rsp+118h+var_C8], r14d
0x18037b26b  mov     [rsp+118h+var_D0], r14
0x18037b270  mov     [rsp+118h+var_D8], edi
0x18037b274  mov     [rsp+118h+var_E0], rbx
0x18037b279  mov     [rsp+118h+var_E8], r13
0x18037b27e  mov     [rsp+118h+var_F0], rsi
0x18037b283  mov     [rsp+118h+var_F8], 0AB5h
0x18037b28b  xor     r9d, r9d
0x18037b28e  mov     r8, r12
0x18037b291  xor     edx, edx
0x18037b293  mov     rcx, rax
0x18037b296  call    cs:__imp_WdsSetupLogMessageW
0x18037b29c  mov     esi, 8007006Fh
0x18037b2a1  jmp     loc_18037B914
0x18037b2a6  lea     rcx, [rsp+118h+var_A8]
0x18037b2ab  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18037b2b1  mov     rcx, rax
0x18037b2b4  call    cs:__imp_?Exists@File@UnBCL@@SAHPEBVString@2@@Z; UnBCL::File::Exists(UnBCL::String const *)
0x18037b2ba  test    eax, eax
0x18037b2bc  jz      loc_18037B435
0x18037b2c2  call    cs:__imp_GetLastError
0x18037b2c8  mov     edi, eax
0x18037b2ca  call    cs:__imp_CurrentIP
0x18037b2d0  mov     rbx, rax
0x18037b2d3  lea     rcx, [rsp+118h+var_A8]
0x18037b2d8  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18037b2de  mov     rcx, rax
0x18037b2e1  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18037b2e7  mov     r8, rax
0x18037b2ea  lea     rdx, aFileSAlreadyEx; "File [%s] already exists, will try a ne"...
0x18037b2f1  mov     ecx, 4000000h; unsigned int
0x18037b2f6  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18037b2fb  mov     [rsp+118h+var_C8], r14d
0x18037b300  mov     [rsp+118h+var_D0], r14
0x18037b305  mov     [rsp+118h+var_D8], edi
0x18037b309  mov     [rsp+118h+var_E0], rbx
0x18037b30e  mov     [rsp+118h+var_E8], r13
0x18037b313  mov     [rsp+118h+var_F0], rsi
0x18037b318  mov     [rsp+118h+var_F8], 0ABFh
0x18037b320  xor     r9d, r9d
0x18037b323  mov     r8, r12
0x18037b326  xor     edx, edx
0x18037b328  mov     rcx, rax
0x18037b32b  call    cs:__imp_WdsSetupLogMessageW
0x18037b331  lea     rcx, [rsp+118h+var_A8]
0x18037b336  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18037b33c  mov     rcx, rax
0x18037b33f  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18037b345  mov     rcx, rax; unsigned __int16 *
0x18037b348  xor     r8d, r8d; unsigned __int16 *
0x18037b34b  lea     rdx, aMove_0; ".Move."
  ... truncated ...
```
