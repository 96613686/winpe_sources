# OSRollbackService::CCheckpoint::MoveOrCopyFiles(UnBCL::String const &,UnBCL::String const &,UnBCL::String const &,UnBCL::String const &,UnBCL::String const &)

- ea: `0x18047c9fc`
- end: `0x18047d4aa`
- name: `?MoveOrCopyFiles@CCheckpoint@OSRollbackService@@IEAAHAEBVString@UnBCL@@0000@Z`
- size: `2734`
- prototype: `__int64 __fastcall(OSRollbackService::CCheckpoint *__hidden this, const struct UnBCL::String *, const struct UnBCL::String *, const struct UnBCL::String *, const struct UnBCL::String *, const struct UnBCL::String *)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1802a0158`
- `0x1802a1140`
- `0x1802aa1e0`
- `0x18047e04c`

## callees

- `0x180057dec`
- `0x18047c9fc`
- `0x180509010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18047ca42`
- `KERNEL32!GetLastError` at `0x18047cae0`
- `KERNEL32!GetLastError` at `0x18047caf1`
- `KERNEL32!GetLastError` at `0x18047d04b`
- `KERNEL32!GetLastError` at `0x18047d0af`
- `KERNEL32!GetLastError` at `0x18047d0bf`
- `KERNEL32!GetLastError` at `0x18047d174`
- `KERNEL32!GetLastError` at `0x18047d232`
- `KERNEL32!GetLastError` at `0x18047d32a`
- `KERNEL32!GetLastError` at `0x18047d352`
- `KERNEL32!GetLastError` at `0x18047d3a9`
- `KERNEL32!GetLastError` at `0x18047d3d1`
- `KERNEL32!GetLastError` at `0x18047ca42`
- `KERNEL32!GetLastError` at `0x18047cae0`
- `KERNEL32!GetLastError` at `0x18047caf1`
- `KERNEL32!GetLastError` at `0x18047d04b`
- `KERNEL32!GetLastError` at `0x18047d0af`
- `KERNEL32!GetLastError` at `0x18047d0bf`
- `KERNEL32!GetLastError` at `0x18047d174`
- `KERNEL32!GetLastError` at `0x18047d232`
- `KERNEL32!GetLastError` at `0x18047d32a`
- `KERNEL32!GetLastError` at `0x18047d352`
- `KERNEL32!GetLastError` at `0x18047d3a9`
- `KERNEL32!GetLastError` at `0x18047d3d1`
- `KERNEL32!CreateDirectoryW` at `0x18047cad2`
- `KERNEL32!CreateDirectoryW` at `0x18047cad2`
- `KERNEL32!SetFileAttributesW` at `0x18047d31c`
- `KERNEL32!SetFileAttributesW` at `0x18047d31c`
- `KERNEL32!GetFileAttributesW` at `0x18047d2ef`
- `KERNEL32!GetFileAttributesW` at `0x18047d2ef`
- `KERNEL32!MoveFileExW` at `0x18047d043`
- `KERNEL32!MoveFileExW` at `0x18047d043`
- `KERNEL32!CopyFileExW` at `0x18047d0a7`
- `KERNEL32!CopyFileExW` at `0x18047d0a7`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x18047cbd0`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x18047cc16`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x18047ccb6`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x18047cd21`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x18047cd94`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x18047cbd0`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x18047cc16`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x18047ccb6`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x18047cd21`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x18047cd94`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047cbb8`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047d486`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047cbb8`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047d486`
- `unbcl!?GetFiles@Directory@UnBCL@@SAPEAV?$Array@PEAVString@UnBCL@@@2@PEBVString@2@0H@Z` at `0x18047cb85`
- `unbcl!?GetFiles@Directory@UnBCL@@SAPEAV?$Array@PEAVString@UnBCL@@@2@PEBVString@2@0H@Z` at `0x18047cb85`
- `unbcl!??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z` at `0x18047cb96`
- `unbcl!??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z` at `0x18047cb96`
- `unbcl!?GetFileNameWithoutExtension@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18047cd48`
- `unbcl!?GetFileNameWithoutExtension@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18047cd48`
- `unbcl!?GetFileNameExtension@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18047cdbb`
- `unbcl!?GetFileNameExtension@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18047cdbb`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18047cc92`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18047cca4`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18047ce01`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18047ce8c`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18047cc92`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18047cca4`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18047ce01`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18047ce8c`
- `unbcl!?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18047cc3d`
- `unbcl!?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18047ccdd`
- `unbcl!?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18047cc3d`
- `unbcl!?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18047ccdd`
- `unbcl!?get_P@?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@2@XZ` at `0x18047cba5`
- `unbcl!?get_P@?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@2@XZ` at `0x18047cba5`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x18047ca31`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x18047ca31`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18047cfc6`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18047cff7`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18047cfc6`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18047cff7`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z` at `0x18047ce36`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z` at `0x18047cec1`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z` at `0x18047cf43`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z` at `0x18047ce36`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z` at `0x18047cec1`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z` at `0x18047cf43`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047cc5d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047cd62`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047cddb`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047ce75`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047cf00`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047cfa3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047cfba`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047cfe6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047cc5d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047cd62`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047cddb`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047ce75`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047cf00`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047cfa3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047cfba`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18047cfe6`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18047cc83`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18047cc83`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18047cd05`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18047ce5b`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18047cee6`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18047cf6b`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18047cd05`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18047ce5b`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18047cee6`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18047cf6b`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047ce10`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047ceac`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047cf17`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047cf2e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047d011`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047d02b`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047d061`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047d07b`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047d0d6`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047d0f0`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047d18a`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047d1a4`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047d248`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047d262`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047d2dd`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047d308`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047d340`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047d3bf`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047ce10`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047ceac`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047cf17`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047cf2e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047d011`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047d02b`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047d061`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047d07b`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047d0d6`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047d0f0`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047d18a`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047d1a4`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047d248`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047d262`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047d2dd`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047d308`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047d340`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18047d3bf`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047ca56`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047cac7`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047cb05`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047ce19`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047ce2a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047ce9e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047ceb5`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047cf20`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047cf37`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047d01a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047d034`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047d06a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047d084`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047d0df`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047d0f9`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047d193`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047d1ad`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047d251`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047d26b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047d2e6`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047d311`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047d349`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047d3c8`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047ca56`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047cac7`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047cb05`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047ce19`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047ce2a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047ce9e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047ceb5`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047cf20`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047cf37`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047d01a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047d034`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047d06a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047d084`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047d0df`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047d0f9`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047d193`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047d1ad`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047d251`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047d26b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047d2e6`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047d311`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047d349`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18047d3c8`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047cc70`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047cd72`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047cd81`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047cdee`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047ce6a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047cef5`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047cf7a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047cf89`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047cf95`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18047d434`

## string_xrefs

- `0x18047ca8f`: `base\ntsetup\lib\rollback\src\rollback.cpp`
- `0x18047cb3e`: `base\ntsetup\lib\rollback\src\rollback.cpp`
- `0x18047d13d`: `base\ntsetup\lib\rollback\src\rollback.cpp`
- `0x18047d1fa`: `base\ntsetup\lib\rollback\src\rollback.cpp`
- `0x18047d2a7`: `base\ntsetup\lib\rollback\src\rollback.cpp`
- `0x18047d2d1`: `base\ntsetup\lib\rollback\src\rollback.cpp`
- `0x18047d1c3`: `OSRollbackService::CCheckpoint::MoveOrCopyFiles: failed to move (error %u) or copy (error %u) from %s to %s`
- `0x18047d3dd`: `OSRollbackService::CCheckpoint::MoveOrCopyFiles: failed to get attributes (error %u) from %s`
- `0x18047ca5f`: `OSRollbackService::CCheckpoint::MoveOrCopyFiles: Source directory %s does not exist; nothing to do`
- `0x18047ca83`: `OSRollbackService::CCheckpoint::MoveOrCopyFiles`
- `0x18047cb32`: `OSRollbackService::CCheckpoint::MoveOrCopyFiles`
- `0x18047cbf7`: `OSRollbackService::CCheckpoint::MoveOrCopyFiles`
- `0x18047d131`: `OSRollbackService::CCheckpoint::MoveOrCopyFiles`
- `0x18047d1ee`: `OSRollbackService::CCheckpoint::MoveOrCopyFiles`
- `0x18047d38e`: `OSRollbackService::CCheckpoint::MoveOrCopyFiles`
- `0x18047d363`: `OSRollbackService::CCheckpoint::MoveOrCopyFiles: failed to set attributes 0x%08x (error %u) on %s`
- `0x18047d105`: `OSRollbackService::CCheckpoint::MoveOrCopyFiles: Copied %s to %s`
- `0x18047d277`: `OSRollbackService::CCheckpoint::MoveOrCopyFiles: Moved %s to %s`
- `0x18047cb0e`: `OSRollbackService::CCheckpoint::MoveOrCopyFiles: failed to create %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=2
__int64 __fastcall OSRollbackService::CCheckpoint::MoveOrCopyFiles(
        OSRollbackService::CCheckpoint *this,
        const struct UnBCL::String *a2,
        const struct UnBCL::String *a3,
        const struct UnBCL::String *a4,
        const struct UnBCL::String *a5,
        const struct UnBCL::String *a6)
{
  UnBCL::String *v8; // rsi
  DWORD LastError; // edi
  __int64 v10; // rbx
  const char *CString; // rax
  struct tagLOG_PARTIAL_MSG *v12; // rax
  const WCHAR *v14; // rax
  DWORD v15; // edi
  __int64 v16; // rbx
  const char *v17; // rax
  struct tagLOG_PARTIAL_MSG *v18; // rax
  __int64 Files; // rax
  unsigned int v20; // r13d
  __int64 v21; // rax
  __int64 (__fastcall ***v22)(_QWORD); // rcx
  int v23; // eax
  __int64 v24; // rax
  __int64 v25; // rcx
  const struct UnBCL::String **v26; // rax
  struct UnBCL::String *FileName; // rax
  __int64 v28; // rax
  __int64 v29; // rcx
  const struct UnBCL::String **v30; // rax
  struct UnBCL::String *v31; // rax
  _BYTE *v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rcx
  const struct UnBCL::String **v35; // rax
  struct UnBCL::String *FileNameWithoutExtension; // rax
  __int64 v37; // rax
  __int64 v38; // rcx
  const struct UnBCL::String **v39; // rax
  struct UnBCL::String *FileNameExtension; // rax
  UnBCL::String *v41; // rax
  const unsigned __int16 *v42; // rbx
  const unsigned __int16 *v43; // rax
  struct UnBCL::String *v44; // rax
  const unsigned __int16 *v45; // rbx
  UnBCL::String *v46; // rax
  const unsigned __int16 *v47; // rax
  struct UnBCL::String *v48; // rax
  UnBCL::String *v49; // rax
  const unsigned __int16 *v50; // rbx
  UnBCL::String *v51; // rax
  const unsigned __int16 *v52; // rax
  struct UnBCL::String *v53; // rax
  const struct UnBCL::String *P; // rax
  struct UnBCL::String *v55; // rax
  const struct UnBCL::String *v56; // rax
  struct UnBCL::String *v57; // rax
  UnBCL::String *v58; // rax
  const WCHAR *v59; // rbx
  UnBCL::String *v60; // rax
  const WCHAR *v61; // rax
  DWORD v62; // r12d
  UnBCL::String *v63; // rax
  const WCHAR *v64; // rbx
  UnBCL::String *v65; // rax
  const WCHAR *v66; // rax
  DWORD v67; // edi
  DWORD v68; // r14d
  __int64 v69; // r15
  UnBCL::String *v70; // rax
  const char *v71; // rsi
  UnBCL::String *v72; // rax
  const char *v73; // rax
  struct tagLOG_PARTIAL_MSG *v74; // rax
  DWORD v75; // esi
  __int64 v76; // r14
  UnBCL::String *v77; // rax
  const char *v78; // rbx
  UnBCL::String *v79; // rax
  const char *v80; // rax
  struct tagLOG_PARTIAL_MSG *v81; // rax
  DWORD v82; // edi
  __int64 v83; // rsi
  UnBCL::String *v84; // rax
  const char *v85; // rbx
  UnBCL::String *v86; // rax
  const char *v87; // rax
  struct tagLOG_PARTIAL_MSG *v88; // rax
  UnBCL::String *v89; // rax
  const WCHAR *v90; // rax
  DWORD FileAttributesW; // ebx
  DWORD v92; // ebx
  UnBCL::String *v93; // rax
  const WCHAR *v94; // rax
  DWORD v95; // esi
  __int64 v96; // r14
  UnBCL::String *v97; // rax
  const char *v98; // rdi
  DWORD v99; // eax
  struct tagLOG_PARTIAL_MSG *v100; // rax
  DWORD v101; // edi
  __int64 v102; // rsi
  UnBCL::String *v103; // rax
  const char *v104; // rbx
  DWORD v105; // eax
  struct tagLOG_PARTIAL_MSG *v106; // rax
  _BYTE v107[16]; // [rsp+60h] [rbp-138h] BYREF
  _BYTE v108[16]; // [rsp+70h] [rbp-128h] BYREF
  _BYTE v109[16]; // [rsp+80h] [rbp-118h] BYREF
  _BYTE v110[16]; // [rsp+90h] [rbp-108h] BYREF
  _BYTE v111[16]; // [rsp+A0h] [rbp-F8h] BYREF
  int v112; // [rsp+B0h] [rbp-E8h]
  _BYTE v113[16]; // [rsp+B8h] [rbp-E0h] BYREF
  _BYTE v114[16]; // [rsp+C8h] [rbp-D0h] BYREF
  _BYTE v115[16]; // [rsp+D8h] [rbp-C0h] BYREF
  _BYTE v116[16]; // [rsp+E8h] [rbp-B0h] BYREF
  _BYTE v117[16]; // [rsp+F8h] [rbp-A0h] BYREF
  _BYTE v118[16]; // [rsp+108h] [rbp-90h] BYREF
  __int64 v119; // [rsp+118h] [rbp-80h]
  unsigned int v120; // [rsp+1A0h] [rbp+8h]

  v119 = -2;
  v8 = a2;
  if ( !UnBCL::Directory::Exists(a2) )
  {
    LastError = GetLastError();
    v10 = CurrentIP();
    CString = (const char *)UnBCL::String::get_CString(v8);
    v12 = ConstructPartialMsgW(
            0x4000000u,
            "OSRollbackService::CCheckpoint::MoveOrCopyFiles: Source directory %s does not exist; nothing to do",
            CString);
    WdsSetupLogMessageW(
      v12,
      409600,
      L"D",
      0,
      129,
      L"base\\ntsetup\\lib\\rollback\\src\\rollback.cpp",
      L"OSRollbackService::CCheckpoint::MoveOrCopyFiles",
      v10,
      LastError,
      0,
      0);
    return 1;
  }
  v14 = UnBCL::String::get_CString(a3);
  if ( !CreateDirectoryW(v14, 0) && GetLastError() != 183 )
  {
    v15 = GetLastError();
    v16 = CurrentIP();
    v17 = (const char *)UnBCL::String::get_CString(a3);
    v18 = ConstructPartialMsgW(0x28001C5u, "OSRollbackService::CCheckpoint::MoveOrCopyFiles: failed to create %s", v17);
    WdsSetupLogMessageW(
      v18,
      409600,
      L"D",
      0,
      137,
      L"base\\ntsetup\\lib\\rollback\\src\\rollback.cpp",
      L"OSRollbackService::CCheckpoint::MoveOrCopyFiles",
      v16,
      v15,
      0,
      0);
    return 0;
  }
  v120 = 1;
  Files = UnBCL::Directory::GetFiles(v8, a4, 0);
  UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::SmartPtr<UnBCL::Array<UnBCL::String *>>(v111, Files);
  if ( !UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::get_P(v111) )
  {
    UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::~SmartPtr<UnBCL::Array<UnBCL::String *>>(v111);
    return 0;
  }
  v20 = 0;
  v21 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v111);
  v22 = (__int64 (__fastcall ***)(_QWORD))(v21 + 8 + *(int *)(*(_QWORD *)(v21 + 8) + 12LL));
  v23 = (**v22)(v22);
  v112 = v23;
  while ( (int)v20 < v23 )
  {
    v24 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v111);
    v25 = v24 + 8 + *(int *)(*(_QWORD *)(v24 + 8) + 16LL);
    v26 = (const struct UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v25 + 24LL))(v25, v20);
    FileName = UnBCL::Path::GetFileName(*v26);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v110, FileName);
    if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(v110) )
      goto LABEL_11;
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v109);
    if ( (int)UnBCL::String::get_Length(a5) > 0 || (int)UnBCL::String::get_Length(a6) > 0 )
    {
      v33 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v111);
      v34 = v33 + 8 + *(int *)(*(_QWORD *)(v33 + 8) + 16LL);
      v35 = (const struct UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v34 + 24LL))(
                                             v34,
                                             v20);
      FileNameWithoutExtension = UnBCL::Path::GetFileNameWithoutExtension(*v35);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v107, FileNameWithoutExtension);
      if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(v107) )
        goto LABEL_16;
      v37 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v111);
      v38 = v37 + 8 + *(int *)(*(_QWORD *)(v37 + 8) + 16LL);
      v39 = (const struct UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v38 + 24LL))(
                                             v38,
                                             v20);
      FileNameExtension = UnBCL::Path::GetFileNameExtension(*v39);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v113, FileNameExtension);
      if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(v113) )
        goto LABEL_19;
      if ( (int)UnBCL::String::get_Length(a5) > 0 )
      {
        v41 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v107);
        v42 = UnBCL::String::get_CString(v41);
        v43 = UnBCL::String::get_CString(a5);
        v44 = UnBCL::String::Concat(v43, v42);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v116, v44);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v107, v116);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v116);
        if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(v107) )
          goto LABEL_19;
      }
      if ( (int)UnBCL::String::get_Length(a6) > 0 )
      {
        v45 = UnBCL::String::get_CString(a6);
        v46 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v107);
        v47 = UnBCL::String::get_CString(v46);
        v48 = UnBCL::String::Concat(v47, v45);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v117, v48);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v107, v117);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v117);
        if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(v107) )
        {
LABEL_19:
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v113);
LABEL_16:
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v107);
LABEL_17:
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v109);
LABEL_11:
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v110);
          goto LABEL_37;
        }
      }
      v49 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v113);
      v50 = UnBCL::String::get_CString(v49);
      v51 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v107);
      v52 = UnBCL::String::get_CString(v51);
      v53 = UnBCL::String::Concat(v52, v50);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v118, v53);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v109, v118);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v118);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v113);
      v32 = v107;
    }
    else
    {
      v28 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v111);
      v29 = v28 + 8 + *(int *)(*(_QWORD *)(v28 + 8) + 16LL);
      v30 = (const struct UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v29 + 24LL))(
                                             v29,
                                             v20);
      v31 = UnBCL::Path::GetFileName(*v30);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v115, v31);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v109, v115);
      v32 = v115;
    }
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v32);
    if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(v109) )
      goto LABEL_17;
    P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v110);
    v55 = UnBCL::Path::Combine(v8, P);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v114, v55);
    v56 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v109);
    v57 = UnBCL::Path::Combine(a3, v56);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v108, v57);
    v58 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v108);
    v59 = UnBCL::String::get_CString(v58);
    v60 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v114);
    v61 = UnBCL::String::get_CString(v60);
    LODWORD(v59) = MoveFileExW(v61, v59, 0);
    v62 = GetLastError();
    if ( (_DWORD)v59 )
    {
      v82 = GetLastError();
      v83 = CurrentIP();
      v84 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v108);
      v85 = (const char *)UnBCL::String::get_CString(v84);
      v86 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v114);
      v87 = (const char *)UnBCL::String::get_CString(v86);
      v88 = ConstructPartialMsgW(
              0x4000000u,
              "OSRollbackService::CCheckpoint::MoveOrCopyFiles: Moved %s to %s",
              v87,
              v85);
      WdsSetupLogMessageW(
        v88,
        409600,
        L"D",
        0,
        221,
        L"base\\ntsetup\\lib\\rollback\\src\\rollback.cpp",
        L"OSRollbackService::CCheckpoint::MoveOrCopyFiles",
        v83,
        v82,
        0,
        0);
