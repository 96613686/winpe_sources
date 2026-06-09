# CProcessDrivers::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)

- ea: `0x1801ab850`
- end: `0x1801ae4d3`
- name: `?DoExecute@CProcessDrivers@@UEAAJPEAUIExecutionContext@@PEAXPEAUIInternalOperationsProgress@@@Z`
- size: `11395`
- prototype: `void __fastcall __noreturn(CProcessDrivers *__hidden this, struct IExecutionContext *, void *, struct IInternalOperationsProgress *)`
- caller_count: `0`
- callee_count: `32`
- tags: `file_ops, reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18001413d`
- `0x180044754`
- `0x1800447ec`
- `0x180044810`
- `0x180044820`
- `0x180057dec`
- `0x18005dd24`
- `0x1800ae6b4`
- `0x1800b3068`
- `0x18012a5c0`
- `0x18012b0fc`
- `0x1801556c4`
- `0x180156314`
- `0x18015debc`
- `0x18019e424`
- `0x18019f5c4`
- `0x1801a0648`
- `0x1801a06a4`
- `0x1801a2f8c`
- `0x1801a4b38`
- `0x1801ab850`
- `0x1801b107c`
- `0x1801b3c20`
- `0x1801b5328`
- `0x1801b79bc`
- `0x1802e4200`
- `0x1802fb1a8`
- `0x18032e7dc`
- `0x1803f2ca0`
- `0x180405958`
- `0x1804aba5c`
- `0x180509010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1801ac1a9`
- `ntdll!RtlNtStatusToDosError` at `0x1801ac1b8`
- `ntdll!RtlNtStatusToDosError` at `0x1801ac1a9`
- `ntdll!RtlNtStatusToDosError` at `0x1801ac1b8`
- `KERNEL32!GetLastError` at `0x1801ab990`
- `KERNEL32!GetLastError` at `0x1801aba2e`
- `KERNEL32!GetLastError` at `0x1801abd44`
- `KERNEL32!GetLastError` at `0x1801abe2b`
- `KERNEL32!GetLastError` at `0x1801abf06`
- `KERNEL32!GetLastError` at `0x1801ac0f0`
- `KERNEL32!GetLastError` at `0x1801ac1ea`
- `KERNEL32!GetLastError` at `0x1801ac6b7`
- `KERNEL32!GetLastError` at `0x1801ac795`
- `KERNEL32!GetLastError` at `0x1801ac894`
- `KERNEL32!GetLastError` at `0x1801acfab`
- `KERNEL32!GetLastError` at `0x1801ad468`
- `KERNEL32!GetLastError` at `0x1801ad482`
- `KERNEL32!GetLastError` at `0x1801ad4a3`
- `KERNEL32!GetLastError` at `0x1801ad53a`
- `KERNEL32!GetLastError` at `0x1801ad5b7`
- `KERNEL32!GetLastError` at `0x1801ad745`
- `KERNEL32!GetLastError` at `0x1801ad7ee`
- `KERNEL32!GetLastError` at `0x1801ad87b`
- `KERNEL32!GetLastError` at `0x1801ad914`
- `KERNEL32!GetLastError` at `0x1801ad9a7`
- `KERNEL32!GetLastError` at `0x1801ada3f`
- `KERNEL32!GetLastError` at `0x1801adb0e`
- `KERNEL32!GetLastError` at `0x1801adbb8`
- `KERNEL32!GetLastError` at `0x1801adc9e`
- `KERNEL32!GetLastError` at `0x1801add44`
- `KERNEL32!GetLastError` at `0x1801add5a`
- `KERNEL32!GetLastError` at `0x1801add7d`
- `KERNEL32!GetLastError` at `0x1801ade3a`
- `KERNEL32!GetLastError` at `0x1801ade50`
- `KERNEL32!GetLastError` at `0x1801ade73`
- `KERNEL32!GetLastError` at `0x1801adf46`
- `KERNEL32!GetLastError` at `0x1801ab990`
- `KERNEL32!GetLastError` at `0x1801aba2e`
- `KERNEL32!GetLastError` at `0x1801abd44`
- `KERNEL32!GetLastError` at `0x1801abe2b`
- `KERNEL32!GetLastError` at `0x1801abf06`
- `KERNEL32!GetLastError` at `0x1801ac0f0`
- `KERNEL32!GetLastError` at `0x1801ac1ea`
- `KERNEL32!GetLastError` at `0x1801ac6b7`
- `KERNEL32!GetLastError` at `0x1801ac795`
- `KERNEL32!GetLastError` at `0x1801ac894`
- `KERNEL32!GetLastError` at `0x1801acfab`
- `KERNEL32!GetLastError` at `0x1801ad468`
- `KERNEL32!GetLastError` at `0x1801ad482`
- `KERNEL32!GetLastError` at `0x1801ad4a3`
- `KERNEL32!GetLastError` at `0x1801ad53a`
- `KERNEL32!GetLastError` at `0x1801ad5b7`
- `KERNEL32!GetLastError` at `0x1801ad745`
- `KERNEL32!GetLastError` at `0x1801ad7ee`
- `KERNEL32!GetLastError` at `0x1801ad87b`
- `KERNEL32!GetLastError` at `0x1801ad914`
- `KERNEL32!GetLastError` at `0x1801ad9a7`
- `KERNEL32!GetLastError` at `0x1801ada3f`
- `KERNEL32!GetLastError` at `0x1801adb0e`
- `KERNEL32!GetLastError` at `0x1801adbb8`
- `KERNEL32!GetLastError` at `0x1801adc9e`
- `KERNEL32!GetLastError` at `0x1801add44`
- `KERNEL32!GetLastError` at `0x1801add5a`
- `KERNEL32!GetLastError` at `0x1801add7d`
- `KERNEL32!GetLastError` at `0x1801ade3a`
- `KERNEL32!GetLastError` at `0x1801ade50`
- `KERNEL32!GetLastError` at `0x1801ade73`
- `KERNEL32!GetLastError` at `0x1801adf46`
- `KERNEL32!GetProcAddress` at `0x1801ad3a8`
- `KERNEL32!GetProcAddress` at `0x1801ad3a8`
- `KERNEL32!LoadLibraryExW` at `0x1801ad387`
- `KERNEL32!LoadLibraryExW` at `0x1801ad387`
- `unbcl!?EndsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1801abc08`
- `unbcl!?EndsWith@String@UnBCL@@QEBAHPEBGH@Z` at `0x1801abc08`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x1801abb10`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x1801abba5`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x1801abbd5`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x1801abc1e`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x1801abb10`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x1801abba5`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x1801abbd5`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x1801abc1e`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801abfc4`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801abfc4`
- `unbcl!?GetFiles@Directory@UnBCL@@SAPEAV?$Array@PEAVString@UnBCL@@@2@PEBVString@2@0H@Z` at `0x1801abad9`
- `unbcl!?GetFiles@Directory@UnBCL@@SAPEAV?$Array@PEAVString@UnBCL@@@2@PEBVString@2@0H@Z` at `0x1801abad9`
- `unbcl!??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z` at `0x1801abaea`
- `unbcl!??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z` at `0x1801abaea`
- `unbcl!?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1801ac29f`
- `unbcl!?GetParentPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1801ac29f`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG00@Z` at `0x1801acbb3`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG00@Z` at `0x1801acc17`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG00@Z` at `0x1801acc78`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG00@Z` at `0x1801ad170`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG00@Z` at `0x1801ad1d4`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG00@Z` at `0x1801ad235`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG00@Z` at `0x1801acbb3`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG00@Z` at `0x1801acc17`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG00@Z` at `0x1801acc78`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG00@Z` at `0x1801ad170`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG00@Z` at `0x1801ad1d4`
- `unbcl!?Concat@String@UnBCL@@SAPEAV12@PEBG00@Z` at `0x1801ad235`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1801ab949`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1801ab949`
- `unbcl!?get_P@?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@2@XZ` at `0x1801abaf9`
- `unbcl!?get_P@?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@2@XZ` at `0x1801abaf9`
- `unbcl!?DecRef@Object@UnBCL@@QEAAHXZ` at `0x1801abddb`
- `unbcl!?DecRef@Object@UnBCL@@QEAAHXZ` at `0x1801abddb`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1801abc53`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1801ad31b`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1801ad3e6`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1801ae050`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1801ae1f1`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1801abc53`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1801ad31b`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1801ad3e6`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1801ae050`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1801ae1f1`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1801ad639`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1801ad639`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x1801abcd8`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x1801abcd8`
- `unbcl!??0String@UnBCL@@QEAA@XZ` at `0x1801ac975`
- `unbcl!??0String@UnBCL@@QEAA@XZ` at `0x1801ac9bf`
- `unbcl!??0String@UnBCL@@QEAA@XZ` at `0x1801ac9fb`
- `unbcl!??0String@UnBCL@@QEAA@XZ` at `0x1801acd5b`
- `unbcl!??0String@UnBCL@@QEAA@XZ` at `0x1801acd97`
- `unbcl!??0String@UnBCL@@QEAA@XZ` at `0x1801acdd3`
- `unbcl!??0String@UnBCL@@QEAA@XZ` at `0x1801ac975`
- `unbcl!??0String@UnBCL@@QEAA@XZ` at `0x1801ac9bf`
- `unbcl!??0String@UnBCL@@QEAA@XZ` at `0x1801ac9fb`
- `unbcl!??0String@UnBCL@@QEAA@XZ` at `0x1801acd5b`
- `unbcl!??0String@UnBCL@@QEAA@XZ` at `0x1801acd97`
- `unbcl!??0String@UnBCL@@QEAA@XZ` at `0x1801acdd3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801ab972`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801abac6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801abc47`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801ac04f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801ac20d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801ac288`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801ac296`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801ac2bf`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801ac2d2`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801ac31f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801ac3d0`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801ac476`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801ac525`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801ac5c7`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801ad0af`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801ad430`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801ab972`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801abac6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801abc47`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801ac04f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801ac20d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801ac288`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801ac296`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801ac2bf`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801ac2d2`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801ac31f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801ac3d0`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801ac476`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801ac525`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801ac5c7`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801ad0af`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801ad430`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1801ab915`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1801ab924`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1801ace8e`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1801ab915`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1801ab924`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1801ace8e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1801ad33b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1801ad406`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1801ae070`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1801ae211`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1801ae3b6`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1801ad33b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1801ad406`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1801ae070`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1801ae211`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1801ae3b6`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801acf22`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801ad2f6`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801ad3c9`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801ae02b`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801ae1cc`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801ae395`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801acf22`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801ad2f6`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801ad3c9`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801ae02b`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801ae1cc`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801ae395`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801abb3b`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801abcba`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801ac3e6`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801ac488`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801ac537`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1801ac5d9`

## string_xrefs

- `0x1801ad5c8`: `Ignoring error due to operation configuration.`
- `0x1801ab9a1`: `Attempting to remove unused drivers`
- `0x1801aba4f`: `Removed drivers: Count: %u, Size: %I64u`
- `0x1801ad928`: `Failed to open WinPE DISM session. Error: 0x%08X`
- `0x1801ac116`: `Opening DISM session for SafeOS %s`
- `0x1801ac7a9`: `CreateSetupOneSettings failed. Error: 0x%08X`
- `0x1801ac236`: `Opening DISM session for the source system (%s)`
- `0x1801ad9be`: `Failed to open new session: (%s). Error: 0x%08X`
- `0x1801adcb5`: `Failed to process installation of driver package %s. Error: 0x%08X`
- `0x1801ad034`: `DriverInfGetInfoFailedPath`
- `0x1801ad2e7`: `PnpPropMig.dll`
- `0x1801ae2bc`: `DriverSafeOSInstallFailedList`
- `0x1801ae2f6`: `DriverSafeOSInstallFailureIgnoredList`
- `0x1801ae282`: `DriverSafeOSInstalledList`

## pseudocode

```c
// Hidden C++ exception states: #wind=94 #try_helpers=2
void __fastcall __noreturn CProcessDrivers::DoExecute(
        CProcessDrivers *this,
        struct IExecutionContext *a2,
        void *a3,
        struct IInternalOperationsProgress *a4)
{
  CProcessDrivers *v4; // rdi
  DWORD LastError; // edi
  __int64 v6; // rbx
  struct tagLOG_PARTIAL_MSG *v7; // rax
  CProcessDrivers *v8; // rcx
  DWORD v9; // edi
  __int64 v10; // rbx
  struct tagLOG_PARTIAL_MSG *v11; // rax
  char *v12; // r15
  __int64 P; // rax
  __int64 Files; // rax
  __int64 v15; // rax
  unsigned int (__fastcall ***v16)(_QWORD); // rcx
  struct UnBCL::String *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rax
  unsigned int i; // edi
  __int64 v21; // rax
  int (__fastcall ***v22)(_QWORD); // rcx
  __int64 v23; // rax
  __int64 v24; // rcx
  UnBCL::String **v25; // rax
  __int64 v26; // rax
  __int64 v27; // rcx
  const struct UnBCL::String *v28; // rbx
  const struct UnBCL::String *v29; // rax
  struct UnBCL::String *v30; // rax
  UnBCL::String *v31; // rax
  const unsigned __int16 *CString; // rax
  __int64 v33; // rsi
  __int64 v34; // r14
  void *v35; // rbx
  __int64 v36; // rax
  __int64 v37; // r9
  __int64 v38; // rax
  unsigned int (__fastcall ***v39)(_QWORD); // rcx
  DWORD v40; // ebx
  __int64 v41; // rdi
  UnBCL::String *v42; // rax
  const char *v43; // rax
  struct tagLOG_PARTIAL_MSG *v44; // rax
  __int64 v45; // rdx
  DWORD v46; // edi
  __int64 v47; // rsi
  UnBCL::String *v48; // rax
  const char *v49; // rbx
  __int64 (__fastcall ***v50)(_QWORD); // rcx
  int v51; // eax
  DWORD v52; // ebx
  __int64 v53; // rdi
  UnBCL::String *v54; // rax
  const char *v55; // rax
  struct tagLOG_PARTIAL_MSG *v56; // rax
  unsigned int (__fastcall ***v57)(_QWORD); // rcx
  UnBCL::String *v58; // rax
  const unsigned __int16 *v59; // rbx
  UnBCL::String *v60; // rax
  const unsigned __int16 *v61; // rax
  int v62; // esi
  char *v63; // rsi
  UnBCL::String *v64; // rax
  unsigned int v65; // eax
  int v66; // r8d
  int v67; // r9d
  DWORD v68; // ebx
  __int64 v69; // rdi
  UnBCL::String *v70; // rax
  const char *v71; // rax
  struct tagLOG_PARTIAL_MSG *v72; // rax
  UnBCL::String *v73; // rax
  const unsigned __int16 *v74; // rax
  NTSTATUS v75; // eax
  NTSTATUS v76; // esi
  bool v77; // zf
  DWORD v78; // ebx
  __int64 v79; // rdi
  char *v80; // rsi
  UnBCL::String *v81; // rax
  const unsigned __int16 *v82; // rax
  struct tagLOG_PARTIAL_MSG *v83; // rax
  struct UnBCL::String *ParentPath; // rax
  const struct UnBCL::String *v85; // rax
  struct UnBCL::String *v86; // rax
  struct UnBCL::String *v87; // rax
  UnBCL::String *v88; // rax
  const wchar_t *v89; // rsi
  int v90; // r14d
  struct UnBCL::String *v91; // rax
  __int64 v92; // rax
  UnBCL::String *v93; // rax
  const unsigned __int16 *v94; // rax
  struct UnBCL::String *v95; // rax
  __int64 v96; // rax
  UnBCL::String *v97; // rax
  const unsigned __int16 *v98; // rax
  struct UnBCL::String *v99; // rax
  __int64 v100; // rax
  UnBCL::String *v101; // rax
  const unsigned __int16 *v102; // rax
  struct UnBCL::String *v103; // rax
  __int64 v104; // rax
  UnBCL::String *v105; // rax
  const unsigned __int16 *v106; // rax
  int Drivers; // esi
  DWORD v108; // edi
  __int64 v109; // rbx
  struct tagLOG_PARTIAL_MSG *v110; // rax
  struct ISetupOneSettings **v111; // rax
  const unsigned __int16 *v112; // rdx
  const unsigned __int16 *v113; // rcx
  int SetupOneSettings; // esi
  DWORD v115; // edi
  __int64 v116; // rbx
  struct tagLOG_PARTIAL_MSG *v117; // rax
  void (__fastcall ***v118)(_QWORD, const wchar_t *, char *); // rax
  DWORD v119; // edi
  __int64 v120; // rbx
  struct tagLOG_PARTIAL_MSG *v121; // rax
  struct UnBCL::String *v122; // rax
  __int64 v123; // rax
  struct UnBCL::String *v124; // rax
  struct UnBCL::String *v125; // rbx
  struct UnBCL::String *v126; // rax
  struct UnBCL::String *v127; // rbx
  struct UnBCL::String *v128; // rax
  struct UnBCL::String *v129; // rbx
  unsigned int j; // r12d
  __int64 v131; // rsi
  __int16 v132; // r15
  __int64 v133; // rbx
  int v134; // edi
  int v135; // r14d
  int v136; // r14d
  const unsigned __int16 *v137; // rbx
  UnBCL::String *v138; // rax
  const unsigned __int16 *v139; // rax
  struct UnBCL::String *v140; // rax
  struct UnBCL::String **v141; // rcx
  const unsigned __int16 *v142; // rbx
  UnBCL::String *v143; // rax
  const unsigned __int16 *v144; // rax
  struct UnBCL::String *v145; // rax
  const unsigned __int16 *v146; // rbx
  UnBCL::String *v147; // rax
  const unsigned __int16 *v148; // rax
  struct UnBCL::String *v149; // rax
  struct UnBCL::String *v150; // rax
  __int64 v151; // rax
  struct UnBCL::String *v152; // rax
  struct UnBCL::String *v153; // rbx
  struct UnBCL::String *v154; // rax
  struct UnBCL::String *v155; // rbx
  struct UnBCL::String *v156; // rax
  struct UnBCL::String *v157; // rbx
  __int64 v158; // rdx
  unsigned int v159; // r15d
  int v160; // edi
  __int64 v161; // rsi
  unsigned int (__fastcall ***v162)(_QWORD); // rcx
  __int64 v163; // rcx
  _QWORD *v164; // rax
  UnBCL::String *v165; // rax
  const char *v166; // r14
  __int64 v167; // rcx
  _QWORD *v168; // rax
  struct UnBCL::String *v169; // rbx
  __int64 v170; // rcx
  _QWORD *v171; // rax
  UnBCL::String *v172; // rax
  const unsigned __int16 *v173; // rax
  __int64 v174; // rcx
  int DriverInfo; // esi
  DWORD v176; // edi
  __int64 v177; // rbx
  struct tagLOG_PARTIAL_MSG *v178; // rax
  __int64 v179; // rbx
  __int64 v180; // rbx
  __int64 v181; // rax
  int v182; // esi
  const unsigned __int16 *v183; // rbx
  UnBCL::String *v184; // rax
  const unsigned __int16 *v185; // rax
  struct UnBCL::String *v186; // rax
  _BYTE *v187; // rcx
  const unsigned __int16 *v188; // rbx
  UnBCL::String *v189; // rax
  const unsigned __int16 *v190; // rax
  struct UnBCL::String *v191; // rax
  const unsigned __int16 *v192; // rbx
  UnBCL::String *v193; // rax
  const unsigned __int16 *v194; // rax
  struct UnBCL::String *v195; // rax
  const struct UnBCL::String *v196; // rbx
  const struct UnBCL::String *v197; // rax
  struct UnBCL::String *v198; // rax
  UnBCL::String *v199; // rax
  const unsigned __int16 *v200; // rax
  UnBCL::String *v201; // rax
  const WCHAR *v202; // rax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rdi
  const struct UnBCL::String *v205; // rbx
  const struct UnBCL::String *v206; // rax
  struct UnBCL::String *v207; // rax
  UnBCL::String *v208; // rax
  const unsigned __int16 *v209; // rbx
  UnBCL::String *v210; // rax
  const unsigned __int16 *v211; // rax
  signed int v212; // eax
  bool v213; // sf
  signed int v214; // eax
  signed int v215; // esi
  DWORD v216; // edi
  __int64 v217; // rbx
  struct tagLOG_PARTIAL_MSG *v218; // rax
  DWORD v219; // edi
  __int64 v220; // rbx
  struct tagLOG_PARTIAL_MSG *v221; // rax
  DWORD v222; // edi
  __int64 v223; // rbx
  struct tagLOG_PARTIAL_MSG *v224; // rax
  DWORD v225; // edi
  __int64 v226; // rbx
  struct tagLOG_PARTIAL_MSG *v227; // rax
  DWORD v228; // edi
  __int64 v229; // rbx
  struct tagLOG_PARTIAL_MSG *v230; // rax
  DWORD v231; // edi
  __int64 v232; // rbx
  struct tagLOG_PARTIAL_MSG *v233; // rax
  DWORD v234; // edi
  __int64 v235; // rbx
  struct tagLOG_PARTIAL_MSG *v236; // rax
  DWORD v237; // edi
  __int64 v238; // rbx
  struct tagLOG_PARTIAL_MSG *v239; // rax
  DWORD v240; // edi
  __int64 v241; // rbx
  struct tagLOG_PARTIAL_MSG *v242; // rax
  DWORD v243; // edi
  __int64 v244; // rbx
  struct tagLOG_PARTIAL_MSG *v245; // rax
  DWORD v246; // edi
  __int64 v247; // rbx
  struct tagLOG_PARTIAL_MSG *v248; // rax
  signed int v249; // eax
  bool v250; // sf
  signed int v251; // eax
  unsigned int v252; // esi
  DWORD v253; // ebx
  __int64 v254; // rdi
  UnBCL::String *v255; // rax
  const char *v256; // rax
  struct tagLOG_PARTIAL_MSG *v257; // rax
  signed int v258; // eax
  bool v259; // sf
  signed int v260; // eax
  unsigned int v261; // esi
  DWORD v262; // edi
  __int64 v263; // rbx
  struct tagLOG_PARTIAL_MSG *v264; // rax
  DWORD v265; // ebx
  __int64 v266; // rdi
  UnBCL::String *v267; // rax
  const char *v268; // rax
  struct tagLOG_PARTIAL_MSG *v269; // rax
  __int64 v270; // rax
  int (__fastcall ***v271)(_QWORD); // rcx
  const struct UnBCL::String *v272; // rbx
  const struct UnBCL::String *v273; // rax
  struct UnBCL::String *v274; // rax
  UnBCL::String *v275; // rax
  __int64 v276; // rax
  __int64 v277; // rdx
  __int64 v278; // rdi
  void (__fastcall *v279)(__int64, const wchar_t *, const wchar_t *, const unsigned __int16 *); // rbx
  UnBCL::String *v280; // rax
  const unsigned __int16 *v281; // rax
  void (__fastcall *v282)(__int64, const wchar_t *, const wchar_t *, const unsigned __int16 *); // rbx
  UnBCL::String *v283; // rax
  const unsigned __int16 *v284; // rax
  void (__fastcall *v285)(__int64, const wchar_t *, const wchar_t *, const unsigned __int16 *); // rbx
  UnBCL::String *v286; // rax
  const unsigned __int16 *v287; // rax
  __int64 v288; // rax
  int (__fastcall ***v289)(_QWORD); // rcx
  const struct UnBCL::String *v290; // rbx
  const struct UnBCL::String *v291; // rax
  struct UnBCL::String *v292; // rax
  UnBCL::String *v293; // rax
  __int64 v294; // rax
  __int64 v295; // rdx
  void (__fastcall *v296)(__int64, const wchar_t *, const wchar_t *, const unsigned __int16 *); // rbx
  UnBCL::String *v297; // rax
  const unsigned __int16 *v298; // rax
  void (__fastcall *v299)(__int64, const wchar_t *, const wchar_t *, const unsigned __int16 *); // rbx
  UnBCL::String *v300; // rax
  const unsigned __int16 *v301; // rax
  void (__fastcall *v302)(__int64, const wchar_t *, const wchar_t *, const unsigned __int16 *); // rbx
  UnBCL::String *v303; // rax
  const unsigned __int16 *v304; // rax
  __int64 v305; // rbx
  struct UnBCL::String *v306; // rax
  CBool *v307; // rdx
  void (__fastcall *v308)(struct IExecutionContext *, __int64, char *); // rdi
  char *v309; // rbx
  __int64 v310; // rax
  int v311; // [rsp+20h] [rbp-388h]
  int v312; // [rsp+20h] [rbp-388h]
  int v313; // [rsp+28h] [rbp-380h]
  int v314; // [rsp+30h] [rbp-378h]
  int v315; // [rsp+38h] [rbp-370h]
  __int64 v316; // [rsp+38h] [rbp-370h]
  int v317; // [rsp+40h] [rbp-368h]
  DWORD v318; // [rsp+40h] [rbp-368h]
  int v319; // [rsp+48h] [rbp-360h]
  __int64 v320; // [rsp+50h] [rbp-358h]
  _QWORD v321[2]; // [rsp+88h] [rbp-320h] BYREF
  int v322; // [rsp+98h] [rbp-310h] BYREF
  struct UnBCL::String *v323[2]; // [rsp+A0h] [rbp-308h] BYREF
  int v324; // [rsp+B0h] [rbp-2F8h] BYREF
  unsigned int v325; // [rsp+B4h] [rbp-2F4h] BYREF
  int v326; // [rsp+B8h] [rbp-2F0h] BYREF
  void **v327; // [rsp+C0h] [rbp-2E8h] BYREF
  __int64 v328; // [rsp+C8h] [rbp-2E0h]
  __int64 v329; // [rsp+D0h] [rbp-2D8h] BYREF
  _QWORD v330[2]; // [rsp+D8h] [rbp-2D0h] BYREF
  _QWORD v331[2]; // [rsp+E8h] [rbp-2C0h] BYREF
  unsigned int v332; // [rsp+F8h] [rbp-2B0h] BYREF
  _DWORD v333[3]; // [rsp+FCh] [rbp-2ACh] BYREF
  __int64 v334; // [rsp+108h] [rbp-2A0h]
  __int64 v335; // [rsp+110h] [rbp-298h] BYREF
  unsigned int v336[2]; // [rsp+118h] [rbp-290h] BYREF
  __int64 v337; // [rsp+120h] [rbp-288h]
  int v338; // [rsp+128h] [rbp-280h]
  __int64 v339; // [rsp+130h] [rbp-278h] BYREF
  _BYTE v340[48]; // [rsp+138h] [rbp-270h] BYREF
  _BYTE v341[24]; // [rsp+168h] [rbp-240h] BYREF
  __int64 v342; // [rsp+180h] [rbp-228h] BYREF
  __int64 v343; // [rsp+188h] [rbp-220h]
  const __int64 *v344; // [rsp+190h] [rbp-218h] BYREF
  __int64 v345; // [rsp+198h] [rbp-210h]
  _BYTE v346[24]; // [rsp+1A0h] [rbp-208h] BYREF
  _BYTE v347[16]; // [rsp+1B8h] [rbp-1F0h] BYREF
  HMODULE v348; // [rsp+1C8h] [rbp-1E0h]
  _BYTE v349[8]; // [rsp+1D0h] [rbp-1D8h] BYREF
  __int64 v350; // [rsp+1D8h] [rbp-1D0h]
  void **v351; // [rsp+1E0h] [rbp-1C8h]
  __int64 v352; // [rsp+1E8h] [rbp-1C0h]
  void **v353; // [rsp+1F0h] [rbp-1B8h] BYREF
  __int64 v354; // [rsp+1F8h] [rbp-1B0h]
  _BYTE v355[8]; // [rsp+200h] [rbp-1A8h] BYREF
  __int64 v356; // [rsp+208h] [rbp-1A0h]
  _BYTE v357[24]; // [rsp+210h] [rbp-198h] BYREF
  _QWORD v358[7]; // [rsp+228h] [rbp-180h] BYREF
  _BYTE v359[16]; // [rsp+260h] [rbp-148h] BYREF
  _BYTE v360[16]; // [rsp+270h] [rbp-138h] BYREF
  _BYTE v361[16]; // [rsp+280h] [rbp-128h] BYREF
  _BYTE v362[16]; // [rsp+290h] [rbp-118h] BYREF
  _BYTE v363[16]; // [rsp+2A0h] [rbp-108h] BYREF
  _BYTE v364[24]; // [rsp+2B0h] [rbp-F8h] BYREF
  _QWORD *v365; // [rsp+2C8h] [rbp-E0h] BYREF
  _QWORD *pExceptionObject; // [rsp+2D0h] [rbp-D8h] BYREF
  _QWORD *v367; // [rsp+2E0h] [rbp-C8h] BYREF
  _QWORD *v368; // [rsp+2E8h] [rbp-C0h] BYREF
  _QWORD *v369; // [rsp+2F0h] [rbp-B8h] BYREF
  _QWORD *v370; // [rsp+2F8h] [rbp-B0h] BYREF
  _QWORD *v371; // [rsp+300h] [rbp-A8h] BYREF
  _QWORD *v372; // [rsp+308h] [rbp-A0h] BYREF
  _QWORD *v373; // [rsp+310h] [rbp-98h] BYREF
  _QWORD *v374; // [rsp+318h] [rbp-90h] BYREF
  _QWORD *v375; // [rsp+320h] [rbp-88h] BYREF
  _QWORD *v376; // [rsp+328h] [rbp-80h] BYREF
  _QWORD *v377; // [rsp+330h] [rbp-78h] BYREF
  _QWORD v378[5]; // [rsp+338h] [rbp-70h] BYREF
  _BYTE v379[72]; // [rsp+360h] [rbp-48h] BYREF

