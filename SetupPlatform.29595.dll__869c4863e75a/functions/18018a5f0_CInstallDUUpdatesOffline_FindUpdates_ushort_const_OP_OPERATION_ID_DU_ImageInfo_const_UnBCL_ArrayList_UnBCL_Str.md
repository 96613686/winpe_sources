# CInstallDUUpdatesOffline::FindUpdates(ushort const *,OP_OPERATION_ID,DU::ImageInfo const *,UnBCL::ArrayList<UnBCL::String *> *,UnBCL::ArrayList<UnBCL::String *> *)

- ea: `0x18018a5f0`
- end: `0x18018b326`
- name: `?FindUpdates@CInstallDUUpdatesOffline@@SAJPEBGW4OP_OPERATION_ID@@PEBUImageInfo@DU@@PEAV?$ArrayList@PEAVString@UnBCL@@@UnBCL@@3@Z`
- size: `3382`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180183760`
- `0x18018f630`

## callees

- `0x180044810`
- `0x180057dec`
- `0x18018a5f0`
- `0x180196ef4`
- `0x18036e758`
- `0x18040c348`
- `0x180509010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18018aa00`
- `msvcrt!_wtoi` at `0x18018aa00`
- `KERNEL32!GetProcessHeap` at `0x18018a7e4`
- `KERNEL32!GetProcessHeap` at `0x18018a7e4`
- `KERNEL32!HeapFree` at `0x18018a7f2`
- `KERNEL32!HeapFree` at `0x18018a7f2`
- `KERNEL32!GetLastError` at `0x18018a63a`
- `KERNEL32!GetLastError` at `0x18018a74e`
- `KERNEL32!GetLastError` at `0x18018aa63`
- `KERNEL32!GetLastError` at `0x18018ab5b`
- `KERNEL32!GetLastError` at `0x18018af0f`
- `KERNEL32!GetLastError` at `0x18018af8e`
- `KERNEL32!GetLastError` at `0x18018b073`
- `KERNEL32!GetLastError` at `0x18018a63a`
- `KERNEL32!GetLastError` at `0x18018a74e`
- `KERNEL32!GetLastError` at `0x18018aa63`
- `KERNEL32!GetLastError` at `0x18018ab5b`
- `KERNEL32!GetLastError` at `0x18018af0f`
- `KERNEL32!GetLastError` at `0x18018af8e`
- `KERNEL32!GetLastError` at `0x18018b073`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x18018a909`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x18018a935`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x18018ab33`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x18018abdb`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x18018ac25`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x18018a909`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x18018a935`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x18018ab33`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x18018abdb`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x18018ac25`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018acf3`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b068`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b1a0`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b2fe`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018acf3`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b068`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b1a0`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b2fe`
- `unbcl!?GetFiles@Directory@UnBCL@@SAPEAV?$Array@PEAVString@UnBCL@@@2@PEBVString@2@0H@Z` at `0x18018ab11`
- `unbcl!?GetFiles@Directory@UnBCL@@SAPEAV?$Array@PEAVString@UnBCL@@@2@PEBVString@2@0H@Z` at `0x18018ab11`
- `unbcl!??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z` at `0x18018a7dd`
- `unbcl!??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z` at `0x18018ab1e`
- `unbcl!??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z` at `0x18018a7dd`
- `unbcl!??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z` at `0x18018ab1e`
- `unbcl!?Substring@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x18018a9b5`
- `unbcl!?Substring@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x18018a9b5`
- `unbcl!?LastIndexOf@String@UnBCL@@QEBAHG@Z` at `0x18018a99b`
- `unbcl!?LastIndexOf@String@UnBCL@@QEBAHG@Z` at `0x18018a99b`
- `unbcl!?Remove@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x18018a9d6`
- `unbcl!?Remove@String@UnBCL@@QEBAPEAV12@HH@Z` at `0x18018a9d6`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18018a8d9`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18018a8d9`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x18018a96c`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x18018a987`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x18018a96c`
- `unbcl!?StartsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x18018a987`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18018a6e3`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18018aa2f`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18018ac5c`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18018a6e3`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18018aa2f`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18018ac5c`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18018a840`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18018a896`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18018ac08`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18018ac7d`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18018ae9c`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18018b1b2`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18018b215`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18018b233`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18018b296`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18018a840`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18018a896`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18018ac08`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18018ac7d`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18018ae9c`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18018b1b2`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18018b215`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18018b233`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x18018b296`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18018a820`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18018a876`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18018ad63`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18018a820`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18018a876`
- `unbcl!??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18018ad63`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x18018a835`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x18018a88b`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x18018a835`
- `unbcl!??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z` at `0x18018a88b`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b052`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b05d`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b18a`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b195`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b2e8`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b2f3`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b052`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b05d`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b18a`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b195`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b2e8`
- `unbcl!??1?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b2f3`
- `unbcl!?FromMultiSz@MultiSz@UnBCL@@SAPEAV?$Array@PEAVString@UnBCL@@@2@PEBG@Z` at `0x18018a7d0`
- `unbcl!?FromMultiSz@MultiSz@UnBCL@@SAPEAV?$Array@PEAVString@UnBCL@@@2@PEBG@Z` at `0x18018a7d0`
- `unbcl!?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x18018b1e8`
- `unbcl!?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x18018b269`
- `unbcl!?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x18018b1e8`
- `unbcl!?get_P@?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@2@XZ` at `0x18018b269`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18018aa0e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18018ab02`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18018ac50`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18018adfc`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18018aa0e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18018ab02`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18018ac50`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18018adfc`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18018a6fb`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18018a706`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18018aa47`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18018ab29`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18018a6fb`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18018a706`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18018aa47`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18018ab29`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18018a6c6`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18018a6d6`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18018aa22`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18018aaf5`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18018acc6`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18018a6c6`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18018a6d6`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18018aa22`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18018aaf5`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18018acc6`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18018a801`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18018a85e`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18018ac9b`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18018ad4b`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18018a801`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18018a85e`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18018ac9b`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18018ad4b`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18018a710`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18018a9ee`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18018aa78`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18018ab70`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18018acb1`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18018addd`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18018b088`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18018a710`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18018a9ee`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18018aa78`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18018ab70`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18018acb1`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18018addd`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18018b088`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18018a719`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18018a9f7`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18018aa81`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18018ab79`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18018acba`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18018ade6`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18018af24`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18018b091`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18018a719`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18018a9f7`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18018aa81`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18018ab79`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18018acba`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18018ade6`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18018af24`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18018b091`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018ae6f`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018ae7a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018ae85`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018affe`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b009`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b014`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b01f`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b13a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b145`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b150`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b15b`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b2b5`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b30b`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018ae6f`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018ae7a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018ae85`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018affe`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b009`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b014`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b01f`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b13a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b145`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b150`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b15b`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b2b5`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18018b30b`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18018a6f0`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18018a8e6`

## string_xrefs

- `0x18018a685`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x18018a796`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x18018a8f4`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x18018b0d1`: `base\ntsetup\setupplatform\lib\src\dynamicupdate.cpp`
- `0x18018a75f`: `No updates to install; leaving.`
- `0x18018a679`: `CInstallDUUpdatesOffline::FindUpdates`
- `0x18018a78a`: `CInstallDUUpdatesOffline::FindUpdates`
- `0x18018a8fb`: `CInstallDUUpdatesOffline::FindUpdates`
- `0x18018b0c5`: `CInstallDUUpdatesOffline::FindUpdates`
- `0x18018a64e`: `CInstallDUUpdatesOffline::FindUpdates: Unexpected operation ID %d`
- `0x18018afa7`: `CInstallDUUpdatesOffline::FindUpdates: Failed to create devices database; hr = 0x%08X`
- `0x18018b0a1`: `CInstallDUUpdatesOffline::FindUpdates: Failed to get installable drivers from package %s; hr = 0x%08X`
- `0x18018ab82`: `Component update %s has cab file(s); will install each one`
- `0x18018aa8f`: `CInstallDUUpdatesOffline::FindUpdates: Unexpected update type %d for path %s.`
- `0x18018af2d`: `CInstallDUUpdatesOffline::FindUpdates: Malformed line found in updates section: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall CInstallDUUpdatesOffline::FindUpdates(
        const unsigned __int16 *a1,
        unsigned int a2,
        int *a3,
        __int64 a4,
        __int64 a5)
{
  const WCHAR *SectionName; // rdi
  DWORD v9; // edi
  __int64 v10; // rbx
  struct tagLOG_PARTIAL_MSG *v11; // rax
  const struct UnBCL::String *v13; // rbx
  const struct UnBCL::String *v14; // rax
  struct UnBCL::String *v15; // rax
  UnBCL::String *v16; // rax
  const WCHAR *CString; // rax
  unsigned int v18; // r12d
  __int64 Str; // rax
  void *v20; // rbx
  DWORD v21; // edi
  __int64 v22; // rbx
  struct tagLOG_PARTIAL_MSG *v23; // rax
  unsigned int v24; // edi
  __int64 v25; // rax
  HANDLE ProcessHeap; // rax
  UnBCL::String *v27; // rax
  UnBCL::String *v28; // rbx
  __int64 v29; // rax
  UnBCL::String *v30; // rax
  UnBCL::String *v31; // rbx
  __int64 v32; // rax
  struct UnBCL::String *v33; // rax
  int i; // ebx
  __int64 v35; // rax
  int (__fastcall ***v36)(_QWORD); // rcx
  __int64 v37; // rax
  __int64 v38; // rcx
  UnBCL::String *v39; // rbx
  int IndexOf; // eax
  struct UnBCL::String *v41; // rax
  struct UnBCL::String *v42; // rax
  UnBCL::String *v43; // rax
  const wchar_t *v44; // rax
  const struct UnBCL::String *P; // rbx
  const struct UnBCL::String *v46; // rax
  struct UnBCL::String *v47; // rax
  DWORD v48; // edi
  __int64 v49; // rbx
  UnBCL::String *v50; // rax
  const char *v51; // rax
  struct tagLOG_PARTIAL_MSG *v52; // rax
  __int64 v53; // rbx
  __int64 v54; // rax
  __int64 Files; // rax
  __int64 v56; // rax
  int (__fastcall ***v57)(_QWORD); // rcx
  DWORD v58; // edi
  __int64 v59; // rbx
  UnBCL::String *v60; // rax
  const char *v61; // rax
  struct tagLOG_PARTIAL_MSG *v62; // rax
  int j; // r14d
  __int64 v64; // rax
  int (__fastcall ***v65)(_QWORD); // rcx
  __int64 v66; // rax
  __int64 v67; // rsi
  void (__fastcall *v68)(__int64, struct UnBCL::String *); // rdi
  __int64 v69; // rax
  __int64 v70; // rcx
  const struct UnBCL::String *v71; // rbx
  const struct UnBCL::String *v72; // rax
  struct UnBCL::String *v73; // rax
  __int64 v74; // rax
  __int64 v75; // rsi
  void (__fastcall *v76)(__int64, UnBCL::String *); // r14
  UnBCL::String *v77; // rbx
  UnBCL::String *v78; // rax
  const unsigned __int16 *v79; // rax
  struct IDeviceIdDatabase **v80; // rax
  int v81; // edx
  const struct _GUID *v82; // rcx
  _QWORD *v83; // rax
  _QWORD *v84; // rbx
  __int64 v85; // rax
  __int64 v86; // r15
  __int64 (__fastcall *v87)(__int64, __int64, _QWORD, const unsigned __int16 *, __int64); // r14
  __int64 v88; // rsi
  UnBCL::String *v89; // rax
  const unsigned __int16 *v90; // rbx
  unsigned int v91; // edi
  __int64 v92; // rax
  int v93; // eax
  void (__fastcall ***v94)(_QWORD, __int64); // rcx
  __int64 v95; // rbx
  void (__fastcall *v96)(__int64, __int64); // rsi
  __int64 v97; // rax
  __int64 v98; // rdx
  __int64 v99; // rax
  DWORD LastError; // edi
  __int64 v101; // rbx
  const char *v102; // rax
  struct tagLOG_PARTIAL_MSG *v103; // rax
  DWORD v104; // edi
  __int64 v105; // rbx
  struct tagLOG_PARTIAL_MSG *v106; // rax
  DWORD v107; // edi
  __int64 v108; // rbx
  UnBCL::String *v109; // rax
  const char *v110; // rax
  struct tagLOG_PARTIAL_MSG *v111; // rax
  void (__fastcall ***v112)(_QWORD, __int64); // rcx
  __int64 v113; // rax
  int (__fastcall ***v114)(_QWORD); // rcx
  void (__fastcall *v115)(__int64, __int64); // rbx
  __int64 v116; // rax
  __int64 v117; // rdx
  __int64 v118; // rax
  __int64 v119; // rax
  int (__fastcall ***v120)(_QWORD); // rcx
  void (__fastcall *v121)(__int64, __int64); // rsi
  __int64 v122; // rax
  __int64 v123; // rdx
  __int64 v124; // rax
  unsigned int v125; // [rsp+68h] [rbp-A0h]
  __int64 v126; // [rsp+70h] [rbp-98h] BYREF
  void **v127; // [rsp+78h] [rbp-90h] BYREF
  _QWORD *v128; // [rsp+80h] [rbp-88h]
  void **v129; // [rsp+88h] [rbp-80h] BYREF
  __int64 v130; // [rsp+90h] [rbp-78h]
  int v131; // [rsp+98h] [rbp-70h]
  _BYTE v132[16]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v133[16]; // [rsp+B0h] [rbp-58h] BYREF
  _BYTE v134[16]; // [rsp+C0h] [rbp-48h] BYREF
  UnBCL::String *v135; // [rsp+D0h] [rbp-38h]
  _BYTE v136[16]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v137[16]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v138[24]; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v139[16]; // [rsp+110h] [rbp+8h] BYREF
  _BYTE v140[24]; // [rsp+120h] [rbp+18h] BYREF
  _BYTE v141[16]; // [rsp+138h] [rbp+30h] BYREF
  __int64 v142; // [rsp+148h] [rbp+40h]
  UnBCL::String *v143; // [rsp+150h] [rbp+48h]
  void *v144; // [rsp+158h] [rbp+50h]
  _BYTE v145[24]; // [rsp+160h] [rbp+58h] BYREF
  _BYTE v146[80]; // [rsp+178h] [rbp+70h] BYREF

  v142 = -2;
  SectionName = (const WCHAR *)pGetSectionName(a2);
  if ( SectionName )
  {
    v13 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v138, L"SetupPlatform.ini");
    v14 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v140, a1);
    v15 = UnBCL::Path::Combine(v14, v13);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v141, v15);
    UnBCL::String::~String((UnBCL::String *)v140);
    UnBCL::String::~String((UnBCL::String *)v138);
    v16 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v141);
    CString = UnBCL::String::get_CString(v16);
    v18 = 1;
    Str = IniGetStr(CString, SectionName, 0, 1, 1, 0);
    v20 = (void *)Str;
    if ( Str )
    {
      v24 = 0;
      v125 = 0;
      v25 = UnBCL::MultiSz::FromMultiSz(Str);
      UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::SmartPtr<UnBCL::Array<UnBCL::String *>>(v137, v25);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v20);
      v27 = (UnBCL::String *)UnBCL::Object::operator new(0xB0u);
      v28 = v27;
      v135 = v27;
      if ( v27 )
      {
        UnBCL::ArrayList<UnBCL::String *>::ArrayList<UnBCL::String *>(v27, 1);
        *((_QWORD *)v28 + 6) = UnBCL::ArrayList<UnBCL::String *>::`local vftable'{for `UnBCL::Object'};
      }
      else
      {
        v28 = 0;
      }
      UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v133, v28);
      v29 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v133);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v29 + 40LL))(v29, 1);
      v30 = (UnBCL::String *)UnBCL::Object::operator new(0xB0u);
      v31 = v30;
      v135 = v30;
      if ( v30 )
      {
        UnBCL::ArrayList<UnBCL::String *>::ArrayList<UnBCL::String *>(v30, 1);
        *((_QWORD *)v31 + 6) = UnBCL::ArrayList<UnBCL::String *>::`local vftable'{for `UnBCL::Object'};
      }
      else
      {
        v31 = 0;
      }
      UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v134, v31);
      v32 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v134);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v32 + 40LL))(v32, 1);
      v130 = 0;
      v129 = &RAII::CAutoRelease<IDeviceIdDatabase *>::`vftable';
      v33 = UnBCL::String::Format(
              L"%d.%d.%d",
              **((unsigned int **)a3 + 4),
              *(unsigned int *)(*((_QWORD *)a3 + 4) + 4LL),
              *(unsigned int *)(*((_QWORD *)a3 + 4) + 8LL));
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v139, v33);
      for ( i = 0; ; i = v131 + 1 )
      {
        v131 = i;
        v35 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v137);
        v36 = (int (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v35 + 8) + 12LL) + v35 + 8);
        if ( i >= (**v36)(v36) )
          break;
        v37 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v137);
        v38 = *(int *)(*(_QWORD *)(v37 + 8) + 16LL) + v37 + 8;
        v39 = *(UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v38 + 24LL))(
                                   v38,
                                   (unsigned int)i);
        v135 = v39;
        if ( !UnBCL::String::StartsWith(v39, L"ImageInfo", 1) && !UnBCL::String::StartsWith(v39, L"SpaceNeeded", 1) )
        {
          IndexOf = UnBCL::String::LastIndexOf(v39, 0x3Du);
          LODWORD(v126) = IndexOf;
          if ( IndexOf <= 0 )
          {
            LastError = GetLastError();
            v101 = CurrentIP();
            v102 = (const char *)UnBCL::String::get_CString(v135);
            v103 = ConstructPartialMsgW(
                     0x3000000u,
                     "CInstallDUUpdatesOffline::FindUpdates: Malformed line found in updates section: %s",
                     v102);
            WdsSetupLogMessageW(
              v103,
              819200,
              L"D",
              0,
              4642,
              L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
              L"CInstallDUUpdatesOffline::FindUpdates",
              v101,
              LastError,
              0,
              0);
            v24 = v125;
          }
          else
          {
            v41 = UnBCL::String::Substring(v39, 0, IndexOf);
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v136, v41);
            v42 = UnBCL::String::Remove(v39, 0, (int)v126 + 1);
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v138, v42);
            v43 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v138);
            v44 = UnBCL::String::get_CString(v43);
            LODWORD(v126) = _wtoi(v44);
            P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v136);
            v46 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v145, a1);
            v47 = UnBCL::Path::Combine(v46, P);
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v132, v47);
            UnBCL::String::~String((UnBCL::String *)v145);
            if ( (_DWORD)v126 == 2 )
            {
              v126 = 0;
              if ( ((unsigned __int8 (__fastcall *)(void ***, __int64 *))v129[7])(&v129, &v126) )
              {
                v80 = (struct IDeviceIdDatabase **)((__int64 (__fastcall *)(void ***))v129[1])(&v129);
                LODWORD(v126) = SPCreateDeviceIdDatabase(v82, v81, v80);
                if ( (int)v126 < 0 )
                {
                  v104 = GetLastError();
                  v105 = CurrentIP();
                  v18 = v126;
                  v106 = ConstructPartialMsgW(
                           0x2000000u,
                           "CInstallDUUpdatesOffline::FindUpdates: Failed to create devices database; hr = 0x%08X",
                           v126);
                  WdsSetupLogMessageW(
                    v106,
                    819200,
                    L"D",
                    0,
                    4605,
                    L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
                    L"CInstallDUUpdatesOffline::FindUpdates",
                    v105,
                    v104,
                    0,
                    0);
                  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v132);
                  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v138);
                  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v136);
                  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v139);
                  v129 = &RAII::CAutoRelease<IDeviceIdDatabase *>::`vftable';
                  if ( v130 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v130 + 16LL))(v130);
                    v130 = 0;
                  }
                  UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v134);
                  UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v133);
                  UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::~SmartPtr<UnBCL::Array<UnBCL::String *>>(v137);
                  goto LABEL_67;
                }
              }
              v83 = UnBCL::Object::operator new(0xB0u);
              v84 = v83;
              v144 = v83;
              if ( v83 )
              {
                UnBCL::ArrayList<UnBCL::String *>::ArrayList<UnBCL::String *>(v83, 1);
                v84[6] = UnBCL::ArrayList<UnBCL::String *>::`local vftable'{for `UnBCL::Object'};
              }
              else
              {
                v84 = 0;
              }
              v128 = v84;
              v127 = &RAII::CAutoDelete<UnBCL::ArrayList<UnBCL::String *> *>::`vftable';
              v85 = RAII::CAutoCleanupBase<void *>::operator->(&v127);
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v85 + 40LL))(v85, 1);
              v86 = ((__int64 (__fastcall *)(void ***))v129[3])(&v129);
              v87 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, const unsigned __int16 *, __int64))(*(_QWORD *)v86 + 8LL);
              v88 = ((__int64 (__fastcall *)(void ***))v127[1])(&v127);
              v89 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v139);
              v90 = UnBCL::String::get_CString(v89);
              v91 = *a3;
              v92 = UnBCL::SmartPtr<UnBCL::String>::get_P(v132);
              v93 = v87(v86, v92, v91, v90, v88);
              v24 = v93;
              v125 = v93;
              if ( v93 == -2147023728 )
              {
                v24 = 0;
                v125 = 0;
              }
              else
              {
                if ( v93 < 0 )
                {
                  v107 = GetLastError();
                  v108 = CurrentIP();
                  v109 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v132);
                  v110 = (const char *)UnBCL::String::get_CString(v109);
                  v111 = ConstructPartialMsgW(
                           0x2000000u,
                           "CInstallDUUpdatesOffline::FindUpdates: Failed to get installable drivers from package %s; hr = 0x%08X",
                           v110,
                           v125);
                  WdsSetupLogMessageW(
                    v111,
                    819200,
                    L"D",
                    0,
                    4626,
                    L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
                    L"CInstallDUUpdatesOffline::FindUpdates",
                    v108,
                    v107,
                    0,
                    0);
                  v127 = &RAII::CAutoDelete<UnBCL::ArrayList<UnBCL::String *> *>::`vftable';
                  if ( v128 )
                  {
                    v112 = (void (__fastcall ***)(_QWORD, __int64))((char *)v128 + *(int *)(v128[1] + 4LL) + 8);
                    (**v112)(v112, 1);
                    v128 = 0;
                  }
                  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v132);
                  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v138);
                  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v136);
                  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v139);
                  v129 = &RAII::CAutoRelease<IDeviceIdDatabase *>::`vftable';
                  if ( v130 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v130 + 16LL))(v130);
                    v130 = 0;
                  }
                  UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v134);
                  UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v133);
                  UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::~SmartPtr<UnBCL::Array<UnBCL::String *>>(v137);
                  v18 = v125;
                  goto LABEL_67;
                }
                v95 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v134);
                v96 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v95 + 80LL);
                v97 = ((__int64 (__fastcall *)(void ***))v127[4])(&v127);
                if ( v97 )
                  v98 = v97 + *(int *)(*(_QWORD *)(v97 + 8) + 12LL) + 8LL;
                else
                  v98 = 0;
                v96(v95, v98);
                v99 = ((__int64 (__fastcall *)(void ***))v127[3])(&v127);
                (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v99 + 40LL))(v99, 0);
              }
              v127 = &RAII::CAutoDelete<UnBCL::ArrayList<UnBCL::String *> *>::`vftable';
              if ( v128 )
              {
                v94 = (void (__fastcall ***)(_QWORD, __int64))((char *)v128 + *(int *)(v128[1] + 4LL) + 8);
                (**v94)(v94, 1);
                v128 = 0;
              }
            }
            else if ( (_DWORD)v126 == 4 )
            {
              v53 = UnBCL::String::String((UnBCL::String *)v146, L"*.cab");
              v54 = UnBCL::SmartPtr<UnBCL::String>::get_P(v132);
              Files = UnBCL::Directory::GetFiles(v54, v53, 0);
              UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::SmartPtr<UnBCL::Array<UnBCL::String *>>(v140, Files);
              UnBCL::String::~String((UnBCL::String *)v146);
              v56 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v140);
              v57 = (int (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v56 + 8) + 12LL) + v56 + 8);
              if ( (**v57)(v57) <= 0 )
              {
                v74 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v133);
                v75 = v74 + *(int *)(*(_QWORD *)(v74 + 8) + 16LL);
                v76 = *(void (__fastcall **)(__int64, UnBCL::String *))(*(_QWORD *)(v75 + 8) + 40LL);
                v77 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
                v143 = v77;
                if ( v77 )
                {
                  v78 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v132);
                  v79 = UnBCL::String::get_CString(v78);
                  UnBCL::String::String(v77, v79);
                  *(_QWORD *)v77 = &UnBCL::String::`local vftable';
                }
                else
                {
                  v77 = 0;
                }
                v76(v75 + 8, v77);
              }
              else
              {
                v58 = GetLastError();
                v59 = CurrentIP();
                v60 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v136);
                v61 = (const char *)UnBCL::String::get_CString(v60);
                v62 = ConstructPartialMsgW(
                        0x4000000u,
                        "Component update %s has cab file(s); will install each one",
                        v61);
                WdsSetupLogMessageW(
                  v62,
                  819200,
                  L"D",
                  0,
                  4584,
                  L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
                  L"CInstallDUUpdatesOffline::FindUpdates",
                  v59,
                  v58,
                  0,
                  0);
                for ( j = 0; ; ++j )
                {
                  v64 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v140);
                  v65 = (int (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v64 + 8) + 12LL) + v64 + 8);
                  if ( j >= (**v65)(v65) )
                    break;
                  v66 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v133);
                  v67 = v66 + *(int *)(*(_QWORD *)(v66 + 8) + 16LL);
                  v68 = *(void (__fastcall **)(__int64, struct UnBCL::String *))(*(_QWORD *)(v67 + 8) + 40LL);
                  v69 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v140);
                  v70 = *(int *)(*(_QWORD *)(v69 + 8) + 16LL) + v69 + 8;
                  v71 = *(const struct UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v70 + 24LL))(
                                                          v70,
                                                          (unsigned int)j);
                  v72 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v132);
                  v73 = UnBCL::Path::Combine(v72, v71);
                  v68(v67 + 8, v73);
                }
                v24 = v125;
              }
              UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::~SmartPtr<UnBCL::Array<UnBCL::String *>>(v140);
            }
            else
            {
              v48 = GetLastError();
              v49 = CurrentIP();
              v50 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v132);
              v51 = (const char *)UnBCL::String::get_CString(v50);
              v52 = ConstructPartialMsgW(
                      0x2000000u,
                      "CInstallDUUpdatesOffline::FindUpdates: Unexpected update type %d for path %s.",
                      v126,
                      v51);
              WdsSetupLogMessageW(
                v52,
                819200,
                L"D",
                0,
                4637,
                L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
                L"CInstallDUUpdatesOffline::FindUpdates",
                v49,
                v48,
                0,
                0);
              v24 = v125;
            }
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v132);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v138);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v136);
          }
        }
      }
      v113 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v133);
      v114 = (int (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v113 + 8) + 12LL) + v113 + 8);
      if ( (**v114)(v114) > 0 )
      {
        v115 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a4 + 80LL);
        v116 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::get_P(v133);
        if ( v116 )
          v117 = v116 + *(int *)(*(_QWORD *)(v116 + 8) + 12LL) + 8LL;
        else
          v117 = 0;
        v115(a4, v117);
        v118 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v133);
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v118 + 40LL))(v118, 0);
      }
      v119 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v134);
      v120 = (int (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v119 + 8) + 12LL) + v119 + 8);
      if ( (**v120)(v120) > 0 )
      {
        v121 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a5 + 80LL);
        v122 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::get_P(v134);
        if ( v122 )
          v123 = v122 + *(int *)(*(_QWORD *)(v122 + 8) + 12LL) + 8LL;
        else
          v123 = 0;
        v121(a5, v123);
        v124 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(v134);
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v124 + 40LL))(v124, 0);
      }
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v139);
      v129 = &RAII::CAutoRelease<IDeviceIdDatabase *>::`vftable';
      if ( v130 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v130 + 16LL))(v130);
        v130 = 0;
      }
      UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v134);
      UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(v133);
      UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::~SmartPtr<UnBCL::Array<UnBCL::String *>>(v137);
      v18 = v24;
    }
    else
    {
      v21 = GetLastError();
      v22 = CurrentIP();
      v23 = ConstructPartialMsgW(0x4000000u, "No updates to install; leaving.");
      WdsSetupLogMessageW(
        v23,
        819200,
        L"D",
        0,
        4538,
        L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
        L"CInstallDUUpdatesOffline::FindUpdates",
        v22,
        v21,
        0,
        0);
    }