LABEL_31:
      v89 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v108);
      v90 = UnBCL::String::get_CString(v89);
      FileAttributesW = GetFileAttributesW(v90);
      if ( FileAttributesW == -1 )
      {
        v101 = GetLastError();
        v102 = CurrentIP();
        v103 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v108);
        v104 = (const char *)UnBCL::String::get_CString(v103);
        v105 = GetLastError();
        v106 = ConstructPartialMsgW(
                 0x2000000u,
                 "OSRollbackService::CCheckpoint::MoveOrCopyFiles: failed to get attributes (error %u) from %s",
                 v105,
                 v104);
        WdsSetupLogMessageW(
          v106,
          409600,
          L"D",
          0,
          250,
          L"base\\ntsetup\\lib\\rollback\\src\\rollback.cpp",
          L"OSRollbackService::CCheckpoint::MoveOrCopyFiles",
          v102,
          v101,
          0,
          0);
      }
      else
      {
        v92 = FileAttributesW & 0xFFFFFFF9;
        v93 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v108);
        v94 = UnBCL::String::get_CString(v93);
        if ( !SetFileAttributesW(v94, v92) )
        {
          v95 = GetLastError();
          v96 = CurrentIP();
          v97 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v108);
          v98 = (const char *)UnBCL::String::get_CString(v97);
          v99 = GetLastError();
          v100 = ConstructPartialMsgW(
                   0x2000000u,
                   "OSRollbackService::CCheckpoint::MoveOrCopyFiles: failed to set attributes 0x%08x (error %u) on %s",
                   v92,
                   v99,
                   v98);
          WdsSetupLogMessageW(
            v100,
            409600,
            L"D",
            0,
            242,
            L"base\\ntsetup\\lib\\rollback\\src\\rollback.cpp",
            L"OSRollbackService::CCheckpoint::MoveOrCopyFiles",
            v96,
            v95,
            0,
            0);
        }
      }
      goto LABEL_36;
    }
    v63 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v108);
    v64 = UnBCL::String::get_CString(v63);
    v65 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v114);
    v66 = UnBCL::String::get_CString(v65);
    LODWORD(v64) = CopyFileExW(v66, v64, 0, 0, 0, 0);
    v67 = GetLastError();
    if ( (_DWORD)v64 )
    {
      v68 = GetLastError();
      v69 = CurrentIP();
      v70 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v108);
      v71 = (const char *)UnBCL::String::get_CString(v70);
      v72 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v114);
      v73 = (const char *)UnBCL::String::get_CString(v72);
      v74 = ConstructPartialMsgW(
              0x4000000u,
              "OSRollbackService::CCheckpoint::MoveOrCopyFiles: Copied %s to %s",
              v73,
              v71);
      WdsSetupLogMessageW(
        v74,
        409600,
        L"D",
        0,
        226,
        L"base\\ntsetup\\lib\\rollback\\src\\rollback.cpp",
        L"OSRollbackService::CCheckpoint::MoveOrCopyFiles",
        v69,
        v68,
        0,
        0);
      goto LABEL_31;
    }
    v75 = GetLastError();
    v76 = CurrentIP();
    v77 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v108);
    v78 = (const char *)UnBCL::String::get_CString(v77);
    v79 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v114);
    v80 = (const char *)UnBCL::String::get_CString(v79);
    v81 = ConstructPartialMsgW(
            0x28001C3u,
            "OSRollbackService::CCheckpoint::MoveOrCopyFiles: failed to move (error %u) or copy (error %u) from %s to %s",
            v62,
            v67,
            v80,
            v78);
    WdsSetupLogMessageW(
      v81,
      409600,
      L"D",
      0,
      260,
      L"base\\ntsetup\\lib\\rollback\\src\\rollback.cpp",
      L"OSRollbackService::CCheckpoint::MoveOrCopyFiles",
      v76,
      v75,
      0,
      0);
    v120 = 0;