  v378[4] = -2;
  v4 = this;
  v343 = (*(__int64 (__fastcall **)(struct IExecutionContext *, struct IExecutionContext *, void *, struct IInternalOperationsProgress *))(*(_QWORD *)a2 + 64LL))(
           a2,
           a2,
           a3,
           a4);
  v338 = 0;
  v326 = 0;
  v325 = 0;
  v351 = &UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,int>>::`vftable';
  v352 = 0;
  v339 = 0;
  v342 = 0;
  v332 = 0;
  v329 = 0;
  v322 = 0;
  v344 = &UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>>::`vftable';
  v345 = 0;
  v335 = 0;
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v379);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v362);
  v333[0] = 0;
  v348 = 0;
  UnBCL::Exception::Exception((UnBCL::Exception *)v358);
  v358[0] = &`CProcessDrivers::DoExecute'::`3'::CXXXXXHandledException::`vftable';
  if ( *((_DWORD *)v4 + 86) == 1 && !UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v4 + 208) )
  {
    v336[0] = 0;
    v323[0] = 0;
    LastError = GetLastError();
    v6 = CurrentIP();
    v7 = ConstructPartialMsgW(0x4000000u, "Attempting to remove unused drivers");
    WdsSetupLogMessageW(
      v7,
      819200,
      L"D",
      0,
      1685,
      L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
      L"CProcessDrivers::DoExecute",
      v6,
      LastError,
      0,
      0);
    if ( (unsigned int)CProcessDrivers::CleanupDrivers(v8, a3, v336, (unsigned __int64 *)v323) )
    {
      v9 = GetLastError();
      v10 = CurrentIP();
      v11 = ConstructPartialMsgW(0x4000000u, "Removed drivers: Count: %u, Size: %I64u", v336[0], v323[0]);
      WdsSetupLogMessageW(
        v11,
        819200,
        L"D",
        0,
        1688,
        L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
        L"CProcessDrivers::DoExecute",
        v10,
        v9,
        0,
        0);
    }
    v4 = this;
  }
  if ( *((_DWORD *)v4 + 86) == 2 )
  {
    v12 = (char *)v4 + 224;
    P = UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v4 + 224);
    Files = UnBCL::Directory::GetFiles(P, 0, 1);
    UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::SmartPtr<UnBCL::Array<UnBCL::String *>>(v321, Files);
    if ( UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::get_P(v321)
      && (v15 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v321),
          v16 = (unsigned int (__fastcall ***)(_QWORD))(v15 + 8 + *(int *)(*(_QWORD *)(v15 + 8) + 12LL)),
          (**v16)(v16)) )
    {
      v17 = (struct UnBCL::String *)UnBCL::Object::operator new(0x80u);
      v323[0] = v17;
      if ( v17 )
        v19 = UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>(
                v17,
                v18);
      else
        v19 = 0;
      UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>>::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>>(
        &v333[1],
        v19);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v334 + 40LL))(v334, 1);
      for ( i = 0; ; ++i )
      {
        v21 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v321);
        v22 = (int (__fastcall ***)(_QWORD))(v21 + 8 + *(int *)(*(_QWORD *)(v21 + 8) + 12LL));
        if ( (int)i >= (**v22)(v22) )
          break;
        v23 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v321);
        v24 = v23 + 8 + *(int *)(*(_QWORD *)(v23 + 8) + 16LL);
        v25 = (UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 24LL))(v24, i);
        if ( UnBCL::String::EndsWith(*v25, L".inf", 1) )
        {
          v26 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v321);
          v27 = v26 + 8 + *(int *)(*(_QWORD *)(v26 + 8) + 16LL);
          v28 = *(const struct UnBCL::String **)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v27 + 24LL))(
                                                  v27,
                                                  i);
          v29 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v12);
          v30 = UnBCL::Path::Combine(v29, v28);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v327, v30);
          v323[0] = 0;
          v31 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(&v327);
          CString = UnBCL::String::get_CString(v31);
          SPRetrieveDriverInstallInfo(CString, v323);
          v33 = v334 + *(int *)(*(_QWORD *)(v334 + 8) + 16LL);
          v34 = *(_QWORD *)(v33 + 8);
          v35 = UnBCL::Object::operator new(0x40u);
          *(_QWORD *)v336 = v35;
          if ( v35 )
          {
            v36 = UnBCL::SmartPtr<UnBCL::String>::Steal(&v327);
            v38 = UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>::DictionaryEntry<UnBCL::String *,UnBCL::String *>(
                    v35,
                    v36,
                    v323[0],
                    v37,
                    v311,
                    v313);
          }
          else
          {
            v38 = 0;
          }
          (*(void (__fastcall **)(__int64, __int64))(v34 + 40))(v33 + 8, v38);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v327);
        }
      }
      v39 = (unsigned int (__fastcall ***)(_QWORD))(v334 + 8 + *(int *)(*(_QWORD *)(v334 + 8) + 12LL));
      if ( (**v39)(v39) )
      {
        if ( v334 )
        {
          UnBCL::Object::DecRef((UnBCL::Object *)(v334 + 8 + *(int *)(*(_QWORD *)(v334 + 8) + 4LL)));
          v45 = v334;
          v334 = 0;
        }
        else
        {
          v45 = 0;
        }
        UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>>::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>>(
          &v327,
          v45);
        UnBCL::SmartPtr<UnBCL::ArrayList<CRegCreationData *>>::operator=(&v344, &v327);
        v327 = (void **)&UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>>::`vftable';
        UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v327);
        v46 = GetLastError();
        v47 = CurrentIP();
        v48 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v12);
        v49 = (const char *)UnBCL::String::get_CString(v48);
        v50 = (__int64 (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v345 + 8) + 12LL) + v345 + 8);
        v51 = (**v50)(v50);
        v44 = ConstructPartialMsgW(0x4000000u, "Found %d driver packages in %s.", v51, v49);
        v318 = v46;
        v316 = v47;
        v312 = 1732;
      }
      else
      {
        v40 = GetLastError();
        v41 = CurrentIP();
        v42 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v12);
        v43 = (const char *)UnBCL::String::get_CString(v42);
        v44 = ConstructPartialMsgW(0x3000000u, "Did not find any driver packages in %s", v43);
        v318 = v40;
        v316 = v41;
        v312 = 1727;
      }
      WdsSetupLogMessageW(
        v44,
        819200,
        L"D",
        0,
        v312,
        L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
        L"CProcessDrivers::DoExecute",
        v316,
        v318,
        0,
        0);
      *(_QWORD *)&v333[1] = &UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>>::`vftable';
      UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(&v333[1]);
    }
    else
    {
      v52 = GetLastError();
      v53 = CurrentIP();
      v54 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v12);
      v55 = (const char *)UnBCL::String::get_CString(v54);
      v56 = ConstructPartialMsgW(0x3000000u, "Did not find any files in %s", v55);
      WdsSetupLogMessageW(
        v56,
        819200,
        L"D",
        0,
        1698,
        L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
        L"CProcessDrivers::DoExecute",
        v53,
        v52,
        0,
        0);
    }
    if ( !v345
      || (v57 = (unsigned int (__fastcall ***)(_QWORD))(v345 + 8 + *(int *)(*(_QWORD *)(v345 + 8) + 12LL)), !(**v57)(v57)) )
    {
      v228 = GetLastError();
      v229 = CurrentIP();
      v230 = ConstructPartialMsgW(0x4000000u, "No drivers to process; leaving.");
      WdsSetupLogMessageW(
        v230,
        819200,
        L"D",
        0,
        1740,
        L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
        L"CProcessDrivers::DoExecute",
        v229,
        v228,
        0,
        0);
      v365 = v358;
      throw (`CProcessDrivers::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v365;
    }
    UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::~SmartPtr<UnBCL::Array<UnBCL::String *>>(v321);
    v4 = this;
  }
  v58 = (UnBCL::String *)(*(__int64 (__fastcall **)(struct IExecutionContext *))(*(_QWORD *)a2 + 8LL))(a2);
  v59 = UnBCL::String::get_CString(v58);
  v60 = (UnBCL::String *)(*(__int64 (__fastcall **)(struct IExecutionContext *))(*(_QWORD *)a2 + 24LL))(a2);
  v61 = UnBCL::String::get_CString(v60);
  v62 = DismInitialize(2, v61, v59);
  if ( v62 < 0 )
  {
    v225 = GetLastError();
    v226 = CurrentIP();
    v227 = ConstructPartialMsgW(0x2000000u, "Failed to initialize DISM. Error: 0x%08X", v62);
    WdsSetupLogMessageW(
      v227,
      819200,
      L"D",
      0,
      1749,
      L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
      L"CProcessDrivers::DoExecute",
      v226,
      v225,
      0,
      0);
    pExceptionObject = v358;
    throw (`CProcessDrivers::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&pExceptionObject;
  }
  v338 = 1;
  v63 = (char *)v4 + 240;
  *(_QWORD *)v336 = (char *)v4 + 240;
  if ( !UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v4 + 240) )
    goto LABEL_42;
  if ( *((_DWORD *)v4 + 86) == 2 )
  {
    v323[0] = 0;
    v64 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)v4 + 240);
    v65 = (unsigned int)UnBCL::String::get_CString(v64);
    CProcessDrivers::GetInboxDeviceClasses(v65, (unsigned int)v323, v66, v67, v311, v313, v314, v315, v317, v319, v320);
  }
  v68 = GetLastError();
  v69 = CurrentIP();
  v70 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v63);
  v71 = (const char *)UnBCL::String::get_CString(v70);
  v72 = ConstructPartialMsgW(0x4000000u, "Opening DISM session for SafeOS %s", v71);
  WdsSetupLogMessageW(
    v72,
    819200,
    L"D",
    0,
    1770,
    L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
    L"CProcessDrivers::DoExecute",
    v69,
    v68,
    0,
    0);
  v73 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v63);
  v74 = UnBCL::String::get_CString(v73);
  v75 = DismOpenSession(v74, 0, 0, &v326);
  v76 = v75;
  if ( v75 >= 0 )
    goto LABEL_42;
  if ( (v75 & 0x10000000) != 0 )
  {
    if ( RtlNtStatusToDosError(v75) != 317 )
    {
      v75 = RtlNtStatusToDosError(v76);
      goto LABEL_41;
    }
  }
  else
  {
    v77 = (v75 & 0x1FFF0000) == 458752;
    v75 = (unsigned __int16)v75;
    if ( v77 )
      goto LABEL_41;
  }
  v75 = v76;