LABEL_67:
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v141);
    return v18;
  }
  else
  {
    v9 = GetLastError();
    v10 = CurrentIP();
    v11 = ConstructPartialMsgW(0x3000000u, "CInstallDUUpdatesOffline::FindUpdates: Unexpected operation ID %d", a2);
    WdsSetupLogMessageW(
      v11,
      819200,
      L"D",
      0,
      4529,
      L"base\\ntsetup\\setupplatform\\lib\\src\\dynamicupdate.cpp",
      L"CInstallDUUpdatesOffline::FindUpdates",
      v10,
      v9,
      0,
      0);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x18018a5f0  mov     rax, rsp
0x18018a5f3  mov     [rax+20h], r9
0x18018a5f7  mov     [rax+18h], r8
0x18018a5fb  mov     [rax+8], rcx
0x18018a5ff  push    rbp
0x18018a600  push    rbx
0x18018a601  push    rsi
0x18018a602  push    rdi
0x18018a603  push    r12
0x18018a605  push    r14
0x18018a607  push    r15
0x18018a609  lea     rbp, [rax-0C8h]
0x18018a610  sub     rsp, 190h
0x18018a617  mov     [rbp+0C0h+var_80], 0FFFFFFFFFFFFFFFEh
0x18018a61f  mov     r15, r8
0x18018a622  mov     esi, edx
0x18018a624  mov     r14, rcx
0x18018a627  mov     ecx, edx
0x18018a629  call    ?pGetSectionName@@YAPEBGW4OP_OPERATION_ID@@@Z; pGetSectionName(OP_OPERATION_ID)
0x18018a62e  mov     rdi, rax
0x18018a631  test    rax, rax
0x18018a634  jnz     loc_18018A6BB
0x18018a63a  call    cs:__imp_GetLastError
0x18018a640  mov     edi, eax
0x18018a642  call    cs:__imp_CurrentIP
0x18018a648  mov     rbx, rax
0x18018a64b  mov     r8d, esi
0x18018a64e  lea     rdx, aCinstallduupda_14; "CInstallDUUpdatesOffline::FindUpdates: "...
0x18018a655  mov     ecx, 3000000h; unsigned int
0x18018a65a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18018a65f  mov     dword ptr [rsp+50h], 0
0x18018a667  mov     qword ptr [rsp+1C0h+var_178], 0
0x18018a670  mov     dword ptr [rsp+1C0h+var_180], edi
0x18018a674  mov     qword ptr [rsp+1C0h+var_188], rbx
0x18018a679  lea     rcx, aCinstallduupda_6; "CInstallDUUpdatesOffline::FindUpdates"
0x18018a680  mov     [rsp+1C0h+var_190], rcx
0x18018a685  lea     rcx, aBaseNtsetupSet_38; "base\\ntsetup\\setupplatform\\lib\\src"...
0x18018a68c  mov     qword ptr [rsp+1C0h+var_198], rcx
0x18018a691  mov     [rsp+1C0h+var_1A0], 11B1h
0x18018a699  xor     r9d, r9d
0x18018a69c  lea     r8, aD_0; "D"
0x18018a6a3  mov     edx, 0C8000h
0x18018a6a8  mov     rcx, rax
0x18018a6ab  call    cs:__imp_WdsSetupLogMessageW
0x18018a6b1  mov     eax, 8000FFFFh
0x18018a6b6  jmp     loc_18018B314
0x18018a6bb  lea     rdx, aSetupplatformI; "SetupPlatform.ini"
0x18018a6c2  lea     rcx, [rbp+0C0h+var_D0]
0x18018a6c6  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18018a6cc  mov     rbx, rax
0x18018a6cf  mov     rdx, r14
0x18018a6d2  lea     rcx, [rbp+0C0h+var_A8]
0x18018a6d6  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18018a6dc  nop
0x18018a6dd  mov     rdx, rbx
0x18018a6e0  mov     rcx, rax
0x18018a6e3  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x18018a6e9  mov     rdx, rax
0x18018a6ec  lea     rcx, [rbp+0C0h+var_90]
0x18018a6f0  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18018a6f6  nop
0x18018a6f7  lea     rcx, [rbp+0C0h+var_A8]
0x18018a6fb  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18018a701  nop
0x18018a702  lea     rcx, [rbp+0C0h+var_D0]
0x18018a706  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18018a70c  lea     rcx, [rbp+0C0h+var_90]
0x18018a710  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18018a716  mov     rcx, rax
0x18018a719  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18018a71f  mov     [rsp+1C0h+var_190], 0; __int64
0x18018a728  mov     r12d, 1
0x18018a72e  mov     [rsp+1C0h+var_198], r12d; int
0x18018a733  mov     [rsp+1C0h+var_1A0], r12d; int
0x18018a738  xor     r8d, r8d; lpKeyName
0x18018a73b  mov     rdx, rdi; lpAppName
0x18018a73e  mov     rcx, rax; lpFileName
0x18018a741  call    IniGetStr
0x18018a746  mov     rbx, rax
0x18018a749  test    rax, rax
0x18018a74c  jnz     short loc_18018A7C7
0x18018a74e  call    cs:__imp_GetLastError
0x18018a754  mov     edi, eax
0x18018a756  call    cs:__imp_CurrentIP
0x18018a75c  mov     rbx, rax
0x18018a75f  lea     rdx, aNoUpdatesToIns; "No updates to install; leaving."
0x18018a766  mov     ecx, 4000000h; unsigned int
0x18018a76b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18018a770  mov     dword ptr [rsp+50h], 0
0x18018a778  mov     qword ptr [rsp+1C0h+var_178], 0
0x18018a781  mov     dword ptr [rsp+1C0h+var_180], edi
0x18018a785  mov     qword ptr [rsp+1C0h+var_188], rbx
0x18018a78a  lea     rcx, aCinstallduupda_6; "CInstallDUUpdatesOffline::FindUpdates"
0x18018a791  mov     [rsp+1C0h+var_190], rcx
0x18018a796  lea     rcx, aBaseNtsetupSet_38; "base\\ntsetup\\setupplatform\\lib\\src"...
0x18018a79d  mov     qword ptr [rsp+1C0h+var_198], rcx
0x18018a7a2  mov     [rsp+1C0h+var_1A0], 11BAh
0x18018a7aa  xor     r9d, r9d
0x18018a7ad  lea     r8, aD_0; "D"
0x18018a7b4  mov     edx, 0C8000h
0x18018a7b9  mov     rcx, rax
0x18018a7bc  call    cs:__imp_WdsSetupLogMessageW
0x18018a7c2  jmp     loc_18018B307
0x18018a7c7  xor     edi, edi
0x18018a7c9  mov     dword ptr [rsp+1C0h+var_160], edi
0x18018a7cd  mov     rcx, rbx
0x18018a7d0  call    cs:__imp_?FromMultiSz@MultiSz@UnBCL@@SAPEAV?$Array@PEAVString@UnBCL@@@2@PEBG@Z; UnBCL::MultiSz::FromMultiSz(ushort const *)
0x18018a7d6  mov     rdx, rax
0x18018a7d9  lea     rcx, [rbp+0C0h+var_E0]
0x18018a7dd  call    cs:__imp_??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::SmartPtr<UnBCL::Array<UnBCL::String *>>(UnBCL::Array<UnBCL::String *> *)
0x18018a7e3  nop
0x18018a7e4  call    cs:__imp_GetProcessHeap
0x18018a7ea  mov     rcx, rax; hHeap
0x18018a7ed  mov     r8, rbx; lpMem
0x18018a7f0  xor     edx, edx; dwFlags
0x18018a7f2  call    cs:__imp_HeapFree
0x18018a7f8  mov     r14d, 0B0h
0x18018a7fe  mov     ecx, r14d
0x18018a801  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18018a807  mov     rbx, rax
0x18018a80a  mov     [rbp+0C0h+var_F8], rax
0x18018a80e  lea     rsi, ??_S?$ArrayList@PEAVString@UnBCL@@@UnBCL@@6BObject@1@@; const UnBCL::ArrayList<UnBCL::String *>::`local vftable'{for `UnBCL::Object'}
0x18018a815  test    rax, rax
0x18018a818  jz      short loc_18018A82C
0x18018a81a  mov     edx, r12d
0x18018a81d  mov     rcx, rax
0x18018a820  call    cs:__imp_??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::ArrayList<UnBCL::String *>::ArrayList<UnBCL::String *>(void)
0x18018a826  mov     [rbx+30h], rsi
0x18018a82a  jmp     short loc_18018A82E
0x18018a82c  xor     ebx, ebx
0x18018a82e  mov     rdx, rbx
0x18018a831  lea     rcx, [rbp+0C0h+var_118]
0x18018a835  call    cs:__imp_??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(UnBCL::ArrayList<UnBCL::String *> *)
0x18018a83b  nop
0x18018a83c  lea     rcx, [rbp+0C0h+var_118]
0x18018a840  call    cs:__imp_??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(void)
0x18018a846  mov     r8, rax
0x18018a849  mov     rcx, [rax]
0x18018a84c  mov     rax, [rcx+28h]
0x18018a850  mov     edx, r12d
0x18018a853  mov     rcx, r8
0x18018a856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018a85b  mov     rcx, r14
0x18018a85e  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18018a864  mov     rbx, rax
0x18018a867  mov     [rbp+0C0h+var_F8], rax
0x18018a86b  test    rax, rax
0x18018a86e  jz      short loc_18018A882
0x18018a870  mov     edx, r12d
0x18018a873  mov     rcx, rax
0x18018a876  call    cs:__imp_??0?$ArrayList@PEAVString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::ArrayList<UnBCL::String *>::ArrayList<UnBCL::String *>(void)
0x18018a87c  mov     [rbx+30h], rsi
0x18018a880  jmp     short loc_18018A884
0x18018a882  xor     ebx, ebx
0x18018a884  mov     rdx, rbx
0x18018a887  lea     rcx, [rbp+0C0h+var_108]
0x18018a88b  call    cs:__imp_??0?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVString@UnBCL@@@1@@Z; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>(UnBCL::ArrayList<UnBCL::String *> *)
0x18018a891  nop
0x18018a892  lea     rcx, [rbp+0C0h+var_108]
0x18018a896  call    cs:__imp_??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(void)
0x18018a89c  mov     r8, rax
0x18018a89f  mov     rcx, [rax]
0x18018a8a2  mov     rax, [rcx+28h]
0x18018a8a6  mov     edx, r12d
0x18018a8a9  mov     rcx, r8
0x18018a8ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018a8b1  mov     [rbp+0C0h+var_138], 0
0x18018a8b9  lea     rax, ??_7?$CAutoRelease@PEAUIDeviceIdDatabase@@@RAII@@6B@; const RAII::CAutoRelease<IDeviceIdDatabase *>::`vftable'
0x18018a8c0  mov     [rbp+0C0h+var_140], rax
0x18018a8c4  mov     rdx, [r15+20h]
0x18018a8c8  mov     r9d, [rdx+8]
0x18018a8cc  mov     r8d, [rdx+4]
0x18018a8d0  mov     edx, [rdx]
0x18018a8d2  lea     rcx, aDDD; "%d.%d.%d"
0x18018a8d9  call    cs:__imp_?Format@String@UnBCL@@SAPEAV12@PEBGZZ; UnBCL::String::Format(ushort const *,...)
0x18018a8df  mov     rdx, rax
0x18018a8e2  lea     rcx, [rbp+0C0h+var_B8]
0x18018a8e6  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18018a8ec  nop
0x18018a8ed  xor     ebx, ebx
0x18018a8ef  mov     esi, 0C8000h
0x18018a8f4  lea     r15, aBaseNtsetupSet_38; "base\\ntsetup\\setupplatform\\lib\\src"...
0x18018a8fb  lea     r14, aCinstallduupda_6; "CInstallDUUpdatesOffline::FindUpdates"
0x18018a902  mov     [rbp+0C0h+var_130], ebx
0x18018a905  lea     rcx, [rbp+0C0h+var_E0]
0x18018a909  call    cs:__imp_??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(void)
0x18018a90f  mov     rcx, [rax+8]
0x18018a913  movsxd  rdx, dword ptr [rcx+0Ch]
0x18018a917  lea     rcx, [rax+8]
0x18018a91b  add     rcx, rdx
0x18018a91e  mov     rax, [rcx]
0x18018a921  mov     rax, [rax]
0x18018a924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018a929  cmp     ebx, eax
0x18018a92b  jge     loc_18018B1AE
0x18018a931  lea     rcx, [rbp+0C0h+var_E0]
0x18018a935  call    cs:__imp_??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(void)
0x18018a93b  mov     rcx, [rax+8]
0x18018a93f  movsxd  rdx, dword ptr [rcx+10h]
0x18018a943  lea     rcx, [rax+8]
0x18018a947  add     rcx, rdx
0x18018a94a  mov     rax, [rcx]
0x18018a94d  mov     edx, ebx
0x18018a94f  mov     rax, [rax+18h]
0x18018a953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018a958  mov     rbx, [rax]
0x18018a95b  mov     [rbp+0C0h+var_F8], rbx
0x18018a95f  mov     r8d, r12d
0x18018a962  lea     rdx, aImageinfo; "ImageInfo"
0x18018a969  mov     rcx, rbx
0x18018a96c  call    cs:__imp_?StartsWith@String@UnBCL@@QEBAHPEBGH@Z; UnBCL::String::StartsWith(ushort const *,int)
0x18018a972  test    eax, eax
0x18018a974  jnz     loc_18018AF83
0x18018a97a  mov     r8d, r12d
0x18018a97d  lea     rdx, aSpaceneeded; "SpaceNeeded"
0x18018a984  mov     rcx, rbx
0x18018a987  call    cs:__imp_?StartsWith@String@UnBCL@@QEBAHPEBGH@Z; UnBCL::String::StartsWith(ushort const *,int)
0x18018a98d  test    eax, eax
0x18018a98f  jnz     loc_18018AF83
0x18018a995  lea     edx, [rax+3Dh]
0x18018a998  mov     rcx, rbx
0x18018a99b  call    cs:__imp_?LastIndexOf@String@UnBCL@@QEBAHG@Z; UnBCL::String::LastIndexOf(ushort)
0x18018a9a1  mov     dword ptr [rsp+1C0h+var_158], eax
0x18018a9a5  test    eax, eax
0x18018a9a7  jle     loc_18018AF0F
0x18018a9ad  mov     r8d, eax
0x18018a9b0  xor     edx, edx
0x18018a9b2  mov     rcx, rbx
0x18018a9b5  call    cs:__imp_?Substring@String@UnBCL@@QEBAPEAV12@HH@Z; UnBCL::String::Substring(int,int)
0x18018a9bb  mov     rdx, rax
0x18018a9be  lea     rcx, [rbp+0C0h+var_F0]
0x18018a9c2  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18018a9c8  nop
0x18018a9c9  mov     r8d, dword ptr [rsp+1C0h+var_158]
0x18018a9ce  inc     r8d
0x18018a9d1  xor     edx, edx
0x18018a9d3  mov     rcx, rbx
0x18018a9d6  call    cs:__imp_?Remove@String@UnBCL@@QEBAPEAV12@HH@Z; UnBCL::String::Remove(int,int)
0x18018a9dc  mov     rdx, rax
0x18018a9df  lea     rcx, [rbp+0C0h+var_D0]
0x18018a9e3  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18018a9e9  nop
0x18018a9ea  lea     rcx, [rbp+0C0h+var_D0]
0x18018a9ee  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18018a9f4  mov     rcx, rax
0x18018a9f7  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18018a9fd  mov     rcx, rax; String
0x18018aa00  call    cs:__imp__wtoi
0x18018aa06  mov     dword ptr [rsp+1C0h+var_158], eax
0x18018aa0a  lea     rcx, [rbp+0C0h+var_F0]
0x18018aa0e  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18018aa14  mov     rbx, rax
0x18018aa17  mov     rdx, [rbp+0C0h+arg_0]
0x18018aa1e  lea     rcx, [rbp+0C0h+var_68]
0x18018aa22  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18018aa28  nop
0x18018aa29  mov     rdx, rbx
0x18018aa2c  mov     rcx, rax
0x18018aa2f  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x18018aa35  mov     rdx, rax
0x18018aa38  lea     rcx, [rbp+0C0h+var_128]
0x18018aa3c  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18018aa42  nop
0x18018aa43  lea     rcx, [rbp+0C0h+var_68]
0x18018aa47  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18018aa4d  mov     eax, dword ptr [rsp+1C0h+var_158]
0x18018aa51  cmp     eax, 2
0x18018aa54  jz      loc_18018ACFE
0x18018aa5a  cmp     eax, 4
0x18018aa5d  jz      loc_18018AAEA
0x18018aa63  call    cs:__imp_GetLastError
0x18018aa69  mov     edi, eax
0x18018aa6b  call    cs:__imp_CurrentIP
0x18018aa71  mov     rbx, rax
0x18018aa74  lea     rcx, [rbp+0C0h+var_128]
0x18018aa78  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18018aa7e  mov     rcx, rax
0x18018aa81  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18018aa87  mov     r9, rax
0x18018aa8a  mov     r8d, dword ptr [rsp+1C0h+var_158]
0x18018aa8f  lea     rdx, aCinstallduupda_17; "CInstallDUUpdatesOffline::FindUpdates: "...
0x18018aa96  mov     ecx, 2000000h; unsigned int
0x18018aa9b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18018aaa0  mov     dword ptr [rsp+50h], 0
0x18018aaa8  mov     qword ptr [rsp+1C0h+var_178], 0
0x18018aab1  mov     dword ptr [rsp+1C0h+var_180], edi
0x18018aab5  mov     qword ptr [rsp+1C0h+var_188], rbx
0x18018aaba  mov     [rsp+1C0h+var_190], r14
0x18018aabf  mov     qword ptr [rsp+1C0h+var_198], r15
0x18018aac4  mov     [rsp+1C0h+var_1A0], 121Dh
0x18018aacc  xor     r9d, r9d
0x18018aacf  lea     r8, aD_0; "D"
0x18018aad6  mov     edx, esi
0x18018aad8  mov     rcx, rax
0x18018aadb  call    cs:__imp_WdsSetupLogMessageW
0x18018aae1  mov     edi, dword ptr [rsp+1C0h+var_160]
0x18018aae5  jmp     loc_18018AE6B
0x18018aaea  lea     rdx, aCab_0; "*.cab"
0x18018aaf1  lea     rcx, [rbp+0C0h+var_50]
0x18018aaf5  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
  ... truncated ...
```