LABEL_36:
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v108);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v114);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v109);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v110);
    v8 = a2;
LABEL_37:
    ++v20;
    v23 = v112;
  }
  UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::~SmartPtr<UnBCL::Array<UnBCL::String *>>(v111);
  return v120;
}

```

## disassembly

```asm
0x18047c9fc  mov     rax, rsp
0x18047c9ff  mov     [rax+18h], r8
0x18047ca03  mov     [rax+10h], rdx
0x18047ca07  mov     [rax+8], rcx
0x18047ca0b  push    rbx
0x18047ca0c  push    rsi
0x18047ca0d  push    rdi
0x18047ca0e  push    r12
0x18047ca10  push    r13
0x18047ca12  push    r14
0x18047ca14  push    r15
0x18047ca16  sub     rsp, 160h
0x18047ca1d  mov     qword ptr [rax-80h], 0FFFFFFFFFFFFFFFEh
0x18047ca25  mov     rbx, r9
0x18047ca28  mov     r14, r8
0x18047ca2b  mov     rsi, rdx
0x18047ca2e  mov     rcx, rdx
0x18047ca31  call    cs:__imp_?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z; UnBCL::Directory::Exists(UnBCL::String const *)
0x18047ca37  xor     r15d, r15d
0x18047ca3a  test    eax, eax
0x18047ca3c  jnz     loc_18047CAC4
0x18047ca42  call    cs:__imp_GetLastError
0x18047ca48  mov     edi, eax
0x18047ca4a  call    cs:__imp_CurrentIP
0x18047ca50  mov     rbx, rax
0x18047ca53  mov     rcx, rsi
0x18047ca56  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18047ca5c  mov     r8, rax
0x18047ca5f  lea     rdx, aOsrollbackserv_7; "OSRollbackService::CCheckpoint::MoveOrC"...
0x18047ca66  mov     ecx, 4000000h; unsigned int
0x18047ca6b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18047ca70  mov     [rsp+198h+var_148], r15d
0x18047ca75  mov     [rsp+198h+var_150], r15
0x18047ca7a  mov     [rsp+198h+var_158], edi
0x18047ca7e  mov     [rsp+198h+var_160], rbx
0x18047ca83  lea     rcx, aOsrollbackserv_18; "OSRollbackService::CCheckpoint::MoveOrC"...
0x18047ca8a  mov     [rsp+198h+var_168], rcx
0x18047ca8f  lea     rcx, aBaseNtsetupLib_0; "base\\ntsetup\\lib\\rollback\\src\\roll"...
0x18047ca96  mov     qword ptr [rsp+198h+dwCopyFlags], rcx
0x18047ca9b  mov     dword ptr [rsp+198h+pbCancel], 81h
0x18047caa3  xor     r9d, r9d
0x18047caa6  lea     r8, aD_0; "D"
0x18047caad  mov     edx, 64000h
0x18047cab2  mov     rcx, rax
0x18047cab5  call    cs:__imp_WdsSetupLogMessageW
0x18047cabb  lea     eax, [r15+1]
0x18047cabf  jmp     loc_18047D496
0x18047cac4  mov     rcx, r14
0x18047cac7  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18047cacd  mov     rcx, rax; lpPathName
0x18047cad0  xor     edx, edx; lpSecurityAttributes
0x18047cad2  call    cs:__imp_CreateDirectoryW
0x18047cad8  test    eax, eax
0x18047cada  jnz     loc_18047CB71
0x18047cae0  call    cs:__imp_GetLastError
0x18047cae6  cmp     eax, 0B7h
0x18047caeb  jz      loc_18047CB71
0x18047caf1  call    cs:__imp_GetLastError
0x18047caf7  mov     edi, eax
0x18047caf9  call    cs:__imp_CurrentIP
0x18047caff  mov     rbx, rax
0x18047cb02  mov     rcx, r14
0x18047cb05  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18047cb0b  mov     r8, rax
0x18047cb0e  lea     rdx, aOsrollbackserv_22; "OSRollbackService::CCheckpoint::MoveOrC"...
0x18047cb15  mov     ecx, 28001C5h; unsigned int
0x18047cb1a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18047cb1f  mov     [rsp+198h+var_148], r15d
0x18047cb24  mov     [rsp+198h+var_150], r15
0x18047cb29  mov     [rsp+198h+var_158], edi
0x18047cb2d  mov     [rsp+198h+var_160], rbx
0x18047cb32  lea     rcx, aOsrollbackserv_18; "OSRollbackService::CCheckpoint::MoveOrC"...
0x18047cb39  mov     [rsp+198h+var_168], rcx
0x18047cb3e  lea     rcx, aBaseNtsetupLib_0; "base\\ntsetup\\lib\\rollback\\src\\roll"...
0x18047cb45  mov     qword ptr [rsp+198h+dwCopyFlags], rcx
0x18047cb4a  mov     dword ptr [rsp+198h+pbCancel], 89h
0x18047cb52  xor     r9d, r9d
0x18047cb55  lea     r8, aD_0; "D"
0x18047cb5c  mov     edx, 64000h
0x18047cb61  mov     rcx, rax
0x18047cb64  call    cs:__imp_WdsSetupLogMessageW
0x18047cb6a  xor     eax, eax
0x18047cb6c  jmp     loc_18047D496
0x18047cb71  mov     [rsp+198h+arg_0], 1
0x18047cb7c  xor     r8d, r8d
0x18047cb7f  mov     rdx, rbx
0x18047cb82  mov     rcx, rsi
0x18047cb85  call    cs:__imp_?GetFiles@Directory@UnBCL@@SAPEAV?$Array@PEAVString@UnBCL@@@2@PEBVString@2@0H@Z; UnBCL::Directory::GetFiles(UnBCL::String const *,UnBCL::String const *,int)
0x18047cb8b  mov     rdx, rax
0x18047cb8e  lea     rcx, [rsp+198h+var_F8]
0x18047cb96  call    cs:__imp_??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::SmartPtr<UnBCL::Array<UnBCL::String *>>(UnBCL::Array<UnBCL::String *> *)
0x18047cb9c  nop
0x18047cb9d  lea     rcx, [rsp+198h+var_F8]
0x18047cba5  call    cs:__imp_?get_P@?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@2@XZ; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::get_P(void)
0x18047cbab  test    rax, rax
0x18047cbae  jnz     short loc_18047CBC5
0x18047cbb0  lea     rcx, [rsp+198h+var_F8]
0x18047cbb8  call    cs:__imp_??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::~SmartPtr<UnBCL::Array<UnBCL::String *>>(void)
0x18047cbbe  xor     eax, eax
0x18047cbc0  jmp     loc_18047D496
0x18047cbc5  xor     r13d, r13d
0x18047cbc8  lea     rcx, [rsp+198h+var_F8]
0x18047cbd0  call    cs:__imp_??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(void)
0x18047cbd6  mov     rcx, [rax+8]
0x18047cbda  movsxd  rcx, dword ptr [rcx+0Ch]
0x18047cbde  add     rax, 8
0x18047cbe2  add     rcx, rax
0x18047cbe5  mov     rax, [rcx]
0x18047cbe8  mov     rax, [rax]
0x18047cbeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18047cbf0  mov     [rsp+198h+var_E8], eax
0x18047cbf7  lea     r14, aOsrollbackserv_18; "OSRollbackService::CCheckpoint::MoveOrC"...
0x18047cbfe  lea     r15, aD_0; "D"
0x18047cc05  cmp     r13d, eax
0x18047cc08  jge     loc_18047D47E
0x18047cc0e  lea     rcx, [rsp+198h+var_F8]
0x18047cc16  call    cs:__imp_??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(void)
0x18047cc1c  mov     rcx, [rax+8]
0x18047cc20  movsxd  rcx, dword ptr [rcx+10h]
0x18047cc24  add     rax, 8
0x18047cc28  add     rcx, rax
0x18047cc2b  mov     rax, [rcx]
0x18047cc2e  mov     edx, r13d
0x18047cc31  mov     rax, [rax+18h]
0x18047cc35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18047cc3a  mov     rcx, [rax]
0x18047cc3d  call    cs:__imp_?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFileName(UnBCL::String const *)
0x18047cc43  mov     rdx, rax
0x18047cc46  lea     rcx, [rsp+198h+var_108]
0x18047cc4e  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18047cc54  nop
0x18047cc55  lea     rcx, [rsp+198h+var_108]
0x18047cc5d  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18047cc63  test    rax, rax
0x18047cc66  jnz     short loc_18047CC7B
0x18047cc68  lea     rcx, [rsp+198h+var_108]
0x18047cc70  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18047cc76  jmp     loc_18047D46F
0x18047cc7b  lea     rcx, [rsp+198h+var_118]
0x18047cc83  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x18047cc89  nop
0x18047cc8a  mov     rcx, [rsp+198h+arg_20]
0x18047cc92  call    cs:__imp_?get_Length@String@UnBCL@@QEBAHXZ; UnBCL::String::get_Length(void)
0x18047cc98  test    eax, eax
0x18047cc9a  jg      short loc_18047CD19
0x18047cc9c  mov     rcx, [rsp+198h+arg_28]
0x18047cca4  call    cs:__imp_?get_Length@String@UnBCL@@QEBAHXZ; UnBCL::String::get_Length(void)
0x18047ccaa  test    eax, eax
0x18047ccac  jg      short loc_18047CD19
0x18047ccae  lea     rcx, [rsp+198h+var_F8]
0x18047ccb6  call    cs:__imp_??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(void)
0x18047ccbc  mov     rcx, [rax+8]
0x18047ccc0  movsxd  rcx, dword ptr [rcx+10h]
0x18047ccc4  add     rax, 8
0x18047ccc8  add     rcx, rax
0x18047cccb  mov     rax, [rcx]
0x18047ccce  mov     edx, r13d
0x18047ccd1  mov     rax, [rax+18h]
0x18047ccd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18047ccda  mov     rcx, [rax]
0x18047ccdd  call    cs:__imp_?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFileName(UnBCL::String const *)
0x18047cce3  mov     rdx, rax
0x18047cce6  lea     rcx, [rsp+198h+var_C0]
0x18047ccee  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18047ccf4  nop
0x18047ccf5  lea     rdx, [rsp+198h+var_C0]
0x18047ccfd  lea     rcx, [rsp+198h+var_118]
0x18047cd05  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x18047cd0b  nop
0x18047cd0c  lea     rcx, [rsp+198h+var_C0]
0x18047cd14  jmp     loc_18047CF95
0x18047cd19  lea     rcx, [rsp+198h+var_F8]
0x18047cd21  call    cs:__imp_??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(void)
0x18047cd27  mov     rcx, [rax+8]
0x18047cd2b  movsxd  rcx, dword ptr [rcx+10h]
0x18047cd2f  add     rax, 8
0x18047cd33  add     rcx, rax
0x18047cd36  mov     rax, [rcx]
0x18047cd39  mov     edx, r13d
0x18047cd3c  mov     rax, [rax+18h]
0x18047cd40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18047cd45  mov     rcx, [rax]
0x18047cd48  call    cs:__imp_?GetFileNameWithoutExtension@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFileNameWithoutExtension(UnBCL::String const *)
0x18047cd4e  mov     rdx, rax
0x18047cd51  lea     rcx, [rsp+198h+var_138]
0x18047cd56  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18047cd5c  nop
0x18047cd5d  lea     rcx, [rsp+198h+var_138]
0x18047cd62  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18047cd68  test    rax, rax
0x18047cd6b  jnz     short loc_18047CD8C
0x18047cd6d  lea     rcx, [rsp+198h+var_138]
0x18047cd72  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18047cd78  nop
0x18047cd79  lea     rcx, [rsp+198h+var_118]
0x18047cd81  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18047cd87  jmp     loc_18047CC68
0x18047cd8c  lea     rcx, [rsp+198h+var_F8]
0x18047cd94  call    cs:__imp_??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(void)
0x18047cd9a  mov     rcx, [rax+8]
0x18047cd9e  movsxd  rcx, dword ptr [rcx+10h]
0x18047cda2  add     rax, 8
0x18047cda6  add     rcx, rax
0x18047cda9  mov     rax, [rcx]
0x18047cdac  mov     edx, r13d
0x18047cdaf  mov     rax, [rax+18h]
0x18047cdb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18047cdb8  mov     rcx, [rax]
0x18047cdbb  call    cs:__imp_?GetFileNameExtension@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFileNameExtension(UnBCL::String const *)
0x18047cdc1  mov     rdx, rax
0x18047cdc4  lea     rcx, [rsp+198h+var_E0]
0x18047cdcc  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18047cdd2  nop
0x18047cdd3  lea     rcx, [rsp+198h+var_E0]
0x18047cddb  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18047cde1  test    rax, rax
0x18047cde4  jnz     short loc_18047CDF9
0x18047cde6  lea     rcx, [rsp+198h+var_E0]
0x18047cdee  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18047cdf4  jmp     loc_18047CD6D
0x18047cdf9  mov     rcx, [rsp+198h+arg_20]
0x18047ce01  call    cs:__imp_?get_Length@String@UnBCL@@QEBAHXZ; UnBCL::String::get_Length(void)
0x18047ce07  test    eax, eax
0x18047ce09  jle     short loc_18047CE84
0x18047ce0b  lea     rcx, [rsp+198h+var_138]
0x18047ce10  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18047ce16  mov     rcx, rax
0x18047ce19  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18047ce1f  mov     rbx, rax
0x18047ce22  mov     rcx, [rsp+198h+arg_20]
0x18047ce2a  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18047ce30  mov     rdx, rbx
0x18047ce33  mov     rcx, rax
0x18047ce36  call    cs:__imp_?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z; UnBCL::String::Concat(ushort const *,ushort const *)
0x18047ce3c  mov     rdx, rax
0x18047ce3f  lea     rcx, [rsp+198h+var_B0]
0x18047ce47  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18047ce4d  nop
0x18047ce4e  lea     rdx, [rsp+198h+var_B0]
0x18047ce56  lea     rcx, [rsp+198h+var_138]
0x18047ce5b  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x18047ce61  nop
0x18047ce62  lea     rcx, [rsp+198h+var_B0]
0x18047ce6a  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18047ce70  lea     rcx, [rsp+198h+var_138]
0x18047ce75  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18047ce7b  test    rax, rax
0x18047ce7e  jz      loc_18047CDE6
0x18047ce84  mov     rcx, [rsp+198h+arg_28]
0x18047ce8c  call    cs:__imp_?get_Length@String@UnBCL@@QEBAHXZ; UnBCL::String::get_Length(void)
0x18047ce92  test    eax, eax
0x18047ce94  jle     short loc_18047CF0F
0x18047ce96  mov     rcx, [rsp+198h+arg_28]
0x18047ce9e  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18047cea4  mov     rbx, rax
0x18047cea7  lea     rcx, [rsp+198h+var_138]
0x18047ceac  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18047ceb2  mov     rcx, rax
0x18047ceb5  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18047cebb  mov     rdx, rbx
0x18047cebe  mov     rcx, rax
0x18047cec1  call    cs:__imp_?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z; UnBCL::String::Concat(ushort const *,ushort const *)
0x18047cec7  mov     rdx, rax
0x18047ceca  lea     rcx, [rsp+198h+var_A0]
0x18047ced2  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18047ced8  nop
0x18047ced9  lea     rdx, [rsp+198h+var_A0]
0x18047cee1  lea     rcx, [rsp+198h+var_138]
0x18047cee6  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x18047ceec  nop
0x18047ceed  lea     rcx, [rsp+198h+var_A0]
0x18047cef5  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18047cefb  lea     rcx, [rsp+198h+var_138]
0x18047cf00  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18047cf06  test    rax, rax
0x18047cf09  jz      loc_18047CDE6
0x18047cf0f  lea     rcx, [rsp+198h+var_E0]
0x18047cf17  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18047cf1d  mov     rcx, rax
0x18047cf20  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18047cf26  mov     rbx, rax
0x18047cf29  lea     rcx, [rsp+198h+var_138]
0x18047cf2e  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18047cf34  mov     rcx, rax
0x18047cf37  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18047cf3d  mov     rdx, rbx
0x18047cf40  mov     rcx, rax
0x18047cf43  call    cs:__imp_?Concat@String@UnBCL@@SAPEAV12@PEBG0@Z; UnBCL::String::Concat(ushort const *,ushort const *)
0x18047cf49  mov     rdx, rax
0x18047cf4c  lea     rcx, [rsp+198h+var_90]
0x18047cf54  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18047cf5a  nop
0x18047cf5b  lea     rdx, [rsp+198h+var_90]
0x18047cf63  lea     rcx, [rsp+198h+var_118]
0x18047cf6b  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x18047cf71  nop
0x18047cf72  lea     rcx, [rsp+198h+var_90]
0x18047cf7a  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18047cf80  nop
0x18047cf81  lea     rcx, [rsp+198h+var_E0]
  ... truncated ...
```