LABEL_41:
  if ( v75 != 3 )
  {
    v231 = GetLastError();
    v232 = CurrentIP();
    v233 = ConstructPartialMsgW(0x2000000u, "Failed to open WinPE DISM session. Error: 0x%08X", v76);
    WdsSetupLogMessageW(
      v233,
      819200,
      L"D",
      0,
      1774,
      L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
      L"CProcessDrivers::DoExecute",
      v232,
      v231,
      0,
      0);
    v367 = v358;
    throw (`CProcessDrivers::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v367;
  }
LABEL_42:
  v78 = GetLastError();
  v79 = CurrentIP();
  v80 = (char *)this + 208;
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 208) )
  {
    v81 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v80);
    v82 = UnBCL::String::get_CString(v81);
  }
  else
  {
    v82 = L"Online";
  }
  v83 = ConstructPartialMsgW(0x4000000u, "Opening DISM session for the source system (%s)", (const char *)v82);
  WdsSetupLogMessageW(
    v83,
    819200,
    L"D",
    0,
    1779,
    L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
    L"CProcessDrivers::DoExecute",
    v79,
    v78,
    0,
    0);
  ParentPath = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v80);
  if ( ParentPath )
  {
    v85 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v80);
    ParentPath = UnBCL::Path::GetParentPath(v85);
  }
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v347, ParentPath);
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v347) )
  {
    v86 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v347);
    v87 = SPGetDirectoryPath(v86);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v327, v87);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v347, &v327);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(&v327);
  }
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v347) )
  {
    v88 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v347);
    v89 = UnBCL::String::get_CString(v88);
  }
  else
  {
    v89 = L"DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF845}";
  }
  v90 = DismOpenSession(v89, 0, 0, &v325);
  if ( v90 < 0 )
  {
    v234 = GetLastError();
    v235 = CurrentIP();
    v236 = ConstructPartialMsgW(0x2000000u, "Failed to open new session: (%s). Error: 0x%08X", (const char *)v89, v90);
    WdsSetupLogMessageW(
      v236,
      819200,
      L"D",
      0,
      1789,
      L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
      L"CProcessDrivers::DoExecute",
      v235,
      v234,
      0,
      0);
    v378[0] = v358;
    throw (`CProcessDrivers::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)v378;
  }
  v327 = &UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,unsigned long>>::`vftable';
  v328 = 0;
  v353 = &UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,unsigned long>>::`vftable';
  v354 = 0;
  *(_QWORD *)v336 = &UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,unsigned long>>::`vftable';
  v337 = 0;
  *(_QWORD *)&v333[1] = &UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,unsigned long>>::`vftable';
  v334 = 0;
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 280) )
  {
    v91 = (struct UnBCL::String *)UnBCL::Object::operator new(0xC0u);
    v323[0] = v91;
    if ( v91 )
      v92 = UnBCL::Hashtable<UnBCL::String *,unsigned long>::Hashtable<UnBCL::String *,unsigned long>(v91);
    else
      v92 = 0;
    UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,unsigned long>>::SmartPtr<UnBCL::Hashtable<UnBCL::String *,unsigned long>>(
      v321,
      v92);
    UnBCL::SmartPtr<UnBCL::ArrayList<CRegCreationData *>>::operator=(&v327, v321);
    v321[0] = &UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,unsigned long>>::`vftable';
    UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(v321);
    v93 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)this + 280);
    v94 = UnBCL::String::get_CString(v93);
    CProcessDrivers::ReadFileInTable(v94, v328);
  }
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 296) )
  {
    v95 = (struct UnBCL::String *)UnBCL::Object::operator new(0xC0u);
    v323[0] = v95;
    if ( v95 )
      v96 = UnBCL::Hashtable<UnBCL::String *,unsigned long>::Hashtable<UnBCL::String *,unsigned long>(v95);
    else
      v96 = 0;
    UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,unsigned long>>::SmartPtr<UnBCL::Hashtable<UnBCL::String *,unsigned long>>(
      v321,
      v96);
    UnBCL::SmartPtr<UnBCL::ArrayList<CRegCreationData *>>::operator=(&v353, v321);
    v321[0] = &UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,unsigned long>>::`vftable';
    UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(v321);
    v97 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)this + 296);
    v98 = UnBCL::String::get_CString(v97);
    CProcessDrivers::ReadFileInTable(v98, v354);
  }
  if ( v326 )
  {
    if ( UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 312) )
    {
      v99 = (struct UnBCL::String *)UnBCL::Object::operator new(0xC0u);
      v323[0] = v99;
      if ( v99 )
        v100 = UnBCL::Hashtable<UnBCL::String *,unsigned long>::Hashtable<UnBCL::String *,unsigned long>(v99);
      else
        v100 = 0;
      UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,unsigned long>>::SmartPtr<UnBCL::Hashtable<UnBCL::String *,unsigned long>>(
        v321,
        v100);
      UnBCL::SmartPtr<UnBCL::ArrayList<CRegCreationData *>>::operator=(v336, v321);
      v321[0] = &UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,unsigned long>>::`vftable';
      UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(v321);
      v101 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)this + 312);
      v102 = UnBCL::String::get_CString(v101);
      CProcessDrivers::ReadFileInTable(v102, v337);
    }
    if ( UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 328) )
    {
      v103 = (struct UnBCL::String *)UnBCL::Object::operator new(0xC0u);
      v323[0] = v103;
      if ( v103 )
        v104 = UnBCL::Hashtable<UnBCL::String *,unsigned long>::Hashtable<UnBCL::String *,unsigned long>(v103);
      else
        v104 = 0;
      UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,unsigned long>>::SmartPtr<UnBCL::Hashtable<UnBCL::String *,unsigned long>>(
        v321,
        v104);
      UnBCL::SmartPtr<UnBCL::ArrayList<CRegCreationData *>>::operator=(&v333[1], v321);
      v321[0] = &UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,unsigned long>>::`vftable';
      UnBCL::SmartPtr<UnBCL::Hashtable<unsigned long,IVdsVDisk *>>::DeAssign(v321);
      v105 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)this + 328);
      v106 = UnBCL::String::get_CString(v105);
      CProcessDrivers::ReadFileInTable(v106, v334);
    }
  }
  if ( *((_DWORD *)this + 86) == 1 )
  {
    Drivers = _DismGetDriversEx(v325, 0, &off_180829128, 1, &v342, &v332);
    if ( Drivers == -2147024846 )
    {
      v108 = GetLastError();
      v109 = CurrentIP();
      v110 = ConstructPartialMsgW(
               0x3000000u,
               "Getting driver package properties is not supported; falling back to DismGetDrivers");
      WdsSetupLogMessageW(
        v110,
        819200,
        L"D",
        0,
        1836,
        L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
        L"CProcessDrivers::DoExecute",
        v109,
        v108,
        0,
        0);
      v342 = 0;
      Drivers = DismGetDrivers(v325, 0, &v339, &v332);
    }
    if ( Drivers < 0 )
    {
      v237 = GetLastError();
      v238 = CurrentIP();
      v239 = ConstructPartialMsgW(
               0x2000000u,
               "Failed to get driver packages from the online system. Error: 0x%08X",
               Drivers);
      WdsSetupLogMessageW(
        v239,
        819200,
        L"D",
        0,
        1843,
        L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
        L"CProcessDrivers::DoExecute",
        v238,
        v237,
        0,
        0);
      v374 = v358;
      throw (`CProcessDrivers::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v374;
    }
  }
  *((_DWORD *)this + 90) = 1;
  v330[1] = 0;
  v330[0] = &RAII::CAutoRelease<ISetupOneSettings *>::`vftable';
  v111 = (struct ISetupOneSettings **)RAII::CAutoCleanupBase<VdsVolumePathEnumerator *>::operator&(v330);
  SetupOneSettings = CreateSetupOneSettings(v113, v112, v111);
  if ( SetupOneSettings < 0 )
  {
    v115 = GetLastError();
    v116 = CurrentIP();
    v117 = ConstructPartialMsgW(0x3000000u, "CreateSetupOneSettings failed. Error: 0x%08X", SetupOneSettings);
    WdsSetupLogMessageW(
      v117,
      819200,
      L"D",
      0,
      1856,
      L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
      L"CProcessDrivers::DoExecute",
      v116,
      v115,
      0,
      0);
    (*(void (__fastcall **)(_QWORD *, _QWORD))(v330[0] + 48LL))(v330, 0);
  }
  v323[0] = 0;
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, struct UnBCL::String **))(v330[0] + 64LL))(v330, v323) )
  {
    v118 = (void (__fastcall ***)(_QWORD, const wchar_t *, char *))(*(__int64 (__fastcall **)(_QWORD *))(v330[0] + 24LL))(v330);
    (**v118)(v118, L"EnableDriverMigration", (char *)this + 360);
    v119 = GetLastError();
    v120 = CurrentIP();
    v121 = ConstructPartialMsgW(
             0x4000000u,
             "Result of onesetting query to enable driver triggered extra WinRE driver migration phase: %d",
             *((_DWORD *)this + 90));
    WdsSetupLogMessageW(
      v121,
      819200,
      L"D",
      0,
      1866,
      L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
      L"CProcessDrivers::DoExecute",
      v120,
      v119,
      0,
      0);
  }
  v324 = 0;
  v122 = (struct UnBCL::String *)UnBCL::Object::operator new(0x80u);
  v323[0] = v122;
  if ( v122 )
    v123 = UnBCL::ArrayList<UnBCL::DictionaryEntry<CGlobalPath *,CDriverInstallInfo *> *>::ArrayList<UnBCL::DictionaryEntry<CGlobalPath *,CDriverInstallInfo *> *>(v122);
  else
    v123 = 0;
  UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<CGlobalPath *,CDriverInstallInfo *> *>>::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<CGlobalPath *,CDriverInstallInfo *> *>>(
    v349,
    v123);
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v350 + 40LL))(v350, 1);
  v124 = (struct UnBCL::String *)UnBCL::Object::operator new(0x18u);
  v125 = v124;
  v323[0] = v124;
  if ( v124 )
  {
    UnBCL::String::String(v124);
    *(_QWORD *)v125 = &UnBCL::String::`local vftable';
  }
  else
  {
    v125 = 0;
  }
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v331, v125);
  v126 = (struct UnBCL::String *)UnBCL::Object::operator new(0x18u);
  v127 = v126;
  v323[0] = v126;
  if ( v126 )
  {
    UnBCL::String::String(v126);
    *(_QWORD *)v127 = &UnBCL::String::`local vftable';
  }
  else
  {
    v127 = 0;
  }
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v364, v127);
  v128 = (struct UnBCL::String *)UnBCL::Object::operator new(0x18u);
  v129 = v128;
  v323[0] = v128;
  if ( v128 )
  {
    UnBCL::String::String(v128);
    *(_QWORD *)v129 = &UnBCL::String::`local vftable';
  }
  else
  {
    v129 = 0;
  }
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v361, v129);
  for ( j = 0; ; ++j )
  {
    if ( j >= v332 )
    {
      v150 = (struct UnBCL::String *)UnBCL::Object::operator new(0x80u);
      v323[0] = v150;
      if ( v150 )
        v151 = UnBCL::ArrayList<UnBCL::DictionaryEntry<CGlobalPath *,CDriverInstallInfo *> *>::ArrayList<UnBCL::DictionaryEntry<CGlobalPath *,CDriverInstallInfo *> *>(v150);
      else
        v151 = 0;
      UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<CGlobalPath *,CDriverInstallInfo *> *>>::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<CGlobalPath *,CDriverInstallInfo *> *>>(
        v355,
        v151);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v356 + 40LL))(v356, 1);
      v152 = (struct UnBCL::String *)UnBCL::Object::operator new(0x18u);
      v153 = v152;
      v323[0] = v152;
      if ( v152 )
      {
        UnBCL::String::String(v152);
        *(_QWORD *)v153 = &UnBCL::String::`local vftable';
      }
      else
      {
        v153 = 0;
      }
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v363, v153);
      v154 = (struct UnBCL::String *)UnBCL::Object::operator new(0x18u);
      v155 = v154;
      v323[0] = v154;
      if ( v154 )
      {
        UnBCL::String::String(v154);
        *(_QWORD *)v155 = &UnBCL::String::`local vftable';
      }
      else
      {
        v155 = 0;
      }
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v360, v155);
      v156 = (struct UnBCL::String *)UnBCL::Object::operator new(0x18u);
      v157 = v156;
      v323[0] = v156;
      if ( v156 )
      {
        UnBCL::String::String(v156);
        *(_QWORD *)v157 = &UnBCL::String::`local vftable';
      }
      else
      {
        v157 = 0;
      }
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v359, v157);
      v159 = 0;
      v160 = (int)this;
      while ( 2 )
      {
        v161 = v345;
        if ( !v345
          || (v162 = (unsigned int (__fastcall ***)(_QWORD))(v345 + *(int *)(*(_QWORD *)(v345 + 8) + 12LL) + 8LL),
              v159 >= (**v162)(v162)) )
        {
          if ( *((_DWORD *)this + 86) != 1 )
            goto LABEL_204;
          v196 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v341, L"PnpPropMig.dll");
          v197 = (const struct UnBCL::String *)(**(__int64 (__fastcall ***)(struct IExecutionContext *))a2)(a2);
          v198 = UnBCL::Path::Combine(v197, v196);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v321, v198);
          UnBCL::String::~String((UnBCL::String *)v341);
          v199 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v321);
          v200 = UnBCL::String::get_CString(v199);
          if ( (unsigned int)FileExists(v200) )
          {
            v201 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v321);
            v202 = UnBCL::String::get_CString(v201);
            Library = LoadLibraryExW(v202, 0, 0);
            v348 = Library;
            if ( !Library )
            {
              v249 = GetLastError();
              v250 = v249 < 0;
              if ( v249 > 0 )
                v250 = 1;
              if ( v250 )
              {
                v251 = GetLastError();
                v252 = v251;
                if ( v251 > 0 )
                  v252 = (unsigned __int16)v251 | 0x80070000;
              }
              else
              {
                v252 = -2147467259;
              }
              v253 = GetLastError();
              v254 = CurrentIP();
              v255 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v321);
              v256 = (const char *)UnBCL::String::get_CString(v255);
              v257 = ConstructPartialMsgW(
                       0x2000000u,
                       "%hs: Failed to load module %s. Error: 0x%08X",
                       "CProcessDrivers::DoExecute",
                       v256,
                       v252);
              WdsSetupLogMessageW(
                v257,
                819200,
                L"D",
                0,
                2069,
                L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
                L"CProcessDrivers::DoExecute",
                v254,
                v253,
                0,
                0);
              v368 = v358;
              throw (`CProcessDrivers::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v368;
            }
            ProcAddress = GetProcAddress(Library, "PnpPropMigGatherW");
            if ( !ProcAddress )
            {
              v258 = GetLastError();
              v259 = v258 < 0;
              if ( v258 > 0 )
                v259 = 1;
              if ( v259 )
              {
                v260 = GetLastError();
                v261 = v260;
                if ( v260 > 0 )
                  v261 = (unsigned __int16)v260 | 0x80070000;
              }
              else
              {
                v261 = -2147467259;
              }
              v262 = GetLastError();
              v263 = CurrentIP();
              v264 = ConstructPartialMsgW(
                       0x2000000u,
                       "%hs: GetProcAddress failed. Error: 0x%08X",
                       "CProcessDrivers::DoExecute",
                       v261);
              WdsSetupLogMessageW(
                v264,
                819200,
                L"D",
                0,
                2077,
                L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
                L"CProcessDrivers::DoExecute",
                v263,
                v262,
                0,
                0);
              v369 = v358;
              throw (`CProcessDrivers::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v369;
            }
            v205 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v346, L"drvstore.props.dat");
            v206 = (const struct UnBCL::String *)(**(__int64 (__fastcall ***)(struct IExecutionContext *))a2)(a2);
            v207 = UnBCL::Path::Combine(v206, v205);
            UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v340, v207);
            UnBCL::String::~String((UnBCL::String *)v346);
            v208 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v340);
            v209 = UnBCL::String::get_CString(v208);
            if ( UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 208) )
            {
              v210 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)this + 208);
              v211 = UnBCL::String::get_CString(v210);
            }
            else
            {
              v211 = 0;
            }
            if ( !((unsigned int (__fastcall *)(const unsigned __int16 *, const unsigned __int16 *))ProcAddress)(
                    v211,
                    v209) )
            {
              v212 = GetLastError();
              v213 = v212 < 0;
              if ( v212 > 0 )
                v213 = 1;
              if ( v213 )
              {
                v214 = GetLastError();
                v215 = v214;
                if ( v214 > 0 )
                  v215 = (unsigned __int16)v214 | 0x80070000;
                if ( v215 == -2147024846 )
                {
                  v216 = GetLastError();
                  v217 = CurrentIP();
                  v218 = ConstructPartialMsgW(
                           0x3000000u,
                           "%hs: PnpPropMigGatherW is not supported; skipping.",
                           "CProcessDrivers::DoExecute");
                  WdsSetupLogMessageW(
                    v218,
                    819200,
                    L"D",
                    0,
                    2087,
                    L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
                    L"CProcessDrivers::DoExecute",
                    v217,
                    v216,
                    0,
                    0);
                  goto LABEL_167;
                }
              }
              else
              {
                v215 = -2147467259;
              }
              v219 = GetLastError();
              v220 = CurrentIP();
              v221 = ConstructPartialMsgW(
                       0x2000000u,
                       "%hs: PnpPropMigGatherW failed. Error: 0x%08X",
                       "CProcessDrivers::DoExecute",
                       v215);
              WdsSetupLogMessageW(
                v221,
                819200,
                L"D",
                0,
                2092,
                L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
                L"CProcessDrivers::DoExecute",
                v220,
                v219,
                0,
                0);
              if ( *((_DWORD *)this + 89) )
              {
                v222 = GetLastError();
                v223 = CurrentIP();
                v224 = ConstructPartialMsgW(0x4000000u, "Ignoring error due to operation configuration.");
                WdsSetupLogMessageW(
                  v224,
                  819200,
                  L"D",
                  0,
                  2095,
                  L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
                  L"CProcessDrivers::DoExecute",
                  v223,
                  v222,
                  0,
                  0);
              }
              else if ( v215 < 0 )
              {
                v370 = v358;
                throw (`CProcessDrivers::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v370;
              }
            }
LABEL_167:
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v340);
          }
          else
          {
            v265 = GetLastError();
            v266 = CurrentIP();
            v267 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v321);
            v268 = (const char *)UnBCL::String::get_CString(v267);
            v269 = ConstructPartialMsgW(
                     0x3000000u,
                     "%hs: Module %s not available; skipping.",
                     "CProcessDrivers::DoExecute",
                     v268);
            WdsSetupLogMessageW(
              v269,
              819200,
              L"D",
              0,
              2107,
              L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
              L"CProcessDrivers::DoExecute",
              v266,
              v265,
              0,
              0);
          }
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v321);
          if ( *((_DWORD *)this + 86) == 1 )
          {
            v270 = RAII::CAutoCleanupBase<void *>::operator->(v349);
            v271 = (int (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v270 + 8) + 12LL) + v270 + 8);
            if ( (**v271)(v271) > 0 )
            {
              v272 = (const struct UnBCL::String *)UnBCL::String::String(
                                                     (UnBCL::String *)v346,
                                                     L"SetupPlatform.Drivers.ini");
              v273 = (const struct UnBCL::String *)(**(__int64 (__fastcall ***)(struct IExecutionContext *))a2)(a2);
              v274 = UnBCL::Path::Combine(v273, v272);
              UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v341, v274);
              UnBCL::String::~String((UnBCL::String *)v346);
              v275 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v341);
              UnBCL::String::get_CString(v275);
              v276 = RAII::CAutoCleanupBase<void *>::operator->(v349);
              SPWriteDriversList(v276, v277, 0);
              UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v341);
            }
            v278 = v343;
            if ( v343 )
            {
              v279 = *(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, const unsigned __int16 *))(*(_QWORD *)v343 + 16LL);
              v280 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v331);
              v281 = UnBCL::String::get_CString(v280);
              v279(v278, L"SP_DRIVER_INFO", L"DriverSafeOSMigratedList", v281);
              v282 = *(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, const unsigned __int16 *))(*(_QWORD *)v278 + 16LL);
              v283 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v364);
              v284 = UnBCL::String::get_CString(v283);
              v282(v278, L"SP_DRIVER_INFO", L"DriverSafeOSMigrateFailedList", v284);
              v285 = *(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, const unsigned __int16 *))(*(_QWORD *)v278 + 16LL);
              v286 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v361);
              v287 = UnBCL::String::get_CString(v286);
              v285(v278, L"SP_DRIVER_INFO", L"DriverSafeOSMigrateFailureIgnoredList", v287);
            }
          }
          else
          {
LABEL_204:
            v278 = v343;
          }
          if ( *((_DWORD *)this + 86) == 2 )
          {
            v288 = RAII::CAutoCleanupBase<void *>::operator->(v355);
            v289 = (int (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v288 + 8) + 12LL) + v288 + 8);
            if ( (**v289)(v289) > 0 )
            {
              v290 = (const struct UnBCL::String *)UnBCL::String::String(
                                                     (UnBCL::String *)v346,
                                                     L"SetupPlatform.Drivers.External.ini");
              v291 = (const struct UnBCL::String *)(**(__int64 (__fastcall ***)(struct IExecutionContext *))a2)(a2);
              v292 = UnBCL::Path::Combine(v291, v290);
              UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v341, v292);
              UnBCL::String::~String((UnBCL::String *)v346);
              v293 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v341);
              UnBCL::String::get_CString(v293);
              v294 = RAII::CAutoCleanupBase<void *>::operator->(v355);
              SPWriteDriversList(v294, v295, 0);
              UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v341);
            }
            if ( v278 )
            {
              v296 = *(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, const unsigned __int16 *))(*(_QWORD *)v278 + 16LL);
              v297 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v363);
              v298 = UnBCL::String::get_CString(v297);
              v296(v278, L"SP_DRIVER_INFO", L"DriverSafeOSInstalledList", v298);
              v299 = *(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, const unsigned __int16 *))(*(_QWORD *)v278 + 16LL);
              v300 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v360);
              v301 = UnBCL::String::get_CString(v300);
              v299(v278, L"SP_DRIVER_INFO", L"DriverSafeOSInstallFailedList", v301);
              v302 = *(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, const unsigned __int16 *))(*(_QWORD *)v278 + 16LL);
              v303 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v359);
              v304 = UnBCL::String::get_CString(v303);
              v302(v278, L"SP_DRIVER_INFO", L"DriverSafeOSInstallFailureIgnoredList", v304);
            }
          }
          if ( (unsigned __int8)UnBCL::operator!=((char *)this + 240, v158) && v333[0] )
          {
            v305 = *(_QWORD *)a2;
            v306 = (struct UnBCL::String *)UnBCL::Object::operator new(0x40u);
            v323[0] = v306;
            if ( v306 )
              v307 = CBool::CBool(v306, 1);
            else
              v307 = 0;
            v308 = *(void (__fastcall **)(struct IExecutionContext *, __int64, char *))(v305 + 96);
            if ( v307 )
              v309 = (char *)v307 + *(int *)(*((_QWORD *)v307 + 1) + 8LL) + 8;
            else
              v309 = 0;
            v310 = UnBCL::String::String((UnBCL::String *)v341, L"WinREMigrateDrivers");
            v308(a2, v310, v309);
            UnBCL::String::~String((UnBCL::String *)v341);
          }
          if ( v339 )
          {
            DismDelete();
            v339 = 0;
          }
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v359);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v360);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v363);
          UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<CGlobalPath *,CDriverInstallInfo *> *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<CGlobalPath *,CDriverInstallInfo *> *>>(v355);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v361);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v364);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v331);
          UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<CGlobalPath *,CDriverInstallInfo *> *>>::~SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<CGlobalPath *,CDriverInstallInfo *> *>>(v349);
          RAII::CAutoRelease<ISetupOneSettings *>::~CAutoRelease<ISetupOneSettings *>(v330);
          UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,unsigned long>>::~SmartPtr<UnBCL::Hashtable<UnBCL::String *,unsigned long>>(&v333[1]);
          UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,unsigned long>>::~SmartPtr<UnBCL::Hashtable<UnBCL::String *,unsigned long>>(v336);
          UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,unsigned long>>::~SmartPtr<UnBCL::Hashtable<UnBCL::String *,unsigned long>>(&v353);
          UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,unsigned long>>::~SmartPtr<UnBCL::Hashtable<UnBCL::String *,unsigned long>>(&v327);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v347);
          v375 = v358;
          throw (`CProcessDrivers::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v375;
        }
        if ( (unsigned int)SPIsEventSet(a3) )
        {
          v372 = v358;
          throw (`CProcessDrivers::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v372;
        }
        v163 = v161 + *(int *)(*(_QWORD *)(v161 + 8) + 16LL) + 8LL;
        v164 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v163 + 24LL))(v163, v159);
        v165 = (UnBCL::String *)(**(__int64 (__fastcall ***)(_QWORD))*v164)(*v164);
        v166 = (const char *)UnBCL::String::get_CString(v165);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v321);
        v167 = v161 + *(int *)(*(_QWORD *)(v161 + 8) + 16LL) + 8LL;
        v168 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v167 + 24LL))(v167, v159);
        if ( (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v168 + 16LL))(*v168) )
        {
          v169 = (struct UnBCL::String *)UnBCL::Object::operator new(0x18u);
          v323[0] = v169;
          if ( v169 )
          {
            v170 = v161 + *(int *)(*(_QWORD *)(v161 + 8) + 16LL) + 8LL;
            v171 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v170 + 24LL))(v170, v159);
            v172 = (UnBCL::String *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v171 + 16LL))(*v171);
            v173 = UnBCL::String::get_CString(v172);
            UnBCL::String::String(v169, v173);
            *(_QWORD *)v169 = &UnBCL::String::`local vftable';
          }
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v357, v169);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v321, v357);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v357);
        }
        v174 = (unsigned int)v326;
        if ( !v326 )
          v174 = v325;
        DriverInfo = DismGetDriverInfo(v174, v166, &v329, &v322, &v335);
        if ( DriverInfo < 0 )
        {
          v176 = GetLastError();
          v177 = CurrentIP();
          v178 = ConstructPartialMsgW(
                   0x2000000u,
                   "Failed to get driver info from external driver package %s. Error: 0x%08X",
                   v166,
                   DriverInfo);
          WdsSetupLogMessageW(
            v178,
            819200,
            L"D",
            0,
            1993,
            L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
            L"CProcessDrivers::DoExecute",
            v177,
            v176,
            0,
            0);
          v179 = v343;
          if ( v343 )
          {
            (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, const char *))(*(_QWORD *)v343 + 16LL))(
              v343,
              L"SP_DRIVER_INFO",
              L"DriverInfGetInfoFailedPath",
              v166);
            (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, _QWORD))(*(_QWORD *)v179 + 24LL))(
              v179,
              L"SP_DRIVER_INFO",
              L"DriverInfGetInfoFailedHR",
              (unsigned int)DriverInfo);
          }
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v321);
          v160 = (int)this;
LABEL_151:
          ++v159;
          continue;
        }
        break;
      }
      v180 = v335;
      v324 = 0;
      v181 = UnBCL::SmartPtr<UnBCL::String>::get_P(v321);
      v182 = CProcessDrivers::ProcessDriverInstallation(
               v160,
               v180,
               v329,
               v322,
               (__int64)a2,
               v326,
               v352,
               v356,
               (__int64)v333,
               v181,
               (__int64)&v324);
      switch ( v324 )
      {
        case 1:
          v192 = *(const unsigned __int16 **)(v180 + 8);
          v193 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v363);
          v194 = UnBCL::String::get_CString(v193);
          v195 = UnBCL::String::Concat(v194, L";NEW;", v192);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v340, v195);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v363, v340);
          v187 = v340;
          break;
        case 2:
          v188 = *(const unsigned __int16 **)(v180 + 8);
          v189 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v360);
          v190 = UnBCL::String::get_CString(v189);
          v191 = UnBCL::String::Concat(v190, L";NEW;", v188);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v341, v191);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v360, v341);
          v187 = v341;
          break;
        case 3:
          v183 = *(const unsigned __int16 **)(v180 + 8);
          v184 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v359);
          v185 = UnBCL::String::get_CString(v184);
          v186 = UnBCL::String::Concat(v185, L";NEW;", v183);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v346, v186);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v359, v346);
          v187 = v346;
          break;
        default:
LABEL_145:
          if ( v182 < 0 )
          {
            v246 = GetLastError();
            v247 = CurrentIP();
            v248 = ConstructPartialMsgW(
                     0x2000000u,
                     "Failed to process installation of driver package %s. Error: 0x%08X",
                     v166,
                     v182);
            WdsSetupLogMessageW(
              v248,
              819200,
              L"D",
              0,
              2034,
              L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
              L"CProcessDrivers::DoExecute",
              v247,
              v246,
              0,
              0);
            v371 = v358;
            throw (`CProcessDrivers::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v371;
          }
          if ( v329 )
          {
            DismDelete();
            v329 = 0;
            v322 = 0;
          }
          if ( v335 )
          {
            DismDelete();
            v335 = 0;
          }
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v321);
          goto LABEL_151;
      }
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v187);
      goto LABEL_145;
    }
    if ( (unsigned int)SPIsEventSet(a3) )
    {
      v377 = v358;
      throw (`CProcessDrivers::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v377;
    }
    if ( v342 )
    {
      v131 = v342 + 114LL * j;
      v132 = *(_WORD *)(v131 + 100);
      v133 = *(_QWORD *)(v131 + 106);
      v134 = *(_DWORD *)(v131 + 102);
    }
    else
    {
      v132 = -1;
      v133 = 0;
      v134 = 0;
      v131 = v339 + 100LL * j;
    }
    v135 = DismGetDriverInfo(v325, *(_QWORD *)(v131 + 8), &v329, &v322, 0);
    if ( v135 < 0 )
    {
      v240 = GetLastError();
      v241 = CurrentIP();
      v242 = ConstructPartialMsgW(
               0x2000000u,
               "Failed to get driver info from driver package %s. Error: 0x%08X",
               *(const char **)(v131 + 8),
               v135);
      WdsSetupLogMessageW(
        v242,
        819200,
        L"D",
        0,
        1905,
        L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
        L"CProcessDrivers::DoExecute",
        v241,
        v240,
        0,
        0);
      v376 = v358;
      throw (`CProcessDrivers::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v376;
    }
    v324 = 0;
    v136 = CProcessDrivers::ProcessDriverMigration(
             this,
             (struct _DismDriverPackage *)v131,
             (__int64)a2,
             v326,
             v328,
             v354,
             v337,
             v334,
             v350,
             (__int64)v333,
             v132,
             v133,
             v134,
             (__int64)&v324);
    switch ( v324 )
    {
      case 1:
        v146 = *(const unsigned __int16 **)(v131 + 8);
        v147 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v331);
        v148 = UnBCL::String::get_CString(v147);
        v149 = UnBCL::String::Concat(v148, L";NEW;", v146);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v357, v149);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v331, v357);
        v141 = (struct UnBCL::String **)v357;
        break;
      case 2:
        v142 = *(const unsigned __int16 **)(v131 + 8);
        v143 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v364);
        v144 = UnBCL::String::get_CString(v143);
        v145 = UnBCL::String::Concat(v144, L";NEW;", v142);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v323, v145);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v364, v323);
        v141 = v323;
        break;
      case 3:
        v137 = *(const unsigned __int16 **)(v131 + 8);
        v138 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v361);
        v139 = UnBCL::String::get_CString(v138);
        v140 = UnBCL::String::Concat(v139, L";NEW;", v137);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v321, v140);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v361, v321);
        v141 = (struct UnBCL::String **)v321;
        break;
      default:
        goto LABEL_108;
    }
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v141);
LABEL_108:
    if ( v136 < 0 )
    {
      v243 = GetLastError();
      v244 = CurrentIP();
      v245 = ConstructPartialMsgW(
               0x2000000u,
               "Failed to process migration of driver package %s. Error: 0x%08X",
               *(const char **)(v131 + 8),
               v136);
      WdsSetupLogMessageW(
        v245,
        819200,
        L"D",
        0,
        1942,
        L"base\\ntsetup\\setupplatform\\lib\\src\\drivermigration.cpp",
        L"CProcessDrivers::DoExecute",
        v244,
        v243,
        0,
        0);
      v373 = v358;
      throw (`CProcessDrivers::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v373;
    }
    if ( v329 )
    {
      DismDelete();
      v329 = 0;
      v322 = 0;
    }
  }
}

```

## disassembly

```asm
0x1801ab850  mov     rax, rsp
0x1801ab853  mov     [rax+18h], r8
0x1801ab857  mov     [rax+10h], rdx
0x1801ab85b  mov     [rax+8], rcx
0x1801ab85f  push    rbx
0x1801ab860  push    rsi
0x1801ab861  push    rdi
0x1801ab862  push    r12
0x1801ab864  push    r13
0x1801ab866  push    r14
0x1801ab868  push    r15
0x1801ab86a  sub     rsp, 370h
0x1801ab871  mov     qword ptr [rax-50h], 0FFFFFFFFFFFFFFFEh
0x1801ab879  mov     rdi, rcx
0x1801ab87c  xor     ebx, ebx
0x1801ab87e  mov     [rsp+3A8h+var_328], ebx
0x1801ab885  mov     rax, [rdx]
0x1801ab888  mov     rcx, rdx
0x1801ab88b  mov     rax, [rax+40h]
0x1801ab88f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ab894  mov     [rsp+3A8h+var_220], rax
0x1801ab89c  mov     [rsp+3A8h+var_280], ebx
0x1801ab8a3  mov     [rsp+3A8h+var_2F0], ebx
0x1801ab8aa  mov     dword ptr [rsp+3A8h+var_2F8+4], ebx
0x1801ab8b1  lea     r13, ??_7?$SmartPtr@V?$Hashtable@PEAVString@UnBCL@@H@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::Hashtable<UnBCL::String *,int>>::`vftable'
0x1801ab8b8  mov     [rsp+3A8h+var_1C8], r13
0x1801ab8c0  mov     [rsp+3A8h+var_1C0], rbx
0x1801ab8c8  mov     [rsp+3A8h+var_278], rbx
0x1801ab8d0  mov     [rsp+3A8h+var_228], rbx
0x1801ab8d8  mov     [rsp+3A8h+var_2B0], ebx
0x1801ab8df  mov     [rsp+3A8h+var_2D8], rbx
0x1801ab8e7  mov     [rsp+3A8h+var_310], ebx
0x1801ab8ee  lea     r12, ??_7?$SmartPtr@V?$ArrayList@PEAV?$DictionaryEntry@PEAVString@UnBCL@@PEAV12@@UnBCL@@@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>>::`vftable'
0x1801ab8f5  mov     [rsp+3A8h+var_218], r12
0x1801ab8fd  mov     [rsp+3A8h+var_210], rbx
0x1801ab905  mov     [rsp+3A8h+var_298], rbx
0x1801ab90d  lea     rcx, [rsp+3A8h+var_48]
0x1801ab915  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x1801ab91b  nop
0x1801ab91c  lea     rcx, [rsp+3A8h+var_118]
0x1801ab924  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x1801ab92a  nop
0x1801ab92b  mov     dword ptr [rsp+3A8h+var_2AC], ebx
0x1801ab932  mov     [rsp+3A8h+var_1E0], rbx
0x1801ab93a  mov     [rsp+3A8h+var_324], ebx
0x1801ab941  lea     rcx, [rsp+3A8h+var_180]
0x1801ab949  call    cs:__imp_??0Exception@UnBCL@@QEAA@XZ; UnBCL::Exception::Exception(void)
0x1801ab94f  lea     rax, ??_7CXXXXXHandledException@?2??DoExecute@CProcessDrivers@@UEAAJPEAUIExecutionContext@@PEAXPEAUIInternalOperationsProgress@@@Z@6B@; const `CProcessDrivers::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException::`vftable'
0x1801ab956  mov     [rsp+3A8h+var_180], rax
0x1801ab95e  cmp     dword ptr [rdi+158h], 1
0x1801ab965  jnz     loc_1801ABB58
0x1801ab96b  lea     rcx, [rdi+0D0h]
0x1801ab972  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1801ab978  test    rax, rax
0x1801ab97b  jnz     loc_1801ABB58
0x1801ab981  mov     [rsp+3A8h+var_290], ebx
0x1801ab988  mov     [rsp+3A8h+var_308], rbx
0x1801ab990  call    cs:__imp_GetLastError
0x1801ab996  mov     edi, eax
0x1801ab998  call    cs:__imp_CurrentIP
0x1801ab99e  mov     rbx, rax
0x1801ab9a1  lea     rdx, aAttemptingToRe_0; "Attempting to remove unused drivers"
0x1801ab9a8  mov     ecx, 4000000h; unsigned int
0x1801ab9ad  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801ab9b2  mov     dword ptr [rsp+3A8h+var_358], 0
0x1801ab9ba  mov     [rsp+3A8h+var_360], 0
0x1801ab9c3  mov     dword ptr [rsp+3A8h+var_368], edi
0x1801ab9c7  mov     [rsp+3A8h+var_370], rbx
0x1801ab9cc  lea     rsi, aCprocessdriver_7; "CProcessDrivers::DoExecute"
0x1801ab9d3  mov     [rsp+3A8h+var_378], rsi
0x1801ab9d8  lea     rbx, aBaseNtsetupSet_14; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1801ab9df  mov     qword ptr [rsp+3A8h+var_380], rbx
0x1801ab9e4  mov     dword ptr [rsp+3A8h+var_388], 695h
0x1801ab9ec  xor     r9d, r9d
0x1801ab9ef  lea     r15, aD_0; "D"
0x1801ab9f6  mov     r8, r15
0x1801ab9f9  mov     r14d, 0C8000h
0x1801ab9ff  mov     edx, r14d
0x1801aba02  mov     rcx, rax
0x1801aba05  call    cs:__imp_WdsSetupLogMessageW
0x1801aba0b  lea     r9, [rsp+3A8h+var_308]; unsigned __int64 *
0x1801aba13  lea     r8, [rsp+3A8h+var_290]; unsigned int *
0x1801aba1b  mov     rdx, [rsp+3A8h+arg_10]; void *
0x1801aba23  call    ?CleanupDrivers@CProcessDrivers@@IEAAHPEAXAEAKAEA_K@Z; CProcessDrivers::CleanupDrivers(void *,ulong &,unsigned __int64 &)
0x1801aba28  xor     ebx, ebx
0x1801aba2a  test    eax, eax
0x1801aba2c  jz      short loc_1801ABAA7
0x1801aba2e  call    cs:__imp_GetLastError
0x1801aba34  mov     edi, eax
0x1801aba36  call    cs:__imp_CurrentIP
0x1801aba3c  mov     rbx, rax
0x1801aba3f  mov     r9, [rsp+3A8h+var_308]
0x1801aba47  mov     r8d, [rsp+3A8h+var_290]
0x1801aba4f  lea     rdx, aRemovedDrivers; "Removed drivers: Count: %u, Size: %I64u"
0x1801aba56  mov     ecx, 4000000h; unsigned int
0x1801aba5b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801aba60  mov     dword ptr [rsp+3A8h+var_358], 0
0x1801aba68  mov     [rsp+3A8h+var_360], 0
0x1801aba71  mov     dword ptr [rsp+3A8h+var_368], edi
0x1801aba75  mov     [rsp+3A8h+var_370], rbx
0x1801aba7a  mov     [rsp+3A8h+var_378], rsi
0x1801aba7f  lea     rcx, aBaseNtsetupSet_14; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1801aba86  mov     qword ptr [rsp+3A8h+var_380], rcx
0x1801aba8b  mov     dword ptr [rsp+3A8h+var_388], 698h
0x1801aba93  xor     r9d, r9d
0x1801aba96  mov     r8, r15
0x1801aba99  mov     edx, r14d
0x1801aba9c  mov     rcx, rax
0x1801aba9f  call    cs:__imp_WdsSetupLogMessageW
0x1801abaa5  xor     ebx, ebx
0x1801abaa7  mov     rdi, [rsp+3A8h+arg_0]
0x1801abaaf  cmp     dword ptr [rdi+158h], 2
0x1801abab6  jnz     loc_1801ABFD2
0x1801ababc  lea     r15, [rdi+0E0h]
0x1801abac3  mov     rcx, r15
0x1801abac6  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1801abacc  mov     edi, 1
0x1801abad1  mov     r8d, edi
0x1801abad4  xor     edx, edx
0x1801abad6  mov     rcx, rax
0x1801abad9  call    cs:__imp_?GetFiles@Directory@UnBCL@@SAPEAV?$Array@PEAVString@UnBCL@@@2@PEBVString@2@0H@Z; UnBCL::Directory::GetFiles(UnBCL::String const *,UnBCL::String const *,int)
0x1801abadf  mov     rdx, rax
0x1801abae2  lea     rcx, [rsp+3A8h+var_320]
0x1801abaea  call    cs:__imp_??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::SmartPtr<UnBCL::Array<UnBCL::String *>>(UnBCL::Array<UnBCL::String *> *)
0x1801abaf0  nop
0x1801abaf1  lea     rcx, [rsp+3A8h+var_320]
0x1801abaf9  call    cs:__imp_?get_P@?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@2@XZ; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::get_P(void)
0x1801abaff  test    rax, rax
0x1801abb02  jz      loc_1801ABF06
0x1801abb08  lea     rcx, [rsp+3A8h+var_320]
0x1801abb10  call    cs:__imp_??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(void)
0x1801abb16  mov     rcx, [rax+8]
0x1801abb1a  movsxd  rcx, dword ptr [rcx+0Ch]
0x1801abb1e  add     rax, 8
0x1801abb22  add     rcx, rax
0x1801abb25  mov     rax, [rcx]
0x1801abb28  mov     rax, [rax]
0x1801abb2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801abb30  test    eax, eax
0x1801abb32  jz      loc_1801ABF06
0x1801abb38  lea     ecx, [rdi+7Fh]
0x1801abb3b  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1801abb41  mov     [rsp+3A8h+var_308], rax
0x1801abb49  test    rax, rax
0x1801abb4c  jz      short loc_1801ABB71
0x1801abb4e  mov     rcx, rax
0x1801abb51  call    ??0?$ArrayList@PEAV?$DictionaryEntry@PEAVString@UnBCL@@PEAV12@@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>(void)
0x1801abb56  jmp     short loc_1801ABB74
0x1801abb58  lea     rsi, aCprocessdriver_7; "CProcessDrivers::DoExecute"
0x1801abb5f  lea     r15, aD_0; "D"
0x1801abb66  mov     r14d, 0C8000h
0x1801abb6c  jmp     loc_1801ABAAF
0x1801abb71  mov     rax, rbx
0x1801abb74  mov     rdx, rax
0x1801abb77  lea     rcx, [rsp+3A8h+var_2AC+4]
0x1801abb7f  call    ??0?$SmartPtr@V?$ArrayList@PEAV?$DictionaryEntry@PEAVString@UnBCL@@PEAV12@@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAV?$DictionaryEntry@PEAVString@UnBCL@@PEAV12@@UnBCL@@@1@@Z; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>>::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>>(UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *> *)
0x1801abb84  nop
0x1801abb85  mov     rcx, [rsp+3A8h+var_2A0]
0x1801abb8d  mov     rax, [rcx]
0x1801abb90  mov     edx, edi
0x1801abb92  mov     rax, [rax+28h]
0x1801abb96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801abb9b  mov     edi, ebx
0x1801abb9d  lea     rcx, [rsp+3A8h+var_320]
0x1801abba5  call    cs:__imp_??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(void)
0x1801abbab  mov     rcx, [rax+8]
0x1801abbaf  movsxd  rcx, dword ptr [rcx+0Ch]
0x1801abbb3  add     rax, 8
0x1801abbb7  add     rcx, rax
0x1801abbba  mov     rax, [rcx]
0x1801abbbd  mov     rax, [rax]
0x1801abbc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801abbc5  cmp     edi, eax
0x1801abbc7  jge     loc_1801ABD1E
0x1801abbcd  lea     rcx, [rsp+3A8h+var_320]
0x1801abbd5  call    cs:__imp_??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(void)
0x1801abbdb  mov     rcx, [rax+8]
0x1801abbdf  movsxd  rcx, dword ptr [rcx+10h]
0x1801abbe3  add     rax, 8
0x1801abbe7  add     rcx, rax
0x1801abbea  mov     rax, [rcx]
0x1801abbed  mov     edx, edi
0x1801abbef  mov     rax, [rax+18h]
0x1801abbf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801abbf8  mov     r8d, 1
0x1801abbfe  lea     rdx, aInf_0; ".inf"
0x1801abc05  mov     rcx, [rax]
0x1801abc08  call    cs:__imp_?EndsWith@String@UnBCL@@QEBAHPEBGH@Z; UnBCL::String::EndsWith(ushort const *,int)
0x1801abc0e  test    eax, eax
0x1801abc10  jz      loc_1801ABD17
0x1801abc16  lea     rcx, [rsp+3A8h+var_320]
0x1801abc1e  call    cs:__imp_??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(void)
0x1801abc24  mov     rcx, [rax+8]
0x1801abc28  movsxd  rcx, dword ptr [rcx+10h]
0x1801abc2c  add     rax, 8
0x1801abc30  add     rcx, rax
0x1801abc33  mov     rax, [rcx]
0x1801abc36  mov     edx, edi
0x1801abc38  mov     rax, [rax+18h]
0x1801abc3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801abc41  mov     rbx, [rax]
0x1801abc44  mov     rcx, r15
0x1801abc47  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1801abc4d  mov     rdx, rbx
0x1801abc50  mov     rcx, rax
0x1801abc53  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1801abc59  mov     rdx, rax
0x1801abc5c  lea     rcx, [rsp+3A8h+var_2E8]
0x1801abc64  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1801abc6a  nop
0x1801abc6b  mov     [rsp+3A8h+var_308], 0
0x1801abc77  lea     rcx, [rsp+3A8h+var_2E8]
0x1801abc7f  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1801abc85  mov     rcx, rax
0x1801abc88  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1801abc8e  lea     rdx, [rsp+3A8h+var_308]; struct UnBCL::String **
0x1801abc96  mov     rcx, rax; unsigned __int16 *
0x1801abc99  call    ?SPRetrieveDriverInstallInfo@@YAHPEBGPEAPEAVString@UnBCL@@@Z; SPRetrieveDriverInstallInfo(ushort const *,UnBCL::String * *)
0x1801abc9e  mov     rdx, [rsp+3A8h+var_2A0]
0x1801abca6  mov     rax, [rdx+8]
0x1801abcaa  movsxd  rsi, dword ptr [rax+10h]
0x1801abcae  add     rsi, rdx
0x1801abcb1  mov     r14, [rsi+8]
0x1801abcb5  mov     ecx, 40h ; '@'
0x1801abcba  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1801abcc0  mov     rbx, rax
0x1801abcc3  mov     qword ptr [rsp+3A8h+var_290], rax
0x1801abccb  test    rbx, rbx
0x1801abcce  jz      short loc_1801ABCF5
0x1801abcd0  lea     rcx, [rsp+3A8h+var_2E8]
0x1801abcd8  call    cs:__imp_?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::Steal(void)
0x1801abcde  mov     r8, [rsp+3A8h+var_308]
0x1801abce6  mov     rdx, rax
0x1801abce9  mov     rcx, rbx
0x1801abcec  call    ??0?$DictionaryEntry@PEAVString@UnBCL@@PEAV12@@UnBCL@@QEAA@PEAVString@1@0HH@Z; UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *>::DictionaryEntry<UnBCL::String *,UnBCL::String *>(UnBCL::String *,UnBCL::String *,int,int)
0x1801abcf1  xor     ebx, ebx
0x1801abcf3  jmp     short loc_1801ABCF8
0x1801abcf5  mov     rax, rbx
0x1801abcf8  mov     rdx, rax
0x1801abcfb  lea     rcx, [rsi+8]
0x1801abcff  mov     rax, [r14+28h]
0x1801abd03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801abd08  nop
0x1801abd09  lea     rcx, [rsp+3A8h+var_2E8]
0x1801abd11  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1801abd17  inc     edi
0x1801abd19  jmp     loc_1801ABB9D
0x1801abd1e  mov     rdx, [rsp+3A8h+var_2A0]
0x1801abd26  mov     rax, [rdx+8]
0x1801abd2a  movsxd  rcx, dword ptr [rax+0Ch]
0x1801abd2e  add     rdx, 8
0x1801abd32  add     rcx, rdx
0x1801abd35  mov     rax, [rcx]
0x1801abd38  mov     rax, [rax]
0x1801abd3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801abd40  test    eax, eax
0x1801abd42  jnz     short loc_1801ABDBA
0x1801abd44  call    cs:__imp_GetLastError
0x1801abd4a  mov     ebx, eax
0x1801abd4c  call    cs:__imp_CurrentIP
0x1801abd52  mov     rdi, rax
0x1801abd55  mov     rcx, r15
0x1801abd58  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1801abd5e  mov     rcx, rax
0x1801abd61  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1801abd67  mov     r8, rax
0x1801abd6a  lea     rdx, aDidNotFindAnyD; "Did not find any driver packages in %s"
0x1801abd71  mov     ecx, 3000000h; unsigned int
0x1801abd76  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801abd7b  mov     dword ptr [rsp+3A8h+var_358], 0
0x1801abd83  mov     [rsp+3A8h+var_360], 0
0x1801abd8c  mov     dword ptr [rsp+3A8h+var_368], ebx
0x1801abd90  mov     [rsp+3A8h+var_370], rdi
0x1801abd95  lea     rsi, aCprocessdriver_7; "CProcessDrivers::DoExecute"
0x1801abd9c  mov     [rsp+3A8h+var_378], rsi
0x1801abda1  lea     rcx, aBaseNtsetupSet_14; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1801abda8  mov     qword ptr [rsp+3A8h+var_380], rcx
0x1801abdad  mov     dword ptr [rsp+3A8h+var_388], 6BFh
0x1801abdb5  jmp     loc_1801ABEC4
0x1801abdba  mov     rdx, [rsp+3A8h+var_2A0]
0x1801abdc2  test    rdx, rdx
0x1801abdc5  jnz     short loc_1801ABDCC
0x1801abdc7  mov     rdx, rbx
0x1801abdca  jmp     short loc_1801ABDF1
0x1801abdcc  mov     rax, [rdx+8]
0x1801abdd0  movsxd  rcx, dword ptr [rax+4]
0x1801abdd4  add     rdx, 8
0x1801abdd8  add     rcx, rdx
0x1801abddb  call    cs:__imp_?DecRef@Object@UnBCL@@QEAAHXZ; UnBCL::Object::DecRef(void)
0x1801abde1  mov     rdx, [rsp+3A8h+var_2A0]
0x1801abde9  mov     [rsp+3A8h+var_2A0], rbx
0x1801abdf1  lea     rcx, [rsp+3A8h+var_2E8]
0x1801abdf9  call    ??0?$SmartPtr@V?$ArrayList@PEAV?$DictionaryEntry@PEAVString@UnBCL@@PEAV12@@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAV?$DictionaryEntry@PEAVString@UnBCL@@PEAV12@@UnBCL@@@1@@Z; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>>::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *>>(UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,UnBCL::String *> *> *)
0x1801abdfe  nop
0x1801abdff  lea     rdx, [rsp+3A8h+var_2E8]
0x1801abe07  lea     rcx, [rsp+3A8h+var_218]
0x1801abe0f  call    ??4?$SmartPtr@V?$ArrayList@PEAVCRegCreationData@@@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::ArrayList<CRegCreationData *>>::operator=(UnBCL::SmartPtr<UnBCL::ArrayList<CRegCreationData *>> const &)
0x1801abe14  nop
0x1801abe15  mov     [rsp+3A8h+var_2E8], r12
0x1801abe1d  lea     rcx, [rsp+3A8h+var_2E8]
  ... truncated ...
```
